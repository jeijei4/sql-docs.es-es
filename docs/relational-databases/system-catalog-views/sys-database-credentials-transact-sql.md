---
title: Sys. database_credentials (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 02/27/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.database_credentials
- sys.database_credentials_TSQL
- database_credentials
- database_credentials_TSQL
helpviewer_keywords:
- sys.database_credentials catalog view
ms.assetid: 796322df-e62a-45bf-b519-89e1d521abce
author: VanMSFT
ms.author: vanto
monikerRange: =azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 2521d9543c71d9dee298fbb58518163fd45fbfdc
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "67999530"
---
# <a name="sysdatabase_credentials-transact-sql"></a>Sys. database_credentials (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-asdw-xxx-md.md)]

  Devuelve una fila por cada credencial de ámbito de base de datos de la base de datos.  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]Use [Sys. database_scoped_credentials](../../relational-databases/system-catalog-views/sys-database-scoped-credentials-transact-sql.md) en su lugar.    
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|credential_id|**int**|IDENTIFICADOR de la credencial con ámbito de base de datos. Es único en la base de datos.|  
|name|**sysname**|Nombre de la credencial con ámbito de base de datos. Es único en la base de datos.|  
|credential_identity|**nvarchar(4000)**|Nombre de la identidad que se va a utilizar. Suele ser un usuario de Windows. No tiene que ser único.|  
|create_date|**datetime**|Hora a la que se creó la credencial con ámbito de base de datos.|  
|modify_date|**datetime**|Hora a la que se modificó por última vez la credencial con ámbito de base de datos.|  
|target_type|**nvarchar(100**|Tipo de credencial de ámbito de base de datos. Devuelve NULL para las credenciales con ámbito de base de datos.|  
|target_id|**int**|IDENTIFICADOR del objeto al que está asignada la credencial con ámbito de base de datos. Devuelve 0 para las credenciales con ámbito de base de datos|  
  
## <a name="permissions"></a>Permisos  
 Debe tener el permiso `CONTROL` para la base de datos.  
  
## <a name="see-also"></a>Consulte también  
 [Credenciales &#40;Motor de base de datos&#41;](../../relational-databases/security/authentication-access/credentials-database-engine.md)   
 [CREAR credencial con ámbito de base de datos &#40;Transact-SQL&#41;](../../t-sql/statements/create-database-scoped-credential-transact-sql.md)   
 [MODIFICAR credencial de ámbito de base de datos &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-scoped-credential-transact-sql.md)   
 [QUITAR credencial con ámbito de base de datos &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-scoped-credential-transact-sql.md)   
 [CREAR credencial &#40;Transact-SQL&#41;](../../t-sql/statements/create-credential-transact-sql.md)   
 [sys.credentials &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-credentials-transact-sql.md)  
  
  
