---
title: Evento WillExecute (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- WillExecute
- Connection::WillExecute
helpviewer_keywords:
- WillExecute event [ADO]
ms.assetid: dd755e46-f589-48a3-93a9-51ff998d44b5
author: rothja
ms.author: jroth
ms.openlocfilehash: ef47b4bac626d82754ce01685504b4a48303a4b4
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764456"
---
# <a name="willexecute-event-ado"></a>Evento WillExecute (ADO)
Se llama al evento **WillExecute** justo antes de que se ejecute un comando pendiente en una conexión.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
WillExecute Source, CursorType, LockType, Options, adStatus, pCommand, pRecordset, pConnection  
```  
  
#### <a name="parameters"></a>Parámetros  
 *Origen*  
 **Cadena** que contiene un comando SQL o un nombre de procedimiento almacenado.  
  
 *CursorType*  
 Un objeto [CursorTypeEnum](../../../ado/reference/ado-api/cursortypeenum.md) que contiene el tipo de cursor para el **conjunto de registros** que se va a abrir. Con este parámetro, puede cambiar el cursor a cualquier tipo durante una operación **Recordset**[Open Method (ADO Recordset)](../../../ado/reference/ado-api/open-method-ado-recordset.md) . *CursorType* se omitirá para cualquier otra operación.  
  
 *LockType*  
 Un [LockTypeEnum](../../../ado/reference/ado-api/locktypeenum.md) que contiene el tipo de bloqueo para el **conjunto de registros** que se va a abrir. Con este parámetro, puede cambiar el bloqueo a cualquier tipo durante una operación **RecordsetOpen** . *LockType* se omitirá para cualquier otra operación.  
  
 *Opciones*  
 Un valor **Long** que indica las opciones que se pueden utilizar para ejecutar el comando o abrir el **conjunto de registros**.  
  
 *adStatus*  
 Un valor de estado de [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) que puede ser **adStatusCantDeny** o **adStatusOK** cuando se llama a este evento. Si es **adStatusCantDeny**, es posible que este evento no solicite la cancelación de la operación pendiente.  
  
 *pRecordset*  
 Objeto de [comando (ADO)](../../../ado/reference/ado-api/command-object-ado.md) al que se aplica esta notificación de eventos.  
  
 *pRecordset*  
 Objeto de [conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md) al que se aplica esta notificación de eventos.  
  
 *pConnection*  
 Objeto de [conexión (ADO)](../../../ado/reference/ado-api/connection-object-ado.md) al que se aplica esta notificación de eventos.  
  
## <a name="remarks"></a>Comentarios  
 Un evento **WillExecute** puede producirse debido a una conexión.  Método [Execute (conexión ADO)](../../../ado/reference/ado-api/execute-method-ado-connection.md), método [Execute (comando ADO)](../../../ado/reference/ado-api/execute-method-ado-command.md)o método [Open (ADO Recordset)](../../../ado/reference/ado-api/open-method-ado-recordset.md) el parámetro *pConnection* siempre debe contener una referencia válida a un objeto **Connection** . Si el evento se debe a **Connection. Execute**, los parámetros *pRecordset* y *pCommand* se establecen en **Nothing**. Si el evento se debe a **Recordset. Open**, el parámetro *pRecordset* hará referencia al objeto de **conjunto de registros** y el parámetro *pCommand* se establecerá en **Nothing**. Si el evento se debe a **Command. Execute**, el parámetro *pCommand* hará referencia al objeto **Command** y el parámetro *pRecordset* se establecerá en **Nothing**.  
  
 **WillExecute** permite examinar y modificar los parámetros de ejecución pendientes. Este evento puede devolver una solicitud de cancelación del comando pendiente.  
  
> [!NOTE]
>  Si el origen original de un **comando** es una secuencia especificada por la propiedad [CommandStream (ADO)](../../../ado/reference/ado-api/commandstream-property-ado.md) , la asignación de una nueva cadena al parámetro de **WillExecute**_origen_ WillExecute cambia el origen del **comando**. La propiedad **CommandStream** se borrará y la propiedad [CommandText (ADO)](../../../ado/reference/ado-api/commandtext-property-ado.md) se actualizará con el nuevo origen. La secuencia original especificada por **CommandStream** se liberará y no se podrá obtener acceso a ella.  
  
 Si el dialecto de la nueva cadena de origen difiere del valor original de la propiedad de [propiedad de dialecto](../../../ado/reference/ado-api/dialect-property.md) (que corresponde a **CommandStream**), se debe especificar el dialecto correcto estableciendo la propiedad de **dialecto** del objeto de comando al que se hace referencia en *pCommand*.  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de modelo de eventos de ADO (VC + +)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Resumen del controlador de eventos de ADO](../../../ado/guide/data/ado-event-handler-summary.md)   
 [Objeto de conexión (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)
