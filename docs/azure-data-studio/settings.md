---
title: Configuración del usuario y el área de trabajo
description: Procedimiento para personalizar Azure Data Studio al modificar la configuración del usuario y el área de trabajo.
ms.custom: seodec18
ms.date: 09/24/2018
ms.prod: azure-data-studio
ms.technology: ''
ms.reviewer: alayu, maghan, sstein
ms.topic: conceptual
author: yualan
ms.author: alayu
ms.openlocfilehash: 00c7248050d3bf7e0d5d31df6a1e628dbcc03605
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85758383"
---
# <a name="modify-user-and-workspace-settings"></a>Modificación de la configuración del usuario y el área de trabajo

Gracias a las diferentes opciones que ofrece, configurar Azure Data Studio a su gusto es fácil. Casi todas las partes del editor, la interfaz de usuario y el comportamiento funcional de Azure Data Studio tienen opciones que se pueden modificar.

Azure Data Studio proporciona dos ámbitos distintos para la configuración:

* **Usuario**: esta configuración se aplica globalmente a cualquier instancia de Azure Data Studio que abra.
* **Área de trabajo**: esta configuración es específica de una carpeta del equipo y solo está disponible cuando la carpeta está abierta en la barra lateral del explorador. La configuración que se define en este ámbito invalida el ámbito de usuario.

## <a name="creating-user-and-workspace-settings"></a>Creación de la configuración del usuario y el área de trabajo

El comando de menú **Archivo** > **Preferencias** > **Configuración** (**Código** > **Preferencias** > **Configuración** en Mac) proporciona el punto de entrada para configurar las opciones del usuario y el área de trabajo. Se le proporciona una lista de opciones de configuración predeterminadas. Copie cualquier configuración que quiera cambiar en el archivo `settings.json` adecuado. Mediante las pestañas de la derecha puede cambiar rápidamente entre los archivos de configuración del usuario y el área de trabajo.

También puede abrir la configuración del usuario y el área de trabajo desde la **paleta de comandos** (**Ctrl+Mayús+P**) con **Preferencias: Abrir configuración del usuario** y **Preferencias: Abrir configuración del área de trabajo** o si usa el método abreviado de teclado (**Ctrl+,** ).

En el siguiente ejemplo se deshabilitan los números de línea en el editor y se configuran las líneas de código para que se les aplique la sangría automáticamente.

![Configuración de ejemplo](media/settings/sample-settings.png)

Azure Data Studio vuelve a cargar los cambios realizados en la configuración después de guardar el archivo `settings.json` modificado.

> [!NOTE] 
> La configuración del área de trabajo resulta útil para compartir la configuración específica del proyecto en un equipo.

## <a name="settings-file-locations"></a>Ubicaciones del archivo de configuración

En función de la plataforma, el archivo de configuración del usuario se encuentra aquí:

* **Windows** `%APPDATA%\azuredatastudio\User\settings.json`
* **Mac** `$HOME/Library/Application Support/azuredatastudio/User/settings.json`
* **Linux** `$HOME/.config/azuredatastudio/User/settings.json`

El archivo de configuración del área de trabajo se encuentra en la carpeta `.Azure Data Studio` del proyecto.

## <a name="hot-exit"></a>Salida rápida

De forma predeterminada, Azure Data Studio recuerda los cambios no guardados en los archivos al salir. Este comportamiento es igual que la característica de salida rápida en Visual Studio Code.

De forma predeterminada, la salida rápida está desactivada. Para habilitar la salida rápida, edite la configuración `files.hotExit`. Para obtener más información, consulte [Salida rápida (en la documentación de Visual Studio Code)](https://code.visualstudio.com/docs/editor/codebasics#_hot-exit).


## <a name="tab-color"></a>Color de las pestañas

Para simplificar la identificación de las conexiones con las que está trabajando, las pestañas abiertas en el editor pueden establecer sus colores para que coincidan con el color del grupo de servidores al que pertenece la conexión. De forma predeterminada, los colores de las pestañas están desactivados. Para habilitar los colores de las pestañas, edite la configuración `sql.tabColorMode`.

## <a name="additional-resources"></a>Recursos adicionales

Dado que Azure Data Studio hereda su función de configuración de usuario y área de trabajo de Visual Studio Code, la información detallada sobre la configuración se encuentra en el artículo [Configuración de Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings).
