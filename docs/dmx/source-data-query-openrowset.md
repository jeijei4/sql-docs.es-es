---
title: OPENROWSET (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: b19b897b65ffb3a4c9e940370ffdead1e10b6d31
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "86970326"
---
# <a name="ltsource-data-querygt---openrowset"></a>&lt;consulta de datos &gt; de origen: OPENROWSET
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Reemplaza la consulta de datos de origen por una consulta a un proveedor externo. Las instrucciones INSERT, SELECT FROM predicción JOIN y SELECT FROM NATURAL PREDICT JOIN admiten **OPENROWSET**.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
OPENROWSET(provider_name,provider_string,query_syntax)  
```  
  
## <a name="arguments"></a>Argumentos  
 *provider_name*  
 Nombre de proveedor OLE DB.  
  
 *provider_string*  
 La cadena de conexión OLE DB para el proveedor especificado.  
  
 *query_syntax*  
 Sintaxis de consulta que devuelve un conjunto de filas.  
  
## <a name="remarks"></a>Observaciones  
 El proveedor de minería de datos establecerá una conexión con el objeto de origen de datos utilizando *provider_name* y *provider_string,* y ejecutará la consulta especificada en *query_syntax* para recuperar el conjunto de filas de los datos de origen.  
  
## <a name="examples"></a>Ejemplos  
 El siguiente ejemplo puede usarse en una instrucción PREDICTION JOIN para recuperar datos de la base de datos [!INCLUDE[ssSampleDBDWobject](../includes/sssampledbdwobject-md.md)] mediante una instrucción SELECT de [!INCLUDE[tsql](../includes/tsql-md.md)].  
  
```  
OPENROWSET  
(  
'SQLOLEDB.1',  
'Provider=SQLOLEDB.1;Integrated Security=SSPI;Persist Security     Info=False;Initial Catalog=AdventureWorksDW2012;Data Source=localhost',  
'SELECT TOP 1000 * FROM vTargetMail'  
)  
```  
  
## <a name="see-also"></a>Consulte también  
 [&#60;consulta de datos de origen&#62;](../dmx/source-data-query.md)   
 [Extensiones de minería de datos &#40;DMX&#41; instrucciones de manipulación de datos](../dmx/dmx-statements-data-manipulation.md)   
 [Referencia de instrucciones de Extensiones de minería de datos &#40;DMX&#41;](../dmx/data-mining-extensions-dmx-statements.md)  
  
  
