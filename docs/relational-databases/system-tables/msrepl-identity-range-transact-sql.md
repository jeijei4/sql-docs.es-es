---
title: MSrepl_identity_range (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSrepl_identity_range_TSQL
- MSrepl_identity_range
dev_langs:
- TSQL
helpviewer_keywords:
- MSrepl_identity_range system table
ms.assetid: 6e92a8e8-7667-4c98-b1c4-46735bac50d8
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4aafc6415d968d25b7ba4e708985e72378f9d95f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889510"
---
# <a name="msrepl_identity_range-transact-sql"></a>MSrepl_identity_range (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  En la tabla **MSrepl_identity_range** se proporciona compatibilidad con la administración del intervalo de identidad. Esta tabla se almacena en las bases de datos de publicaciones, distribución y suscripciones.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**publisher**|**sysname**|El nombre del publicador.|  
|**publisher_db**|**sysname**|Nombre de la base de datos de publicación.|  
|**NombreTabla**|**sysname**|Nombre de la tabla.|  
|**identity_support**|**int**|Especifica si se habilita el control automático de intervalo de identidad. 0 especifica que no se habilita el control automático de intervalo de identidad.|  
|**next_seed**|**bigint**|Si se habilita el intervalo automático de identidad, indica el punto de inicio del siguiente intervalo.|  
|**pub_range**|**bigint**|Tamaño del intervalo de identidad del publicador.|  
|**range**|**bigint**|Tamaño de los valores de identidad consecutivos que podrían asignarse a los suscriptores en un ajuste.|  
|**max_identity**|**bigint**|Límite máximo del intervalo de identidad.|  
|**threshold**|**int**|Porcentaje de umbral del intervalo de identidad.|  
|**current_max**|**bigint**|Máximo actual que se puede asignar, aunque no necesariamente.|  
  
## <a name="see-also"></a>Consulte también  
 [Tablas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vistas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
