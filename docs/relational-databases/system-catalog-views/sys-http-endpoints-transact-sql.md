---
title: Sys. http_endpoints (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.http_endpoints
- http_endpoints
- sys.http_endpoints_TSQL
- http_endpoints_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.http_endpoints catalog view
ms.assetid: 16f59695-ecd9-457e-8874-055af63f8ea7
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 527cc2d7596a1bdd894ba71c1e3b1139150efc63
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85896268"
---
# <a name="syshttp_endpoints-transact-sql"></a>sys.http_endpoints (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contiene una fila para cada extremo creado en el servidor que utiliza el protocolo HTTP.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**< columnas heredadas>**||Hereda columnas de [Sys. endpoints &#40;&#41;de Transact-SQL ](../../relational-databases/system-catalog-views/sys-endpoints-transact-sql.md).|  
|**visitante**|**nvarchar(128)**|Nombre del equipo host del sitio según se especifica en la opción SITE =.|  
|**url_path**|**nvarchar(4000)**|Parte solo de la ruta de la URL para este extremo HTTP según se especifica en la opción PATH=.|  
|**is_clear_port_enabled**|**bit**|1 = Puerto libre habilitado con la opción PORT = CLEAR.|  
|**clear_port**|**int**|Número de puerto especificado con la opción CLEAR PORT =.<br /><br /> NULL = Sin especificar.|  
|**is_ssl_port_enabled**|**bit**|1 = Puerto SSL habilitado con la opción PORT = SSL.|  
|**ssl_port**|**int**|Número de puerto especificado con la opción SSL PORT =.<br /><br /> NULL = Sin especificar.|  
|**is_anonymous_enabled**|**bit**|1 = Acceso anónimo habilitado con la opción AUTHENTICATION = ANONYMOUS.|  
|**is_basic_auth_enabled**|**bit**|1 = Autenticación básica habilitada con la opción AUTHENTICATION = BASIC.|  
|**is_digest_auth_enabled**|**bit**|1 = Autenticación implícita habilitada con la opción AUTHENTICATION = DIGEST.|  
|**is_kerberos_auth_enabled**|**bit**|1 = Autenticación integrada habilitada con la opción AUTHENTICATION = KERBEROS.|  
|**is_ntlm_auth_enabled**|**bit**|1 = Autenticación integrada habilitada con la opción AUTHENTICATION = NTLM.|  
|**is_integrated_auth_enabled**|**bit**|1 = Autenticación integrada habilitada con la opción AUTHENTICATION = INTEGRATED.|  
|**authorization_realm**|**nvarchar(128)**|Sugerencia devuelta al cliente como parte del desafío de la autenticación HTTP DIGEST. Es el valor de la opción AUTH REALM.<br /><br /> Es NULL si no se especifica o si la autenticación DIGEST no está habilitada.|  
|**default_logon_domain**|**nvarchar(128)**|Dominio de inicio de sesión predeterminado al habilitar la autenticación BASIC. Es el valor de la opción DEFAULT LOGON DOMAIN.<br /><br /> Es NULL si no se especifica o si la autenticación BASIC no está habilitada.|  
|**is_compression_enabled**|**bit**|1 = Se establece la opción COMPRESSION = ENABLED.|  
  
## <a name="permissions"></a>Permisos  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Endpoints Catalog Views &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/endpoints-catalog-views-transact-sql.md) [Vistas de catálogo de extremos &#40;Transact-SQL&#41;]  
  
  
