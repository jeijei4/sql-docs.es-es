---
title: sys.sysfulltextcatalogs (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysfulltextcatalogs
- sys.sysfulltextcatalogs_TSQL
- sysfulltextcatalogs_TSQL
- sys.sysfulltextcatalogs
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sysfulltextcatalogs compatibility view
- sysfulltextcatalogs system table
ms.assetid: 18ac6ad5-01e8-428f-8422-a9ca29626977
author: rothja
ms.author: jroth
monikerRange: '>=aps-pdw-2016||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 1966f1bfa62fb85d99cee1db6900ad78e6a89b24
ms.sourcegitcommit: 8515bb2021cfbc7791318527b8554654203db4ad
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "86091797"
---
# <a name="syssysfulltextcatalogs-transact-sql"></a>sys.sysfulltextcatalogs (Transact-SQL)
[!INCLUDE [sql-asdbmi-pdw](../../includes/applies-to-version/sql-asdbmi-pdw.md)]

  Contiene información sobre los catálogos de texto completo.  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssnoteCompView](../../includes/ssnotecompview-md.md)]  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**ftcatid**|**smallint**|Identificador del catálogo de texto completo.|  
|**name**|**sysname**|Nombre del catálogo de texto completo especificado por el usuario.|  
|**status**|**smallint**|[!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]|  
|**path**|**nvarchar(260)**|Ruta raíz especificada por el usuario.<br /><br /> NULL = Ruta no especificada. Se utiliza la ruta predeterminada (instalación).|  
  
## <a name="see-also"></a>Consulte también  
 [Asignar tablas del sistema a vistas del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-tables/mapping-system-tables-to-system-views-transact-sql.md)   
 [Vistas de compatibilidad &#40;Transact-SQL&#41;](~/relational-databases/system-compatibility-views/system-compatibility-views-transact-sql.md)  
  
  
