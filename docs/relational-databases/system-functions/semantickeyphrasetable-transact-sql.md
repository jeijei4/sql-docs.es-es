---
title: semantickeyphrasetable (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- semantickeyphrasetable
- semantickeyphrasetable_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- semantickeyphrasetable function
ms.assetid: d33b973a-2724-4d4b-aaf7-67675929c392
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3782b8139b84d87a30ac575476f5535173cdc66a
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85662574"
---
# <a name="semantickeyphrasetable-transact-sql"></a>semantickeyphrasetable (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Devuelve una tabla con cero, una o más filas para las frases clave asociadas a las columnas especificadas de la tabla indicada.  
  
 Se puede hacer referencia a esta función de conjunto de filas en la cláusula FROM de una instrucción SELECT como si fuese un nombre de tabla normal.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
SEMANTICKEYPHRASETABLE  
    (  
    table,  
    { column | (column_list) | * }  
     [ , source_key ]  
    )  
```  
  
##  <a name="arguments"></a><a name="Arguments"></a>Argumentos  
 **table**  
 Nombre de una tabla con indización de texto completo y semántica habilitada.  
  
 Este nombre puede ser un nombre de una a cuatro partes, pero no se permite un nombre de servidor remoto.  
  
 **column**  
 Nombre de la columna indizada para la que deben devolverse resultados. La columna debe tener habilitada la indización semántica.  
  
 **lista_de_columnas**  
 Indica varias columnas, separadas por comas y escritas entre paréntesis. Todas las columnas deben tener habilitada la indización semántica.  
  
 **\***  
 Indica que se incluyen todas las columnas que tienen la indización semántica habilitada.  
  
 **source_key**  
 Clave única de la fila, para solicitar los resultados de una fila concreta.  
  
 La clave se convierte implícitamente al tipo de la clave única de texto completo en la tabla de origen siempre que sea posible. La clave se puede especificar como una constante o como una variable, pero no puede ser una expresión ni el resultado de una subconsulta escalar. Si se omite source_key, se devuelven resultados para todas las filas.  
  
## <a name="table-returned"></a>Tabla devuelta  
 En la tabla siguiente se describe la información sobre las frases clave que devuelve esta función de conjunto de filas.  
  
|Column_name|Tipo|Descripción|  
|------------------|----------|-----------------|  
|**column_id**|**int**|IDENTIFICADOR de la columna de la que se ha extraído la frase clave actual y se ha indexado.<br /><br /> Vea las funciones COL_NAME y COLUMNPROPERTY para obtener información detallada sobre cómo recuperar el nombre de columna desde column_id y viceversa.|  
|**document_key**|**\***<br /><br /> Esta clave coincide con el tipo de la clave única de la tabla de origen.|Valor de clave único del documento o fila de los que se indizó la palabra clave actual.|  
|**frase clave**|**NVARCHAR**|La frase clave encontrada en la columna identificada por column_id y asociada al documento especificado por document_key.|  
|**carácter**|**IMPUESTOS**|Valor relativo de esta frase clave en su relación con todas las demás frases clave del mismo documento de la columna indizada.<br /><br /> El valor es un valor fraccionario decimal en el intervalo de [0.0, 1.0] donde una puntuación superior representa una ponderación mayor y 1.0 es la puntuación perfecta.|  
  
## <a name="general-remarks"></a>Notas generales  
 Para obtener más información, vea [Buscar frases clave en documentos con la búsqueda semántica](../../relational-databases/search/find-key-phrases-in-documents-with-semantic-search.md).  
  
## <a name="metadata"></a>Metadatos  
 Para obtener información y estado sobre la extracción y el rellenado de frases clave semánticas, consulte las siguientes vistas de administración dinámica:  
  
-   [sys.dm_db_fts_index_physical_stats &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-db-fts-index-physical-stats-transact-sql.md)  
  
-   [sys.dm_fts_index_population &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-fts-index-population-transact-sql.md)  
  
## <a name="security"></a>Seguridad  
  
### <a name="permissions"></a>Permisos  
 Necesita permisos SELECT en la tabla base en la que se crearon los índices semánticos y de texto completo.  
  
## <a name="examples"></a>Ejemplos  
  
###  <a name="example-1-find-the-top-key-phrases-in-a-specific-document"></a><a name="HowToTopPhrases"></a>Ejemplo 1: buscar las frases clave principales de un documento específico  
 En el ejemplo siguiente se recuperan las 10 frases clave principales del documento especificado por la variable @DocumentId en la columna Document de la tabla Production.Document de la base de datos de ejemplo AdventureWorks. La variable @DocumentId representa un valor de la columna de clave del índice de texto completo. La función **SEMANTICKEYPHRASETABLE** recupera estos resultados eficazmente mediante una búsqueda de índice en vez de un recorrido de tabla. En este ejemplo se supone que la columna está configurada para texto completo y para indización semántica.  
  
```sql  
SELECT TOP(10) KEYP_TBL.keyphrase  
FROM SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document,  
    @DocumentId  
    ) AS KEYP_TBL  
ORDER BY KEYP_TBL.score DESC;  
  
```  
  
###  <a name="example-2-find-the-top-documents-that-contain-a-specific-key-phrase"></a><a name="HowToTopDocuments"></a>Ejemplo 2: buscar los documentos principales que contienen una frase clave específica  
 En el ejemplo siguiente se recuperan los 25 primeros documentos que contengan la palabra clave "Bracket" de la columna Document de la tabla Production.Document de la base de datos de ejemplo AdventureWorks. En este ejemplo se supone que la columna está configurada para texto completo y para indización semántica.  
  
```sql  
SELECT TOP (25) DOC_TBL.DocumentID, DOC_TBL.DocumentSummary  
FROM Production.Document AS DOC_TBL  
    INNER JOIN SEMANTICKEYPHRASETABLE  
    (  
    Production.Document,  
    Document  
    ) AS KEYP_TBL  
ON DOC_TBL.DocumentID = KEYP_TBL.document_key  
WHERE KEYP_TBL.keyphrase = 'Bracket'  
ORDER BY KEYP_TBL.Score DESC;  
  
```  
  
  
