---
title: Qué es Azure Data Studio
description: Azure Data Studio es una herramienta gratuita y ligera que se ejecuta en Windows, macOS y Linux para administrar SQL Server, Azure SQL Database y Azure SQL Data Warehouse.
ms.prod: azure-data-studio
ms.technology: ''
ms.topic: overview
author: markingmyname
ms.author: maghan
ms.reviewer: alayu, maghan, sstein
ms.custom: seodec18, sqlfreshmay19
ms.date: 01/15/2020
ms.openlocfilehash: 05819f1bafef5095ac9d3534b0293817f3841f96
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85771930"
---
# <a name="what-is-azure-data-studio"></a>¿Qué es Azure Data Studio?

Azure Data Studio es una herramienta de base de datos multiplataforma para profesionales de datos que usan la familia de las plataformas de datos locales y en la nube de Microsoft en Windows, macOS y Linux.

Azure Data Studio ofrece una experiencia de editor moderna con IntelliSense, fragmentos de código, integración del control de código fuente y un terminal integrado. Se ha diseñado para usuarios de plataformas de datos, con gráficos integrados de conjuntos de resultados de consultas y paneles personalizables.

El código fuente de Azure Data Studio y sus proveedores de datos está disponible en GitHub en un CLUF de código fuente que proporciona derechos para modificar y usar el software, pero no para redistribuirlo ni hospedarlo en un servicio en la nube. Para obtener más información, vea [Preguntas más frecuentes de Azure Data Studio](faq.md).

**[Descarga e instalación de Azure Data Studio](download.md)**

## <a name="sql-code-editor-with-intellisense"></a>Editor de código SQL con IntelliSense

Azure Data Studio ofrece una experiencia de código SQL moderna y centrada en el teclado que hace que sus tareas diarias sean más fáciles con características integradas como varias ventanas de pestañas, un editor de SQL completo, IntelliSense, finalización de palabras clave, fragmentos de código, navegación de código e integración del control de código fuente (Git). Ejecute consultas SQL a petición, vea y guarde los resultados como texto, JSON o Excel. Edite los datos, organice sus conexiones de bases de datos favoritas y examine los objetos de base de datos en una experiencia de exploración de objetos conocida. Para obtener información sobre cómo usar el editor de SQL, vea [Usar el editor de SQL para crear objetos de base de datos](tutorial-sql-editor.md).

## <a name="smart-sql-code-snippets"></a>Fragmentos de código SQL inteligentes

Los fragmentos de código SQL generan la sintaxis SQL adecuada para crear bases de datos, tablas, vistas, procedimientos almacenados, usuarios, inicios de sesión y roles, así como para actualizar los objetos de base de datos existentes. Use fragmentos de código inteligentes para crear rápidamente copias de la base de datos con fines de desarrollo o prueba, y para generar y ejecutar scripts CREATE e INSERT.

Azure Data Studio también proporciona una funcionalidad para crear fragmentos de código SQL personalizados. Para obtener más información, vea [Crear y usar fragmentos de código](code-snippets.md).

## <a name="customizable-server-and-database-dashboards"></a>Paneles de servidor y base de datos personalizables

Cree paneles personalizables completos para supervisar y solucionar rápidamente los cuellos de botella de rendimiento en las bases de datos. Para obtener información sobre los widgets de datos y los paneles de base de datos (y servidor), consulte [Administrar servidores y bases de datos con los widgets de datos](insight-widgets.md).

## <a name="connection-management-server-groups"></a>Administración de la conexión (grupos de servidores)

Los grupos de servidores proporcionan una manera de organizar la información de conexión de los servidores y las bases de datos con los que se trabaja. Para obtener más información, consulte [Grupos de servidores](server-groups.md).

## <a name="integrated-terminal"></a>Terminal integrado

Use sus herramientas de línea de comandos favoritas (por ejemplo, Bash, PowerShell, sqlcmd, bcp y ssh) en la ventana del terminal integrado directamente desde la interfaz de usuario de Azure Data Studio. Para obtener información sobre el terminal integrado, consulte [Terminal integrado](integrated-terminal.md).

## <a name="extensibility-and-extension-authoring"></a>Extensibilidad y creación de extensiones

Amplíe la funcionalidad de la instalación básica para mejorar la experiencia de Azure Data Studio. Azure Data Studio proporciona puntos de extensibilidad para las actividades de administración de datos, así como compatibilidad con la creación de extensiones.

Para obtener información sobre la extensibilidad en Azure Data Studio, consulte [Extensibilidad](extensibility.md).
Para obtener información sobre las extensiones, vea [Crear extensiones](extension-authoring.md).

## <a name="feature-comparison-with-sql-server-management-studio-ssms"></a>Comparación de características con SQL Server Management Studio (SSMS)

**Use Azure Data Studio si:**

- Necesita ejecutarlo en macOS o Linux.
- Se está conectando a un clúster de macrodatos de SQL Server 2019.
- Dedica la mayor parte del tiempo a editar o ejecutar consultas.
- Necesita la capacidad de crear gráficos rápidamente y visualizar los conjuntos de resultados.
- Puede ejecutar la mayoría de las tareas administrativas mediante el terminal integrado con sqlcmd o PowerShell.
- Tiene una necesidad mínima de las experiencias del asistente.
- No necesita realizar una configuración administrativa profunda.

**Use SQL Server Management Studio si:**

- Dedica la mayor parte del tiempo a las tareas de administración de bases de datos.
- Realiza una configuración administrativa profunda.
- Administra la seguridad, incluida la administración de usuarios, la evaluación de vulnerabilidades y la configuración de características de seguridad.
- Usa los informes del almacén de consultas de SQL Server.
- Necesita usar los paneles y los asesores de optimización del rendimiento.
- Está importando o exportando DACPAC.
- Necesita acceso a los servidores registrados y quiere controlar los servicios de SQL Server en Windows.

### <a name="shell"></a>Shell

|Característica|Azure Data Studio|SSMS|
|:---|:---|:---|
|Inicio de sesión de Azure|Sí|Sí|
|Panel|Sí||
|Extensiones|Sí||
|Terminal integrado|Sí||
|Explorador de objetos|Sí|Sí|
|Scripting de objetos|Sí|Sí|
|Sistema de proyectos|Sí||
|Seleccionar elementos de la tabla|Sí|Sí|
|Control de código fuente|Sí||
|Panel de tareas|Sí||
|Temas|Sí||
|Modo oscuro|Sí||
|Azure Resource Explorer|Versión preliminar||
|Asistente para generar scripts||Versión preliminar|
|Importación y exportación de DACPAC||Sí|
|Propiedades de objeto||Versión preliminar|
|Diseñador de tablas||Sí|

### <a name="query-editor"></a>Editor de consultas

|Característica|Azure Data Studio|SSMS|
|:---|:---|:---|
|Visor de gráficos|Sí||
|Exportar resultados a CSV, JSON o XLSX|Sí||
|IntelliSense|Sí|Sí|
|Fragmentos de código|Sí|Sí|
|Mostrar plan|Versión preliminar|Sí|
|Estadísticas de clientes||Sí|
|Estadísticas de consultas dinámicas||Sí|
|Opciones de consulta||Sí|
|Resultados a archivo||Sí|
|Resultados a texto||Sí|
|Visor espacial||Sí|
|SQLCMD||Sí|
|Cuaderno|Sí||
|Guardar consulta como fragmento de código|Sí||

### <a name="operating-system-support"></a>Compatibilidad con sistema operativo

|Característica|Azure Data Studio|SSMS|
|:---|:---|:---|
|Linux|Sí||
|macOS|Sí||
|Windows|Sí|Sí|

### <a name="data-engineering"></a>Ingeniería de datos

|Característica|Azure Data Studio|SSMS|
|:---|:---|:---|
|Asistente para crear tablas externas|Sí||
|Integración de HDFS|Sí||
|Cuaderno|Sí||

### <a name="database-administration"></a>Administración de bases de datos

|Característica|Azure Data Studio|SSMS|
|:---|:---|:---|
|Copia de seguridad o restauración|Sí|Sí|
|Compatibilidad con clúster de macrodatos|Sí||
|Importación de archivos planos|Versión preliminar|Sí|
|Agente SQL|Versión preliminar|Sí|
|SQL Profiler|Versión preliminar|Sí|
|Always On||Sí|
|Always Encrypted||Sí|
|Asistente para copiar datos||Sí|
|Database Engine Tuning Advisor||Sí|
|Visor de registros de errores||Sí|
|Planes de mantenimiento||Sí|
|Consulta multiservidor||Sí|
|administración basada en directivas||Sí|
|PolyBase||Sí|
|Almacén de consultas||Sí|
|Servidores registrados||Sí|
|Replicación||Sí|
|Administración de seguridad||Sí|
|Service Broker||Sí|
|SQL Mail||Sí|
|Template Explorer||Sí|
|Evaluación de vulnerabilidad||Sí|
|Administración de XEvent||Sí|
|Integración de la API SQL Assessment||Sí|

## <a name="next-steps"></a>Pasos siguientes

- [Descarga e instalación de Azure Data Studio](download.md)
- [Conectarse y consultar SQL Server](quickstart-sql-server.md)
- [Conectarse y consultar Azure SQL Database](quickstart-sql-database.md)

[!INCLUDE[get-help-sql-tools](../includes/paragraph-content/get-help-sql-tools.md)]

[!INCLUDE[contribute-to-content](../includes/paragraph-content/contribute-to-content.md)]
