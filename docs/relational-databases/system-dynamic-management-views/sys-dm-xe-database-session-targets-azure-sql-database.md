---
title: sys.dm_xe_database_session_targets
titleSuffix: Azure SQL Database
ms.date: 06/10/2016
ms.service: sql-database
ms.prod_service: sql-database
ms.reviewer: ''
ms.topic: language-reference
ms.assetid: 7f353e2a-f8fc-4366-97e4-aa1c49eadaf4
author: CarlRabeler
ms.author: carlrab
monikerRange: = azuresqldb-current || = sqlallproducts-allversions
ms.custom: seo-dt-2019
ms.openlocfilehash: 7cc1e66845d07dca1dcb5efeb597751fc3ae55e9
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85675976"
---
# <a name="sysdm_xe_database_session_targets-azure-sql-database"></a>sys.dm_xe_database_session_targets (Azure SQL Database)
[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

  Devuelve información acerca de los destinos de la sesión.  
  
||  
|-|  
|**Se aplica a**: [!INCLUDE[ssSDSfull](../../includes/sssdsfull-md.md)] V12 y a las versiones futuras.|  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|event_session_address|**varbinary(8**|La dirección de memoria de la sesión de eventos. Tiene una relación de varios a uno con sys. dm_xe_database_sessions. Address. No admite valores NULL.|  
|target_name|**nvarchar(60)**|El nombre del destino dentro de una sesión. No admite valores NULL.|  
|target_package_guid|**uniqueidentifier**|GUID del paquete que contiene el destino. No admite valores NULL.|  
|execution_count|**bigint**|El número de veces que se ha ejecutado el destino para la sesión. No admite valores NULL.|  
|execution_duration_ms|**bigint**|El tiempo total, en milisegundos, que se ha estado ejecutando el destino. No admite valores NULL.|  
|target_data|**nvarchar(max)**|Datos que mantiene el destino como, por ejemplo, información de agregación de eventos. Acepta valores NULL.|  
  
## <a name="permissions"></a>Permisos  
 Necesita el permiso VIEW DATABASE STATE.  
  
### <a name="relationship-cardinalities"></a>Cardinalidades de relación  
  
|De|A|Relación|  
|----------|--------|------------------|  
|Sys. dm_xe_database_session_targets. event_session_address|Sys. dm_xe_database_sessions. Address|Varios a uno|  
  
  
