---
title: Sys. dm_clr_tasks (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_clr_tasks
- sys.dm_clr_tasks_TSQL
- dm_clr_tasks
- dm_clr_tasks_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_clr_tasks dynamic management view
ms.assetid: 462b9061-09fa-4858-9707-03d6cc19c769
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 1a8a56fc4775c42eba7c448c6666399132936ed8
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85771595"
---
# <a name="sysdm_clr_tasks-transact-sql"></a>sys.dm_clr_tasks (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Devuelve una fila de todas las tareas CLR (Common Language Runtime) que se están ejecutando actualmente. Un lote de [!INCLUDE[tsql](../../includes/tsql-md.md)] que contiene una referencia a una rutina CLR crea una tarea independiente para la ejecución de todo el código administrado en ese lote. Muchas instrucciones del lote que requieren la ejecución del código administrado utilizan la misma tarea CLR. La tarea CLR es responsable del mantenimiento de objetos y el estado relativo a la ejecución de código administrado y también de las transacciones entre la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y CLR.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**task_address**|**varbinary(8**|Dirección de la tarea CLR.|  
|**sos_task_address**|**varbinary(8**|Dirección de la tarea del lote [!INCLUDE[tsql](../../includes/tsql-md.md)] subyacente.|  
|**appdomain_address**|**varbinary(8**|Dirección del dominio de la aplicación en la que se ejecuta esta tarea.|  
|**state**|**nvarchar(128)**|Estado actual de la tarea.|  
|**abort_state**|**nvarchar(128)**|Estado en el que está actualmente la cancelación (si la tarea se ha cancelado). Hay varios estados implicados en la anulación de tareas.|  
|**type**|**nvarchar(128)**|Tipo de tarea.|  
|**affinity_count**|**int**|Afinidad de la tarea.|  
|**forced_yield_count**|**int**|Número de veces que se forzó a la tarea a producir.|  
  
## <a name="permissions"></a>Permisos  

En [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] , requiere el `VIEW SERVER STATE` permiso.   
En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles Premium, requiere el `VIEW DATABASE STATE` permiso en la base de datos. En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles estándar y básico, requiere el **Administrador del servidor** o una cuenta de **Administrador de Azure Active Directory** .   
  
## <a name="see-also"></a>Consulte también  
 [Funciones y vistas de administración dinámica &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Vistas de administración dinámica relacionadas con Common Language Runtime &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/common-language-runtime-related-dynamic-management-views-transact-sql.md)  
  
  

