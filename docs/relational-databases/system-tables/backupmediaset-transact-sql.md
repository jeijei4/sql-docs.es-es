---
title: backupmediaset (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 08/09/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- backupmediaset
- backupmediaset_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- backup media [SQL Server], backupmediaset system table
- backupmediaset system table
ms.assetid: d9c18a93-cab9-4db8-ae09-c6bd8145ab8f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 43f54ff292e21e28ec32e8581633872ced2333d7
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85890666"
---
# <a name="backupmediaset-transact-sql"></a>backupmediaset (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contiene una fila por cada conjunto de medios de copia de seguridad. Esta tabla se almacena en la base de datos **msdb** .  
 
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**media_set_id**|**int**|Número exclusivo de identificación del conjunto de medios. Clave principal de identidad.|  
|**media_uuid**|**uniqueidentifier**|UUID del conjunto de medios. Todos los [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conjuntos de medios tienen un UUID.<br /><br /> En el caso de las versiones anteriores de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , sin embargo, si un conjunto de medios solo contiene una familia de medios, la columna de **media_uuid** puede ser null (**media_family_count** es 1).|  
|**media_family_count**|**tinyint**|Número de familias de medios en el conjunto de medios. Puede ser NULL.|  
|**name**|**nvarchar(128)**|Nombre del conjunto de medios. Puede ser NULL.<br /><br /> Para obtener más información, consulte MEDIANAme y MEDIADESCRIPTION en [BACKUP &#40;Transact-SQL&#41;](../../t-sql/statements/backup-transact-sql.md).|  
|**description**|**nvarchar(255)**|Texto de descripción del conjunto de medios. Puede ser NULL.<br /><br /> Para obtener más información, consulte MEDIANAme y MEDIADESCRIPTION en [BACKUP &#40;Transact-SQL&#41;](../../t-sql/statements/backup-transact-sql.md).|  
|**software_name**|**nvarchar(128)**|Nombre del software de copia de seguridad que escribió la etiqueta del medio. Puede ser NULL.|  
|**software_vendor_id**|**int**|Número de identificación del proveedor de software que escribió la etiqueta del medio de copia de seguridad. Puede ser NULL.<br /><br /> El valor de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es hexadecimal 0x1200.|  
|**MTF_major_version**|**tinyint**|Número principal de la versión de formato de cinta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] utilizada para generar este conjunto de medios. Puede ser NULL.|  
|**mirror_count**|**tinyint**|Número de reflejos en el conjunto de medios.|  
|**is_password_protected**|**bit**|Indica si el conjunto de medios está protegido con contraseña:<br /><br /> 0 = Sin protección <br /><br /> 1 = Protegido|  
|**is_compressed**|**bit**|Si la copia de seguridad está comprimida:<br /><br /> 0 = no comprimida<br /><br /> 1 = comprimida<br /><br /> Durante una actualización de **msdb** , este valor se establece en NULL. lo que indica que la copia de seguridad no está comprimida.|  
|**is_encrypted**|**Poco**|Si la copia de seguridad está cifrada:<br /><br /> 0 = No cifrado<br /><br /> 1 = Cifrada|  
  
## <a name="remarks"></a>Comentarios  
 RESTOre VERIFYONLY de *backup_device* con LOADHISTORY rellena las columnas de la tabla **backupmediaset** con los valores adecuados del encabezado de conjunto de medios.  
  
 Para reducir el número de filas de esta tabla y de otras tablas de historial y copia de seguridad, ejecute el [sp_delete_backuphistory](../../relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql.md) procedimiento almacenado.  
  
## <a name="see-also"></a>Consulte también  
 [Copias de seguridad y restauración de tablas &#40;Transact-SQL&#41;](../../relational-databases/system-tables/backup-and-restore-tables-transact-sql.md)   
 [backupfile &#40;Transact-SQL&#41;](../../relational-databases/system-tables/backupfile-transact-sql.md)   
 [backupfilegroup &#40;Transact-SQL&#41;](../../relational-databases/system-tables/backupfilegroup-transact-sql.md)   
 [backupmediafamily &#40;Transact-SQL&#41;](../../relational-databases/system-tables/backupmediafamily-transact-sql.md)   
 [backupset &#40;Transact-SQL&#41;](../../relational-databases/system-tables/backupset-transact-sql.md)   
 [Tablas del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-tables/system-tables-transact-sql.md)  
  
  
