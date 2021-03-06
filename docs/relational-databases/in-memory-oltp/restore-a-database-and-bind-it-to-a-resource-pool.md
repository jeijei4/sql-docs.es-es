---
title: Restaurar una base de datos y enlazarla a un grupo de recursos | Microsoft Docs
description: Obtenga información sobre la restauración de una base de datos con tablas optimizadas para memoria en SQL Server. Siga los procedimientos recomendados enlazando la base de datos a un grupo de recursos con nombre.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 0d20a569-8a27-409c-bcab-0effefb48013
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6a04204d4c3b5c637b4c3aac324bfe4b02265b39
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85722354"
---
# <a name="restore-a-database-and-bind-it-to-a-resource-pool"></a>Restaurar una base de datos y enlazarla a un grupo de recursos de servidor
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Aunque tenga memoria suficiente para restaurar una base de datos con tablas optimizadas para memoria, se aconseja seguir los procedimientos recomendados y enlazar la base de datos a un grupo de recursos de servidor con nombre. Puesto que es preciso que la base de datos exista antes de poder enlazarla al grupo que restaura la base de datos, se trata de un proceso en varias fases. Este tema le guiará a través de ese proceso.  
  
## <a name="restoring-a-database-with-memory-optimized-tables"></a>Restaurar una base de datos de ejemplo con tablas optimizadas para memoria  
 Los pasos siguientes muestran cómo restaurar completamente la base de datos HIMOLTP_DB y enlazarla a Pool_IMOLTP.  
  
1.  [Restaure con NORECOVERY.](../../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md#bkmk_NORECOVERY)  
  
2.  [Crear el grupo de recursos de servidor](../../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md#bkmk_createPool)  
  
3.  [Enlazar la base de datos y el grupo de recursos de servidor](../../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md#bkmk_bind)  
  
4.  [Restaurar con RECOVERY](../../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md#bkmk_RECOVERY)  
  
5.  [Supervisar el rendimiento del grupo de recursos de servidor](../../relational-databases/in-memory-oltp/restore-a-database-and-bind-it-to-a-resource-pool.md#bkmk_Monitor)  
  
###  <a name="restore-with-norecovery"></a><a name="bkmk_NORECOVERY"></a> Restaure con NORECOVERY.  
 Cuando se restaura una base de datos, NORECOVERY provoca que se cree la base de datos y se restaura la imagen de disco sin consumir memoria.  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   FROM DISK = 'C:\IMOLTP_test\IMOLTP_DB.bak'  
   WITH NORECOVERY  
```  
  
###  <a name="create-the-resource-pool"></a><a name="bkmk_createPool"></a> Crear el grupo de recursos de servidor  
 El siguiente código [!INCLUDE[tsql](../../includes/tsql-md.md)] crea un grupo de recursos de servidor denominado Pool_IMOLTP con el 50 % de memoria disponible para su uso.  Una vez creado el grupo, hay que reconfigurar el Regulador de recursos para incluir Pool_IMOLTP.  
  
```sql  
CREATE RESOURCE POOL Pool_IMOLTP WITH (MAX_MEMORY_PERCENT = 50);  
ALTER RESOURCE GOVERNOR RECONFIGURE;  
GO  
```  
  
###  <a name="bind-the-database-and-resource-pool"></a><a name="bkmk_bind"></a> Enlazar la base de datos y el grupo de recursos de servidor  
 Use la función del sistema `sp_xtp_bind_db_resource_pool` para enlazar la base de datos al grupo de recursos de servidor. La función utiliza dos parámetros: el nombre de la base de datos seguido del nombre del grupo de recursos de servidor.  
  
 El siguiente código [!INCLUDE[tsql](../../includes/tsql-md.md)] define un enlace de la base de datos IMOLTP_DB con el grupo de recursos de servidor Pool_IMOLTP. El enlace no toma efecto hasta que se complete el paso siguiente.  
  
```sql  
EXEC sp_xtp_bind_db_resource_pool 'IMOLTP_DB', 'Pool_IMOLTP'  
GO  
```  
  
###  <a name="restore-with-recovery"></a><a name="bkmk_RECOVERY"></a> Restaurar con RECOVERY  
 Cuando restaure la base de datos con RECOVERY, la base de datos se conecta y se restauran todos los datos.  
  
```sql  
RESTORE DATABASE IMOLTP_DB   
   WITH RECOVERY  
```  
  
###  <a name="monitor-the-resource-pool-performance"></a><a name="bkmk_Monitor"></a> Supervisar el rendimiento del grupo de recursos de servidor  
 Una vez que la base de datos se enlaza al grupo de recursos de servidor con nombre y se restaura con la recuperación, supervise el objeto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Estadísticas de grupo de recursos de servidor. Para obtener más información vea [Objeto SQL Server: Estadísticas de grupo de recursos de servidor](../../relational-databases/performance-monitor/sql-server-resource-pool-stats-object.md).  
  
## <a name="see-also"></a>Consulte también  
 [Enlazar una base de datos con tablas con optimización para memoria a un grupo de recursos de servidor](../../relational-databases/in-memory-oltp/bind-a-database-with-memory-optimized-tables-to-a-resource-pool.md)   
 [sys.sp_xtp_bind_db_resource_pool &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-xtp-bind-db-resource-pool-transact-sql.md)   
 [Objeto SQL Server: Estadísticas de grupo de recursos de servidor](../../relational-databases/performance-monitor/sql-server-resource-pool-stats-object.md)   
 [sys.dm_resource_governor_resource_pools](../../relational-databases/system-stored-procedures/sys-sp-xtp-unbind-db-resource-pool-transact-sql.md)  
  
  
