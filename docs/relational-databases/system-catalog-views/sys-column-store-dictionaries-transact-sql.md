---
title: Sys. column_store_dictionaries (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.column_store_dictionaries_TSQL
- column_store_dictionaries
- column_store_dictionaries_TSQL
- sys.column_store_dictionaries
dev_langs:
- TSQL
helpviewer_keywords:
- sys.column_store_dictionaries catalog view
ms.assetid: 56efd563-2f72-4caf-94e3-8a182385c173
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: e7ccd7c93d42cb30eeb2fc24b79c358d519579b6
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85764772"
---
# <a name="syscolumn_store_dictionaries-transact-sql"></a>sys.column_store_dictionaries (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contiene una fila para cada diccionario que se utilice en los índices de almacén de columnas optimizados en memoria xVelocity. Los diccionarios se usan para codificar algunos tipos de datos (no todos), por tanto no todas las columnas en un índice de almacén de columnas tienen diccionarios. Un diccionario puede ser un diccionario primario, para todos los segmentos, y posiblemente para otros diccionarios que se usan para un subconjunto de los segmentos de la columna.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**hobt_id**|**bigint**|IDENTIFICADOR del índice de montículo o árbol B (HoBT) de la tabla que tiene este índice de almacén de columnas.|  
|**column_id**|**int**|IDENTIFICADOR de la columna de almacén de columnas que empieza por 1. La primera columna tiene el identificador 1, la segunda columna tiene el identificador 2, etc.|  
|**dictionary_id**|**int**|Puede haber dos tipos de diccionarios, globales y locales, asociados a un segmento de columna. Un dictionary_id de 0 representa el Diccionario global que se comparte entre todos los segmentos de columna (uno por cada grupo de filas) de esa columna.|  
|**version**|**int**|Versión del formato de diccionario.|  
|**type**|**int**|Tipo de diccionario:<br /><br /> 1: Diccionario hash que contiene valores **int**<br /><br /> 2: no se usa<br /><br /> 3: Diccionario hash que contiene valores de cadena<br /><br /> 4: Diccionario hash que contiene valores **float**<br /><br /> Para obtener más información acerca de los diccionarios, consulte [Guía de índices de almacén de columnas](~/relational-databases/indexes/columnstore-indexes-overview.md).|  
|**last_id**|**int**|El último identificador de datos del diccionario.|  
|**entry_count**|**bigint**|Número de entradas en el diccionario.|  
|**on_disk_size**|**bigint**|Tamaño del diccionario en bytes.|  
|**partition_id**|**bigint**|Indica el identificador de partición. Es único en una base de datos.|  
  
## <a name="permissions"></a>Permisos  
Debe tener un permiso de `VIEW DEFINITION` sobre la tabla. Las columnas siguientes devuelven null a menos que el usuario también tenga `SELECT` permiso: last_id, entry_count data_ptr.  
  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo de objetos &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Preguntas más frecuentes sobre el catálogo del sistema de SQL Server](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)   
 [Sys. Columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-columns-transact-sql.md)   
 [Sys. all_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-all-columns-transact-sql.md)   
 [Sys. computed_columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-computed-columns-transact-sql.md)   
 [Guía de índices de almacén de columnas](~/relational-databases/indexes/columnstore-indexes-overview.md)   
 [Guía de índices de almacén de columnas](~/relational-databases/indexes/columnstore-indexes-overview.md)   
 [sys.column_store_segments &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-column-store-segments-transact-sql.md)  
  
  

