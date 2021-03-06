---
title: Sys. server_resource_stats (Azure SQL Database) | Microsoft Docs
ms.custom: ''
ms.date: 06/28/2018
ms.service: sql-database
ms.reviewer: carlrab, edmaca
ms.topic: language-reference
f1_keywords:
- resource_stats
- sys.resource_stats
- sys.resource_stats_TSQL
- resource_stats_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.resource_stats
- resource_stats
ms.assetid: ''
author: jovanpop-msft
ms.author: jovanpop
monikerRange: =azuresqldb-current||=sqlallproducts-allversions
ms.openlocfilehash: e85a74b203d270223d215ace08a58a0eea980fa1
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85772983"
---
# <a name="sysserver_resource_stats-azure-sql-database"></a>Sys. server_resource_stats (Azure SQL Database)
[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

Devuelve los datos de uso de CPU, e/s y almacenamiento de una Instancia administrada de Azure SQL. Los datos se recopilan y se agregan en intervalos de cinco minutos. Hay una fila por cada 15 segundos de informes. Los datos devueltos incluyen el uso de CPU, el tamaño de almacenamiento, el uso de E/S y la SKU de instancia administrada. Los datos históricos se conservan durante 14 días aproximadamente.

La vista **Sys. server_resource_stats** tiene definiciones diferentes en función de la versión de la instancia administrada de Azure SQL con la que está asociada la base de datos. Tenga en cuenta estas diferencias y cualquier modificación que requiera la aplicación al actualizar a una nueva versión de servidor.
 
  
 En la tabla siguiente se describen las columnas disponibles en un servidor v12:  
  
|Columnas|Tipo de datos|Descripción|  
|----------------------------|---------------|-----------------|  
|start_time|**datetime2**|Hora UTC que indica el inicio del intervalo de informes de quince segundos|  
|end_time|**datetime**|Hora UTC que indica el final del intervalo de informes de quince segundos|
|resource_type|Nvarchar(128)|Tipo del recurso para el que se proporcionan las métricas|
|resource_name|nvarchar(128)|Nombre del recurso.|
|sku|nvarchar(128)|Instancia administrada nivel de servicio de la instancia. Los posibles valores son los siguientes: <br><ul><li>Uso general</li></ul><ul><li>Crítico para la empresa</li></ul>|
|hardware_generation|nvarchar(128)|Identificador de generación de hardware: como gen 4 o gen 5|
|virtual_core_count|int|Representa el número de núcleos virtuales por instancia (8, 16 o 24 en versión preliminar pública)|
|avg_cpu_percent|decimal (5, 2)|Uso de proceso promedio en porcentaje del límite del nivel de servicio Instancia administrada utilizado por la instancia de. Se calcula como suma del tiempo de CPU de todos los grupos de recursos para todas las bases de datos de la instancia y dividido por el tiempo de CPU disponible para ese nivel en el intervalo especificado.|
|reserved_storage_mb|bigint|Almacenamiento reservado por instancia (cantidad de espacio de almacenamiento que el cliente compró para la instancia administrada)|
|storage_space_used_mb|decimal (18, 2)|Almacenamiento utilizado por todos los archivos de bases de datos de instancia administrada (incluidas las bases de datos de usuario y del sistema)|
|io_request|bigint|Número total de operaciones físicas de e/s dentro del intervalo|
|io_bytes_read|bigint|Número de bytes físicos leídos dentro del intervalo|
|io_bytes_written|bigint|Número de bytes físicos escritos en el intervalo|

 
> [!TIP]  
>  Para más información sobre estos límites y los niveles de servicio, consulte los temas [instancia administrada niveles de servicio](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance#managed-instance-service-tiers).  
    
## <a name="permissions"></a>Permisos  
 Esta vista está disponible para todos los roles de usuario con permisos para conectarse a la base de datos **maestra** .  
  
## <a name="remarks"></a>Comentarios  
 Los datos devueltos por **Sys. server_resource_stats** se expresan como el total que se usa en bytes o megabytes (expresado en nombres de columna) distintos de avg_cpu, que se expresa como un porcentaje de los límites máximos permitidos para el nivel de servicio/nivel de rendimiento que se está ejecutando.  
 
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente devuelve todas las bases de datos cuyo promedio de uso de proceso fue al menos del 80 % durante la semana pasada.  
  
```sql  
DECLARE @s datetime;  
DECLARE @e datetime;  
SET @s= DateAdd(d,-7,GetUTCDate());  
SET @e= GETUTCDATE();  
SELECT resource_name, AVG(avg_cpu_percent) AS Average_Compute_Utilization   
FROM sys.server_resource_stats   
WHERE start_time BETWEEN @s AND @e  
GROUP BY resource_name  
HAVING AVG(avg_cpu_percent) >= 80  
```  
    
## <a name="see-also"></a>Consulte también  
 [Instancia administrada niveles de servicio](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance#managed-instance-service-tiers)
