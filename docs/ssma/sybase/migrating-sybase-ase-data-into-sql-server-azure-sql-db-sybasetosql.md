---
title: 'Migración de datos de Sybase ASE en SQL Server: Azure SQL DB | Microsoft Docs'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Migrating data,Client Side Data Migration
- Migrating data,Server Side Data Migration
ms.assetid: 54a39f5e-9250-4387-a3ae-eae47c799811
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 28a07c08fd801a9d5fdcdde4206f7aa6fe7b926f
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68028839"
---
# <a name="migrating-sybase-ase-data-into-sql-server---azure-sql-db--sybasetosql"></a>Migración de datos de Sybase ASE en SQL Server: Azure SQL DB (SybaseToSQL)
Una vez que haya cargado correctamente los objetos de base de datos de Sybase Adaptive Server [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise (ASE) en o Azure SQL dB, puede migrar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] datos de ase a o a Azure SQL dB.  
  
> [!IMPORTANT]  
> Si el motor utilizado es el motor de migración de datos del lado servidor, antes de migrar los datos, debe instalar el paquete de extensión SSMA para Sybase ASE y los proveedores de Sybase ASE en el equipo que ejecuta SSMA. El servicio Agente SQL Server también debe estar en ejecución. Para obtener más información acerca de cómo instalar el paquete de extensión, consulte [instalación de componentes de SSMA en SQL Server (SybaseToSQL)](https://msdn.microsoft.com/5ad9e12c-2cdb-4dd2-8703-05a23242d19d) .  
  
## <a name="setting-migration-options"></a>Establecer opciones de migración  
Antes de migrar datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a o a Azure SQL dB, revise las opciones de migración del proyecto en el cuadro de diálogo **configuración del proyecto** .  
  
-   Mediante este cuadro de diálogo puede establecer opciones como el tamaño del lote de migración, el bloqueo de tablas, la comprobación de restricciones, el control de valores NULL y el control de valores de identidad. Para obtener más información sobre la configuración de migración de proyectos, vea [configuración del proyecto (migración) (Sybase)](https://msdn.microsoft.com/82f8857f-7ab1-4738-ab6e-b1e95ea94924).  
  
    Para obtener más información sobre la configuración de la **migración de datos extendida**, consulte Configuración de la [migración de datos](data-migration-settings-sybasetosql.md)  
  
-   El **motor de migración** en el cuadro de diálogo **configuración del proyecto** permite que el usuario realice el proceso de migración mediante dos tipos de motores de migración de datos, es decir,:  
  
    1.  Motor de migración de datos del lado cliente  
  
    2.  Motor de migración de datos del lado servidor  
  
**Migración de datos del lado cliente:**  
  
-   Para iniciar la migración de datos en el lado cliente, seleccione la opción **motor de migración de datos del lado cliente** en el cuadro de diálogo **configuración del proyecto** .  
  
-   En **configuración del proyecto**, la opción **motor de migración de datos del lado cliente** está establecida de forma predeterminada.  
  
    > [!NOTE]  
    > El motor de migración de datos del lado cliente reside dentro de la aplicación SSMA y, por lo tanto, no depende de la disponibilidad del paquete de extensión.  
  
**Migración de datos del lado servidor:**  
  
-   Durante la migración de datos del lado servidor, el motor reside en la base de datos de destino. Se instala a través del paquete de extensión. Para obtener más información sobre cómo instalar el paquete de extensión, consulte [instalación de componentes de SSMA en SQL Server (SybaseToSQL)](https://msdn.microsoft.com/5ad9e12c-2cdb-4dd2-8703-05a23242d19d) .  
  
-   Para iniciar la migración en el lado del servidor, seleccione la opción **motor de migración de datos del lado servidor** en el cuadro de diálogo **configuración del proyecto** .  
  
> [!NOTE]  
> Cuando se usa Azure SQL DB como base de datos de destino, solo se permite la **migración de datos del lado cliente** y no se admite la migración de datos del lado servidor.  
  
## <a name="migrating-data-to-sql-server-or-azure-sql-db"></a>Migración de datos a SQL Server o a Azure SQL DB  
La migración de datos es una operación de carga masiva que mueve filas de datos de las tablas de ASE a SQL Server tablas de transacciones. El número de filas que se cargan en SQL Server o en Azure SQL DB en cada transacción se configura en la configuración del proyecto.  
  
Para ver los mensajes de migración, asegúrese de que el panel de salida esté visible. En caso contrario, seleccione **salida** en el menú **Ver** .  
  
**Para migrar datos**  
  
1.  Verifique lo siguiente:  
  
    -   Los proveedores de ASE están instalados en el equipo que ejecuta SSMA.  
  
    -   Ha sincronizado los objetos convertidos con la base de datos de destino (SQL Server o Azure SQL DB).  
  
2.  En el explorador de metadatos de Sybase, seleccione los objetos que contienen los datos que desea migrar:  
  
    -   Para migrar datos de todos los esquemas, active la casilla situada junto a **esquemas**.  
  
    -   Para migrar datos u omitir tablas individuales, expanda primero el esquema, expanda **tablas**y, a continuación, Active o desactive la casilla situada junto a la tabla.  
  
3.  Para migrar datos, surgen dos casos:  
  
    **Migración de datos del lado cliente:**  
  
    Para realizar la **migración de datos del lado cliente**, seleccione la opción **motor de migración de datos del lado cliente** en el cuadro de diálogo **configuración del proyecto** .  
  
    **Migración de datos del lado servidor:**  
  
    -   Antes de realizar la migración de datos del lado servidor, asegúrese de lo siguiente:  
  
        1.  SSMA para Sybase Extension Pack está instalado en la instancia de SQL Server.  
  
        2.  El servicio Agente SQL Server se está ejecutando en la instancia de SQL Server  
  
    -   Para realizar la **migración de datos del lado servidor**, seleccione la opción **motor de migración de datos del lado servidor** en el cuadro de diálogo **configuración del proyecto** .  
  
4.  Haga clic con el botón secundario en **esquemas** en Sybase Metadata Explorer y, a continuación, haga clic en **migrar datos**. También puede migrar datos para objetos individuales o categorías de objetos: haga clic con el botón secundario en el objeto o en su carpeta principal y seleccione la opción **migrar datos** .  
  
    > [!NOTE]  
    > Si SSMA for Sybase Extension Pack no está instalado en la instancia de SQL Server, y si el **motor de migración de datos del lado servidor** está seleccionado, al migrar los datos a la base de datos de destino, se produce el siguiente error: "no se encontraron los componentes de migración de datos de ssma en SQL Server, la migración de datos del servidor no será posible. Compruebe si el paquete de extensiones está instalado correctamente. Haga clic en **Cancelar** para finalizar la migración de datos.  
  
5.  En el cuadro de diálogo **conectar a Sybase ase** , escriba las credenciales de conexión y, a continuación, haga clic en **conectar**. Para obtener más información sobre cómo conectarse a Sybase ASE, consulte [conexión a sybase &#40;SybaseToSQL&#41;](../../ssma/sybase/connect-to-sybase-sybasetosql.md)  
  
    Si la base de datos de destino está SQL Server, escriba las credenciales de conexión en el cuadro de diálogo **conectar con SQL Server** y haga clic en **conectar**. Para obtener más información sobre cómo conectarse a SQL Server, consulte [conexión a SQL Server (SybaseToSQL)](https://msdn.microsoft.com/dd368a1a-45b0-40e9-b4d3-5cdb48c26606) .  
  
    Si la base de datos de destino es Azure SQL DB, escriba las credenciales de conexión en el cuadro de diálogo **conectar a base** de datos SQL de Azure y haga clic en **conectar**. Para más información sobre cómo conectarse a Azure SQL DB, consulte [conexión a Azure SQL db &#40;SybaseToSQL&#41;](../../ssma/sybase/connecting-to-azure-sql-db-sybasetosql.md)  
  
    Los mensajes aparecerán en el panel de **resultados** . Una vez completada la migración, aparece el **Informe de migración de datos** . Si no se migró ningún dato, haga clic en la fila que contiene los errores y, a continuación, haga clic en **detalles**. Cuando haya terminado con el informe, haga clic en **cerrar**. Para obtener más información sobre el informe de migración de datos, vea [Informe de migración de datos (SSMA Common)](https://msdn.microsoft.com/bbfb9d88-5a98-4980-8d19-c5d78bd0d241)  
  
> [!NOTE]  
> Cuando se utiliza SQL Express Edition como base de datos de destino, solo se permite la migración de datos del lado cliente y no se admite la migración de datos del lado servidor.  
  
## <a name="see-also"></a>Consulte también  
[Migración de bases de datos de Sybase ASE a SQL Server: Azure SQL DB &#40;SybaseToSQL&#41;](../../ssma/sybase/migrating-sybase-ase-databases-to-sql-server-azure-sql-db-sybasetosql.md)  
  
