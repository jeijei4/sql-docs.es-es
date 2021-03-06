---
title: Tutoriales de R
titleSuffix: SQL machine learning
description: En este artículo se describen los tutoriales de R para el aprendizaje automático de SQL. Obtenga información sobre cómo ejecutar scripts y crear modelos de aprendizaje automático.
ms.prod: sql
ms.technology: machine-learning
ms.topic: tutorial
author: cawrites
ms.author: chadam
ms.reviewer: garye, davidph
ms.date: 05/04/2020
ms.custom: seo-lt-2019
monikerRange: '>=sql-server-2016||>=sql-server-linux-ver15||=sqlallproducts-allversions'
ms.openlocfilehash: 63c271c4e1d59c9446495607b42b0b5ad13ea246
ms.sourcegitcommit: dc965772bd4dbf8dd8372a846c67028e277ce57e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83606927"
---
# <a name="r-tutorials-for-sql-machine-learning"></a>Tutoriales de R para aprendizaje automático de SQL

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

::: moniker range=">=sql-server-ver15||>=sql-server-linux-ver15||=sqlallproducts-allversions"
En este artículo se describen los tutoriales e inicios rápidos de R para [Machine Learning Services en SQL Server](../sql-server-machine-learning-services.md) y en [clústeres de macrodatos](../../big-data-cluster/machine-learning-services.md).
::: moniker-end
::: moniker range="=sql-server-2017||=sqlallproducts-allversions"
En este artículo se describen los tutoriales e inicios rápidos de R para [SQL Server Machine Learning Services](../sql-server-machine-learning-services.md).
::: moniker-end
::: moniker range="=sql-server-2016||=sqlallproducts-allversions"
En este artículo se describen los tutoriales e inicios rápidos de R para [SQL Server 2016 R Services](../r/sql-server-r-services.md).
::: moniker-end

<a name="bkmk_sqltutorials"></a>

## <a name="r-tutorials"></a>Tutoriales de R

| Tutorial | Descripción |
|------|-------------|
| [Predecir el alquiler de esquíes con el árbol de decisión](r-predictive-model-introduction.md) | Use R y un modelo de árbol de decisión para predecir el número de alquileres de esquíes en el futuro. Use cuadernos en Azure Data Studio para preparar los datos y entrenar el modelo y T-SQL para la implementación de modelo. |
| [Categorización de clientes con agrupación en clústeres k-means](r-clustering-model-introduction.md) | Use R para desarrollar e implementar un modelo de agrupación en clústeres k-means para clasificar a los clientes en categorías. Use cuadernos en Azure Data Studio para preparar los datos y entrenar el modelo y T-SQL para la implementación de modelo. |
| [Análisis de R en base de datos para científicos de datos](../tutorials/walkthrough-data-science-end-to-end-walkthrough.md) | Los desarrolladores de R que no conozcan SQL Server aprenderán en este tutorial a realizar tareas comunes de ciencia de datos en SQL Server. Cargue y visualice datos, entrene y guarde un modelo para SQL Server y, luego, úselo para realizar análisis predictivos. |
| [Análisis de R en base de datos para desarrolladores de SQL](../tutorials/sqldev-in-database-r-for-sql-developers.md) | Cree e implemente una solución de R completa usando únicamente [!INCLUDE[tsql](../../includes/tsql-md.md)]. Este tutorial se centra en el paso de una solución a producción. Aprenderá cómo ajustar el código de R en un procedimiento almacenado, guardar un modelo de R en una base de datos de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y realizar llamadas con parámetros al modelo de R para la predicción. |

## <a name="r-quickstarts"></a>Inicios rápidos de R

Si no está familiarizado con el aprendizaje automático de SQL, puede probar también los inicios rápidos de R.

| Guía de inicio rápido | Descripción |
|-|-|
| [Ejecución de scripts de R simples](quickstart-r-create-script.md) | Conozca los conceptos básicos sobre cómo llamar a R en T-SQL con [sp_execute_external_script](../../relational-databases/system-stored-procedures/sp-execute-external-script-transact-sql.md). |
| [Objetos y estructuras de datos con R](quickstart-r-data-types-and-objects.md) | Muestra cómo SQL utiliza R para administrar estructuras de datos. |
| [Creación y puntuación de un modelo predictivo en R](quickstart-r-data-types-and-objects.md) | Explica cómo crear, entrenar y usar un modelo de R para hacer predicciones a partir de nuevos datos. |

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información técnica sobre R en SQL Server, consulte [Extensión del lenguaje R en SQL Server](../concepts/extension-r.md).
