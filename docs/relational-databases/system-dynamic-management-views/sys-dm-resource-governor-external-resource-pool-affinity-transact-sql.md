---
title: Sys. dm_resource_governor_external_resource_pool_affinity (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 11/13/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_resource_governor_external_resource_pool_affinity
- sys.dm_resource_governor_external_resource_pool_affinity_TSQL
- dm_resource_governor_external_resource_pool_affinity
- dm_resource_governor_external_resource_pool_affinity_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_resource_governor_external_resource_pool_affinity
- dm_resource_governor_external_resource_pool_affinity
ms.assetid: e32fac49-5161-47c0-8540-af3fe730c00c
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6d583ec570c7532fbafc354d4d5c70016a8cebd1
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86053239"
---
# <a name="sysdm_resource_governor_external_resource_pool_affinity-transact-sql"></a>Sys. dm_resource_governor_external_resource_pool_affinity (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]
**Se aplica a:** [!INCLUDE[sssql15-md](../../includes/sssql15-md.md)] [!INCLUDE[rsql-productname-md](../../includes/rsql-productname-md.md)]y [!INCLUDE[sssql17-md](../../includes/sssql17-md.md)][!INCLUDE[rsql-productnamenew-md](../../includes/rsql-productnamenew-md.md)]

Devuelve información de afinidad de CPU acerca de la configuración actual del grupo de recursos externos.
  
|Nombre de la columna|Tipo de datos|Descripción|
|----------------|---------------|-----------------|
|pool_id|**int**|IDENTIFICADOR del grupo de recursos externos. No admite valores NULL.|
|processor_group|**smallint**|Identificador del grupo de procesadores lógicos de Windows. No admite valores NULL.|
|cpu_mask|**bigint**|Máscara binaria que representa las CPU asociadas a este grupo. No admite valores NULL.|
  
## <a name="remarks"></a>Observaciones

Los grupos creados con una afinidad de no `AUTO` aparecen en esta vista porque no tienen afinidad. Para obtener más información, vea [crear un grupo de recursos externos &#40;Transact-sql&#41;](../../t-sql/statements/create-external-resource-pool-transact-sql.md) y [modificar el grupo de recursos externos &#40;instrucciones de transact-SQL&#41;](../../t-sql/statements/alter-external-resource-pool-transact-sql.md) .

## <a name="permissions"></a>Permisos

Requiere el permiso `VIEW SERVER STATE`.

## <a name="see-also"></a>Consulte también

[Resource governance for machine learning in SQL Server](../../machine-learning/administration/resource-governor.md) (Gobernanza de recursos para aprendizaje automático en SQL Server)

[Sys. dm_resource_governor_resource_pool_affinity &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-resource-governor-resource-pool-affinity-transact-sql.md)

[Opción de configuración de servidor Scripts externos habilitados](../../database-engine/configure-windows/external-scripts-enabled-server-configuration-option.md)

[ALTER EXTERNAL RESOURCE POOL &#40;Transact-SQL&#41;](../../t-sql/statements/alter-external-resource-pool-transact-sql.md)
