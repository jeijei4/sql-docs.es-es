---
title: Componentes del controlador OLE DB para SQL Server | Microsoft Docs
description: Componentes del controlador OLE DB para SQL Server
ms.custom: ''
ms.date: 06/12/2018
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: connectivity
ms.topic: reference
helpviewer_keywords:
- data access [OLE DB Driver for SQL Server], components
- components [OLE DB Driver for SQL Server]
- MSOLEDBSQL, about OLE DB Driver for SQL Server
author: pmasl
ms.author: pelopes
ms.openlocfilehash: c88ef12d636dd5b10e1b7b3cd9418df3e058325b
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86007058"
---
# <a name="components-of-ole-db-driver-for-sql-server"></a>Componentes del controlador OLE DB para SQL Server
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

[!INCLUDE[Driver_OLEDB_Download](../../../includes/driver_oledb_download.md)]

  OLE DB Driver for SQL Server contiene los siguientes componentes:  

|Componente|Descripción|  
|---------------|-----------------|  
|msoledbsql.dll|El archivo de biblioteca de vínculos dinámicos (DLL) que contiene toda la funcionalidad de OLE DB Driver for SQL Server.|  
|msoledbsqlr.rll|El archivo de recursos asociado de la biblioteca de OLE DB Driver for SQL Server.|   
|msoledbsql.h|El archivo de encabezado de OLE DB Driver for SQL Server que contiene todas las definiciones nuevas necesarias para poder usar OLE DB Driver for SQL Server. Este archivo de encabezado reemplaza el archivo de encabezado sqloledb.h.<br /><br /> Nota: Puede hacer referencia a msoledbsql.h y sqloledb.h en el mismo programa, siempre que se defina primero sqloledb.h.|  
|msoledbsql.lib|El archivo de biblioteca necesario para llamar directamente a la función [OpenSqlFilestream](../../../relational-databases/blob/access-filestream-data-with-opensqlfilestream.md) que forma parte de OLE DB Driver for SQL Server.<br /><br /> Nota: Si hace referencia al archivo msoledbsql.lib en el código de programación, tiene que asegurarse de que el archivo msoledbsql.lib está en la ruta de acceso de su sistema y en la del sistema de los usuarios que usan la aplicación.|  

## <a name="see-also"></a>Consulte también  
 [Compilación de aplicaciones con el controlador OLE DB para SQL Server](../../oledb/applications/building-applications-with-oledb-driver-for-sql-server.md)  
