---
title: Tipos de datos de la instancia Oracle CDC | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: eec13d8d-c15a-4542-bfc4-da66b1a6bfe0
caps.latest.revision: 8
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: dd95fa824edc5833b1bfed368cdb00c3684a862b
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37149386"
---
# <a name="oracle-cdc-instance-data-types"></a>Tipos de datos de la instancia CDC de Oracle
  La instancia CDC de Oracle admite la mayoría de los tipos de datos de Oracle. En las secciones siguientes se describen los tipos de datos admitidos y los tipos de datos no admitidos.  
  
## <a name="supported-data-types"></a>Tipos de datos admitidos  
 En la tabla siguiente se describen los tipos de datos de Oracle que se pueden capturar y su asignación predeterminada a tipos de datos de SQL Server en las tablas de cambios. Al agregar una instancia de captura para una tabla de Oracle de origen, puede invalidar algunas de estas asignaciones.  
  
|Tipo de datos de base de datos de Oracle|Tipo de datos de SQL Server|  
|-------------------------------|--------------------------|  
|BINARY_FLOAT|real|  
|BINARY_DOUBLE|FLOAT|  
|CHAR|NVARCHAR|  
|DATE|DATETIME|  
|FLOAT|FLOAT|  
|INT|NUMERIC (38)|  
|INTERVAL|DATETIME|  
|NCHAR|NVARCHAR|  
|NUMBER|FLOAT|  
|NAVARCHAR2|NVARCHAR|  
|RAW|VARBINARY|  
|real|FLOAT|  
|TIMESTAMP|DATETIME2|  
|TIMESTAMP WITH TIME ZONE|VARCHAR (37)|  
|TIMESTAMP WITH LOCAL TIME ZONE|VARCHAR (37)|  
|VARCHAR2|VARCHAR|  
|XMLTYPE|NVARCHAR (MAX)|  
  
## <a name="non-supported-data-types"></a>Tipos de datos no admitidos  
 No se pueden capturar tablas de Oracle de origen con columnas que tengan los tipos de datos de Oracle siguientes. Las columnas capturadas con estos tipos de datos se mostrarán como NULL; sin embargo, un cambio en su valor se indica en la máscara de cambio de las tablas capturadas.  
  
-   LONG  
  
-   XMLTYPE  
  
-   BLOB  
  
-   CLOB  
  
 No se pueden capturar tablas de Oracle de origen con columnas que tengan los tipos de datos de Oracle siguientes.  
  
-   BFILE  
  
-   ROWID  
  
-   REF  
  
-   UROWID  
  
-   Tabla anidada  
  
 Si los tipos de datos siguientes están presentes en una tabla, impedirán que LogMiner obtenga datos de cualquier columna de la tabla:  
  
-   Tipos de datos definidos por el usuario  
  
-   VARRAY  
  
## <a name="see-also"></a>Vea también  
 [Diseñador de captura de datos modificados para Oracle de Attunity](change-data-capture-designer-for-oracle-by-attunity.md)   
 [La instancia CDC de Oracle](the-oracle-cdc-instance.md)  
  
  