---
title: Sys. fn_hadr_is_primary_replica (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.fn_hadr_is_primary_replica
- fn_hadr_is_primary_replica_TSQL
- fn_hadr_is_primary_replica
- sys.fn_hadr_is_primary_replica_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- fn_hadr_is_primary_replica
- sys.fn_hadr_is_primary_replica
ms.assetid: c9b1969f-be1d-4dfb-a33d-551f380b9e27
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5a030bbcd292ade6e52f71f523d60dfccbdf6c79
ms.sourcegitcommit: bfb5e79586fd08d8e48e9df0e9c76d1f6c2004e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82262117"
---
# <a name="sysfn_hadr_is_primary_replica-transact-sql"></a>sys.fn_hadr_is_primary_replica (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2014-xxxx-xxxx-xxx-md](../../includes/tsql-appliesto-ss2014-xxxx-xxxx-xxx-md.md)]

  Se usa para determinar si la réplica actual es la réplica principal.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sys.fn_hadr_is_primary_replica ( 'dbname' )  
```  
  
## <a name="arguments"></a>Argumentos  
 '*dbname*'  
 Es el nombre de la base de datos. *dbname* es de tipo sysname.  
  
## <a name="returns"></a>Devoluciones  
 Devuelve el tipo de datos **bool**: 1 si la base de datos de la instancia actual es la réplica principal, de lo contrario, es 0.  
  
## <a name="remarks"></a>Observaciones  
 Utilice esta función para determinar fácilmente si la instancia local hospeda la réplica principal de la base de datos de disponibilidad especificada. El código de ejemplo podría ser similar al siguiente.  
  
```  
If sys.fn_hadr_is_primary_replica ( @dbname ) <> 1   
BEGIN  
-- If this is not the primary replica, exit (probably without error).  
END  
-- If this is the primary replica, continue to do the backup.  
  
```  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-using-sysfn_hadr_is_primary_replica"></a>A. Usar sys.fn_hadr_is_primary_replica  
 El ejemplo siguiente devuelve 1 si la base de datos especificada en la instancia local es la réplica principal.  
  
```  
SELECT sys.fn_hadr_is_primary_replica ('TestDB');  
GO  
```    
  
## <a name="security"></a>Seguridad  
  
### <a name="permissions"></a>Permisos  
 es necesario contar con el permiso VIEW SERVER STATE en el servidor.  
  
## <a name="see-also"></a>Consulte también  
 [Funciones de Grupos de disponibilidad AlwaysOn &#40;&#41;de Transact-SQL](../../relational-databases/system-functions/always-on-availability-groups-functions-transact-sql.md)   
 [Sys. dm_hadr_database_replica_states &#40;Transact-SQL&#41;](../..//relational-databases/system-dynamic-management-views/sys-dm-hadr-database-replica-states-transact-sql.md) [grupos de disponibilidad AlwaysOn &#40;](../../database-engine/availability-groups/windows/always-on-availability-groups-sql-server.md) SQL Server&#41;   
 [Crear grupo de disponibilidad &#40;Transact-SQL&#41;](../../t-sql/statements/create-availability-group-transact-sql.md)   
 [ALTER AVAILABILITY GROUP &#40;Transact-SQL&#41;](../../t-sql/statements/alter-availability-group-transact-sql.md)   
 [Grupos de disponibilidad AlwaysOn vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/always-on-availability-groups-catalog-views-transact-sql.md)     
  
  
