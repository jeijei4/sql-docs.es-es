---
title: sp_upgrade_log_shipping (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_upgrade_log_shipping
- sp_upgrade_log_shipping_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_upgrade_log_shipping
ms.assetid: ee01092f-9caf-4e88-888b-ec7b84223705
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8afb57d3660f9c69c3ded45f55ed393531a044c4
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891257"
---
# <a name="sp_upgrade_log_shipping-transact-sql"></a>sp_upgrade_log_shipping (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  La sp_upgrade_log_shipping procedimiento almacenado se invoca automáticamente para actualizar los metadatos específicos del trasvase de registros.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_upgrade_log_shipping  
```  
  
## <a name="arguments"></a>Argumentos  
 Ninguno.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (cualquier otro).  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Ninguno.  
  
## <a name="remarks"></a>Comentarios  
 Este procedimiento almacenado se invoca automáticamente durante la actualización de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para los metadatos de actualización del trasvase de registros. No es necesario ejecutar explícitamente este procedimiento, a no ser que se produzca un problema con los metadatos durante la actualización.  
  
 sp_upgrade_log_shipping se debe ejecutar desde la base de datos maestra del servidor principal, secundario o de supervisión.  
  
## <a name="permissions"></a>Permisos  
 Requiere la pertenencia al rol fijo de servidor **sysadmin** .  
  
## <a name="see-also"></a>Consulte también  
 [Acerca del trasvase de registros &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
