---
title: Sys. server_triggers (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- server_triggers
- sys.server_triggers_TSQL
- server_triggers_TSQL
- sys.server_triggers
dev_langs:
- TSQL
helpviewer_keywords:
- sys.server_triggers catalog view
ms.assetid: 25926ff4-9271-45bf-bc32-d5d3344bd47a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 7ce21b1c997a1530212f9a0317632f665c9ef503
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85884467"
---
# <a name="sysserver_triggers-transact-sql"></a>sys.server_triggers (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contiene el conjunto de todos los desencadenadores DDL de servidor cuyo object_type es TR o TA. En el caso de los desencadenadores CLR, el ensamblado se debe cargar en la base de datos **maestra** . Todos los nombres de desencadenadores DDL de nivel de servidor se encuentran en un único ámbito global.  
  
|Nombre de columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Nombre del desencadenador.|  
|**object_id**|**int**|Id. del objeto.|  
|**parent_class**|**tinyint**|Clase del elemento primario. Siempre es:<br /><br /> 100 = Servidor|  
|**parent_class_desc**|**nvarchar(60)**|Descripción de la clase de elemento primario. Siempre es:<br /><br /> Servidor.|  
|**parent_id**|**int**|Siempre es 0 para los desencadenadores de SERVER.|  
|**type**|**char(2)**|Tipo de objeto:<br /><br /> TA = Desencadenador de ensamblado (CLR)<br /><br /> TR = Desencadenador SQL|  
|**type_desc**|**nvarchar(60)**|Descripción de la clase del tipo de objeto.<br /><br /> CLR_TRIGGER<br /><br /> SQL_TRIGGER|  
|**create_date**|**datetime**|Fecha de creación del desencadenador.|  
|**modify_date**|**datetime**|Fecha en que se modificó el desencadenador por última vez mediante una instrucción ALTER.|  
|**is_ms_shipped**|**bit**|Desencadenador creado en nombre del usuario por un componente interno de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|**is_disabled**|**bit**|1 = El desencadenador está deshabilitado.|  
  
## <a name="permissions"></a>Permisos  
 [!INCLUDE[ssCatViewPerm](../../includes/sscatviewperm-md.md)] Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)  
  
  
