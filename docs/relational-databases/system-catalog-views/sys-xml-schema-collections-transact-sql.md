---
title: sys.xml_schema_collections (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.xml_schema_collections_TSQL
- sys.xml_schema_collections
- xml_schema_collections
- xml_schema_collections_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.xml_schema_collections catalog view
ms.assetid: f3f7f3dc-029f-4942-ab3c-75fa9814e40f
author: pmasl
ms.author: pelopes
ms.reviewer: mikeray
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 931eec7ff81ee34f5d686ff432a9f88c69874e96
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85754368"
---
# <a name="sysxml_schema_collections-transact-sql"></a>sys.xml_schema_collections (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Devuelve una fila por cada colección de esquemas XML. Una colección de esquemas XML es un conjunto con nombre de definiciones XSD. La colección de esquemas XML está incluida en un esquema relacional y se identifica por medio de un nombre [!INCLUDE[tsql](../../includes/tsql-md.md)] con ámbito de esquema. Las tuplas siguientes son únicas: xml_collection_id, schema_id y name.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|xml_collection_id|**int**|Identificador de la colección de esquemas XML. Es único en la base de datos.|  
|schema_id|**int**|Identificador del esquema relacional que contiene esta colección de esquemas XML.|  
|principal_id|**int**|Identificador del propietario individual si es diferente del propietario del esquema. De forma predeterminada, los objetos contenidos en el esquema pertenecen al propietario del esquema. No obstante, se puede especificar un propietario alternativo mediante la instrucción ALTER AUTHORIZATION.<br /><br /> NULL = Sin propietario individual alternativo|  
|name|**sysname**|Nombre de la colección de esquemas XML.|  
|create_date|**datetime**|Fecha en que se creó la colección de esquemas XML.|  
|modify_date|**datetime**|Fecha en que se modificó la colección de esquemas XML.|  
  
## <a name="permissions"></a>Permisos  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Esquemas XML &#40;las vistas de catálogo del sistema de tipos XML&#41; &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/xml-schemas-xml-type-system-catalog-views-transact-sql.md)   
 [Consultar las preguntas más frecuentes (P+F) del catálogo del sistema de SQL Server](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
