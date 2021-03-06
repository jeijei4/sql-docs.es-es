---
title: Descarga e instalación de sqlpackage
description: Descarga e instalación de sqlpackage para Windows, macOS o Linux
ms.custom: tools|sos
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: tools-other
ms.topic: conceptual
author: pensivebrian
ms.author: broneill
ms.reviewer: alayu; sstein
ms.date: 06/20/2018
ms.openlocfilehash: 6490dd15619c315288be6a094ceb26e68c0179d1
ms.sourcegitcommit: b8933ce09d0e631d1183a84d2c2ad3dfd0602180
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83151539"
---
# <a name="download-and-install-sqlpackage"></a>Descarga e instalación de sqlpackage

sqlpackage se ejecuta en Windows, macOS y Linux.

Descargue e instale la versión más reciente de .NET Framework y las versiones preliminares de macOS y Linux:

|Plataforma|Descargar|Fecha de la versión|Versión|Build
|:---|:---|:---|:---|:---|
|Windows|[Instalador MSI](https://go.microsoft.com/fwlink/?linkid=2128142)|28 de abril de 2020|18.5|15.0.4769.1|
|macOS .NET Core |[archivo zip](https://go.microsoft.com/fwlink/?linkid=2128145)|28 de abril de 2020| 18.5|15.0.4769.1|
|Linux .NET Core |[archivo zip](https://go.microsoft.com/fwlink/?linkid=2128144)|28 de abril de 2020| 18.5|15.0.4769.1|
|Windows .NET Core |[archivo zip](https://go.microsoft.com/fwlink/?linkid=2128143)|28 de abril de 2020| 18.5|15.0.4769.1|

Para más información sobre la última versión, consulte las [notas de la versión](release-notes-sqlpackage.md). Para descargar idiomas adicionales, consulte la sección de [idiomas disponibles](#available-languages).

[!INCLUDE[Freshness](../includes/paragraph-content/fresh-note-steps-feedback.md)]

## <a name="get-sqlpackage-for-windows"></a>Obtención de sqlpackage para Windows

En esta versión de sqlpackage se incluye una experiencia de instalación estándar de Windows y un archivo .zip: 

1. Descargue y ejecute el [instalador de DacFramework.msi para Windows](https://go.microsoft.com/fwlink/?linkid=2128142).
2. Abra una nueva ventana del símbolo del sistema y ejecute sqlpackage.exe.
    - sqlpackage se instala en la carpeta ```C:\Program Files\Microsoft SQL Server\150\DAC\bin```.

## <a name="get-sqlpackage-net-core-for-windows"></a>Descarga de sqlpackage .NET Core para Windows

1. Descargue [sqlpackage para Windows](https://go.microsoft.com/fwlink/?linkid=2128143).
2. Para extraer el archivo, haga clic con el botón derecho en el archivo en el explorador de Windows, seleccione "Extraer todo..." y seleccione el directorio de destino.
3. Abra una nueva ventana de terminal y el CD en la ubicación donde se extrajo sqlpackage:

   ```cmd
   > sqlpackage
   ```

## <a name="get-sqlpackage-net-core-for-macos"></a>Descarga de sqlpackage .NET Core para macOS

1. Descargue [sqlpackage para macOS](https://go.microsoft.com/fwlink/?linkid=2128145).
2. Para extraer el archivo e iniciar sqlpackage, abra una nueva ventana de terminal y escriba los siguientes comandos:

   ```bash
   $ mkdir sqlpackage
   $ unzip ~/Downloads/sqlpackage-osx-<version string>.zip -d ~/sqlpackage 
   $ echo 'export PATH="$PATH:~/sqlpackage"' >> ~/.bash_profile
   $ source ~/.bash_profile
   $ sqlpackage
   ```

## <a name="get-sqlpackage-net-core-for-linux"></a>Descarga de sqlpackage .NET Core para Linux

1. Descargue [sqlpackage para Linux](https://go.microsoft.com/fwlink/?linkid=2128144) mediante uno de los instaladores o el archivo tar.gz:
2. Para extraer el archivo e iniciar sqlpackage, abra una nueva ventana de terminal y escriba los siguientes comandos:

   ```bash
   $ cd ~
   $ mkdir sqlpackage
   $ unzip ~/Downloads/sqlpackage-linux-<version string>.zip -d ~/sqlpackage 
   $ echo "export PATH=\"\$PATH:$HOME/sqlpackage\"" >> ~/.bashrc
   $ chmod a+x ~/sqlpackage/sqlpackage
   $ source ~/.bashrc
   $ sqlpackage
   ```

   > [!NOTE]
   > En Debian, Red Hat y Ubuntu, puede haber dependencias que faltan. Use los siguientes comandos para instalar estas dependencias según la versión de Linux:

   **Debian:**

   ```bash
   $ sudo apt-get install libunwind8
   ```

   **Redhat:**

   ```bash
   $ yum install libunwind
   $ yum install libicu
   ```

   **Ubuntu:**

   ```bash
   $ sudo apt-get install libunwind8

   # install the libicu library based on the Ubuntu version
   $ sudo apt-get install libicu52      # for 14.x
   $ sudo apt-get install libicu55      # for 16.x
   $ sudo apt-get install libicu57      # for 17.x
   $ sudo apt-get install libicu60      # for 18.x
   ```

## <a name="uninstall-sqlpackage-preview"></a>Desinstalación de sqlpackage (versión preliminar)

Si ha instalado sqlpackage con el instalador de Windows, desinstale de la misma manera que quita cualquier aplicación de Windows.

Si ha instalado sqlpackage con un archivo .zip u otro archivo, elimine los archivos.

## <a name="supported-operating-systems"></a>Sistemas operativos compatibles

sqlpackage se ejecuta en Windows, macOS y Linux, y es compatible con las siguientes plataformas:

### <a name="windows"></a>Windows

- Windows 10
- Windows 8.1
- Windows 7 SP1
- Windows Server 2008 R2
- Windows Server 2012 R2
- Windows Server 2016

### <a name="macos"></a>macOS

- macOS 10.13 High Sierra
- macOS 10.12 Sierra

### <a name="linux-x64"></a>Linux (x64)

- Red Hat Enterprise Linux 7.4
- Red Hat Enterprise Linux 7.3
- SUSE Linux Enterprise Server v12 SP2
- Ubuntu 16.04

## <a name="available-languages"></a>Idiomas disponibles

Esta versión de sqlpackage puede instalarse en los idiomas siguientes:

sqlpackage para Windows:  
[Chino (simplificado)](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x804) | [Chino (tradicional)](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x404) | [Inglés (Estados Unidos)](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x409) | [Francés](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x40c) | [Alemán](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x407) | [Italiano](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x410) | [Japonés](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x411) | [Coreano](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x412) | [Portugués (Brasil)](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x416) | [Ruso](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x419) | [Español](https://go.microsoft.com/fwlink/?linkid=2128142&clcid=0x40a)

sqlpackage .NET Core para Windows:  
[Chino (simplificado)](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x804) | [Chino (tradicional)](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x404) | [Inglés (Estados Unidos)](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x409) | [Francés](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x40c) | [Alemán](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x407) | [Italiano](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x410) | [Japonés](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x411) | [Coreano](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x412) | [Portugués (Brasil)](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x416) | [Ruso](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x419) | [Español](https://go.microsoft.com/fwlink/?linkid=2128143&clcid=0x40a)

sqlpackage .NET Core para macOS:  
[Chino (simplificado)](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x804) | [Chino (tradicional)](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x404) | [Inglés (Estados Unidos)](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x409) | [Francés](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x40c) | [Alemán](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x407) | [Italiano](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x410) | [Japonés](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x411) | [Coreano](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x412) | [Portugués (Brasil)](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x416) | [Ruso](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x419) | [Español](https://go.microsoft.com/fwlink/?linkid=2128145&clcid=0x40a)

sqlpackage .NET Core para Linux:  
[Chino (simplificado)](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x804) | [Chino (tradicional)](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x404) | [Inglés (Estados Unidos)](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x409) | [Francés](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x40c) | [Alemán](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x407) | [Italiano](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x410) | [Japonés](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x411) | [Coreano](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x412) | [Portugués (Brasil)](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x416) | [Ruso](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x419) | [Español](https://go.microsoft.com/fwlink/?linkid=2128144&clcid=0x40a)

## <a name="next-steps"></a>Pasos siguientes

- Mas información sobre [sqlpackage](sqlpackage.md)

[Declaración de privacidad de Microsoft](https://go.microsoft.com/fwlink/?LinkId=521839)
