---
title: sp_getagentparameterlist (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_getagentparameterlist
- sp_getagentparameterlist_TSQL
helpviewer_keywords:
- sp_getagentparameterlist
ms.assetid: 50d3d3c1-b9a1-417c-bad4-674089c9c60d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 9b4239fafd6ec4ecbda7d89dd143b70a4dccb7eb
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85881630"
---
# <a name="sp_getagentparameterlist-transact-sql"></a>sp_getagentparameterlist (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Devuelve una lista con todos los parámetros del Agente de replicación que se pueden establecer en un perfil de agente para el tipo de agente especificado. Este procedimiento almacenado se ejecuta en el distribuidor en el que se está ejecutando el agente, en cualquier base de datos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_getagentparameterlist [ @agent_type = ] 'agent_type'  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @agent_type = ] 'agent_type'`Es el agente de replicación para el que se va a agregar el parámetro. *agent_type* es de **tipo int**y puede tener uno de estos valores:  
  
|Valor|Agente|  
|-----------|-----------|  
|**1**|Depurador de|  
|**2**|Registro del LOG|  
|**3**|Distribución|  
|**4**|Merge|  
|**9**|Lectura de cola|  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="permissions"></a>Permisos  
 Solo los miembros del rol fijo de servidor **sysadmin** pueden ejecutar **sp_getagentparameter**.  
  
## <a name="see-also"></a>Consulte también  
 [sp_add_agent_parameter &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-add-agent-parameter-transact-sql.md)   
 [sp_add_agent_profile &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-add-agent-profile-transact-sql.md)   
 [sp_drop_agent_parameter &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-drop-agent-parameter-transact-sql.md)   
 [sp_help_agent_parameter &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-help-agent-parameter-transact-sql.md)   
 [Perfiles del agente de replicación](../../relational-databases/replication/agents/replication-agent-profiles.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
