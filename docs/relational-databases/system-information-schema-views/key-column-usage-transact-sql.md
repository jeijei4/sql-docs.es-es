---
title: KEY_COLUMN_USAGE (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- KEY_COLUMN_USAGE_TSQL
- KEY_COLUMN_USAGE
dev_langs:
- TSQL
helpviewer_keywords:
- INFORMATION_SCHEMA.KEY_COLUMN_USAGE view
- KEY_COLUMN_USAGE view
ms.assetid: ec1e18c2-63a1-4d2b-ba9a-c13857403782
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: cca6fe4ea0cd6e81fb59dcae3b2f566015dbdf9b
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85775175"
---
# <a name="key_column_usage-transact-sql"></a>KEY_COLUMN_USAGE (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Contiene una fila por cada columna que está restringida como clave en la base de datos actual. Esta vista de esquema de información devuelve información acerca de los objetos para los que el usuario actual tiene permisos.  
  
 Para recuperar información de estas vistas, especifique el nombre completo de **INFORMATION_SCHEMA.** _view_name_.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**CONSTRAINT_CATALOG**|**nvarchar (** 128 **)**|Calificador de la restricción.|  
|**CONSTRAINT_SCHEMA**|**nvarchar (** 128 **)**|Nombre del esquema que contiene la restricción.<br /><br /> Importante no use vistas INFORMATION_SCHEMA para determinar el esquema de un objeto. <strong> \* \* \* \* </strong> INFORMATION_SCHEMA vistas solo representan un subconjunto de los metadatos de un objeto. La única manera confiable de encontrar el esquema de un objeto es consultar la vista de catálogo sys. Objects.|  
|**CONSTRAINT_NAME**|**nvarchar (** 128 **)**|Nombre de la restricción.|  
|**TABLE_CATALOG**|**nvarchar (** 128 **)**|Calificador de tabla.|  
|**TABLE_SCHEMA**|**nvarchar (** 128 **)**|Nombre de esquema que contiene la tabla.<br /><br /> Importante no use vistas INFORMATION_SCHEMA para determinar el esquema de un objeto. <strong> \* \* \* \* </strong> INFORMATION_SCHEMA vistas solo representan un subconjunto de los metadatos de un objeto. La única manera confiable de encontrar el esquema de un objeto es consultar la vista de catálogo sys. Objects.|  
|**TABLE_NAME**|**nvarchar (** 128 **)**|Nombre de la tabla.|  
|**COLUMN_NAME**|**nvarchar (** 128 **)**|Nombre de la columna.|  
|**ORDINAL_POSITION**|**int**|Posición ordinal de la columna.|  
  
## <a name="see-also"></a>Consulte también  
 [Vistas del sistema &#40;Transact-SQL&#41;](https://msdn.microsoft.com/library/35a6161d-7f43-4e00-bcd3-3091f2015e90)   
 [Vistas de esquema de información &#40;Transact-SQL&#41;](~/relational-databases/system-information-schema-views/system-information-schema-views-transact-sql.md)   
 [Sys. Columns &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-columns-transact-sql.md)   
 [Sys. Indexes &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-indexes-transact-sql.md)   
 [Sys. Objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md)   
 [Sys. foreign_keys &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-foreign-keys-transact-sql.md)   
 [Sys. key_constraints &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-key-constraints-transact-sql.md)  
  
  
