---
title: Sys. server_event_session_events (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- server_event_session_events
- server_event_session_events_TSQL
- sys.server_event_session_events
- sys.server_event_session_events_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_event_session_events catalog view
- xe
ms.assetid: 75986e91-1fc7-4f14-98ac-4e90154a74db
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 52559b61d2447aabea35bc8d01454046a9cbbe85
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86914787"
---
# <a name="sysserver_event_session_events-transact-sql"></a>sys.server_event_session_events (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2008-xxxx-xxxx-xxx-md.md)]

  Devuelve una fila por cada evento de una sesión de eventos.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|event_session_id|**int**|Identificador de la sesión de eventos. No admite valores NULL.|  
|event_id|**int**|Id. del evento. Este Id. es único dentro de un objeto de sesión de eventos. No admite valores NULL.|  
|name|**sysname**|Nombre del evento. No admite valores NULL.|  
|Paquete|**sysname**|Nombre del paquete de eventos que contiene el evento. No admite valores NULL.|  
|module|**sysname**|Nombre del módulo que contiene el evento. No admite valores NULL.|  
|predicate|**nvarchar (3000)**|La expresión de predicado aplicada al evento. Acepta valores NULL.|  
|predicate_xml|**nvarchar (3000)**|La expresión de predicado XML aplicada al evento. Acepta valores NULL.|  
  
## <a name="permissions"></a>Permisos  
 es necesario contar con el permiso VIEW SERVER STATE en el servidor.  
  
## <a name="remarks"></a>Observaciones  
 Esta vista tiene las siguientes cardinalidades de relación.  
  
| De | A | Relación |
| ---- | -- | ------------ |
|sys.server_event_session_events.event_session_id|Sys. server_event_sessions. event_session_id|Varios a uno|  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Vistas de catálogo de eventos extendidos &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/extended-events-catalog-views-transact-sql.md)   
 [Eventos extendidos](../../relational-databases/extended-events/extended-events.md)  
  
  
