---
title: sp_polybase_leave_group (Transact-SQL) | Microsoft Docs
description: El comando de Transact-SQL sp_polybase_leave_group quita una instancia de SQL Server de un grupo de polybase para el cálculo de escalado horizontal.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.technology: polybase
ms.topic: conceptual
f1_keywords:
- sp_polybase_leave_group
- sp_polybase_leave_group_TSQL
helpviewer_keywords:
- sp_polybase_leave_group
ms.assetid: ef87a8f1-5407-47b5-b8bf-bd7d08c0f0fe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 82bcad58a97fa41938f127c0a814c312c4e22ec9
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052730"
---
# <a name="sp_polybase_leave_group-transact-sql"></a>sp_polybase_leave_group (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  Quita una instancia de SQL Server de un grupo de polybase para el cálculo de escalado horizontal. 
 
 La instancia de SQL Server debe tener instalada la característica de la [Guía de polybase](../../relational-databases/polybase/polybase-guide.md) .  Polybase permite la integración de orígenes de datos que no son de SQL Server, como Hadoop y Azure BLOB Storage. Vea también [sp_polybase_join_group](../../relational-databases/system-stored-procedures/polybase-stored-procedures-sp-polybase-join-group.md).  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_polybase_leave_group;  
  
```  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="permissions"></a>Permisos  
 Requiere el permiso CONTROL SERVER.  
  
## <a name="remarks"></a>Observaciones  
 Solo puede quitar un nodo de proceso de un grupo.  
  
 Después de ejecutar el procedimiento almacenado, reinicie el motor de polybase y Movimiento de datos de PolyBase servicio en la máquina. Para comprobar, ejecute la siguiente DMV en el nodo principal: **Sys. dm_exec_compute_nodes**.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo se quita el equipo actual de un grupo de polybase.  
  
```sql  
EXEC sp_polybase_leave_group ;  
```  
  
## <a name="see-also"></a>Consulte también  
 [Introducción a polybase](../../relational-databases/polybase/get-started-with-polybase.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
