---
title: sysmail_delete_profileaccount_sp (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysmail_delete_profileaccount_sp
- sysmail_delete_profileaccount_sp_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysmail_delete_profileaccount_sp
ms.assetid: b58d06f2-d6c9-4c8e-95bd-027c50f4621a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 27568d450bed5a937931164ed1c04cd09d0b7c2f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890933"
---
# <a name="sysmail_delete_profileaccount_sp-transact-sql"></a>sysmail_delete_profileaccount_sp (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Quita una cuenta de un perfil del Correo electrónico de base de datos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sysmail_delete_profileaccount_sp  {   [ @profile_id = ] profile_id | [ @profile_name = ] 'profile_name' } ,  
    {   [ @account_id = ] account_id | [ @account_name = ] 'account_name' }  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @profile_id = ] profile_id`IDENTIFICADOR del perfil que se va a eliminar. *profile_id* es de **tipo int**y su valor predeterminado es NULL. Se puede especificar el *profile_id* o el *profile_name* .  
  
`[ @profile_name = ] 'profile_name'`Nombre del perfil que se va a eliminar. *profile_name* es de **tipo sysname y su**valor predeterminado es NULL. Se puede especificar el *profile_id* o el *profile_name* .  
  
`[ @account_id = ] account_id`IDENTIFICADOR de cuenta que se va a eliminar. *ACCOUNT_ID* es de **tipo int**y su valor predeterminado es NULL. Se puede especificar el *ACCOUNT_ID* o el *account_name* .  
  
`[ @account_name = ] 'account_name'`Nombre de la cuenta que se va a eliminar. *account_name* es de **tipo sysname y su**valor predeterminado es NULL. Se puede especificar el *ACCOUNT_ID* o el *account_name* .  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 None  
  
## <a name="remarks"></a>Observaciones  
 Devuelve un error si la cuenta especificada no está asociada al perfil especificado.  
  
 Cuando se especifica una cuenta pero no se especifica ningún perfil, este procedimiento almacenado quita la cuenta especificada de todos los perfiles. Por ejemplo, si está preparando el apagado de un servidor SMTP, quita las cuentas que utiliza el servidor SMTP de todos los perfiles, en lugar de quitar cada cuenta de cada perfil.  
  
 Cuando se especifica un perfil pero no se especifica ninguna cuenta, este procedimiento almacenado quita todas las cuentas del perfil especificado. Por ejemplo, si va a cambiar los servidores SMTP que utiliza un perfil, puede ser conveniente quitar todas las cuentas del perfil y agregar después cuentas nuevas según sea necesario.  
  
 El procedimiento almacenado **sysmail_delete_profileaccount_sp** está en la base de datos **msdb** y pertenece al esquema **DBO** . El procedimiento se debe ejecutar con un nombre de tres partes si la base de datos actual no es **msdb**.  
  
## <a name="permissions"></a>Permisos  
 Los permisos de ejecución para este procedimiento tienen como valor predeterminado los miembros del rol fijo de servidor **sysadmin** .  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente muestra cómo se quita la cuenta `Audit Account` del perfil `AdventureWorks Administrator`.  
  
```  
EXECUTE msdb.dbo.sysmail_delete_profileaccount_sp  
    @profile_name = 'AdventureWorks Administrator',  
    @account_name = 'Audit Account' ;  
```  
  
## <a name="see-also"></a>Consulte también  
 [Correo electrónico de base de datos](../../relational-databases/database-mail/database-mail.md)   
 [Creación de una cuenta de Correo electrónico de base de datos](../../relational-databases/database-mail/create-a-database-mail-account.md)   
 [Correo electrónico de base de datos objetos de configuración](../../relational-databases/database-mail/database-mail-configuration-objects.md)   
 [Correo electrónico de base de datos procedimientos almacenados &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/database-mail-stored-procedures-transact-sql.md)  
  
  
