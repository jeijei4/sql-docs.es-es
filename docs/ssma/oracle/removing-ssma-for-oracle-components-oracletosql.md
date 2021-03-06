---
title: Quitar SSMA para los componentes de Oracle (OracleToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Uninstalling the Extension Pack
ms.assetid: 8b527a56-4e52-487a-9ac9-2320388e6d7d
author: Shamikg
ms.author: Shamikg
manager: shamikg
ms.openlocfilehash: 0434f88c46d14672c84f5f7939488a827b229e27
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68266558"
---
# <a name="removing-ssma--for-oracle-components-oracletosql"></a>Eliminación de componentes de SSMA para Oracle (OracleToSQL)
Cuando haya terminado de migrar las bases de datos de Oracle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]a, es posible que desee desinstalar los componentes de SSMA. Puede desinstalar los componentes de cliente en cualquier momento. Sin embargo, no debe desinstalar el paquete de extensiones [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de a menos que las bases de datos migradas dejen de usar funciones en el esquema de **ssma_oracle** de la base de datos **sysdb** .  
  
## <a name="uninstalling-the-ssma-for-oracle-client"></a>Desinstalar SSMA para el cliente de Oracle  
Puede desinstalar SSMA mediante **Agregar o quitar programas**.  
  
**Para desinstalar SSMA**  
  
1.  En el Panel de control, abra **Agregar o quitar programas**.  
  
2.  ** [!INCLUDE[msCoName](../../includes/msconame_md.md)] Seleccione [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Migration Assistant para Oracle**y, a continuación, haga clic en **quitar**.  
  
3.  Para confirmar que desea desinstalar SSMA, haga clic en **sí**.  
  
## <a name="uninstalling-the-extension-pack"></a>Desinstalación del paquete de extensiones  
Si está seguro de que las bases de datos migradas no usan objetos en el esquema **sysdb. ssma_oracle** , puede quitar el paquete de extensión mediante **Agregar o quitar programas**.  
  
**Para desinstalar el paquete de extensiones**  
  
1.  En el Panel de control, abra **Agregar o quitar programas**.  
  
2.  Seleccione **Microsoft SQL Server Migration Assistant para Oracle Extension Pack**y, a continuación, haga clic en **quitar**.  
  
3.  Para confirmar que desea desinstalar el paquete de extensión, haga clic en **sí**.  
  
4.  En la página instancias con scripts de base de datos de utilidades, seleccione una instancia y, a continuación, haga clic en **siguiente**.  
  
5.  En la página parámetros de conexión, seleccione el método de autenticación y, a continuación, haga clic en **siguiente**.  
  
    La autenticación de Windows utilizará las credenciales de Windows para intentar iniciar sesión en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]la instancia de. Si selecciona [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] autenticación, debe escribir un nombre de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] inicio de sesión y una contraseña.  
  
6.  En la página operación completada, haga clic en **Aceptar**.  
  
7.  En la página finalizar, haga clic en **salir**.  
  
Después de la desinstalación, puede confirmar que los objetos del esquema **sysdb. ssma_oracle** y, posiblemente, toda la base de datos de **sysdb** , se [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]han quitado mediante. Sin embargo, si utiliza otros productos de SSMA, también usarán la base de datos **sysdb** . Si la base de datos existe y está seguro de que ninguna otra base de datos hace referencia a objetos de esta base de datos, puede separar la base de datos.  
  
## <a name="see-also"></a>Consulte también  
[Instalación de SSMA para el cliente de Oracle &#40;OracleToSQL&#41;](../../ssma/oracle/installing-ssma-for-oracle-client-oracletosql.md)  
[Instalación de componentes de SSMA en SQL Server &#40;OracleToSQL&#41;](../../ssma/oracle/installing-ssma-components-on-sql-server-oracletosql.md)  
  
