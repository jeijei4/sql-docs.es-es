---
title: FieldAttributeEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- FieldAttributeEnum
helpviewer_keywords:
- FieldAttributeEnum enumeration [ADO]
ms.assetid: 6e34d886-005a-40dc-bd5c-6adcbf81e5cd
author: rothja
ms.author: jroth
ms.openlocfilehash: ca14531410942a77add7c6c99756b64bf99e785c
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764526"
---
# <a name="fieldattributeenum"></a>FieldAttributeEnum
Especifica uno o más atributos de un objeto de [campo](../../../ado/reference/ado-api/field-object.md) .  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adFldCacheDeferred**|0x1000|Indica que el proveedor almacena en memoria caché los valores de campo y que las lecturas posteriores se realizan desde la memoria caché.|  
|**adFldFixed**|0x10|Indica que el campo contiene datos de longitud fija.|  
|**adFldIsChapter**|0x2000|Indica que el campo contiene un valor de capítulo, que especifica un conjunto de registros secundario concreto relacionado con este campo primario. Normalmente, los campos de capítulo se usan con los filtros o la forma de los datos.|  
|**adFldIsCollection**|0x40000|Indica que el campo especifica que el recurso representado por el registro es una colección de otros recursos, como una carpeta, en lugar de un recurso simple, como un archivo de texto.|  
|**adFldKeyColumn**|0x8000|Indica que el campo especifica toda o parte de la clave principal de la columna.|  
|**adFldIsDefaultStream**|0x20000|Indica que el campo contiene el flujo predeterminado para el recurso representado por el registro. Por ejemplo, la secuencia predeterminada puede ser el contenido HTML de una carpeta raíz en un sitio web, que se atiende automáticamente cuando se especifica la dirección URL raíz.|  
|**adFldIsNullable**|0x20|Indica que el campo acepta valores NULL.|  
|**adFldIsRowURL**|0x10000|Indica que el campo contiene la dirección URL que nombra el recurso del almacén de datos representado por el registro.|  
|**adFldLong**|0x80|Indica que el campo es un campo binario largo. También indica que puede utilizar los métodos [AppendChunk](../../../ado/reference/ado-api/appendchunk-method-ado.md) y [GetChunk](../../../ado/reference/ado-api/getchunk-method-ado.md) .|  
|**adFldMayBeNull**|0x40|Indica que se pueden leer los valores NULL del campo.|  
|**adFldMayDefer**|0x2|Indica que el campo es diferido, es decir, los valores de campo no se recuperan del origen de datos con el registro completo, sino solo cuando se accede a ellos de forma explícita.|  
|**adFldNegativeScale**|0x4000|Indica que el campo representa un valor numérico de una columna que admite valores de escala negativos. La escala se especifica mediante la propiedad [NumericScale](../../../ado/reference/ado-api/numericscale-property-ado.md) .|  
|**adFldRowID**|0x100|Indica que el campo contiene un identificador de fila persistente en el que no se puede escribir y que no tiene ningún valor significativo excepto para identificar la fila (como un número de registro, un identificador único, etc.).|  
|**adFldRowVersion**|0x200|Indica que el campo contiene algún tipo de marca de fecha y hora que se usa para realizar el seguimiento de las actualizaciones.|  
|**adFldUnknownUpdatable**|0x8|Indica que el proveedor no puede determinar si puede escribir en el campo.|  
|**adFldUnspecified**|-1 0xFFFFFFFF|Indica que el proveedor no especifica los atributos de campo.|  
|**adFldUpdatable**|0x4|Indica que se puede escribir en el campo.|  
  
## <a name="adowfc-equivalent"></a>Equivalente de ADO/WFC  
 Paquete: **com. ms. wfc. Data**  
  
|Constante|  
|--------------|  
|AdoEnums. FieldAttribute. CACHEDEFERRED|  
|AdoEnums. FieldAttribute. FIXED|  
|AdoEnums. FieldAttribute. ISNULLABLE|  
|AdoEnums. FieldAttribute. LONG|  
|AdoEnums. FieldAttribute. MAYBENULL|  
|AdoEnums. FieldAttribute. MAYDEFER|  
|AdoEnums. FieldAttribute. NEGATIVESCALE|  
|AdoEnums. FieldAttribute. ROWID|  
|AdoEnums. FieldAttribute. ROWVERSION|  
|AdoEnums. FieldAttribute. UNKNOWNUPDATABLE|  
|AdoEnums. FieldAttribute. no especificado|  
|AdoEnums. FieldAttribute. ACTUALIZAble|  
  
## <a name="applies-to"></a>Se aplica a  
  
|||  
|-|-|  
|[Append (método) (ADO)](../../../ado/reference/ado-api/append-method-ado.md)|[Propiedad Attributes (ADO)](../../../ado/reference/ado-api/attributes-property-ado.md)|
