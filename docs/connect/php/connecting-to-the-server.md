---
title: Conexión al servidor | Microsoft Docs
ms.custom: ''
ms.date: 03/26/2018
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: c251a239-e0bd-4f45-9207-b76651072dd0
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 669a80ce744306cd12379af134951bde7936798e
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80920264"
---
# <a name="connecting-to-the-server"></a>Conexión al servidor
[!INCLUDE[Driver_PHP_Download](../../includes/driver_php_download.md)]

En los temas de esta sección se describen las opciones y los procedimientos para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante los [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)].  

Los [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] pueden conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la autenticación de Windows o SQL Server. De forma predeterminada, los [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] intentan conectarse al servidor mediante la autenticación de Windows.  

## <a name="in-this-section"></a>En esta sección  

|Tema|Descripción|  
|---------|---------------|  
|[Conexión mediante la autenticación de Windows](../../connect/php/how-to-connect-using-windows-authentication.md)|Describe cómo establecer una conexión mediante la autenticación de Windows.|  
|[Conexión mediante la autenticación de SQL Server](../../connect/php/how-to-connect-using-sql-server-authentication.md)|Describe cómo establecer una conexión con autenticación de SQL Server.|  
|[Conexión con la autenticación de Azure Active Directory](../../connect/php/azure-active-directory.md)|Se describe cómo establecer el modo de autenticación y conectarse mediante identidades de Azure Active Directory.|  
|[Conexión a un puerto específico](../../connect/php/how-to-connect-on-a-specified-port.md)|Describe cómo conectarse al servidor en un puerto específico.|  
|[Agrupación de conexiones](../../connect/php/connection-pooling-microsoft-drivers-for-php-for-sql-server.md)|Proporciona información acerca de la agrupación de conexiones en el controlador.|  
|[Deshabilitar los conjuntos de resultados activos múltiples (MARS)](../../connect/php/how-to-disable-multiple-active-resultsets-mars.md)|Describe cómo deshabilitar la característica MARS al establecer una conexión.|  
|[Opciones de conexión](../../connect/php/connection-options.md)|Enumera las opciones que se permiten en la matriz asociativa que contiene atributos de conexión.|  
|[Compatibilidad con LocalDB](../../connect/php/php-driver-for-sql-server-support-for-localdb.md)|Describe la compatibilidad de los [!INCLUDE[ssDriverPHP](../../includes/ssdriverphp_md.md)] con la característica LocalDB, que se agregó en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].|  
|[Compatibilidad con alta disponibilidad y recuperación ante desastres](../../connect/php/php-driver-for-sql-server-support-for-high-availability-disaster-recovery.md)|Describe cómo se puede configurar una aplicación para aprovechar las características de alta disponibilidad con recuperación ante desastres que se han agregado en [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)].|  
|[Conexión a Microsoft Azure SQL Database](../../connect/php/connecting-to-microsoft-azure-sql-database.md)|Trata sobre cómo conectar a Azure SQL Database.|  
|[Resistencia de la conexión](../../connect/php/connection-resiliency.md)|Se describe la característica de resistencia de conexión que restablece las conexiones interrumpidas.|  

## <a name="see-also"></a>Consulte también  
[Guía de programación para los controladores de Microsoft para PHP para SQL Server](../../connect/php/programming-guide-for-php-sql-driver.md)

[Aplicación de ejemplo &#40;controlador SQLSRV&#41;](../../connect/php/example-application-sqlsrv-driver.md)  
