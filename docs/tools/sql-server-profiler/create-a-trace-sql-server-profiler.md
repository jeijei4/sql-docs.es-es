---
title: Crear un seguimiento
titleSuffix: SQL Server Profiler
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
ms.assetid: 0302fa6d-d2b5-43fe-ad70-7a337575b112
author: markingmyname
ms.author: maghan
ms.custom: seo-lt-2019
ms.date: 08/01/2016
ms.openlocfilehash: 5a5c004bbc7e93720f18df998b989c46ced0188e
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2020
ms.locfileid: "75307330"
---
# <a name="create-a-trace-sql-server-profiler"></a>Crear un seguimiento (SQL Server Profiler)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

En este tema se describe cómo utilizar [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] para crear un seguimiento.  
  
### <a name="to-create-a-trace"></a>Para crear un seguimiento  
  
1.  En el menú **Archivo** , haga clic en **Nueva seguimiento**y conéctese a una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
     Aparecerá el cuadro de diálogo **Propiedades de seguimiento** .  
  
    > **NOTA:** Si se ha seleccionado **Iniciar el seguimiento inmediatamente tras realizar la conexión** , no aparecerá el cuadro de diálogo **Propiedades de seguimiento** y, en su lugar, se iniciará el seguimiento. Para desactivar esta configuración, en el menú **Herramientas**, haga clic en **Opciones** y desactive la casilla Iniciar el seguimiento inmediatamente tras realizar la conexión.  
  
2.  En el cuadro **Nombre de seguimiento** , escriba un nombre para el seguimiento.  
  
3.  En la lista **Usar la plantilla** , seleccione la plantilla de seguimiento que desea utilizar para el seguimiento o seleccione la opción **En blanco** si no desea utilizar ninguna plantilla.  
  
4.  Para guardar los resultados del seguimiento, realice una de las siguientes operaciones:  
  
    -   Haga clic en **Guardar en el archivo** para capturar el seguimiento en un archivo. Especifique un valor en **Establecer el tamaño máximo de archivo (MB)** . El valor predeterminado es 5 megabytes (MB).  
  
         También puede seleccionar **Habilitar sustitución incremental de archivos** para crear automáticamente nuevos archivos cuando se alcance el tamaño máximo del archivo También puede seleccionar **El servidor procesa los datos de seguimiento**, que hace que el servicio que ejecuta el seguimiento procese los datos del seguimiento en lugar de la aplicación cliente. Cuando el servidor procese los datos del seguimiento, no se omitirá ningún evento en condiciones de gran demanda; sin embargo, puede que el rendimiento del servidor se vea afectado.  
  
    -   Haga clic en **Guardar en tabla** para capturar el seguimiento en una tabla de base de datos.  
  
         Si lo desea, haga clic en **Establecer número máximo de filas**y especifique un valor.  
  
    > **PRECAUCIÓN** Si no guarda los resultados del seguimiento puede en un archivo o una tabla, podrá ver el seguimiento mientras el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] esté abierto. No obstante, perderá los resultados del seguimiento al detenerlo y cerrar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]. Para evitarlo, haga clic en la opción **Guardar** del menú **Archivo** para guardar los resultados antes de cerrar el [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)].  
  
5.  Opcionalmente, active la casilla **Habilitar hora de detención de seguimiento** para especificar una fecha y hora de detención.  
  
6.  Para agregar o quitar eventos, columnas de datos o filtros, haga clic en la pestaña **Selección de eventos**  . Para más información, consulte: [Especificar eventos y columnas de datos para un archivo de seguimiento &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/specify-events-and-data-columns-for-a-trace-file-sql-server-profiler.md)  
  
7.  Haga clic en **Ejecutar** para iniciar el seguimiento.  
  
## <a name="see-also"></a>Consulte también  
 [Permisos necesarios para ejecutar SQL Server Profiler](../../tools/sql-server-profiler/permissions-required-to-run-sql-server-profiler.md)   
 [Plantillas y permisos de SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md)   
 [SQL Server Profiler](../../tools/sql-server-profiler/sql-server-profiler.md)   
 [Establecer correlaciones de un seguimiento con datos del registro de rendimiento de Windows &#40;SQL Server Profiler&#41;](../../tools/sql-server-profiler/correlate-a-trace-with-windows-performance-log-data-sql-server-profiler.md)  
  
  
