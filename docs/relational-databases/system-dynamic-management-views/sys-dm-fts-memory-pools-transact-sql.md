---
title: Sys. dm_fts_memory_pools (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_fts_memory_pools_TSQL
- sys.dm_fts_memory_pools_TSQL
- sys.dm_fts_memory_pools
- dm_fts_memory_pools
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_fts_memory_pools dynamic management view
ms.assetid: 24747239-cd78-4d55-a00a-19233a457f42
author: pmasl
ms.author: pelopes
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 0f14acaaf8e4f92a603270619c181e9d97108c5d
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85734525"
---
# <a name="sysdm_fts_memory_pools-transact-sql"></a>sys.dm_fts_memory_pools (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Devuelve información acerca de los bloques de memoria compartida disponibles para el recopilador de texto completo en un rastreo de texto completo o un intervalo de rastreo de texto completo.  
   
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**pool_id**|**int**|Id. del grupo de memoria asignado.<br /><br /> 0 = Búferes pequeños<br /><br /> 1 = Búferes grandes|  
|**buffer_size**|**int**|Tamaño de cada búfer asignado en el grupo de memoria.|  
|**min_buffer_limit**|**int**|Número mínimo de búferes permitidos en el grupo de memoria.|  
|**max_buffer_limit**|**int**|Número máximo de búferes permitidos en el grupo de memoria.|  
|**buffer_count**|**int**|Número actual de búferes de memoria compartida en el grupo de memoria.|  
  
## <a name="permissions"></a>Permisos  

En [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] , requiere el `VIEW SERVER STATE` permiso.   
En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles Premium, requiere el `VIEW DATABASE STATE` permiso en la base de datos. En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles estándar y básico, requiere el **Administrador del servidor** o una cuenta de **Administrador de Azure Active Directory** .   
 
## <a name="physical-joins"></a>Combinaciones físicas  
 ![Combinaciones significativas de esta vista de administración dinámica](../../relational-databases/system-dynamic-management-views/media/join-dm-fts-memory-pools-1.gif "Combinaciones significativas de esta vista de administración dinámica")  
  
## <a name="relationship-cardinalities"></a>Cardinalidades de relación  
  
|De|A|Relación|  
|----------|--------|------------------|  
|dm_fts_memory_buffers.pool_id|dm_fts_memory_pools.pool_id|Varios a uno|  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se devuelve la memoria total compartida propiedad del recopilador de texto completo de [!INCLUDE[msCoName](../../includes/msconame-md.md)] del proceso de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
```  
SELECT SUM(buffer_size * buffer_count) AS "total memory"   
    FROM sys.dm_fts_memory_pools;  
```  
  
## <a name="see-also"></a>Consulte también  
 [Funciones y vistas de administración dinámica de la búsqueda de texto completo y la búsqueda semántica &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/full-text-and-semantic-search-dynamic-management-views-functions.md)  
  
  
