---
title: Trabajo con una conexión mediante JDBC
description: Ejemplos de las diferentes formas de conectarse a una base de datos de SQL Server con la clase SQLServerConnection de Microsoft JDBC Driver para SQL Server.
ms.custom: ''
ms.date: 08/12/2019
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: cf8ee392-8a10-40a3-ae32-31c7b1efdd04
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1253c2ec5822fef83d6da71279752202f2d93ebd
ms.sourcegitcommit: 8ffc23126609b1cbe2f6820f9a823c5850205372
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81631955"
---
# <a name="working-with-a-connection"></a>Trabajo con una conexión

[!INCLUDE[Driver_JDBC_Download](../../includes/driver_jdbc_download.md)]

En las siguientes secciones se proporcionan ejemplos de las diferentes formas de conectar con una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mediante la clase [SQLServerConnection](reference/sqlserverconnection-class.md) del [!INCLUDE[jdbcNoVersion](../../includes/jdbcnoversion_md.md)].

> [!NOTE]  
> Si tiene problemas para conectarse a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] con el controlador JDBC, vea [Solución de problemas de conectividad](troubleshooting-connectivity.md), donde encontrará sugerencias sobre cómo corregirlos.

## <a name="creating-a-connection-by-using-the-drivermanager-class"></a>Crear una conexión con la clase DriverManager

El enfoque más sencillo para crear una conexión a una base de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] es cargar el controlador JDBC y llamar al método getConnection de la clase DriverManager, como en el siguiente ejemplo:

```java
Class.forName("com.microsoft.sqlserver.jdbc.SQLServerDriver");  
String connectionUrl = "jdbc:sqlserver://localhost;database=AdventureWorks;integratedSecurity=true;"  
Connection con = DriverManager.getConnection(connectionUrl);  
```

Este técnica creará una conexión a una base de datos usando el primer controlador disponible de la lista de controladores que se pueda conectar correctamente con la URL dada.

> [!NOTE]  
> Al usar la biblioteca de clases sqljdbc4.jar, las aplicaciones no necesitan registrar o cargar explícitamente el controlador usando el método Class.forName. Cuando se llama al método getConnection de la clase DriverManager, se busca un controlador apropiado en el conjunto de controladores JDBC registrados. Para obtener más información, vea Usar el controlador JDBC

## <a name="creating-a-connection-by-using-the-sqlserverdriver-class"></a>Crear una conexión con la clase SQLServerDriver

Si tiene que especificar un controlador en particular de la lista de controladores para DriverManager, puede crear una conexión a una base de datos con el método [connect](reference/connect-method-sqlserverdriver.md) de la clase [SQLServerDriver](reference/sqlserverdriver-class.md), como en el siguiente ejemplo:

```java
Driver d = (Driver) Class.forName("com.microsoft.sqlserver.jdbc.SQLServerDriver").newInstance();  
String connectionUrl = "jdbc:sqlserver://localhost;database=AdventureWorks;integratedSecurity=true;"  
Connection con = d.connect(connectionUrl, new Properties());  
```

## <a name="creating-a-connection-by-using-the-sqlserverdatasource-class"></a>Crear una conexión con la clase SQLServerDataSource

Si tiene que crear una conexión mediante la clase [SQLServerDataSource](reference/sqlserverdatasource-class.md), puede usar diversos métodos de establecimiento de la clase antes de llamar al método [getConnection](reference/getconnection-method.md), como en el siguiente ejemplo:

```java
SQLServerDataSource ds = new SQLServerDataSource();  
ds.setUser("MyUserName");  
ds.setPassword("*****");  
ds.setServerName("localhost");  
ds.setPortNumber(1433);
ds.setDatabaseName("AdventureWorks");  
Connection con = ds.getConnection();  
```

## <a name="creating-a-connection-that-targets-a-specific-data-source"></a>Creación de una conexión cuyo destino es un origen de datos específico

Si tiene que hacer una conexión a una base de datos cuyo destino es un origen de datos específico, hay varios enfoques posibles. Cada enfoque depende de las propiedades que configure mediante la URL de conexión.

Para conectarse a la instancia predeterminada de un servidor remoto, use el ejemplo siguiente:

```java
String url = "jdbc:sqlserver://MyServer;integratedSecurity=true;"
```

Para conectarse a un puerto específico de un servidor, use el ejemplo siguiente:

```java
String url = "jdbc:sqlserver://MyServer:1533;integratedSecurity=true;"
```

Para conectarse a una instancia con nombre de un servidor, use el ejemplo siguiente:

```java
String url = "jdbc:sqlserver://209.196.43.19;instanceName=INSTANCE1;integratedSecurity=true;"
```

Para conectarse a una base de datos específica de un servidor, use el ejemplo siguiente:

```java
String url = "jdbc:sqlserver://172.31.255.255;database=AdventureWorks;integratedSecurity=true;"
```

Para ver más ejemplos de direcciones URL de conexión, consulte [Creación de la dirección URL de conexión](building-the-connection-url.md).

## <a name="creating-a-connection-with-a-custom-login-timeout"></a>Creación de una conexión con un tiempo de espera de inicio de sesión personalizado

Si tiene que ajustarse a la carga del servidor o el tráfico de red, puede crear una conexión que tenga un valor de tiempo de espera de inicio de sesión específico en segundos, como en el siguiente ejemplo:

```java
String url = "jdbc:sqlserver://MyServer;loginTimeout=90;integratedSecurity=true;"
```

## <a name="create-a-connection-with-application-level-identity"></a>Crear una conexión con identidad de nivel de aplicación

Si tiene que usar perfiles y registros, tendrá que identificar la conexión como originaria de una aplicación específica, como en el siguiente ejemplo:

```java
String url = "jdbc:sqlserver://MyServer;applicationName=MYAPP.EXE;integratedSecurity=true;"
```

## <a name="closing-a-connection"></a>Cerrar una conexión

Puede cerrar explícitamente una conexión a una base de datos llamando al método [close](reference/close-method-sqlserverconnection.md) de la clase SQLServerConnection, como en el siguiente ejemplo:

```java
con.close();
```

De esta forma se liberarán los recursos de la base de datos que está usando el objeto SQLServerConnection, o devolver la conexión al grupo de conexiones en situaciones de agrupamiento.

> [!NOTE]  
> Si llama al método close, también se revertirán todas las transacciones pendientes.

## <a name="see-also"></a>Consulte también

[Conexión a SQL Server con el controlador JDBC](connecting-to-sql-server-with-the-jdbc-driver.md)
