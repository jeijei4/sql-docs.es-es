---
title: Sys. dm_os_stacks (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/13/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- dm_os_stacks
- dm_os_stacks_TSQL
- sys.dm_os_stacks
- sys.dm_os_stacks_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_os_stacks dynamic management view
ms.assetid: a69b06c4-28f0-4535-8fa1-9f132db4d916
author: CarlRabeler
ms.author: carlrab
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 869ebff08a3bb20ea531f3a1bdcdf59eafdcdceb
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85718756"
---
# <a name="sysdm_os_stacks-transact-sql"></a>sys.dm_os_stacks (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usa esta vista de administración dinámica internamente para hacer lo siguiente:  
  
-   Realizar el seguimiento de datos de depuración como asignaciones pendientes.  
  
-   Suponer o validar la lógica que usan los componentes de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en sitios donde el componente supone que se ha realizado una determinada llamada.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**stack_address**|**varbinary(8**|Dirección única para esta asignación de pilas. No admite valores NULL.|  
|**frame_index**|**int**|Cada línea representa una llamada de función que, cuando se ordena en orden ascendente por índice de marco para un **stack_address**determinado, devuelve la pila de llamadas completa. No admite valores NULL.|  
|**frame_address**|**varbinary(8**|Dirección de la llamada a función. No admite valores NULL.|  
  
## <a name="remarks"></a>Comentarios  
 **Sys. dm_os_stacks** requiere que los símbolos del servidor y otros componentes estén presentes en el servidor para mostrar la información correctamente.  
  
## <a name="permissions"></a>Permisos

En [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] , requiere el `VIEW SERVER STATE` permiso.   
En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles Premium, requiere el `VIEW DATABASE STATE` permiso en la base de datos. En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles estándar y básico, requiere el **Administrador del servidor** o una cuenta de **Administrador de Azure Active Directory** .   


## <a name="see-also"></a>Consulte también  
  [SQL Server vistas de administración dinámica relacionadas con el sistema operativo &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/sql-server-operating-system-related-dynamic-management-views-transact-sql.md)  
  
  
