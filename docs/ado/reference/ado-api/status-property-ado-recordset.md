---
title: Propiedad Status (conjunto de registros ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::GetStatus
- Recordset15::Status
helpviewer_keywords:
- Status property [ADO Recordset]
ms.assetid: 41d70d89-880f-4850-9d17-19d9790cc8eb
author: rothja
ms.author: jroth
ms.openlocfilehash: d3ba9ad977fe02a712a675b8a9e4bae4b3d038b1
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82759741"
---
# <a name="status-property-ado-recordset"></a>Propiedad Status (conjunto de registros ADO)
Indica el estado del registro actual con respecto a las actualizaciones por lotes o a otras operaciones masivas.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve una suma de uno o más valores de [RecordStatusEnum](../../../ado/reference/ado-api/recordstatusenum.md) .  
  
## <a name="remarks"></a>Observaciones  
 Use la propiedad **status** para ver qué cambios están pendientes para los registros modificados durante la actualización por lotes. También puede usar la propiedad **status** para ver el estado de los registros que no se superan durante las operaciones masivas, como cuando se llama a los métodos [Resync](../../../ado/reference/ado-api/resync-method.md), [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md)o [CancelBatch](../../../ado/reference/ado-api/cancelbatch-method-ado.md) en un objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) , o se establece la propiedad [Filter](../../../ado/reference/ado-api/filter-property.md) en un objeto de **conjunto de registros** en una matriz de marcadores. Con esta propiedad, puede determinar cómo se produjo un error en un registro determinado y resolverlo en consecuencia.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de la propiedad de estado (conjunto de registros) (VB)](../../../ado/reference/ado-api/status-property-example-recordset-vb.md)   
 [Ejemplo de la propiedad de estado (VC ++)](../../../ado/reference/ado-api/status-property-example-vc.md)   
