---
title: Evento WillConnect (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- WillConnect
- Connection::WillConnect
helpviewer_keywords:
- WillConnect event [ADO]
ms.assetid: da561d58-eb58-446c-a4fd-1838c76073c0
author: rothja
ms.author: jroth
ms.openlocfilehash: 73798796af7629e70dda86bd0e264ec325be8a0e
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764466"
---
# <a name="willconnect-event-ado"></a>Evento WillConnect (ADO)
Se llama al evento **WillConnect** antes de que se inicie una conexión.  
  
 **Se aplica a:** [objeto Connection (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
WillConnect ConnectionString, UserID, Password, Options, adStatus, pConnection  
```  
  
#### <a name="parameters"></a>Parámetros  
 *ConnectionString*  
 **Cadena** que contiene información de conexión para la conexión pendiente.  
  
 *UserID*  
 Una **cadena** que contiene un nombre de usuario para la conexión pendiente.  
  
 *Contraseña*  
 **Cadena** que contiene una contraseña para la conexión pendiente.  
  
 *Opciones*  
 Un valor **Long** que indica cómo el proveedor debe evaluar la *ConnectionString*. La única opción es **adAsyncOpen**.  
  
 *adStatus*  
 Valor de estado de [EventStatusEnum](../../../ado/reference/ado-api/eventstatusenum.md) .  
  
 Cuando se llama a este evento, este parámetro se establece en **adStatusOK** de forma predeterminada. Se establece en **adStatusCantDeny** si el evento no puede solicitar la cancelación de la operación pendiente.  
  
 Antes de que se devuelva este evento, establezca este parámetro en **adStatusUnwantedEvent** para evitar notificaciones posteriores. Establezca este parámetro en **adStatusCancel** para solicitar la operación de conexión que causó la cancelación de esta notificación.  
  
 *pConnection*  
 Objeto de [conexión](../../../ado/reference/ado-api/connection-object-ado.md) para el que se aplica esta notificación de eventos. Los cambios en los parámetros de la **conexión** mediante el controlador de eventos **WillConnect** no surtirán efecto en la **conexión**.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se llama al método **WillConnect** , los parámetros *ConnectionString*, *userid*, *password*y *Options* se establecen en los valores establecidos por la operación que provocó este evento (la conexión pendiente) y se pueden cambiar antes de que el evento vuelva. **WillConnect** puede devolver una solicitud de cancelación de la conexión pendiente.  
  
 Cuando se cancela este evento, se llamará a **ConnectComplete** con su parámetro *adStatus* establecido en **adStatusErrorsOccurred**.  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de modelo de eventos de ADO (VC + +)](../../../ado/reference/ado-api/ado-events-model-example-vc.md)   
 [Conexión ADO y los eventos de conjunto de registros](../../../ado/guide/data/ado-event-handler-summary.md)
