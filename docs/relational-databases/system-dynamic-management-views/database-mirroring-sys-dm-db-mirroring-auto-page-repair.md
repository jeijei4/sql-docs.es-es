---
title: Sys. dm_db_mirroring_auto_page_repair (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_db_mirroring_auto_page_repair_TSQL
- sys.dm_db_mirroring_auto_page_repair_TSQL
- sys.dm_db_mirroring_auto_page_repair
- dm_db_mirroring_auto_page_repair
dev_langs:
- TSQL
helpviewer_keywords:
- automatic page repair
- database mirroring [SQL Server], automatic page repair
- sys.dm_db_mirroring_auto_page_repair dynamic management view
ms.assetid: 49f0fc2a-e25e-47e1-a135-563adb509af1
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c6f86d9c0c334ed5ce86b0227e4fd4f0ce408087
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85894724"
---
# <a name="database-mirroring---sysdm_db_mirroring_auto_page_repair"></a>Creación de reflejo de la base de datos: sys. dm_db_mirroring_auto_page_repair
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Devuelve una fila para cada intento de reparación de página automática en cualquier base de datos reflejada en la instancia del servidor. Esta vista contiene las filas para los últimos intentos de reparación de página automática en una base de datos reflejada determinada, con un máximo de 100 filas por base de datos. En cuanto una base de datos alcanza el máximo, la fila del siguiente intento de reparación de página automática reemplazará una de las entradas existentes. En la tabla siguiente se define el significado de las distintas columnas.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**database_id**|**int**|Identificador la base de datos a la que corresponde esta fila.|  
|**file_id**|**int**|Identificador del archivo en el que se encuentra la página.|  
|**page_id**|**bigint**|Identificador de la página en el archivo.|  
|**error_type**|**int**|Tipo del error. Los valores pueden ser:<br /><br /> **-** 1 = todos los errores de hardware 823<br /><br /> 1 = Errores 824 distintos de una suma de comprobación errónea o una página rasgada (por ejemplo, un identificador de página incorrecto)<br /><br /> 2 = Suma de comprobación incorrecta<br /><br /> 3 = Página rasgada|  
|**page_status**|**int**|El estado del intento de reparación de la página:<br /><br /> 2 = En cola para la solicitud del socio.<br /><br /> 3 = Solicitud enviada al socio.<br /><br /> 4 = En cola para la reparación de página automática (respuesta recibida del socio).<br /><br /> 5 = La reparación de página automática tuvo éxito y la página debería ser utilizable.<br /><br /> 6 = Irreparable. Esto indica que se produjo un error durante el intento de reparación de la página, por ejemplo, porque la página también está dañada en el socio, el socio está desconectado o existe un problema de red. Este estado no es definitivo; si se vuelve a producir un daño en la página, se solicitará de nuevo la página del socio.|  
|**modification_time**|**datetime**|Hora del último cambio en el estado de la página.|  
  
## <a name="security"></a>Seguridad  
  
### <a name="permissions"></a>Permisos  
 es necesario contar con el permiso VIEW SERVER STATE en el servidor.  
  
## <a name="see-also"></a>Consulte también  
 [Reparación de página automática &#40;grupos de disponibilidad: creación de reflejo de la base de datos&#41;](../../sql-server/failover-clusters/automatic-page-repair-availability-groups-database-mirroring.md)   
 [Funciones y vistas de administración dinámica &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [suspect_pages &#40;&#41;de Transact-SQL](../../relational-databases/system-tables/suspect-pages-transact-sql.md)   
 [Administrar la tabla suspect_pages &#40;SQL Server&#41;](../../relational-databases/backup-restore/manage-the-suspect-pages-table-sql-server.md)  
  
  


