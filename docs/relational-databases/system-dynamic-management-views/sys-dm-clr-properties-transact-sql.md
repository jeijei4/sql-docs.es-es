---
title: Sys. dm_clr_properties (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/15/2017
ms.prod: sql
ms.prod_service: database-engine, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.dm_clr_properties
- sys.dm_clr_properties_TSQL
- dm_clr_properties_TSQL
- dm_clr_properties
dev_langs:
- TSQL
helpviewer_keywords:
- sys.dm_clr_properties dynamic management view
ms.assetid: 220d062f-d117-46e7-a448-06fe48db8163
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: a61484691e4e5a2ea5ca4c08b6382b501f1cc851
ms.sourcegitcommit: 8515bb2021cfbc7791318527b8554654203db4ad
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "86091884"
---
# <a name="sysdm_clr_properties-transact-sql"></a>sys.dm_clr_properties (Transact-SQL)
[!INCLUDE [sql-asdbmi-pdw](../../includes/applies-to-version/sql-asdbmi-pdw.md)]

  Devuelve una fila para cada propiedad relacionada con la integración de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y Common Language Runtime (CLR), incluidos la versión y el estado del entorno CLR hospedado. El CLR hospedado se inicializa mediante la ejecución de las instrucciones [Create Assembly](../../t-sql/statements/create-assembly-transact-sql.md), [ALTER ASSEMBLY](../../t-sql/statements/alter-assembly-transact-sql.md)o [Drop Assembly](../../t-sql/statements/drop-assembly-transact-sql.md) , o mediante la ejecución de cualquier rutina, tipo o desencadenador de CLR. La vista **Sys. dm_clr_properties** no especifica si se ha habilitado la ejecución de código CLR de usuario en el servidor. La ejecución del código CLR de usuario se habilita mediante el [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md) procedimiento almacenado con la opción [clr enabled](../../database-engine/configure-windows/clr-enabled-server-configuration-option.md) establecida en 1.  
  
 La vista **Sys. dm_clr_properties** contiene las columnas **nombre** y **valor** . Cada una de las filas de esta vista proporciona información detallada acerca de una propiedad del entorno CLR hospedado. Utilice esta vista para recopilar información acerca del entorno CLR hospedado, como el directorio de instalación de CLR, la versión de CLR y el estado actual del entorno CLR hospedado. Esta vista puede ayudarle a determinar si el código de integración CLR no funciona debido a problemas con la instalación de CLR en el equipo servidor.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**name**|**nvarchar(128)**|El nombre de la propiedad.|  
|**value**|**nvarchar(128)**|Valor de la propiedad.|  
  
## <a name="properties"></a>Propiedades  
 La propiedad **Directory** indica el directorio en el que se instaló el .NET Framework en el servidor. Podría haber varias instalaciones de .NET Framework en el equipo servidor y el valor de esta propiedad identificaría la instalación que [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estaría utilizando.  
  
 La propiedad **version** indica la versión del .NET Framework y el CLR hospedado en el servidor.  
  
 La vista administrada dinámica **Sys. dm_clr_properties** puede devolver seis valores diferentes para la propiedad **State** , que refleja el estado del [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CLR hospedado. Son las siguientes:  
  
-   Mscoree is not loaded.  
  
-   Mscoree is loaded.  
  
-   Locked CLR version with mscoree.  
  
-   CLR is initialized.  
  
-   CLR initialization permanently failed.  
  
-   CLR is stopped.  
  
 **No se carga la Mscoree** y los Estados de **Mscoree se cargan** , lo que muestra la progresión de la inicialización de CLR hospedada al iniciar el servidor y, por tanto, no se verán.  
  
 La **versión de CLR bloqueada con** el estado Mscoree puede aparecer en la que no se está usando el CLR hospedado y, por lo tanto, aún no se ha inicializado. El CLR hospedado se inicializa la primera vez que se ejecuta una instrucción DDL (como [Create assembly &#40;Transact-SQL&#41;](../../t-sql/statements/create-assembly-transact-sql.md)) o un objeto de base de datos administrado.  
  
 El estado **inicializado de CLR** indica que el CLR hospedado se ha inicializado correctamente. Tenga en cuenta que esto no indica si se ha habilitado la ejecución de código CLR de usuario. Si la ejecución del código CLR de usuario se habilita por primera vez y después se deshabilita mediante el [!INCLUDE[tsql](../../includes/tsql-md.md)] [sp_configure](../../relational-databases/system-stored-procedures/sp-configure-transact-sql.md) procedimiento almacenado, el valor de Estado seguirá siendo **CLR inicializado**.  
  
 El estado de **error de inicialización de CLR** indica que se produjo un error de inicialización de CLR hospedado. Una causa probable es la presión de memoria, o también podría ser el resultado de un error del protocolo de enlace de hospedaje entre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y el entorno CLR. En este caso se producirá el mensaje de error 6512 o 6513.  
  
 El **estado detenida de CLR** solo aparece cuando [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] se está cerrando.  
  
## <a name="remarks"></a>Observaciones  
 Las propiedades y los valores de esta vista pueden cambiar en una versión futura de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] debido a las mejoras de la funcionalidad de integración de CLR.  
  
## <a name="permissions"></a>Permisos  
  
En [!INCLUDE[ssNoVersion_md](../../includes/ssnoversion-md.md)] , requiere el `VIEW SERVER STATE` permiso.   
En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles Premium, requiere el `VIEW DATABASE STATE` permiso en la base de datos. En [!INCLUDE[ssSDS_md](../../includes/sssds-md.md)] los niveles estándar y básico, requiere el **Administrador del servidor** o una cuenta de **Administrador de Azure Active Directory** .   

## <a name="examples"></a>Ejemplos  
 En el siguiente ejemplo se recupera información acerca del entorno CLR hospedado:  
  
```  
SELECT name, value   
FROM sys.dm_clr_properties;  
```  
  
## <a name="see-also"></a>Consulte también  
 [Funciones y vistas de administración dinámica &#40;Transact-SQL&#41;](~/relational-databases/system-dynamic-management-views/system-dynamic-management-views.md)   
 [Vistas de administración dinámica relacionadas con Common Language Runtime &#40;Transact-SQL&#41;](../../relational-databases/system-dynamic-management-views/common-language-runtime-related-dynamic-management-views-transact-sql.md)  
  
  
