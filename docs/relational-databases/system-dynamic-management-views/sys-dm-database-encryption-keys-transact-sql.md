---
title: Sys. dm_database_encryption_keys (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/27/2019
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_database_encryption_keys
- sys.dm_database_encryption_keys_TSQL
- dm_database_encryption_keys
- dm_database_encryption_keys_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_database_encryption_keys dynamic management view
ms.assetid: 56fee8f3-06eb-4fff-969e-abeaa0c4b8e4
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 3d42cc2873c1e3e03e2af3e0a01080cdb18c349a
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85754283"
---
# <a name="sysdm_database_encryption_keys-transact-sql"></a>sys.dm_database_encryption_keys (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Devuelve información sobre el estado de cifrado de una base de datos y sus claves de cifrado de la base de datos asociadas. Para obtener más información sobre el cifrado de bases de datos, vea [Cifrado de datos transparente &#40;TDE&#41;](../../relational-databases/security/encryption/transparent-data-encryption.md).  
 
|Nombre de columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|database_id|**int**|Identificador de la base de datos.|  
|encryption_state|**int**|Indica si la base de datos está cifrada o no.<br /><br /> 0 = Ninguna clave de cifrado de la base de datos, sin cifrado<br /><br /> 1 = Sin cifrar<br /><br /> 2 = Cifrado en curso<br /><br /> 3 = Cifrado<br /><br /> 4 = Cambio de clave en curso<br /><br /> 5 = Descifrado en curso<br /><br /> 6 = Cambio de protección en curso (El certificado o clave asimétrica que cifra la clave de cifrado de la base de datos se está cambiando).|  
|create_date|**datetime**|Muestra la fecha (en UTC) con la que se creó la clave de cifrado.|  
|regenerate_date|**datetime**|Muestra la fecha (en UTC) en que se volvió a generar la clave de cifrado.|  
|modify_date|**datetime**|Muestra la fecha (en UTC) con la que se modificó la clave de cifrado.|  
|set_date|**datetime**|Muestra la fecha (en UTC) con la que se aplicó la clave de cifrado a la base de datos.|  
|opened_date|**datetime**|Muestra Cuándo (en UTC) se abrió por última vez la clave de base de datos.|  
|key_algorithm|**nvarchar(32)**|Muestra el algoritmo utilizado por la clave.|  
|key_length|**int**|Muestra la longitud de la clave.|  
|encryptor_thumbprint|**varbinary(20)**|Muestra la huella digital del sistema de cifrado.|  
|encryptor_type|**nvarchar(32)**|**Se aplica a**: [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ( [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] desde hasta la [versión actual](https://go.microsoft.com/fwlink/p/?LinkId=299658)).<br /><br /> Describe el sistema de cifrado.|  
|percent_complete|**real**|Porcentaje completado del cambio de estado del cifrado de la base de datos. Será 0 si no hay ningún cambio de estado.|
|encryption_state_desc|**nvarchar(32)**|**Válido para** : [!INCLUDE[sql-server-2019](../../includes/sssqlv15-md.md)] y versiones posteriores.<br><br> Cadena que indica si la base de datos está cifrada o no está cifrada.<br><br>NONE<br><br>SIN cifrar<br><br>CIFRA<br><br>DECRYPTION_IN_PROGRESS<br><br>ENCRYPTION_IN_PROGRESS<br><br>KEY_CHANGE_IN_PROGRESS<br><br>PROTECTION_CHANGE_IN_PROGRESS|
|encryption_scan_state|**int**|**Válido para** : [!INCLUDE[sql-server-2019](../../includes/sssqlv15-md.md)] y versiones posteriores.<br><br>Indica el estado actual del examen de cifrado. <br><br>0 = no se ha iniciado ningún examen, TDE no está habilitado<br><br>1 = el examen está en curso.<br><br>2 = el examen está en curso, pero se ha suspendido, el usuario se puede reanudar.<br><br>3 = el examen se ha anulado por alguna razón, se requiere la intervención manual. Póngase en contacto con Soporte técnico de Microsoft para obtener más ayuda.<br><br>4 = el examen se ha completado correctamente, TDE está habilitado y el cifrado se ha completado.|
|encryption_scan_state_desc|**nvarchar(32)**|**Válido para** : [!INCLUDE[sql-server-2019](../../includes/sssqlv15-md.md)] y versiones posteriores.<br><br>Cadena que indica el estado actual del examen de cifrado.<br><br> NONE<br><br>RUNNING<br><br>SUSPENDED<br><br>ABORTED<br><br>FINALIZA|
|encryption_scan_modify_date|**datetime**|**Válido para** : [!INCLUDE[sql-server-2019](../../includes/sssqlv15-md.md)] y versiones posteriores.<br><br> Muestra la fecha (en UTC) en que se modificó por última vez el estado de examen de cifrado.|
  
## <a name="permissions"></a>Permisos

En [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] , requiere el `VIEW SERVER STATE` permiso.   
En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles Premium, requiere el `VIEW DATABASE STATE` permiso en la base de datos. En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles estándar y básico, requiere el **Administrador del servidor** o una cuenta de **Administrador de Azure Active Directory** .   

## <a name="see-also"></a>Consulte también  

 [Funciones y vistas de administración dinámica relacionadas con la seguridad &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/security-related-dynamic-management-views-and-functions-transact-sql.md)   
 [Cifrado de datos transparente &#40;TDE&#41;](../../relational-databases/security/encryption/transparent-data-encryption.md)   
 [Cifrado de SQL Server](../../relational-databases/security/encryption/sql-server-encryption.md)   
 [SQL Server y claves de cifrado de base de datos &#40;Motor de base de datos&#41;](../../relational-databases/security/encryption/sql-server-and-database-encryption-keys-database-engine.md)   
 [Jerarquía de cifrado](../../relational-databases/security/encryption/encryption-hierarchy.md)   
 [Opciones de ALTER DATABASE SET &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql-set-options.md)   
 [CREAR la clave de CIFRAdo de base de datos &#40;Transact-SQL&#41;](../../t-sql/statements/create-database-encryption-key-transact-sql.md)   
 [ALTER DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-encryption-key-transact-sql.md)   
 [DROP DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](../../t-sql/statements/drop-database-encryption-key-transact-sql.md)  
  
  
