---
title: Sys. dm_pdw_sys_info (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql
ms.technology: data-warehouse
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 686976b4-2d5d-4d64-bf12-56eba1dc59b1
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 93e0020fb0da67538b37c171b3252ba029184554
ms.sourcegitcommit: 01297f2487fe017760adcc6db5d1df2c1234abb4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86197016"
---
# <a name="sysdm_pdw_sys_info-transact-sql"></a>Sys. dm_pdw_sys_info (Transact-SQL)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  Proporciona un conjunto de contadores de nivel de dispositivo que reflejan la actividad general en el dispositivo.  
  
|Nombre de columna|Tipo de datos|Descripción|Intervalo|  
|-----------------|---------------|-----------------|-----------|  
|total_sessions|**int**|Número de sesiones que se encuentran actualmente en el sistema.|de 0 a max_active_sessions (consulte a continuación).|  
|idle_sessions|**int**|Número de sesiones actualmente inactivas.||  
|active_requests|**int**|Número de solicitudes activas que se están ejecutando actualmente.||  
|queued_requests|**int**|Número de solicitudes actualmente en cola.||  
|active_loads|**int**|Número de cargas que se están ejecutando actualmente en el sistema.||  
|queued_loads|**int**|Número de cargas en cola en espera de la ejecución.||  
|active_backups|**int**|Número de copias de seguridad que se están ejecutando actualmente.||  
|active_restores|**int**|Número de restauraciones de copia de seguridad actualmente en ejecución.||  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de administración dinámica de SQL Data Warehouse y almacenamiento de datos paralelos &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-and-parallel-data-warehouse-dynamic-management-views.md)  
  
  
