---
title: 'Inicio rápido: estructuras de datos de Python'
description: En este inicio rápido, aprenderá a trabajar con estructuras de datos y objetos de datos en Python y SQL Server Machine Learning Services.
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/15/2020
ms.topic: quickstart
author: cawrites
ms.author: chadam
ms.reviewer: garye
ms.custom: seo-lt-2019
monikerRange: '>=sql-server-2017||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 3023287504cbb7b25e194b53d0957e82405d1ea8
ms.sourcegitcommit: dc965772bd4dbf8dd8372a846c67028e277ce57e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83606700"
---
# <a name="quickstart-data-structures-and-objects-using-python-in-sql-server-machine-learning-services"></a>Inicio rápido: estructuras de datos y objetos mediante Python en SQL Server Machine Learning Services
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
En este inicio rápido, aprenderá a usar estructuras de datos y tipos de datos cuando use Python en [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md) o en [clústeres de macrodatos](../../big-data-cluster/machine-learning-services.md). Aprenderá a mover datos entre Python y SQL Server, así como los problemas comunes que pueden producirse.
::: moniker-end
::: moniker range="=sql-server-2017||=sqlallproducts-allversions"
En este inicio rápido, aprenderá a usar estructuras de datos y tipos de datos cuando use Python en [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md). Aprenderá a mover datos entre Python y SQL Server, así como los problemas comunes que pueden producirse.
::: moniker-end

SQL Server se basa en el paquete **pandas** de Python, que es excelente para trabajar con datos tabulares. Sin embargo, no puede pasar un valor escalar desde Python a SQL Server y esperar que funcione. En esta guía de inicio rápido, revisará algunas definiciones de estructura de datos básicas para prepararle para problemas adicionales que podrían ocurrir al pasar datos tabulares entre Python y SQL Server.

Los conceptos más comunes son:

- Una trama de datos es una tabla con _varias_ columnas.
- Una sola columna de una trama de datos es un objeto de tipo lista denominado serie.
- Un valor único de una trama de datos se denomina celda y se obtiene acceso a ella mediante el índice.

¿Cómo se expondría el resultado único de un cálculo como una trama de datos, si una data.frame requiere una estructura tabular? Una respuesta es representar el valor escalar único como una serie, que se convierte fácilmente en una trama de datos. 

> [!NOTE]
> Cuando se devuelven fechas, Python en SQL usa DATETIME, que tiene un intervalo de fechas restringido de 1753-01-01(-53690) a 9999-12-31(2958463). 

## <a name="prerequisites"></a>Prerrequisitos

Para ejecutar este inicio rápido, debe cumplir los siguientes requisitos previos.

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
- SQL Server Machine Learning Services. Para obtener información sobre cómo instalar Machine Learning Services, vea la [Guía de instalación para Windows](../install/sql-machine-learning-services-windows-install.md) o la [Guía de instalación para Linux](../../linux/sql-server-linux-setup-machine-learning.md?toc=%2Fsql%2Fmachine-learning%2Ftoc.json). También puede [habilitar Machine Learning Services en clústeres de macrodatos de SQL Server](../../big-data-cluster/machine-learning-services.md).
::: moniker-end
::: moniker range="=sql-server-2017||=sqlallproducts-allversions"
- SQL Server Machine Learning Services. SQL Server Machine Learning Services: para obtener información sobre cómo instalar Machine Learning Services, vea la [Guía de instalación para Windows](../install/sql-machine-learning-services-windows-install.md). 
::: moniker-end
- También necesita una herramienta para ejecutar consultas SQL que contengan scripts de Python. Puede ejecutar estos scripts con cualquier herramienta de consultas o administración de bases de datos, siempre que pueda conectarse a una instancia de SQL Server y ejecutar una consulta T-SQL o un procedimiento almacenado. En este inicio rápido se utiliza [Azure Data Studio](https://docs.microsoft.com/sql/azure-data-studio/download-azure-data-studio).

## <a name="scalar-value-as-a-series"></a>Valor escalar como una serie

Este ejemplo realiza algunas operaciones matemáticas simples y convierte un valor escalar en una serie.

1. Una serie requiere un índice, que puede asignarlo manualmente, como se muestra aquí, o mediante programación.

   ```sql
   EXECUTE sp_execute_external_script @language = N'Python'
       , @script = N'
   a = 1
   b = 2
   c = a/b
   print(c)
   s = pandas.Series(c, index =["simple math example 1"])
   print(s)
   '
   ```

   Dado que la serie no se ha convertido a data.frame, los valores se devuelven en la ventana mensajes, pero puede ver que los resultados se encuentran en un formato más tabular.

   **Resultados**

   ```text
   STDOUT message(s) from external script: 
   0.5
   simple math example 1    0.5
   dtype: float64
   ```

1. Para aumentar la longitud de la serie, puede agregar nuevos valores mediante una matriz. 

   ```sql
   EXECUTE sp_execute_external_script @language = N'Python'
       , @script = N'
   a = 1
   b = 2
   c = a/b
   d = a*b
   s = pandas.Series([c,d])
   print(s)
   '
   ```

   Si no especifica un índice, se genera un índice con valores que empiezan por 0 y terminan con la longitud de la matriz.

   **Resultados**

   ```text
   STDOUT message(s) from external script: 
   0    0.5
   1    2.0
   dtype: float64
   ```

1. Si aumenta el número de valores del **índice**, pero no agrega nuevos valores de **datos**, los valores de datos se repiten para rellenar la serie.

   ```sql
   EXECUTE sp_execute_external_script @language = N'Python'
       , @script = N'
   a = 1
   b = 2
   c = a/b
   s = pandas.Series(c, index =["simple math example 1", "simple math example 2"])
   print(s)
   '
   ```

   **Resultados**

   ```text
   STDOUT message(s) from external script: 
   0.5
   simple math example 1    0.5
   simple math example 2    0.5
   dtype: float64
   ```

## <a name="convert-series-to-data-frame"></a>Conversión de series en tramas de datos

Después de convertir los resultados matemáticos escalares en una estructura tabular, debe convertirlos a un formato que SQL Server pueda controlar.

1. Para convertir una serie en data.frame, llame al método [DataFrame](https://pandas.pydata.org/pandas-docs/stable/dsintro.html#dataframe) de pandas.

   ```sql
   EXECUTE sp_execute_external_script @language = N'Python'
       , @script = N'
   import pandas as pd
   a = 1
   b = 2
   c = a/b
   d = a*b
   s = pandas.Series([c,d])
   print(s)
   df = pd.DataFrame(s)
   OutputDataSet = df
   '
   WITH RESULT SETS((ResultValue FLOAT))
   ```

   A continuación se muestra el resultado. Incluso si usa el índice para obtener valores específicos de data.Frame, los valores del índice no forman parte de la salida.

   **Resultados**

   |ResultValue|
   |------|
   |0.5|
   |2|

## <a name="output-values-into-dataframe"></a>Los valores de salida en data.frame

Ahora se mostrarán los valores específicos de dos series de resultados matemáticos en data.frame. El primero tiene un índice de valores secuenciales generados por Python. El segundo usa un índice arbitrario de valores de cadena.

1. En el ejemplo siguiente se obtiene un valor de la serie utilizando un índice de entero.

   ```sql
   EXECUTE sp_execute_external_script @language = N'Python'
       , @script = N'
   import pandas as pd
   a = 1
   b = 2
   c = a/b
   d = a*b
   s = pandas.Series([c,d])
   print(s)
   df = pd.DataFrame(s, index=[1])
   OutputDataSet = df
   '
   WITH RESULT SETS((ResultValue FLOAT))
   ```

   **Resultados**

   |ResultValue|
   |------|
   |2.0|

   Recuerde que el índice generado automáticamente comienza en 0. Pruebe a usar un valor de índice fuera de intervalo y vea lo que sucede.

1. Ahora obtenga un valor único de la otra trama de datos mediante un índice de cadena.

   ```sql
   EXECUTE sp_execute_external_script @language = N'Python'
       , @script = N'
   import pandas as pd
   a = 1
   b = 2
   c = a/b
   s = pandas.Series(c, index =["simple math example 1", "simple math example 2"])
   print(s)
   df = pd.DataFrame(s, index=["simple math example 1"])
   OutputDataSet = df
   '
   WITH RESULT SETS((ResultValue FLOAT))
   ```

   **Resultados**

   |ResultValue|
   |------|
   |0.5|

   Si intenta usar un índice numérico para obtener un valor de esta serie, obtendrá un error.

## <a name="next-steps"></a>Pasos siguientes

Para obtener información sobre cómo escribir funciones avanzadas de Python en SQL Server, siga esta guía de inicio rápido:

> [!div class="nextstepaction"]
> [Creación de funciones avanzadas de Python con SQL Server Machine Learning Services](quickstart-python-functions.md)

Para más información sobre cómo usar Python en SQL Server Machine Learning Services, vea los artículos siguientes:

- [Creación y puntuación de un modelo predictivo en Python](quickstart-python-train-score-model.md)
- [¿Qué es SQL Server Machine Learning Services (Python y R)?](../sql-server-machine-learning-services.md)
