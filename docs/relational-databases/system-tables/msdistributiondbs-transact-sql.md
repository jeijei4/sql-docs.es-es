---
title: MSdistributiondbs (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- MSdistributiondbs_TSQL
- MSdistributiondbs
dev_langs:
- TSQL
helpviewer_keywords:
- MSdistributiondbs system table
ms.assetid: d7ffa9df-bf1d-41b8-837e-b762c17c2764
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fde8c78cb37b84ae897e2b12bba6049da8ddc4fa
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85889955"
---
# <a name="msdistributiondbs-transact-sql"></a>MSdistributiondbs (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  La tabla **MSdistributiondbs** contiene una fila por cada base de datos de distribución definida en el distribuidor local. Esta tabla se almacena en la base de datos **msdb** .  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|El nombre de la base de datos de distribución.|  
|**min_distretention**|**int**|El período mínimo de retención, en horas, antes de que se eliminen las transacciones.|  
|**max_distretention**|**int**|El período máximo de retención, en horas, antes de que se eliminen las transacciones.|  
|**history_retention**|**int**|El número de horas que se mantiene el historial.|  
  
## <a name="see-also"></a>Consulte también  
 [Tablas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-tables/replication-tables-transact-sql.md)   
 [Vistas de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-views/replication-views-transact-sql.md)  
  
  
