---
title: Instalación de paquetes de Python con sqlmlutils
description: Obtenga más información sobre cómo usar PIP de Python para instalar nuevos paquetes de Python en una instancia de SQL Server Machine Learning Services.
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/24/2020
ms.topic: conceptual
author: garyericson
ms.author: garye
ms.reviewer: davidph
monikerRange: '>=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 69da04eaad729225ed0629ba78d2f214b30ba942
ms.sourcegitcommit: dc965772bd4dbf8dd8372a846c67028e277ce57e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83606497"
---
# <a name="install-python-packages-with-sqlmlutils"></a>Instalación de paquetes de Python con sqlmlutils

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

En este artículo se describe cómo usar las funciones del paquete [**sqlmlutils**](https://github.com/Microsoft/sqlmlutils) para instalar nuevos paquetes de Python en una instancia de SQL Server Machine Learning Services. Los paquetes que se instalen podrán usarse en los scripts de Python que se ejecutan en la base de datos mediante la instrucción T-SQL [sp_execute_external_script](https://docs.microsoft.com/sql/relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql).

Para obtener más información sobre la ubicación de los paquetes y las rutas de acceso de instalación, consulte [Obtención de información de paquetes de Python](../package-management/python-package-information.md).

> [!NOTE]
> El paquete **sqlmlutils** que se describe en este artículo se usa para agregar paquetes de Python a SQL Server 2019 o versiones posteriores. Para SQL Server 2017 y versiones anteriores, consulte [Instalación de paquetes con las herramientas de Python](https://docs.microsoft.com/sql/machine-learning/package-management/install-python-packages-standard-tools?view=sql-server-2017&viewFallbackFrom=sql-server-ver15).

## <a name="prerequisites"></a>Prerrequisitos

+ Debe tener [SQL Server Machine Learning Services](../install/sql-machine-learning-services-windows-install.md) instalado con la opción de lenguaje Python.

+ Instale [python](https://www.python.org/) en el equipo cliente que usa para conectarse a SQL Server. También puede interesarle un entorno de desarrollo de Python como [Visual Studio Code](https://code.visualstudio.com/download) con la [extensión de Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python). 

+ Instale [Azure Data Studio](https://docs.microsoft.com/sql/azure-data-studio/what-is) en el equipo cliente que usa para conectarse a SQL Server. Puede usar otras herramientas de consulta o administración de bases de datos, pero en este artículo se da por supuesto que emplea Azure Data Studio.

### <a name="other-considerations"></a>Otras consideraciones

+ Los paquetes deben ser compatibles con la versión de Python que tenga. Para obtener información sobre la versión de Python que se incluye con cada versión de SQL Server, consulte [Versiones de Python y R](../sql-server-machine-learning-services.md#versions).

+ La biblioteca de paquetes de Python se encuentra en la carpeta Archivos de programa de la instancia de SQL Server y, de forma predeterminada, se requieren permisos de administrador para instalar contenido en esta carpeta. Para obtener más información, consulte [Ubicación de la biblioteca de paquetes](../package-management/python-package-information.md#default-python-library-location).

+ La instalación de paquetes se realiza por instancia. Si tiene varias instancias de Machine Learning Services, debe agregar el paquete a cada una de ellas.

+ Antes de agregar un paquete, piense si es adecuado para el entorno de SQL Server.

  + Se recomienda usar Python en la base de datos para las tareas que se benefician de la estrecha integración con el motor de base de datos, como el aprendizaje automático, en lugar de para las tareas que simplemente consultan la base de datos.

  + Si agrega paquetes que ejercen demasiada presión de cálculo en el servidor, el rendimiento se verá afectado.

  + En un entorno de SQL Server protegido, probablemente le interese evitar lo siguiente:
    + Paquetes que requieren acceso a la red
    + Paquetes que requieren acceso con privilegios elevados al sistema de archivos
    + Paquetes que se usan para el desarrollo web u otras tareas que no obtienen ningún beneficio al ejecutarse en SQL Server

## <a name="install-sqlmlutils-on-the-client-computer"></a>Instalación de sqlmlutils en el equipo cliente

Para usar **sqlmlutils**, primero debe instalarlo en el equipo cliente que usa para conectarse a SQL Server. Asegúrese de que ha instalado `pip`, consulte la [instalación de pip](https://pip.pypa.io/en/stable/installing/) para más información.

1. Descargue el archivo .zip **sqlmlutils** más reciente desde https://github.com/Microsoft/sqlmlutils/tree/master/Python/dist en el equipo cliente. No descomprima el archivo.

1. Abra un **símbolo del sistema** y ejecute el siguiente comando para instalar el paquete **sqlmlutils**. Sustituya la ruta de acceso completa del archivo .zip **sqlmlutils** que ha descargado. En este ejemplo, se da por supuesto que el archivo descargado es `c:\temp\sqlmlutils-1.0.0.zip`.

   ```console
   pip install --upgrade --upgrade-strategy only-if-needed c:\temp\sqlmlutils-1.0.0.zip
   ```

## <a name="add-a-python-package-on-sql-server"></a>Adición de un paquete de Python en SQL Server

En el ejemplo siguiente, agregará el paquete [text-tools](https://pypi.org/project/text-tools/) en SQL Server.

### <a name="add-the-package-online"></a>Adición del paquete en línea

Si el equipo cliente que usa para conectarse a SQL Server tiene acceso a Internet, puede usar **sqlmlutils** para buscar el paquete **text-tools** y las dependencias a través de Internet y, después, instalar el paquete en una instancia de SQL Server de forma remota.

::: moniker range=">=sql-server-ver15||=sqlallproducts-allversions"

1. En el equipo cliente, abra **Python** o un entorno de Python.

1. Use los comandos siguientes para instalar el paquete **text-tools**. Sustituya la información propia de conexión de base de datos de SQL Server (si usa la autenticación de Windows, no necesita los parámetros `uid` y `pwd`).

::: moniker-end

::: moniker range=">=sql-server-linux-ver15||=sqlallproducts-allversions"

1. En el equipo cliente, abra **Python** o un entorno de Python.

1. Use los comandos siguientes para instalar el paquete **text-tools**. Sustituya la información de conexión de base de datos de SQL Server propia.

::: moniker-end

   ```python
   import sqlmlutils
   connection = sqlmlutils.ConnectionInfo(server="server", database="database", uid="username", pwd="password")
   sqlmlutils.SQLPackageManager(connection).install("text-tools")
   ```

### <a name="add-the-package-offline"></a>Adición del paquete sin conexión

Si el equipo cliente que usa para conectarse a SQL Server no tiene conexión a Internet, puede usar **PIP** en un equipo con acceso a Internet para descargar el paquete y los paquetes dependientes en una carpeta local. Después, copie la carpeta en el equipo cliente en el que puede instalar el paquete sin conexión.

#### <a name="on-a-computer-with-internet-access"></a>En un equipo con acceso a Internet

1. Abra un **símbolo del sistema** y ejecute el comando siguiente para crear una carpeta local que contenga el paquete **text-tools**. En este ejemplo, se crea la carpeta `c:\temp\text-tools`.

   ```console
   pip download text-tools -d c:\temp\text-tools
   ```

1. Copie la carpeta `text-tools` en el equipo cliente. En el ejemplo siguiente se da por supuesto que lo ha copiado en `c:\temp\packages\text-tools`.

#### <a name="on-the-client-computer"></a>En el equipo cliente

Use **sqlmlutils** para instalar cada paquete (archivo .whl) que encuentre en la carpeta local que ha creado **PIP**. No importa en qué orden instale los paquetes.

En este ejemplo, **text-tools** no tiene dependencias, por lo que solo se va a instalar un archivo de la carpeta `text-tools`. Por el contrario, un paquete como **scikit-plot** tiene 11 dependencias, por lo que encontrará 12 archivos en la carpeta (el paquete **scikit-plot** y los 11 paquetes dependientes) y debe instalar cada uno de ellos.

::: moniker range=">=sql-server-ver15||=sqlallproducts-allversions"

Ejecute el siguiente script de Python. Sustituya la ruta de acceso de archivo y el nombre reales del paquete, así como la información propia de conexión de base de datos de SQL Server (si usa la autenticación de Windows, no necesita los parámetros `uid` y `pwd`). Repita la instrucción `sqlmlutils.SQLPackageManager` para cada archivo de paquete de la carpeta.

::: moniker-end

::: moniker range=">=sql-server-linux-ver15||=sqlallproducts-allversions"

Ejecute el siguiente script de Python. Sustituya la ruta de acceso de archivo y el nombre reales del paquete, así como la información propia de conexión de base de datos de SQL Server. Repita la instrucción `sqlmlutils.SQLPackageManager` para cada archivo de paquete de la carpeta.

::: moniker-end

```python
import sqlmlutils
connection = sqlmlutils.ConnectionInfo(server="yourserver", database="yourdatabase", uid="username", pwd="password"))
sqlmlutils.SQLPackageManager(connection).install("text_tools-1.0.0-py3-none-any.whl")
```

## <a name="use-the-package"></a>Uso del paquete

Ahora puede usar el paquete en un script de Python en SQL Server. Por ejemplo:

```python
EXECUTE sp_execute_external_script
  @language = N'Python',
  @script = N'
from text_tools.finders import find_best_string
corpus = "Lorem Ipsum text"
query = "Ipsum"
first_match = find_best_string(query, corpus)
print(first_match)
  '
```

## <a name="remove-the-package-from-sql-server"></a>Eliminación de un paquete de SQL Server

Si quiere quitar el paquete **text-tools**, use el siguiente comando de Python en el equipo cliente, con la misma variable de conexión que definió anteriormente.

```python
sqlmlutils.SQLPackageManager(connection).uninstall("text-tools")
```

## <a name="next-steps"></a>Pasos siguientes

+ Para ver información sobre los paquetes de Python instalados en SQL Server Machine Learning Services, consulte [Obtención de información de paquetes de Python](../package-management/python-package-information.md).

+ Para obtener información sobre cómo instalar paquetes de R en SQL Server Machine Learning Services, consulte [Instalación de nuevos paquetes de R en SQL Server](install-additional-r-packages-on-sql-server.md).
