---
title: Sys. dm_pdw_node_status (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 8e263b65-81d0-49d0-8873-62ef424369d6
author: CarlRabeler
ms.author: carlrab
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: 11c31d586fadfb8919cef1e7c1c6743be60e0548
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82819415"
---
# <a name="sysdm_pdw_node_status-transact-sql"></a>Sys. dm_pdw_node_status (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Contiene información adicional (sobre [Sys. dm_pdw_nodes &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-nodes-transact-sql.md)) sobre el rendimiento y el estado de todos los nodos del dispositivo. Muestra una fila por nodo en el dispositivo.  
  
|Nombre de columna|Tipo de datos|Descripción|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|Identificador numérico único asociado al nodo.<br /><br /> Clave para esta vista.|Único en todo el dispositivo, independientemente del tipo.|  
|process_id|**int**|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]||  
|process_name|**nvarchar(255)**|[!INCLUDE[ssInfoNA](../../includes/ssinfona-md.md)]||  
|allocated_memory|**bigint**|Memoria total asignada en este nodo.||  
|available_memory|**bigint**|Memoria total disponible en este nodo.||  
|process_cpu_usage|**bigint**|Uso total de la CPU del proceso, en pasos.||  
|total_cpu_usage|**bigint**|Uso total de CPU, en pasos.||  
|thread_count|**bigint**|Número total de subprocesos en uso en este nodo.||  
|handle_count|**bigint**|Número total de identificadores en uso en este nodo.||  
|total_elapsed_time|**bigint**|Tiempo total transcurrido desde el inicio o el reinicio del sistema.|Tiempo total transcurrido desde el inicio o el reinicio del sistema. Si total_elapsed_time supera el valor máximo de un entero (24,8 días en milisegundos), se producirá un error de materialización debido al desbordamiento.<br /><br /> El valor máximo en milisegundos es equivalente a 24,8 días.|  
|is_available|**bit**|Marca que indica si este nodo está disponible.||  
|sent_time|**datetime**|Última vez que este nodo envió un paquete de red.||  
|received_time|**datetime**|Última vez que este nodo recibió un paquete de red.||  
|error_id|**nvarchar (36)**|Identificador único del último error que se produjo en este nodo.||  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de administración dinámica de SQL Data Warehouse y almacenamiento de datos paralelos &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
