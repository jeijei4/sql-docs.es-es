---
title: Llamar al tiempo de ejecución de Java
titleSuffix: SQL Server Language Extensions
description: Obtenga información sobre cómo llamar clases de Java desde procedimientos almacenados de SQL Server mediante las extensiones de lenguaje de SQL Server.
author: dphansen
ms.author: davidph
ms.date: 11/05/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: language-extensions
monikerRange: '>=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: bdff924b63b11eda850378987498e8601367d3fe
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2020
ms.locfileid: "73658895"
---
# <a name="how-to-call-the-java-runtime-in-sql-server-language-extensions"></a>Procedimiento para llamar al tiempo de ejecución de Java en las extensiones de lenguaje de SQL Server
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

Las [extensiones del lenguaje de SQL Server](../language-extensions-overview.md) usan el procedimiento almacenado del sistema [sp_execute_external_script](https://docs.microsoft.com/sql/relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql) como interfaz para llamar al tiempo de ejecución de Java. 

En este artículo de procedimientos se explican los detalles de implementación de las clases y los métodos de Java que se ejecutan en SQL Server.

## <a name="where-to-place-java-classes"></a>Dónde se deben colocar las clases de Java

Hay dos métodos para llamar a las clases de Java en SQL Server:

1. Coloque archivos **.class** o **.jar** en la [ruta de clase de Java](#classpath). 

2. Cargue clases compiladas en un archivo **.jar** y otras dependencias en la base de datos mediante el DDL de [biblioteca externa](#external-library). 

> [!NOTE]
> Como recomendación general, use archivos **.jar** en vez de archivos **.class** individuales. Se trata de una práctica común en Java que facilitará la experiencia global. Consulte también [Cómo crear un archivo jar a partir de archivos de clase](create-a-java-jar-file-from-class-files.md).

<a name="classpath"></a>

## <a name="use-classpath"></a>Usar Classpath

### <a name="basic-principles"></a>Principios básicos

A continuación se muestran algunos principios básicos a la hora de ejecutar Java en SQL Server.

* Debe haber clases de Java personalizadas compiladas en los archivos **.class** o **.jar** de la ruta de clase de Java. El [parámetro CLASSPATH](#set-classpath) proporciona la ruta de acceso a los archivos de Java compilados. 

* El método Java al que se está llamando se debe proporcionar en el parámetro **script** del procedimiento almacenado.

* Si la clase pertenece a un paquete, se debe proporcionar **packageName**.

* **params** sirve para pasar parámetros a una clase de Java. No se admiten las llamadas a un método que requiere argumentos. Por lo tanto, los parámetros son la única forma de pasar valores de argumento al método. 

> [!NOTE]
> Esta nota modifica las operaciones admitidas y no admitidas que son específicas de Java en SQL Server 2019, versión candidata para lanzamiento 1.
> * En el procedimiento almacenado se admiten los parámetros de entrada, pero no se admiten los parámetros de salida.

### <a name="call-java-class"></a>Llamar a una clase de Java

El procedimiento almacenado del sistema [sp_execute_external_script](https://docs.microsoft.com/sql/relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql) es la interfaz que se usa para llamar al tiempo de ejecución de Java. En el ejemplo siguiente se muestra un `sp_execute_external_script` que usa la extensión de Java, así como parámetros para especificar la ruta de acceso, el script y el código personalizado.

> [!NOTE]
> Tenga en cuenta que no es necesario definir el método al que se va a llamar. De forma predeterminada, se llama a un método denominado **execute**. Esto significa que debe seguir el [SDK de extensibilidad para Java en SQL Server](extensibility-sdk-java-sql-server.md) e implementar un método execute en la clase Java.

```sql
DECLARE @param1 int
SET @param1 = 3

EXEC sp_execute_external_script
  @language = N'Java'
, @script = N'<packageName>.<ClassName>'
, @input_data_1 = N'<Input Query>'
, @param1 = @param1
```

<a name="set-classpath"></a>

### <a name="set-classpath"></a>Establecer CLASSPATH

Una vez compilada la clase o clases Java y creado un archivo jar en la ruta de clase de Java, tiene dos opciones para proporcionar la ruta de clase a la extensión Java de SQL Server:

1. Usar bibliotecas externas

    La opción más sencilla consiste en hacer que SQL Server busque automáticamente las clases creando bibliotecas externas y apuntando la biblioteca hacia un archivo jar. [Usar bibliotecas externas para Java](#external-library)

2. Registrar una variable de entorno del sistema

    Puede crear una variable de entorno del sistema y proporcionar las rutas de acceso al archivo jar que contiene las clases. Cree una variable de entorno del sistema denominada **CLASSPATH**.

<a name="external-library"></a>

## <a name="use-external-library"></a>Usar una biblioteca externa

En SQL Server 2019, versión candidata para lanzamiento 1, puede usar bibliotecas externas para el lenguaje Java en Windows y Linux. Puede compilar las clases en un archivo .jar y cargarlo junto con otras dependencias en la base de datos mediante el DDL [CREATE EXTERNAL LIBRARY](https://docs.microsoft.com/sql/t-sql/statements/create-external-library-transact-sql).

Ejemplo de cómo cargar un archivo .jar con la biblioteca externa:

```sql 
CREATE EXTERNAL LIBRARY myJar
FROM (CONTENT = '<local path to .jar file>') 
WITH (LANGUAGE = 'Java'); 
GO
```

Al crear una biblioteca externa, SQL Server obtendrá acceso automático a las clases de Java y no será necesario establecer ningún permiso especial en la ruta de clase.

Ejemplo de cómo llamar a un método en una clase desde un paquete cargado como biblioteca externa:

```sql
EXEC sp_execute_external_script
  @language = N'Java'
, @script = N'MyPackage.MyCLass'
, @input_data_1 = N'SELECT * FROM MYTABLE'
with result sets ((column1 int))
```

Para obtener más información, vea [CREATE EXTERNAL LIBRARY](https://docs.microsoft.com/sql/t-sql/statements/create-external-library-transact-sql).

## <a name="next-steps"></a>Pasos siguientes

+ [Tutorial: Búsqueda de una cadena mediante expresiones regulares en Java](../tutorials/search-for-string-using-regular-expressions-in-java.md)