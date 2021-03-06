---
title: CancelUpdate (método) (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::CancelUpdate
helpviewer_keywords:
- CancelUpdate method [ADO]
ms.assetid: eaa856cc-c786-462e-890c-c896261b1741
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ecc08dde974826846058d4d8927df202367d28d
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242412"
---
# <a name="cancelupdate-method-ado"></a>Método CancelUpdate (ADO)
Cancela los cambios realizados en la fila actual o nueva de un objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) , o la colección de [campos](../../../ado/reference/ado-api/fields-collection-ado.md) de un objeto de [registro](../../../ado/reference/ado-api/record-object-ado.md) , antes de llamar al método [Update](../../../ado/reference/ado-api/update-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
recordset.CancelUpdaterecord.Fields.CancelUpdate  
```  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="recordset"></a>DataRecordsets  
 Utilice el método **CancelUpdate** para cancelar los cambios realizados en la fila actual o para descartar una fila recién agregada. No se pueden cancelar los cambios realizados en la fila actual o en una nueva una vez que se llama al método **Update** , a menos que los cambios formen parte de una transacción que se pueda revertir con el método [RollbackTrans](../../../ado/reference/ado-api/begintrans-committrans-and-rollbacktrans-methods-ado.md) o que forme parte de una actualización por lotes. En el caso de una actualización por lotes, puede cancelar la **actualización** con el método **CancelUpdate** o [CancelBatch](../../../ado/reference/ado-api/cancelbatch-method-ado.md) .  
  
 Si va a agregar una nueva fila al llamar al método **CancelUpdate** , la fila actual se convierte en la fila que era la actual antes de la llamada a [AddNew](../../../ado/reference/ado-api/addnew-method-ado.md) .  
  
 Si está en modo de edición y desea salir del registro actual (por ejemplo, con los métodos [Move](../../../ado/reference/ado-api/move-method-ado.md), [NextRecordset](../../../ado/reference/ado-api/nextrecordset-method-ado.md)o [Close](../../../ado/reference/ado-api/close-method-ado.md) ), puede usar **CancelUpdate** para cancelar los cambios pendientes. Es posible que tenga que hacer esto si la actualización no se puede publicar correctamente en el origen de datos. Por ejemplo, un intento de eliminación que genera un error debido a infracciones de integridad referencial deja el **conjunto de registros** en modo de edición después de una llamada a [Delete](../../../ado/reference/ado-api/delete-method-ado-recordset.md).  
  
## <a name="record"></a>Registro  
 El método **CancelUpdate** cancela cualquier inserciones o eliminaciones pendientes de objetos de [campo](../../../ado/reference/ado-api/field-object.md) , y cancela las actualizaciones pendientes de los campos existentes y los restaura a sus valores originales. La propiedad [status](../../../ado/reference/ado-api/status-property-ado-recordset.md) de todos los campos de la colección **Fields** se establece en **adFieldOK**.  
  
## <a name="applies-to"></a>Se aplica a  

:::row:::
    :::column:::
        [Fields (colección) (ADO)](../../../ado/reference/ado-api/fields-collection-ado.md)  
    :::column-end:::
    :::column:::
        [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
    :::column-end:::
:::row-end:::

## <a name="see-also"></a>Consulte también  
 [Ejemplo de los métodos Update y CancelUpdate (VB)](../../../ado/reference/ado-api/update-and-cancelupdate-methods-example-vb.md)   
 [Ejemplo de los métodos Update y CancelUpdate (VC + +)](../../../ado/reference/ado-api/update-and-cancelupdate-methods-example-vc.md)   
 [AddNew (método) (ADO)](../../../ado/reference/ado-api/addnew-method-ado.md)   
 [CANCEL (método) (ADO)](../../../ado/reference/ado-api/cancel-method-ado.md)   
 [Método CANCEL (RDS)](../../../ado/reference/rds-api/cancel-method-rds.md)   
 [CancelBatch (método) (ADO)](../../../ado/reference/ado-api/cancelbatch-method-ado.md)   
 [Método CancelUpdate (RDS)](../../../ado/reference/rds-api/cancelupdate-method-rds.md)   
 [Propiedad EditMode](../../../ado/reference/ado-api/editmode-property.md)   
 [Update (método)](../../../ado/reference/ado-api/update-method.md)
