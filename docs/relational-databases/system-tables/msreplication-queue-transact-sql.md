---
title: MSreplication_queue (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSreplication_queue
- MSreplication_queue_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- MSreplication_queue system table
ms.assetid: 664bf817-8021-4417-96d6-2bb1e4baabff
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3bdbfed403a8b85a195134e053a151905efa128f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889420"
---
# <a name="msreplication_queue-transact-sql"></a>MSreplication_queue (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  El proceso de replicación utiliza la tabla **MSreplication_queue** para almacenar los comandos en cola emitidos por todas las suscripciones de actualización en cola que utilizan la cola basada en SQL. Esta tabla se almacena en la base de datos de suscripciones.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**publisher**|**sysname**|El nombre del publicador.|  
|**publisher_db**|**sysname**|Nombre de la base de datos de publicación.|  
|**publicaciones**|**sysname**|Nombre de la publicación.|  
|**tranid**|**sysname**|Id. de transacción bajo el que se ha ejecutado el comando en cola.|  
|**datos**|**varbinary(8000)**|Secuencia de bytes empaquetados que almacena información acerca del comando en cola.|  
|**datalen**|**int**|Longitud de los datos, en bytes.|  
|**CommandType**|**int**|Tipo de comando en la cola:<br /><br /> 1 = Comando de usuario en la transacción.<br /><br /> 2 = Comando de sincronización de suscripción.|  
|**insertdate**|**datetime**|Fecha de inserción.|  
|**orderkey**|**bigint**|Columna de identidad con una progresión continua.|  
|**cmdstate**|**bit**|Estado del comando:<br /><br /> 0 = Completo.<br /><br /> 1 = Parcial.|  
  
## <a name="see-also"></a>Consulte también  
 [Tablas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vistas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
