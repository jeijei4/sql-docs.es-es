---
title: Sys. dm_repl_tranhash (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_repl_tranhash
- sys.dm_repl_tranhash_TSQL
- dm_repl_tranhash_TSQL
- dm_repl_tranhash
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_repl_tranhash dynamic management view
ms.assetid: 0cc52338-e805-4ed4-9835-b19bbf72448e
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4f2d51c1cc22cc3cb2beb89713d79a8d12ba5688
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85898681"
---
# <a name="sysdm_repl_tranhash-transact-sql"></a>sys.dm_repl_tranhash (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Devuelve información sobre las transacciones que se van a replicar en una publicación transaccional.  
  
|column_name|data_type|description|  
|------------------|----------------|-----------------|  
|**cubos**|**bigint**|Número de depósitos en la tabla de hash.|  
|**hashed_trans**|**bigint**|Número de transacciones comprometidas replicadas en el lote actual.|  
|**completed_trans**|**bigint**|Número de transacciones completadas hasta ahora.|  
|**compensated_trans**|**bigint**|Número de transacciones que contienen operaciones de deshacer parciales.|  
|**first_begin_lsn**|**nvarchar (64)**|Primer número de secuencia del registro (LSN) de inicio del lote actual.|  
|**last_commit_lsn**|**nvarchar (64)**|Último LSN comprometido del lote actual.|  
  
## <a name="permissions"></a>Permisos  
 Requiere el permiso VIEW DATABASE STATE en la base de datos de publicaciones para llamar a **dm_repl_tranhash**.  
  
## <a name="remarks"></a>Comentarios  
 La instancia solo se devuelve para objetos de la base de datos replicada que está cargada actualmente en la caché del artículo de replicación.  
  
## <a name="see-also"></a>Consulte también  
 [Funciones y vistas de administración dinámica &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Vistas de administración dinámica relacionadas con la replicación &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/replication-related-dynamic-management-views-transact-sql.md)  
  
  
