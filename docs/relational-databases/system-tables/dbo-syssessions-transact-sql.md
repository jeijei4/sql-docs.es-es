---
title: Sesiones de dbo.sys(Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2019
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dbo.syssessions_TSQL
- dbo.syssessions
- syssessions_TSQL
- syssessions
dev_langs:
- TSQL
helpviewer_keywords:
- syssessions system table
ms.assetid: 187819b6-c7f4-4a26-b74c-0a89e96695cf
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 13d57b4c36d238cb8e6893ff912e7052ba2e079f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890385"
---
# <a name="dbosyssessions-transact-sql"></a>dbo.syssessions (Transact-SQL)

[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

Cada vez que el Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se inicia, crea una nueva sesión. El Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] utiliza sesiones para mantener el estado de los trabajos cuando el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se reinicia o se detiene de manera inesperada. Cada fila de la tabla **syssessions** contiene información sobre una sesión. Use la tabla **sysjobactivity** para ver el estado del trabajo al final de cada sesión.  
  
 Esta tabla se almacena en la base de datos **msdb** .  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**session_id**|**int**|Id. de una sesión del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Esta session_id no es el SPID de la sesión, sino un valor de identidad dentro de esta tabla del sistema.|  
|**agent_start_date**|**datetime**|Fecha y hora en que se inició el servicio del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para esta sesión.|  
  
## <a name="remarks"></a>Comentarios  
 Solo los usuarios que son miembros del rol fijo de servidor **sysadmin** pueden tener acceso a esta tabla.  
  
## <a name="see-also"></a>Consulte también  
 [dbo.sysjobactivity &#40;Transact-SQL&#41;](../../relational-databases/system-tables/dbo-sysjobactivity-transact-sql.md)  
  
  
