---
title: Clase de eventos QN:Subscription | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: article
topic_type:
- apiref
helpviewer_keywords:
- event classes [SQL Server], QN:Subscription
ms.assetid: 4916167e-8541-43b4-900e-ec8e6adcbc34
caps.latest.revision: 20
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7dd4c06a89eeebe5c3b7e83a699ea17ca68bbd18
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36204610"
---
# <a name="qnsubscription-event-class"></a>QN:Subscription (clase de eventos)
  El evento QN:Subscription ofrece información acerca de las suscripciones a notificaciones.  
  
## <a name="qnsubscription-event-class-data-columns"></a>Columnas de datos de la clase de eventos QN:Subscription  
  
|Columna de datos|Tipo|Descripción|Número de columna|Filtrable|  
|-----------------|----------|-----------------|-------------------|----------------|  
|ApplicationName|`nvarchar`|Nombre de la aplicación cliente que ha creado la conexión a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Esta columna se rellena con los valores que pasa la aplicación, en lugar de con el nombre que se muestra para el programa.|10|Sí|  
|ClientProcessID|`int`|Id. que el equipo host asigna al proceso en el que se ejecuta la aplicación cliente. Esta columna de datos se rellena si el cliente proporciona su identificador de proceso.|9|Sí|  
|DatabaseID|`int`|Identificador de la base de datos especificada mediante la instrucción USE *database* o identificador de la base de datos predeterminada si no se ha emitido la instrucción USE *database*para una instancia determinada. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] muestra el nombre de la base de datos si se captura la columna de datos Server Name en el seguimiento y el servidor está disponible. Determina el valor de una base de datos mediante la función DB_ID.|3|Sí|  
|DatabaseName|`nvarchar`|Nombre de la base de datos en que se ejecuta la instrucción del usuario.|35|Sí|  
|EventClass|`int`|Tipo de evento = 199.|27|no|  
|EventSequence|`int`|Número de secuencia de este evento.|51|no|  
|EventSubClass|`nvarchar`|Tipo de subclase de evento que proporciona más información acerca de cada clase de evento. Esta columna puede incluir los valores siguientes:<br /><br /> Las suscripciones registradas: indica cuando se ha registrado correctamente la suscripción de notificación de consulta en la base de datos.<br /><br /> Suscripción rebobinada: indica cuándo el [!INCLUDE[ssDE](../../includes/ssde-md.md)] recibe una solicitud de suscripción que coincida exactamente con una suscripción existente. En este caso, [!INCLUDE[ssDE](../../includes/ssde-md.md)] establece el valor del tiempo de espera de la suscripción existente en el especificado en la nueva solicitud de suscripción.<br /><br /> La suscripción se desencadenó: indica cuando una suscripción de notificación genera un mensaje de notificación.<br /><br /> Error en activación con error de broker: indica cuando un mensaje de notificación genera un error debido a un [!INCLUDE[ssSB](../../includes/sssb-md.md)] error.<br /><br /> Error en activación sin error de broker: indica cuando un mensaje de notificación se produce un error pero no es debido a un [!INCLUDE[ssSB](../../includes/sssb-md.md)] error.<br /><br /> Interceptada el error de Broker: indica que [!INCLUDE[ssSB](../../includes/sssb-md.md)] proporcionó un error en la conversación que usa la notificación de consulta.<br /><br /> Intento de eliminación de suscripción: indica que el [!INCLUDE[ssDE](../../includes/ssde-md.md)] intentó eliminar una suscripción caducada para liberar recursos.<br /><br /> No se pudo eliminar de suscripción: indica que el intento de eliminar una suscripción caducada ha fracasado. [!INCLUDE[ssDE](../../includes/ssde-md.md)] volverá a programar automáticamente la eliminación de la suscripción para liberar recursos.<br /><br /> Suscripción destruido: indica que el [!INCLUDE[ssDE](../../includes/ssde-md.md)] se eliminó correctamente una suscripción caducada|21|Sí|  
|GroupID|`int`|Id. del grupo de carga de trabajo donde se activa el evento de Seguimiento de SQL.|66|Sí|  
|HostName|`nvarchar`|Nombre del equipo en el que se está ejecutando el cliente. Esta columna de datos se rellena si el cliente proporciona el nombre del host. Para determinar el nombre del host, utilice la función HOST_NAME.|8|Sí|  
|IsSystem|`int`|Indica si el evento ha ocurrido en un proceso del sistema o en un proceso de usuario.<br /><br /> 0 = usuario<br /><br /> 1 = sistema|60|no|  
|LoginName|`nvarchar`|Nombre del inicio de sesión del usuario (inicio de sesión de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o credenciales de inicio de sesión de Windows en formato DOMINIO\nombreDeUsuario).|11|no|  
|LoginSID|`image`|SID (número de identificación de seguridad) del usuario que ha iniciado la sesión. Puede buscar esta información en la vista de catálogo sys.server_principals. Cada SID es único para cada inicio de sesión en el servidor.|41|Sí|  
|NTDomainName|`nvarchar`|Dominio de Windows al que pertenece el usuario.|7|Sí|  
|NTUserName|`nvarchar`|Nombre del usuario al que pertenece la conexión que generó este evento.|6|Sí|  
|IdSolicitud|`int`|Identificador de la solicitud que contiene la instrucción.|49|Sí|  
|ServerName|`nvarchar`|Nombre de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de la que se realiza un seguimiento.|26|no|  
|SessionLoginName|`nvarchar`|Nombre de inicio de sesión del usuario que originó la sesión. Por ejemplo, si una aplicación se conecta a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando inicioDeSesión1 y ejecuta una instrucción como inicioDeSesión2, SessionLoginName muestra "inicioDeSesión1" y LoginName muestra "inicioDeSesión2". En esta columna se muestran los inicios de sesión de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y de Windows.|64|Sí|  
|SPID|`int`|Identificador de la sesión en la que se produjo el evento.|12|Sí|  
|StartTime|`datetime`|Hora a la que se inició el evento, si está disponible.|14|Sí|  
|TextData|`ntext`|Devuelve un documento XML que contiene información específica de este evento. Este documento se ajusta al esquema XML disponible en la página sobre el [esquema de eventos del analizador de notificaciones de consultas de SQL Server](http://go.microsoft.com/fwlink/?LinkId=63331)|1|Sí|  
  
  