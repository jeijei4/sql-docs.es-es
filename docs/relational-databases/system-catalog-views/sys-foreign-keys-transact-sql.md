---
title: Sys. foreign_keys (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- foreign_keys
- sys.foreign_keys
- sys.foreign_keys_TSQL
- foreign_keys_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.foreign_keys catalog view
ms.assetid: e960df1a-13fc-43ee-ba91-34c1b719ac2c
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 451addd3be6c6da4094eab54c962e23f95134de6
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86002318"
---
# <a name="sysforeign_keys-transact-sql"></a>sys.foreign_keys (Transact-SQL)
[!INCLUDE [sql-asdb-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Contiene una fila por cada objeto que es una restricción FOREIGN KEY, con **Sys. Object. Type** = F.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**\<Columns inherited from sys.objects>**||Para obtener una lista de las columnas que hereda esta vista, vea [Sys. objects &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-objects-transact-sql.md).|  
|**referenced_object_id**|**int**|Id. del objeto al que se hace referencia.|  
|**key_index_id**|**int**|Id. del índice de clave dentro del objeto al que se hace referencia.|  
|**is_disabled**|**bit**|La restricción FOREIGN KEY está deshabilitada.|  
|**is_not_for_replication**|**bit**|La restricción FOREIGN KEY se creó con la opción NOT FOR REPLICATION.|  
|**is_not_trusted**|**bit**|El sistema no ha comprobado la restricción FOREIGN KEY.|  
|**delete_referential_action**|**tinyint**|Acción referencial que se declaró para FOREIGN KEY cuando se produce una eliminación.<br /><br /> 0 = Sin acción<br /><br /> 1 = Cascada<br /><br /> 2 = Establecer como NULL<br /><br /> 3 = Establecer valor predeterminado|  
|**delete_referential_action_desc**|**nvarchar(60)**|Descripción de la acción referencial que se declaró para FOREIGN KEY cuando se produce una eliminación:<br /><br /> NO_ACTION<br /><br /> CASCADE<br /><br /> SET_NULL<br /><br /> SET_DEFAULT|  
|**update_referential_action**|**tinyint**|Acción referencial que se declaró para FOREIGN KEY cuando se produce una actualización.<br /><br /> 0 = Sin acción<br /><br /> 1 = Cascada<br /><br /> 2 = Establecer como NULL<br /><br /> 3 = Establecer valor predeterminado|  
|**update_referential_action_desc**|**nvarchar(60)**|Descripción de la acción referencial que se declaró para FOREIGN KEY cuando se produce una actualización:<br /><br /> NO_ACTION<br /><br /> CASCADE<br /><br /> SET_NULL<br /><br /> SET_DEFAULT|  
|**is_system_named**|**bit**|1 = El sistema generó el nombre.<br /><br /> 0 = El usuario proporcionó el nombre.|  
  
## <a name="permissions"></a>Permisos  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Vistas de catálogo de objetos &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/object-catalog-views-transact-sql.md)   
 [Consultar las preguntas más frecuentes (P+F) del catálogo del sistema de SQL Server](../../relational-databases/system-catalog-views/querying-the-sql-server-system-catalog-faq.md)  
  
  
