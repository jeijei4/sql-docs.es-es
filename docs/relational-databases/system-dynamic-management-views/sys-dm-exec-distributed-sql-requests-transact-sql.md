---
title: Sys. dm_exec_distributed_sql_requests (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- DM_EXEC_DISTRIBUTED_SQL_REQUESTS_TSQL
- SYS.DM_EXEC_DISTRIBUTED_SQL_REQUESTS_TSQL
- DM_EXEC_DISTRIBUTED_SQL_REQUESTS
dev_langs:
- TSQL
helpviewer_keywords:
- PolyBase,views
- PolyBase
- sys.dm_exec_distributed_requests management view
- dm_exec_distributed_requests management view
ms.assetid: d065dc01-35d4-472f-9554-53ac41e7d104
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 0bfaaa65c08155263c15a1e4e4ddf17c20913e66
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82827979"
---
# <a name="sysdm_exec_distributed_sql_requests-transact-sql"></a>Sys. dm_exec_distributed_sql_requests (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-xxxx-asdw-pdw-md](../../includes/tsql-appliesto-ss2016-xxxx-asdw-pdw-md.md)]

  Contiene información sobre todas las distribuciones de consultas SQL como parte de un paso de SQL en la consulta.  Esta vista muestra los datos de las últimas 1000 solicitudes; las solicitudes activas siempre tienen los datos presentes en esta vista.  
  
|Nombre de columna|Tipo de datos|Descripción|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|execution_id|**nvarchar(32)**|execution_id y step_index componen la clave para esta vista. Identificador numérico único asociado a la solicitud.|Vea ID en [Sys. dm_exec_requests &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-requests-transact-sql.md)|  
|step_index|**int**|Índice del paso de consulta del que forma parte esta distribución.|Vea step_index en [Sys. dm_exec_distributed_request_steps &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-distributed-request-steps-transact-sql.md).|  
|compute_node_id|**int**|Tipo de la operación representada por este paso.|Vea compute_node_id en [Sys. dm_exec_compute_nodes &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-compute-nodes-transact-sql.md).|  
|distribution_id|**int**|Dónde se está ejecutando el paso.|Se establece en-1 para las solicitudes que se ejecutan en el ámbito de nodo y no en el ámbito de distribución.|  
|status|**nvarchar(32)**|Estado de este paso|Active, Canceled, Completed, failed, queued|  
|error_id|**nvarchar (36)**|Identificador único del error asociado a este paso, si lo hubiera.|Vea el ID. de [Sys. dm_exec_compute_node_errors &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-exec-compute-node-errors-transact-sql.md), NULL si no se ha producido ningún error.|  
|start_time|**datetime**|Hora a la que se inició la ejecución del paso|Menor o igual que la hora actual y mayor o igual que end_compile_time de la consulta a la que pertenece este paso.|  
|end_time|**datetime**|Hora a la que se completó la ejecución de este paso, se canceló o dio error.|Menor o igual que la hora actual y mayor o igual que start_time, se establece en NULL para los pasos que se encuentran actualmente en ejecución o en cola.|  
|total_elapsed_time|**int**|Cantidad total de tiempo que se ha estado ejecutando el paso de la consulta, en milisegundos|Entre 0 y la diferencia entre end_time y start_time. 0 para los pasos en cola.|  
|row_count|**bigint**|Número total de filas cambiadas o devueltas por esta solicitud|0 para los pasos que no cambiaron o devuelven datos, número de filas afectadas de otro modo. Establézcalo en-1 para los pasos de DMS.|  
|spid|**int**|Identificador de sesión de la instancia de SQL Server que ejecuta la distribución de consultas||  
|.|nvarchar(4000)|Contiene el texto completo del comando de este paso.|Cualquier cadena de solicitud válida para un paso. Se trunca si hay más de 4000 caracteres.|  
  
## <a name="see-also"></a>Consulte también  
 [Solución de problemas de polybase con vistas de administración dinámica](https://msdn.microsoft.com/library/ce9078b7-a750-4f47-b23e-90b83b783d80)   
 [Funciones y vistas de administración dinámica &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Vistas de administración dinámica relacionadas con bases de datos &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/database-related-dynamic-management-views-transact-sql.md)  
  
  
