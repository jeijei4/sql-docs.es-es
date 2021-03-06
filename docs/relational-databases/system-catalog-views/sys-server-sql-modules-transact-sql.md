---
title: Sys. server_sql_modules (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.server_sql_modules
- sys.server_sql_modules_TSQL
- server_sql_modules_TSQL
- server_sql_modules
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_sql_modules catalog view
ms.assetid: 9ef9a8b9-c470-4a61-b0c4-ee24ad871d63
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 23c8596a1dc2d4cfa75f01b123d1f11cffcfe546
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85882944"
---
# <a name="sysserver_sql_modules-transact-sql"></a>sys.server_sql_modules (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contiene el conjunto de módulos SQL para los desencadenadores de nivel de servidor de tipo TR. Puede combinar esta relación con sys.server_triggers. La tupla (object_id) es la clave de la relación.  
  
|Nombre de columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|Se trata de una referencia FOREIGN KEY al desencadenador de nivel de servidor en el que se define este módulo.|  
|**definir**|**nvarchar(max)**|Texto SQL que define este módulo.<br /><br /> NULL = Cifrado.|  
|**uses_ansi_nulls**|**bit**|El módulo fue creado con la opción de conjunto ANSI NULLS establecida en ON.|  
|**uses_quoted_identifier**|**bit**|El módulo fue creado con la opción de conjunto QUOTED IDENTIFIER establecida en ON.|  
|**execute_as_principal_id**|**int**|Id. de la entidad de seguridad de servidor EXECUTE AS.<br /><br /> NULL de manera predeterminada o si EXECUTE AS CALLER <br /><br /> IDENTIFICADOR de la entidad de seguridad especificada si EXECUTe AS SELF EXECUTe as principal-2 = EXECUTe AS OWNER.|  
  
## <a name="permissions"></a>Permisos  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
