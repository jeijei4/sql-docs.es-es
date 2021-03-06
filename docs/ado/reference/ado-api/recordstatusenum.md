---
title: RecordStatusEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- RecordStatusEnum
helpviewer_keywords:
- RecordStatusEnum enumeration [ADO]
ms.assetid: 506fdd70-4452-4e83-95d5-c94311988dfa
author: rothja
ms.author: jroth
ms.openlocfilehash: f84f43a90479064c2a95d407b7f816fd48c1c679
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82756757"
---
# <a name="recordstatusenum"></a>RecordStatusEnum
Especifica el [Estado](../../../ado/reference/ado-api/status-property-ado-recordset.md) de un registro con respecto a las actualizaciones por lotes y otras operaciones masivas.  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adRecCanceled**|0x100|Indica que el registro no se guardó porque se canceló la operación.|  
|**adRecCantRelease**|0x400|Indica que el nuevo registro no se guardó porque el registro existente estaba bloqueado.|  
|**adRecConcurrencyViolation**|0x800|Indica que el registro no se guardó porque la simultaneidad optimista estaba en uso.|  
|**adRecDBDeleted**|0x40000|Indica que el registro ya se ha eliminado del origen de datos.|  
|**adRecDeleted**|0x4|Indica que se eliminó el registro.|  
|**adRecIntegrityViolation**|0x1000|Indica que el registro no se guardó porque el usuario infringió las restricciones de integridad.|  
|**adRecInvalid**|0x10|Indica que el registro no se guardó porque su marcador no es válido.|  
|**adRecMaxChangesExceeded**|0x2000|Indica que el registro no se guardó porque hubo demasiados cambios pendientes.|  
|**adRecModified**|0x2|Indica que se modificó el registro.|  
|**adRecMultipleChanges**|0x40|Indica que el registro no se guardó porque habría afectado a varios registros.|  
|**adRecNew**|0x1|Indica que el registro es nuevo.|  
|**adRecObjectOpen**|0x4000|Indica que el registro no se guardó debido a un conflicto con un objeto de almacenamiento abierto.|  
|**adRecOK**|0|Indica que el registro se actualizó correctamente.|  
|**adRecOutOfMemory**|0x8000|Indica que el registro no se guardó porque el equipo se ha quedado sin memoria.|  
|**adRecPendingChanges**|0x80|Indica que el registro no se guardó porque hace referencia a una inserción pendiente.|  
|**adRecPermissionDenied**|0x10000|Indica que el registro no se guardó porque el usuario no tiene permisos suficientes.|  
|**adRecSchemaViolation**|0x20000|Indica que el registro no se guardó porque infringe la estructura de la base de datos subyacente.|  
|**adRecUnmodified**|0x8|Indica que el registro no se ha modificado.|  
  
## <a name="adowfc-equivalent"></a>Equivalente de ADO/WFC  
 AdoEnums. RecordStatus.  
  
 Paquete: **com. ms. wfc. Data**  
  
|Constante|  
|--------------|  
|AdoEnums. RecordStatus. CANCELAdo|  
|AdoEnums. RecordStatus. CANTRELEASE|  
|AdoEnums. RecordStatus. CONCURRENCYVIOLATION|  
|AdoEnums. RecordStatus. DBDELETED|  
|AdoEnums. RecordStatus. DELETEd|  
|AdoEnums. RecordStatus. INTEGRITYVIOLATION|  
|AdoEnums.RecordStatus.INVALID|  
|AdoEnums. RecordStatus. MAXCHANGESEXCEEDED|  
|AdoEnums. RecordStatus. MODIFIed|  
|AdoEnums. RecordStatus. MULTIPLECHANGES|  
|AdoEnums. RecordStatus. NEW|  
|AdoEnums. RecordStatus. OBJECTOPEN|  
|AdoEnums. RecordStatus. OK|  
|AdoEnums. RecordStatus. OUTOFMEMORY|  
|AdoEnums. RecordStatus. PENDINGCHANGES|  
|AdoEnums. RecordStatus. PERMISSIONDENIED|  
|AdoEnums. RecordStatus. SCHEMAVIOLATION|  
|AdoEnums. RecordStatus. Unmodified|  
  
## <a name="applies-to"></a>Se aplica a  
 [Propiedad Status (conjunto de registros ADO)](../../../ado/reference/ado-api/status-property-ado-recordset.md)
