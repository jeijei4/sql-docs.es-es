---
title: Sys. dm_pdw_os_event_logs (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: a0daa8cf-72e2-4349-8be1-d3cc0f9b1e02
author: CarlRabeler
ms.author: carlrab
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: b410cd5a710e0f18bb7afa139e9ef08cfa466ae8
ms.sourcegitcommit: 1be90e93980a8e92275b5cc072b12b9e68a3bb9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84627329"
---
# <a name="sysdm_pdw_os_event_logs-transact-sql"></a>Sys. dm_pdw_os_event_logs (Transact-SQL)
[!INCLUDE[tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md](../../includes/tsql-appliesto-xxxxxx-xxxx-xxxx-pdw-md.md)]

  Contiene información relacionada con los distintos registros de eventos de Windows en los diferentes nodos.  
  
|Nombre de columna|Tipo de datos|Descripción|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|pdw_node_id|**int**|Nodo del dispositivo del que procede este registro.<br /><br /> pdw_node_id y log_name forman la clave de esta vista.||  
|log_name|**nvarchar(255)**|Nombre del registro de eventos de Windows.<br /><br /> pdw_node_id y log_name forman la clave de esta vista.||  
|log_source|**nvarchar(255)**|Nombre del origen del registro de eventos de Windows.||  
|event_id|**int**|IDENTIFICADOR del evento. No es único.||  
|event_type|**nvarchar(255)**|Tipo del evento, que identifica la gravedad.|' Información ', ' ADVERTENCIA ', ' error '|  
|event_message|**nvarchar(4000)**|Detalles del evento.||  
|generate_time|**datetime**|Hora en que se creó el evento.||  
|write_time|**datetime**|Hora en que el evento se escribió realmente en el registro.||  
  
 Para obtener información acerca de las filas máximas retenidas en esta vista, consulte la sección de metadatos en el tema [límites de capacidad](/azure/sql-data-warehouse/sql-data-warehouse-service-capacity-limits#metadata) . 
  
## <a name="see-also"></a>Consulte también  
 [Vistas de administración dinámica de SQL Data Warehouse y almacenamiento de datos paralelos &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
