---
title: 'Inicio rápido: funciones de R'
titleSuffix: SQL machine learning
description: En este inicio rápido, aprenderá a usar las funciones matemáticas y de utilidad de R con el aprendizaje automático de SQL.
ms.prod: sql
ms.technology: machine-learning
ms.date: 04/23/2020
ms.topic: quickstart
author: garyericson
ms.author: garye
ms.reviewer: davidph
ms.custom: seo-lt-2019
monikerRange: '>=sql-server-2016||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: c769862ab2ab1b06169ae5191217945cf8220c9b
ms.sourcegitcommit: dc965772bd4dbf8dd8372a846c67028e277ce57e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83606674"
---
# <a name="quickstart-r-functions-with-sql-machine-learning"></a>Inicio rápido: Funciones de R con aprendizaje automático de SQL
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
En este inicio rápido, aprenderá a usar las funciones matemáticas y de utilidad de R con [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md) o en [clústeres de macrodatos](../../big-data-cluster/machine-learning-services.md). Las funciones estadísticas suelen ser complicadas de implementar en T-SQL, pero esto se puede hacer en R con solo unas pocas líneas de código.
::: moniker-end
::: moniker range="=sql-server-2017||=sqlallproducts-allversions"
En este inicio rápido, aprenderá a usar las funciones matemáticas y de utilidad de R con [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md). Las funciones estadísticas suelen ser complicadas de implementar en T-SQL, pero esto se puede hacer en R con solo unas pocas líneas de código.
::: moniker-end
::: moniker range="=sql-server-2016||=sqlallproducts-allversions"
En este inicio rápido, aprenderá a usar las funciones matemáticas y de utilidad de R con [SQL Server R Services](../r/sql-server-r-services.md). Las funciones estadísticas suelen ser complicadas de implementar en T-SQL, pero esto se puede hacer en R con solo unas pocas líneas de código.
::: moniker-end

## <a name="prerequisites"></a>Prerrequisitos

Para ejecutar este inicio rápido, debe cumplir los siguientes requisitos previos.

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
- SQL Server Machine Learning Services. Para obtener información sobre cómo instalar Machine Learning Services, vea la [Guía de instalación para Windows](../install/sql-machine-learning-services-windows-install.md) o la [Guía de instalación para Linux](../../linux/sql-server-linux-setup-machine-learning.md?toc=%2Fsql%2Fmachine-learning%2Ftoc.json). También puede [habilitar Machine Learning Services en clústeres de macrodatos de SQL Server](../../big-data-cluster/machine-learning-services.md).
::: moniker-end
::: moniker range="=sql-server-2017||=sqlallproducts-allversions"
- SQL Server Machine Learning Services. SQL Server Machine Learning Services: para obtener información sobre cómo instalar Machine Learning Services, vea la [Guía de instalación para Windows](../install/sql-machine-learning-services-windows-install.md). 
::: moniker-end
::: moniker range="=sql-server-2016||=sqlallproducts-allversions"
- SQL Server 2016 R Services. Para obtener más instrucciones sobre cómo instalar R Services, consulte la [Guía de instalación de Windows](../install/sql-r-services-windows-install.md).
::: moniker-end

- Una herramienta para ejecutar consultas de SQL que contengan scripts de R. En este inicio rápido se utiliza [Azure Data Studio](../../azure-data-studio/what-is.md).

## <a name="create-a-stored-procedure-to-generate-random-numbers"></a>Creación de un procedimiento almacenado para generar números aleatorios

Para simplificar, vamos a usar el paquete `stats` de R, que se instala y carga de forma predeterminada. El paquete contiene cientos de funciones para tareas estadísticas comunes, entre otras, la función `rnorm`, que genera una cantidad determinada de números aleatorios que usan la distribución normal, dadas una desviación estándar y la media.

Por ejemplo, el siguiente código de R devuelve 100 números en una media de 50, lo cual da una desviación estándar de 3.

```R
as.data.frame(rnorm(100, mean = 50, sd = 3));
```

Para llamar a esta línea de R desde T-SQL, agregue la función de R del parámetro de script de `sp_execute_external_script`, de la manera siguiente:

```sql
EXECUTE sp_execute_external_script
      @language = N'R'
    , @script = N'
         OutputDataSet <- as.data.frame(rnorm(100, mean = 50, sd =3));'
    , @input_data_1 = N'   ;'
      WITH RESULT SETS (([Density] float NOT NULL));
```

¿Qué ocurriría si quisiera facilitar la generación de un conjunto diferente de números aleatorios?

Puede hacerlo con facilidad en combinación con T-SQL. Defina un procedimiento almacenado que obtenga los argumentos del usuario y, a continuación, pase los argumentos al script de R como variables.

```sql
CREATE PROCEDURE MyRNorm (
    @param1 INT
    , @param2 INT
    , @param3 INT
    )
AS
EXECUTE sp_execute_external_script @language = N'R'
    , @script = N'
         OutputDataSet <- as.data.frame(rnorm(mynumbers, mymean, mysd));'
    , @input_data_1 = N'   ;'
    , @params = N' @mynumbers int, @mymean int, @mysd int'
    , @mynumbers = @param1
    , @mymean = @param2
    , @mysd = @param3
WITH RESULT SETS(([Density] FLOAT NOT NULL));
```

- La primera línea define cada uno de los parámetros de entrada de SQL que son necesarios cuando se ejecuta el procedimiento almacenado.

- La línea que comienza con `@params` define todas las variables usadas por el código de R y los correspondientes tipos de datos de SQL.

- Las líneas inmediatamente a continuación asignan los nombres de parámetro de SQL a los nombres de variable de R correspondientes.

Ahora que ha ajustado la función de R en un procedimiento almacenado, puede llamar a la función fácilmente y pasar distintos valores, como a continuación:

```sql
EXECUTE MyRNorm @param1 = 100,@param2 = 50, @param3 = 3
```

## <a name="use-r-utility-functions-for-troubleshooting"></a>Uso de funciones de utilidad de R para solucionar problemas

El paquete **utils**, instalado de forma predeterminada, ofrece diversas funciones de utilidad para investigar el entorno actual de R. Estas funciones pueden ser útiles si encuentra discrepancias en la forma en que el código de R se ejecuta en SQL Server y en entornos externos.

Por ejemplo, podría usar la función `memory.limit()` de R para obtener memoria para el entorno actual de R. Dado que el paquete `utils` está instalado pero no se carga de forma predeterminada, debe usar la función `library()` para cargarlo primero.

```sql
EXECUTE sp_execute_external_script
      @language = N'R'
    , @script = N'
        library(utils);
        mymemory <- memory.limit();
        OutputDataSet <- as.data.frame(mymemory);'
    , @input_data_1 = N' ;'
WITH RESULT SETS (([Col1] int not null));
```

> [!TIP]
> Muchos usuarios quieren usar las funciones de control de tiempo del sistema de R, como `system.time` y `proc.time`, para capturar el tiempo que tardan los procesos de R y analizar problemas de rendimiento. Para obtener un ejemplo, vea el tutorial [Creación de características de datos](../tutorials/walkthrough-create-data-features.md) donde las funciones de control de tiempo de R se incrustan en la solución.

## <a name="next-steps"></a>Pasos siguientes

Para crear un modelo de aprendizaje automático usando R con aprendizaje automático de SQL, siga este inicio rápido:

> [!div class="nextstepaction"]
> [Creación y puntuación de un modelo predictivo en R con el aprendizaje automático de SQL](quickstart-r-train-score-model.md)
