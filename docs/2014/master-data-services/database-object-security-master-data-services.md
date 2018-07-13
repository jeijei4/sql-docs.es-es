---
title: Seguridad de objetos de base de datos (Master Data Services) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- database [Master Data Services], object security
- security [Master Data Services], database objects
ms.assetid: dd5ba503-7607-45d9-ad0d-909faaade179
caps.latest.revision: 8
author: leolimsft
ms.author: lle
manager: craigg
ms.openlocfilehash: 5195df44c591f4c605cfd33aa6bb9934c7d54908
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37163506"
---
# <a name="database-object-security-master-data-services"></a>Seguridad de objetos de base de datos (Master Data Services)
  En la base de datos [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] , los datos están almacenados en varias tablas de base de datos y se ven en las vistas. La información que pueda haber protegido en la aplicación web [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] está visible para los usuarios con acceso a la base de datos [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] .  
  
 En concreto, la información del sueldo de los empleados podría estar contenida en un modelo Empleado, o la información financiera de la compañía podría estar en un modelo Cuenta. Puede denegar el acceso a un usuario a estos modelos en la interfaz de usuario de [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] , pero los usuarios con acceso a la base de datos pueden ver estos datos.  
  
 Puede conceder permisos a los objetos de base de datos para hacer que datos concretos estén disponibles para los usuarios. Para obtener más información sobre cómo conceder permisos, consulte [GRANT &#40;permisos de objeto de Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql). Para obtener más información acerca de cómo proteger un servidor SQL Server, vea [Securing SQL Server](../relational-databases/security/securing-sql-server.md).  
  
 Las siguientes tareas necesitan acceso a la base de datos de [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] :  
  
-   [Almacenar datos de forma provisional](#Staging)  
  
-   [Validar datos según las reglas de negocios](#rules)  
  
-   [Eliminar versiones](#Versions)  
  
-   [Aplicación inmediata de permisos de los miembros de la jerarquía](#Hierarchy)  
  
-   [Cambio de la cuenta de administrador del sistema](#SysAdmin)  
  
-   [Configuración del sistema](#SysSettings)  
  
##  <a name="Staging"></a> Almacenar datos de forma provisional  
 En la tabla siguiente, cada elemento protegible tiene "name" como parte del nombre. Indica el nombre de la tabla de ensayo que se especificó cuando se creó una entidad. Para obtener más información, consulte [importación de datos &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md)  
  
|Acción|Elementos protegibles|Permisos|  
|------------|----------------|-----------------|  
|Cargar miembros hoja y sus atributos en la tabla de ensayo.|stg.name_Leaf|Obligatorio: INSERT<br /><br /> Opcional: SELECT y UPDATE|  
|Cargar datos de la tabla de ensayo Leaf en las tablas adecuadas de la base de datos de MDS.|stg.udp_name_Leaf|Ejecute|  
|Cargar miembros consolidados y sus atributos en la tabla de ensayo.|stg.name_Consolidated|Obligatorio: INSERT<br /><br /> Opcional: SELECT y UPDATE|  
|Cargar los datos de la tabla de ensayo Consolidated en las tablas adecuadas de la base de datos de MDS.|stg.udp_name_Consolidated|Ejecute|  
|Cargar las relaciones de los miembros hoja y consolidados entre sí en una jerarquía explícita en la tabla de ensayo.|stg.name_Relationship|Obligatorio: INSERT<br /><br /> Opcional: SELECT y UPDATE|  
|Cargar los datos de la tabla de ensayo Relationship en las tablas adecuadas de la base de datos de MDS.|stg.udp_name_Relationship|Ejecute|  
|Ver los errores producidos cuando se insertaban datos de las tablas de ensayo en tablas de la base de datos de MDS.|stg.udp_name_Relationship|SELECT|  
  
 Para más información, vea [Importación de datos &#40;Master Data Services&#41;](overview-importing-data-from-tables-master-data-services.md).  
  
##  <a name="rules"></a> Validar datos según las reglas de negocios  
  
|Acción|Elemento protegible|Permisos|  
|------------|---------------|-----------------|  
|Validar una versión de datos según las reglas de negocios|mdm.udpValidateModel|Ejecute|  
  
 Para obtener más información, consulte [Procedimiento almacenado de validación &#40;Master Data Services&#41;](../../2014/master-data-services/validation-stored-procedure-master-data-services.md).  
  
##  <a name="Versions"></a> Eliminar versiones  
  
|Acción|Elementos protegibles|Permisos|  
|------------|----------------|-----------------|  
|Determinar el identificador de la versión que desea eliminar|mdm.viw_SYSTEM_SCHEMA_VERSION|SELECT|  
|Eliminar una versión de un modelo|mdm.udpVersionDelete|Ejecute|  
  
 Para obtener más información, consulte [Eliminar una versión &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-version-master-data-services.md).  
  
##  <a name="Hierarchy"></a> Aplicación inmediata de permisos de los miembros de la jerarquía  
  
|Acción|Elementos protegibles|Permisos|  
|------------|----------------|-----------------|  
|Aplicar los permisos de los miembros inmediatamente|mdm.udpSecurityMemberProcessRebuildModel|Ejecute|  
  
 Para obtener más información, consulte [Aplicar inmediatamente los permisos de los miembros &#40;Master Data Services&#41;](../../2014/master-data-services/immediately-apply-member-permissions-master-data-services.md).  
  
##  <a name="SysAdmin"></a> Cambio de la cuenta de administrador del sistema  
  
|Acción|Elementos protegibles|Permisos|  
|------------|----------------|-----------------|  
|Determinar el SID del nuevo administrador|mdm.tblUser|SELECT|  
|Cambiar la cuenta del administrador del sistema|mdm.udpSecuritySetAdministrator|Ejecute|  
  
 Para obtener más información, consulte [cambiar la cuenta de administrador del sistema &#40;Master Data Services&#41;](../../2014/master-data-services/change-the-system-administrator-account-master-data-services.md).  
  
##  <a name="SysSettings"></a> Configuración del sistema  
 Hay opciones del sistema que puede configurar para controlar el comportamiento en [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]. Puede ajustar estos valores en [!INCLUDE[ssMDScfgmgr](../includes/ssmdscfgmgr-md.md)] o, si tiene el acceso ACTUALIZAR, puede ajustarlos directamente en la tabla de base de datos mdm.tblSystemSetting. Para obtener más información, vea [Configuración del sistema &#40;Master Data Services&#41;](../../2014/master-data-services/system-settings-master-data-services.md).  
  
## <a name="see-also"></a>Vea también  
 [Seguridad &#40;Master Data Services&#41;](../../2014/master-data-services/security-master-data-services.md)  
  
  