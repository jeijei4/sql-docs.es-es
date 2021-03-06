---
title: Extensión Machine Learning (versión preliminar)
titleSuffix: Azure Data Studio
description: La extensión Machine Learning para Azure Data Studio permite administrar paquetes, importar modelos de Machine Learning, realizar predicciones y crear cuadernos para ejecutar experimentos para las bases de datos SQL.
ms.date: 05/19/2020
ms.reviewer: sstein
ms.prod: azure-data-studio
ms.technology: machine-learning
ms.topic: conceptual
author: dphansen
ms.author: davidph
manager: cgronlun
ms.openlocfilehash: e6b38724e2cb8fde7fe38a544c3f87fba3cebd45
ms.sourcegitcommit: 48d60fe6b6991303a88936fb32322c005dfca2d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2020
ms.locfileid: "85352422"
---
# <a name="machine-learning-extension-preview-for-azure-data-studio"></a>Extensión Machine Learning (versión preliminar) para Azure Data Studio

La extensión Machine Learning para [Azure Data Studio](what-is.md) permite administrar paquetes, importar modelos de Machine Learning, realizar predicciones y crear cuadernos para ejecutar experimentos para las bases de datos SQL. Esta extensión está actualmente en versión preliminar.

## <a name="prerequisites"></a>Requisitos previos

Se deben instalar los requisitos previos siguientes en el equipo en el que se ejecute Azure Data Studio.

- [Python 3](https://www.python.org/downloads/). Una vez que haya instalado Python, debe especificar la ruta de acceso local a una instalación de Python en [Configuración de extensiones](#settings). Si ha usado un [cuaderno de kernel de Python](notebooks-tutorial-python-kernel.md) en Azure Data Studio, la extensión usará de forma predeterminada la ruta de acceso del cuaderno.

- [Microsoft ODBC Driver 17 for SQL Server](../connect/odbc/download-odbc-driver-for-sql-server.md) para Windows, macOS o Linux.

- [R 3.5](https://www.r-project.org/) (opcional). Actualmente no se admite otra versión que no sea la 3.5. Una vez que haya instalado R 3.5, debe habilitar R y especificar la ruta de acceso local a una instalación de R en [Configuración de extensiones](#settings). Esto solo es necesario si quiere administrar paquetes de R en la base de datos.

## <a name="install-the-extension"></a>Instalación de la extensión

Para instalar la extensión Machine Learning en Azure Data Studio, siga los pasos que se indican a continuación.

1. Abra el administrador de extensiones en Azure Data Studio. Puede seleccionar el icono de extensiones o seleccionar Extensiones en el menú Vista.

1. Seleccione la extensión **Machine Learning** y vea sus detalles.

1. Haga clic en **Instalar**.

1. Haga clic en **Recargar** para habilitar la extensión. (Esto solo es necesario la primera vez que se instala una extensión).

<a name="settings"></a>

## <a name="extension-settings"></a>Configuración de extensiones

Para cambiar la configuración de la extensión Machine Learning, siga los pasos que se indican a continuación.

1. Abra el administrador de extensiones en Azure Data Studio. Puede seleccionar el icono de extensiones o seleccionar Extensiones en el menú Vista.

1. Busque la extensión **Machine Learning** en las extensiones **habilitadas**.

1. Haga clic en el icono **Administrar**.

1. Haga clic en el icono **Configuración de la extensión**.

La configuración de la extensión tiene este aspecto:

:::image type="content" source="media/machine-learning-extension/ml-extension-settings.png" alt-text="Configuración de la extensión Machine Learning":::

### <a name="enable-python"></a>Habilitación de Python

Para usar la extensión Machine Learning, así como la administración de paquetes de Python en la base de datos, siga estos pasos.

> [!IMPORTANT]
> La extensión Machine Learning requiere que Python esté habilitado y configurado para que funcionen la mayor parte de las funciones, incluso si no quiere usar la de administración de paquetes de Python en la base de datos.

1. Asegúrese de que **Machine Learning: Habilitar Python** está habilitado. Este valor está habilitado de forma predeterminada.

1. Proporcione la ruta de acceso a la instalación de Python existente en **Machine Learning: Ruta de acceso de Python**. Puede ser la ruta de acceso completa al archivo ejecutable de Python o la carpeta en la que se encuentra el archivo ejecutable. Si ha usado un [cuaderno de kernel de Python](notebooks-tutorial-python-kernel.md) en Azure Data Studio, la extensión usará de forma predeterminada la ruta de acceso del cuaderno.

### <a name="enable-r"></a>Habilitación de R

Para usar la extensión Machine Learning para la administración de paquetes de R en la base de datos, siga estos pasos.

1. Asegúrese de que **Machine Learning: Habilitar R** está habilitado. Este valor está deshabilitado de forma predeterminada.

1. Proporcione la ruta de acceso a la instalación de R existente en **Machine Learning: Ruta de acceso de R**. Debe ser la ruta de acceso completa al archivo ejecutable de R. 

## <a name="use-the-machine-learning-extension"></a>Uso de la extensión Machine Learning

Para usar la extensión Machine Learning en Azure Data Studio, siga estos pasos.

1. Abra las conexiones en Azure Data Studio.

1. Haga clic con el botón derecho en el servidor y seleccione **Administrar**.

1. Haga clic en **Machine Learning** en el menú del lado izquierdo en **General**.

Siga los vínculos que aparecen en **Pasos siguientes** para ver cómo puede usar la extensión Machine Learning para administrar paquetes, realizar predicciones e importar modelos en la base de datos.

## <a name="next-steps"></a>Pasos siguientes

- [Administración de paquetes en la base de datos](machine-learning-extension-manage-packages.md)
- [Realización de predicciones](machine-learning-extension-predictions.md)
- [Importación o visualización de modelos](machine-learning-extension-import-view-models.md)
- [Cuadernos en Azure Data Studio](notebooks-guidance.md)
- [Documentación del aprendizaje automático en SQL](../machine-learning/index.yml)
- [Aprendizaje automático e IA con ONNX en SQL Edge (versión preliminar)](/azure/azure-sql-edge/onnx-overview)
