---
title: Sys. dm_os_windows_info (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_os_windows_info
- dm_os_windows_info_TSQL
- sys.dm_os_windows_info
- sys.dm_os_windows_info_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_windows_info dynamic management view
ms.assetid: adc81283-fdc2-46c0-bb48-abe82bbf2459
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 26cf5253d95a1c716c3c2ecfc1be0d9f99897832
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85898719"
---
# <a name="sysdm_os_windows_info-transact-sql"></a>sys.dm_os_windows_info (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Devuelve una fila con información sobre la versión del sistema operativo Windows.  
  
  Solo se aplica a SQL Server que se ejecutan en Windows. Para ver una informatity similar para SQL Server que se ejecuta en un host que no es de Windows, como Linux, use [Sys. dm_os_host_info &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/sys-dm-os-host-info-transact-sql.md). 
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**windows_release**|**nvarchar(256)**|En Windows, devuelve el número de versión. Para obtener una lista de valores y descripciones, vea [versión del sistema operativo (Windows)](/windows/desktop/SysInfo/operating-system-version). No puede ser NULL.|  
|**windows_service_pack_level**|**nvarchar(256)**| En Windows, devuelve el número de Service Pack. No puede ser NULL. |  
|**windows_sku**|**int**|En Windows, devuelve el identificador de la referencia de almacén (SKU) de Windows. Para obtener una lista de identificadores y descripciones de SKU, consulte [función GetProductInfo](https://msdn.microsoft.com/library/ms724358.aspx). Acepta valores NULL. |  
|**os_language_version**|**int**| En Windows, devuelve el identificador de configuración regional (LCID) de Windows del sistema operativo. Para obtener una lista de valores y descripciones de LCID, consulte ID. de [configuración regional asignados por Microsoft](https://go.microsoft.com/fwlink/?LinkId=208080). No puede ser NULL.|  
  
  
## <a name="permissions"></a>Permisos  
De forma predeterminada, se concede el permiso SELECT en sys. dm_os_windows_info al rol Public. Si se revoca, requiere el permiso VIEW SERVER STATE en el servidor.  

## <a name="limitations-and-restrictions"></a>Limitaciones y restricciones
Para ver la informaton para SQL que se ejecuta en un host que no es de Windows, como Linux, use [Sys. dm_os_host_info &#40;&#41;de Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-os-host-info-transact-sql.md). 
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se devuelven todas las columnas de la vista **Sys. dm_os_windows_info** .  
  
```  
SELECT windows_release, windows_service_pack_level, windows_sku, os_language_version  
FROM sys.dm_os_windows_info;  
```  
  
 A continuación se muestra un conjunto de resultados de ejemplo.  
  
 `windows_release  windows_service_pack_level   windows_sku   os_language_version`  
  
 `---------------  ---------------------------  ------------  -------------------`  
  
 `6.0              Service Pack 2                4            1033`  
  
## <a name="see-also"></a>Consulte también  
 [Sys. dm_os_sys_info &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sys-dm-os-sys-info-transact-sql.md)   
 [sys.dm_os_host_info](../../relational-databases/system-dynamic-management-views/sys-dm-os-host-info-transact-sql.md)  
  
  

