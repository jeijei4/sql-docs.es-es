---
title: Actualización del Monitor de actividad de trabajo | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql13.swb.jobactivitymon.refresh.f1
ms.assetid: 413a368e-fd2b-4e1f-b370-002cdbc85bab
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6343929a2f893d020d992a7bd68ba70e178ed2c3
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85666922"
---
# <a name="job-activity-monitor-refresh"></a>Actualizar el Monitor de actividad de trabajo
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Utilice el cuadro de diálogo **Actualizar configuración** para configurar la frecuencia con la que el Monitor de actividad de trabajo obtiene información nueva sobre la actividad del servidor. El Monitor de actividad debe ejecutar consultas en el servidor supervisado para obtener información sobre la cuadrícula Monitor de actividad de trabajo. Cuando el intervalo de actualización automática se establece en un valor inferior a 30 segundos, el tiempo usado para ejecutar estas consultas puede afectar al rendimiento del servidor.  
  
 Para abrir este cuadro de diálogo, haga clic en **Ver configuración de actualización**, en la sección **Estado** del Monitor de actividad de trabajo.  
  
## <a name="options"></a>Opciones  
 **Actualizar automáticamente cada**  
 Realiza comprobaciones para iniciar la actualización automática de la información del Monitor de actividad. Esta opción está desactivada de forma predeterminada.  
  
 **segundos**  
 Número de segundos entre los distintos intentos de actualización automática. El valor predeterminado es 60 segundos. Realiza actualizaciones cada 5 segundos cuando se establece en 5 o en un valor inferior.  
  
## <a name="see-also"></a>Consulte también  
 [Actividad de trabajos de monitor](../../ssms/agent/monitor-job-activity.md)  
  
  
