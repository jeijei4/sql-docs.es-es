---
title: sp_polybase_join_group | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: conceptual
f1_keywords:
- sp_polybase_join_group
helpviewer_keywords:
- PolyBase
ms.assetid: 48066431-fed2-4a8a-85af-ac704689e183
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bc4a9d78289f6d3fdf3272c6581d9baab586122f
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052732"
---
# <a name="sp_polybase_join_group-transact-sql"></a>sp_polybase_join_group (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  Agrega una instancia de SQL Server como un nodo de proceso a un grupo de polybase para el cálculo de escalado horizontal.  
  
 La instancia de SQL Server debe tener instalada la característica [polybase](../../relational-databases/polybase/polybase-guide.md) .  Polybase permite la integración de orígenes de datos que no son de SQL Server, como Hadoop y Azure BLOB Storage. Vea también [sp_polybase_leave_group &#40;&#41;de Transact-SQL ](../../relational-databases/system-stored-procedures/polybase-stored-procedures-sp-polybase-leave-group.md).  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
sp_polybase_join_group (@head_node_address = N'head_node_address',  
    @dms_control_channel_port = dms_control_channel_port,  
    @head_node_sql_server_instance_name = head_node_sql_server_instance_name)  
[ ; ]          
```  
  
## <a name="arguments"></a>Argumentos  
 * \@ head_node_address* = N '*head_node_address*'  
 Nombre del equipo que hospeda el SQL Server nodo principal del grupo de escalado horizontal de polybase. * \@ head_node_address* es nvarchar (255).  
  
 * \@ dms_control_channel_port* = dms_control_channel_port  
 Puerto en el que se está ejecutando el canal de control del nodo principal Movimiento de datos de PolyBase servicio. * \@ dms_control_channel_port* es un __int16 sin signo. El valor predeterminado es **16450**.  
  
 * \@ head_node_sql_server_instance_name* = head_node_sql_server_instance_name  
 Nombre del nodo principal SQL Server instancia en el grupo de escalado horizontal de polybase. * \@ head_node_sql_server_instance_name* es nvarchar (16).  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="permissions"></a>Permisos  
 Requiere el permiso CONTROL SERVER.  
  
## <a name="remarks"></a>Observaciones  
 Después de ejecutar el procedimiento almacenado, apague el motor de polybase y reinicie el servicio Movimiento de datos de PolyBase en el equipo. Para comprobar, ejecute la siguiente DMV en el nodo principal: **Sys. dm_exec_compute_nodes**.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo se une el equipo actual como un nodo de proceso a un grupo de polybase.  El nombre del nodo principal es **HST01** y el nombre de la instancia de SQL Server en el nodo principal es **MSSQLSERVER**.  
  
```  
EXEC sp_polybase_join_group N'HST01', 16450, N'MSSQLSERVER'   
```  
  
## <a name="see-also"></a>Consulte también  
 [Introducción a polybase](../../relational-databases/polybase/get-started-with-polybase.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
