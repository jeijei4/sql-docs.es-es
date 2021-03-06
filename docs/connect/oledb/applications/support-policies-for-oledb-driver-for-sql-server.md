---
title: Directivas de compatibilidad del controlador OLE DB para SQL Server | Microsoft Docs
description: Directivas de compatibilidad del controlador OLE DB para SQL Server
ms.date: 05/25/2020
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.custom: ''
ms.technology: connectivity
ms.topic: reference
author: pmasl
ms.author: pelopes
ms.openlocfilehash: 7e4b77a700d494f1ed8f11a0004c60b37c5cc361
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86007043"
---
# <a name="support-policies-for-ole-db-driver-for-sql-server"></a>Directivas de compatibilidad del controlador OLE DB para SQL Server
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

En este tema se describe la forma de usar diversos componentes de acceso a datos con OLE DB Driver for SQL Server.  

## <a name="sql-version-support"></a>Soporte para versiones de SQL  

OLE DB Driver for SQL Server se ha probado y admite conexiones a las versiones de SQL Server siguientes.

| Versión del controlador | Azure SQL Database | Azure SQL DW | Instancia administrada de Azure SQL | SQL Server 2019 | SQL Server 2017 | SQL Server 2016 | SQL Server 2014 | SQL Server 2012 |
|----|-|-|-|-|-|-|-|-|
|18.4|Y|Y|Y|Y|Y|Y|Y|Y|
|18.3|Y|Y|Y|Y|Y|Y|Y|Y|
|18.2|Y|Y|Y|Y|Y|Y|Y|Y|
|18.1|Y|Y|Y| |Y|Y|Y|Y|
|18.0|Y|Y|Y| |Y|Y|Y|Y|
| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

## <a name="supported-operating-system-versions"></a>Versiones de sistemas operativos admitidos  

En la tabla siguiente se enumeran los sistemas operativos que admite OLE DB Driver for SQL Server.  

| Versión del controlador | Windows Server 2019 | Windows Server 2016 | Windows Server 2012<sup>1</sup> | Windows Server 2012 R2<sup>2</sup> | Windows 10 | Windows 8.1<sup>3</sup> |
|----|-|-|-|-|-|-|
|18.4|Y|Y|Y|Y|Y|Y|
|18.3|Y|Y|Y|Y|Y|Y|
|18.2|Y|Y|Y|Y|Y|Y|
|18.1| |Y|Y|Y|Y|Y|
|18.0| |Y|Y|Y|Y|Y|
| &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; | &nbsp; |

<sup>1</sup> Se admite en Windows Server 2012 con [KB2999226](https://go.microsoft.com/fwlink/?linkid=2074061).  
<sup>2</sup> Se admite en Windows Server 2012 R2 con [la actualización de abril de 2014](https://go.microsoft.com/fwlink/?linkid=2073785) y [KB2999226](https://go.microsoft.com/fwlink/?linkid=2074061).  
<sup>3</sup> Se admite en Windows 8.1 con [la actualización de abril de 2014](https://go.microsoft.com/fwlink/?linkid=2073785) y [KB2999226](https://go.microsoft.com/fwlink/?linkid=2074061).  

## <a name="ado-support-policies"></a>Directivas de compatibilidad de ADO  

Las aplicaciones ADO pueden usar el proveedor OLE DB SQLOLEDB que se incluye con Windows si no requieren ninguna de las características de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] o posterior.  

Las aplicaciones ADO también pueden usar OLE DB Driver for SQL Server pero, si lo hacen, deben especificar `DataTypeCompatibility=80` en las cadenas de conexión. Solo estarán disponibles las características de [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] cuando `DataTypeCompatibility=80` esté presente en las cadenas de conexión.  

## <a name="ole-db-support-policies"></a>Directivas de soporte de OLE DB  

Las aplicaciones pueden usar el proveedor OLE DB (SQLOLEDB) que se incluye con el sistema operativo Windows. Aunque esto está en modo de mantenimiento y ya no se actualiza. En su lugar, use OLE DB Driver for SQL Server (MSOLEDBSQL).

## <a name="see-also"></a>Consulte también  

[Compilación de aplicaciones con el controlador OLE DB para SQL Server](../../oledb/applications/building-applications-with-oledb-driver-for-sql-server.md)
