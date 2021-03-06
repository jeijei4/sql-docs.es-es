---
title: MSpeer_conflictdetectionconfigrequest (T-SQL)
description: Describe el MSPeer_conflictdetectionconfigurerequest procedimiento almacenado que se usa para realizar un seguimiento de las solicitudes de configuración de toda la topología para una publicación punto a punto.
ms.custom: seo-lt-2019
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSpeer_conflictdetectionconfigrequest_TSQL
- MSpeer_conflictdetectionconfigrequest
dev_langs:
- TSQL
helpviewer_keywords:
- MSpeer_conflictdetectionconfigurerequest
ms.assetid: 83afa0ca-707e-4468-a888-228268ed4e10
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ef226872ae70f7b089e118fffd799d1f3394a228
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889697"
---
# <a name="mspeer_conflictdetectionconfigrequest-transact-sql"></a>MSpeer_conflictdetectionconfigrequest (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Se utiliza en la replicación punto a punto para realizar el seguimiento de las solicitudes de configuración de toda la topología para una publicación. Esta tabla se almacena en la base de datos de publicación.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|id|**int**|Identifica una solicitud de configuración que produce conflicto. La columna request_id de [MSpeer_conflictdetectionconfigresponse](../../relational-databases/system-tables/mspeer-conflictdetectionconfigresponse-transact-sql.md) utiliza este valor.|  
|publication|**sysname**|Nombre de la publicación desde la que se originó la solicitud de configuración que produce conflicto.|  
|sent_date|**datetime**|Fecha y hora en que se inició la solicitud de configuración que produce conflicto.|  
|timeout|**int**|Período de tiempo que un procedimiento debe esperar para que todos los nodos del mismo nivel devuelvan información de conflicto.|  
|modified_date|**datetime**|Fecha y hora en que se completó una fase.|  
|progress_phase|**nvarchar(32)**|Identifica la fase actual de procesamiento, utilizando uno de los valores siguientes:<br /><br /> Comenzado<br /><br /> Explorando topología<br /><br /> Recopilando estado<br /><br /> Estado recopilado|  
|phase_timed_out|**bit**|Indica si la fase actual ha agotado el tiempo de espera.|  
  
## <a name="see-also"></a>Consulte también  
 [Tablas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vistas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
