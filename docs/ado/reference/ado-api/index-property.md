---
title: Propiedad de índice | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset21::Index
helpviewer_keywords:
- Index property
ms.assetid: 1c79e271-21ec-41a8-8163-c5e89f0001a7
author: rothja
ms.author: jroth
ms.openlocfilehash: 2a77aa3c2e144859eaead332e71c5c4c8776608c
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82758701"
---
# <a name="index-property"></a>Propiedad Index
Indica el nombre del índice actualmente activo para un objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) .  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece o devuelve un valor de **cadena** , que es el nombre del índice.  
  
## <a name="remarks"></a>Observaciones  
 El índice denominado por la propiedad de **Índice** debe haberse declarado previamente en la tabla base subyacente al objeto de **conjunto de registros** . Es decir, el índice se debe haber declarado mediante programación como un objeto de [Índice](../../../ado/reference/adox-api/index-object-adox.md) ADOX o cuando se haya creado la tabla base.  
  
 Si no se puede establecer el índice, se producirá un error en tiempo de ejecución. No se puede establecer la propiedad de **Índice** en las siguientes condiciones:  
  
-   Dentro de un controlador de eventos [WillChangeRecordset](../../../ado/reference/ado-api/willchangerecordset-and-recordsetchangecomplete-events-ado.md) o **RecordsetChangeComplete** .  
  
-   Si el **conjunto de registros** sigue ejecutando una operación (que puede estar determinada por la propiedad [State](../../../ado/reference/ado-api/state-property-ado.md) ).  
  
-   Si se ha establecido un filtro en el **conjunto de registros** con la propiedad [Filter](../../../ado/reference/ado-api/filter-property.md) .  
  
 La propiedad de **Índice** siempre se puede establecer correctamente si el **conjunto de registros** está cerrado, pero el conjunto de **registros** no se abrirá correctamente o el índice no se podrá usar, si el proveedor subyacente no admite índices.  
  
 Si se puede establecer el índice, la posición de la fila actual puede cambiar. Esto producirá una actualización de la propiedad [AbsolutePosition](../../../ado/reference/ado-api/absoluteposition-property-ado.md) y desencadenará los eventos **WillChangeRecordset**, **RecordsetChangeComplete**, [WillMove](../../../ado/reference/ado-api/willmove-and-movecomplete-events-ado.md)y [MoveComplete](../../../ado/reference/ado-api/willmove-and-movecomplete-events-ado.md) .  
  
 Si se puede establecer el índice y la propiedad [LockType](../../../ado/reference/ado-api/locktype-property-ado.md) es **adLockPessimistic** o **adLockOptimistic**, se realiza una operación de [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md) implícita. Esto libera los grupos actuales y afectados. Se libera cualquier filtro existente y la posición de la fila actual se cambia a la primera fila del **conjunto de registros**reordenado.  
  
 La propiedad de **Índice** se utiliza junto con el método [Seek](../../../ado/reference/ado-api/seek-method.md) . Si el proveedor subyacente no admite la propiedad de **Índice** y, por lo tanto, el método **Seek** , considere la posibilidad de usar el método [Find](../../../ado/reference/ado-api/find-method-ado.md) en su lugar. Determine si el objeto de **conjunto de registros** admite índices con el método [Supports](../../../ado/reference/ado-api/supports-method.md)**(adIndex)** .  
  
 La propiedad de **Índice** integrada no está relacionada con la propiedad [optimizada](../../../ado/reference/ado-api/optimize-property-dynamic-ado.md) dinámica, aunque ambos tratan los índices.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de la propiedad index y el método Seek (VB)](../../../ado/reference/ado-api/seek-method-and-index-property-example-vb.md)   
 [Index (objeto) (ADOX)](../../../ado/reference/adox-api/index-object-adox.md)   
 [Seek (método)](../../../ado/reference/ado-api/seek-method.md)
