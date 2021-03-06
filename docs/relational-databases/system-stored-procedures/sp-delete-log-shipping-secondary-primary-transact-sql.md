---
title: sp_delete_log_shipping_secondary_primary (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_delete_log_shipping_secondary_primary_TSQL
- sp_delete_log_shipping_secondary_primary
dev_langs:
- TSQL
helpviewer_keywords:
- sp_delete_log_shipping_secondary_primary
ms.assetid: 507fc744-73d9-4cb7-8d2a-bcff88841c6a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a7897600a89a0dab7839dc283a75e0e385ee5787
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85863019"
---
# <a name="sp_delete_log_shipping_secondary_primary-transact-sql"></a>sp_delete_log_shipping_secondary_primary (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Este procedimiento almacenado quita del servidor secundario la información sobre el servidor principal especificado, así como los trabajos de copia y restauración.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_delete_log_shipping_secondary_primary  
[ @primary_server = ] 'primary_server'  
[ @primary_database = ] 'primary_database'  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @primary_server = ] 'primary_server'`Nombre de la instancia principal de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] en la configuración del trasvase de registros. *primary_server* es de **tipo sysname** y no puede ser null.  
  
`[ @primary_database = ] 'primary_database'`Es el nombre de la base de datos del servidor principal. *primary_database* es de **tipo sysname**y no tiene ningún valor predeterminado.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 Ninguno.  
  
## <a name="remarks"></a>Comentarios  
 **sp_delete_log_shipping_secondary_primary** se debe ejecutar desde la base de datos **maestra** en el servidor secundario. Este procedimiento almacenado hace lo siguiente:  
  
1.  Elimina los trabajos de copia y restauración del Id. secundario.  
  
2.  Elimina la entrada de **log_shipping_secondary**.  
  
3.  Llama a **sp_delete_log_shipping_alert_job** en el servidor de supervisión.  
  
## <a name="permissions"></a>Permisos  
 Solo los miembros del rol fijo de servidor **sysadmin** pueden ejecutar este procedimiento.  
  
## <a name="see-also"></a>Consulte también  
 [Acerca del trasvase de registros &#40;SQL Server&#41;](../../database-engine/log-shipping/about-log-shipping-sql-server.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
