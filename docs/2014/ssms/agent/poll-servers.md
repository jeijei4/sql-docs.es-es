---
title: Sondear servidores | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-cross-instance
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- target servers [SQL Server], polling interval
- polling master servers [SQL Server]
- server polling [SQL Server]
- master servers [SQL Server], polling
- polling interval [SQL Server]
ms.assetid: 96f5fd43-3edd-4418-9dd0-4d34e618890e
caps.latest.revision: 20
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: efb1c63e6fed68dff7425145aa89f2be1f79ae84
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36201728"
---
# <a name="poll-servers"></a>Sondear servidores
  Cuando se implementa la administración multiservidor, los servidores de destino se ponen en contacto periódicamente con el servidor maestro para cargar información sobre los trabajos que se han ejecutado y descargar nuevos trabajos. El proceso de ponerse en contacto con el servidor maestro se denomina *sondeo de servidor* y tiene lugar a *intervalos de sondeo*regulares.  
  
## <a name="polling-intervals"></a>Intervalos de sondeo  
 El intervalo de sondeo (de manera predeterminada un minuto) controla la frecuencia con la que el servidor de destino se conecta al servidor maestro para descargar instrucciones y cargar los resultados de la ejecución de trabajos.  
  
 Cuando un servidor de destino sondea el servidor maestro, lee las operaciones asignadas al servidor de destino en la tabla **sysdownloadlist** de la base de datos **msdb** . Estas operaciones controlan trabajos multiservidor y diversos aspectos del comportamiento del servidor de destino. Algunos ejemplos de operaciones son eliminar, insertar e iniciar trabajos, y actualizar el intervalo de sondeo de un servidor de destino.  
  
 Las operaciones se exponen en la tabla **sysdownloadlist** de una de las siguientes formas:  
  
-   Explícitamente mediante el procedimiento almacenado **sp_post_msx_operation** .  
  
-   Implícitamente mediante otros procedimientos almacenados de trabajo.  
  
 Si utiliza procedimientos almacenados de trabajo para modificar pasos de trabajos o programaciones de trabajos multiservidor, o bien Objetos de administración distribuida de SQL (SQL-DMO) para controlar trabajos multiservidor, utilice este comando después de modificar los pasos o las programaciones de un trabajo multiservidor:  
  
```  
EXECUTE msdb.dbo.sp_post_msx_operation 'INSERT', 'JOB', '<job id>'  
```  
  
 Utilice este comando para mantener sincronizados los servidores de destino con la definición del trabajo actual.  
  
 No es necesario exponer explícitamente las operaciones si utiliza:  
  
-   Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para controlar trabajos multiservidor.  
  
-   Procedimientos almacenados de trabajo que no modifican pasos de trabajos ni programaciones de trabajos.  
  
 **Para forzar que un servidor de destino sondee el servidor maestro**  
  
-   [SQL Server Management Studio](force-a-target-server-to-poll-the-master-server.md)  
  
-   [Transact-SQL](/sql/relational-databases/system-stored-procedures/sp-post-msx-operation-transact-sql)  
  
## <a name="see-also"></a>Vea también  
 [Administrar eventos](manage-events.md)  
  
  