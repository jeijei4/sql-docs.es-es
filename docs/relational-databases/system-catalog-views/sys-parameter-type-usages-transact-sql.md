---
title: Sys. parameter_type_usages (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.parameter_type_usages
- sys.parameter_type_usages_TSQL
- parameter_type_usages_TSQL
- parameter_type_usages
dev_langs:
- TSQL
helpviewer_keywords:
- sys.parameter_type_usages catalog view
ms.assetid: af0e167b-bffb-4525-84ec-3607f9268d3d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5dbb261f10afb2fbf9e01f27dc82beccc4d3a145
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85894340"
---
# <a name="sysparameter_type_usages-transact-sql"></a>sys.parameter_type_usages (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Devuelve una fila por cada parámetro que es de tipo definido por el usuario.  
  
> [!NOTE]  
>  Esta vista no devuelve filas para los parámetros de procedimientos numerados.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**object_id**|**int**|Identificador del objeto al que pertenece el parámetro.|  
|**parameter_id**|**int**|IDENTIFICADOR del parámetro. Es único en el objeto.|  
|**user_type_id**|**int**|Id. del tipo definido por el usuario.<br /><br /> Para devolver el nombre del tipo, únase a la vista de catálogo [Sys. Types](../../relational-databases/system-catalog-views/sys-types-transact-sql.md) en esta columna.|  
  
## <a name="permissions"></a>Permisos  
 Debe pertenecer al rol **public** . Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo de tipos escalares &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/scalar-types-catalog-views-transact-sql.md)   
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
