---
title: sp_replcounters (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_replcounters
- sp_replcounters_TSQL
helpviewer_keywords:
- sp_replcounters
ms.assetid: fe585b1f-edda-421f-81d6-8a03a3a535d2
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 98e5064c571a67afe445f265eaac693432cb5b38
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85645443"
---
# <a name="sp_replcounters-transact-sql"></a>sp_replcounters (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Devuelve las estadísticas de replicación relativas a la latencia, el rendimiento y el recuento de transacciones de cada base de datos publicada. Este procedimiento almacenado se ejecuta en el publicador de cualquier base de datos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_replcounters  
  
```  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**Base de datos**|**sysname**|Nombre de la base de datos.|  
|**Replicated transactions**|**int**|Número de transacciones del registro en espera de su entrega a la base de datos de distribución.|  
|**Replication rate trans/sec**|**float**|Numero promedio de transacciones por segundo entregadas en la base de datos de distribución.|  
|**Latencia de replicación**|**float**|Tiempo promedio, en segundos, que las transacciones permanecieron en el registro antes de ser distribuidas.|  
|**Replbeginlsn**|**binary(10)**|Número de flujo de registro (LSN) del punto de truncamiento actual del registro.|  
|**Replnextlsn**|**binary(10)**|Número de secuencia del siguiente registro de confirmación que está en espera de su entrega a la base de datos de distribución.|  
  
## <a name="remarks"></a>Comentarios  
 **sp_replcounters** se utiliza en la replicación transaccional.  
  
## <a name="permissions"></a>Permisos  
 Requiere la pertenencia al rol fijo de base de datos **db_owner** o el rol fijo de servidor **sysadmin** .  
  
## <a name="see-also"></a>Consulte también  
 [sp_replcmds &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-replcmds-transact-sql.md)   
 [sp_repldone &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-repldone-transact-sql.md)   
 [sp_replflush &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-replflush-transact-sql.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
