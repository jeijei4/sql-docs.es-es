---
title: catalog.worker_agents (base de datos de SSISDB) | Microsoft Docs
ms.custom: ''
ms.date: 12/16/2016
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 0bd0d827-e2f1-44fe-aa90-6bf922d68d16
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5f8c494e135764ddca11985f3036068c848f818b
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86912431"
---
# <a name="catalogworker_agents-ssisdb-database"></a>catalog.worker_agents (base de datos de SSISDB)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]

Muestra la información del trabajo de escalabilidad horizontal [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].

|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|WorkerAgentId|**uniqueidentifier**|Id. de agente de trabajo del trabajo de escalabilidad horizontal.|
|IsEnabled|**bit**|Si está habilitado el trabajo de escalabilidad horizontal.|
|DisplayName|**nvarchar(256)**|Nombre para mostrar del trabajo de escalabilidad horizontal.|
|Descripción|**nvarchar(256)**|Descripción del trabajo de escalabilidad horizontal.|
|MachineName|**nvarchar(256)**|Nombre de máquina del trabajo de escalabilidad horizontal.|
|Etiquetas|**nvarchar(max)**|Etiquetas del trabajo de escalabilidad horizontal.|
|UserAccount|**nvarchar(256)**|Cuenta de usuario que ejecuta el servicio de trabajo de escalabilidad horizontal.|
|LastOnlineTime|**datetimeoffset(7)**|Última vez que el trabajo de escalabilidad horizontal estuvo en línea.|

## <a name="remarks"></a>Observaciones
Esta vista muestra una fila para cada trabajo de escalabilidad horizontal que esté conectado al patrón de escalabilidad horizontal que funciona con el catálogo de SSISDB.

## <a name="permissions"></a>Permisos
Esta vista exige uno de los siguientes permisos:

- Pertenencia al rol de base de datos de **ssis_admin**

- Pertenencia al rol de base de datos **ssis_cluster_executor**

- Pertenencia al rol de servidor de **sysadmin**
