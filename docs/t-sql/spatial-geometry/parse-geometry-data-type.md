---
title: Parse (tipo de datos geometry) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
dev_langs:
- TSQL
helpviewer_keywords:
- Parse (geometry Data Type)
ms.assetid: 6e080919-4b64-46cd-8dd2-254a9c232e53
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 48a7a94cea5334a1644dd5a886298b70bea06e47
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86555103"
---
# <a name="parse-geometry-data-type"></a>Parse (tipo de datos geometry)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

Devuelve una instancia de **geometry** a partir de una representación Well-Known Text (WKT) de Open Geospatial Consortium (OGC). `Parse()` es equivalente a [STGeomFromText()](../../t-sql/spatial-geometry/parse-geometry-data-type.md), con la excepción de que presupone un identificador de referencia espacial (SRID) de 0 como parámetro. La entrada puede incluir valores opcionales para Z (elevación) y M (medida).
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Parse ( 'geometry_tagged_text' )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Argumentos
 *geometry_tagged_text*  
 Es la representación WKT de la instancia de **geometry** que se quiere devolver. *geometry_tagged_text* es una expresión **nvarchar**.  
  
## <a name="return-types"></a>Tipos de valor devuelto  
 Tipo de valor devuelto de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **geometry**  
  
 Tipo de valor devuelto de CLR: **SqlGeometry**  
  
## <a name="remarks"></a>Observaciones  
 El tipo OGC de la instancia de **geometry** devuelta por `Parse()` se establece en la entrada WKT correspondiente.  
  
 La cadena "Null" se interpretará como una instancia NULL de **geometry**.  
  
 Este método produce una excepción **FormatException** si la entrada no tiene el formato correcto.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se usa `Parse()` para crear una instancia de `geometry`.  
  
```  
DECLARE @g geometry;   
SET @g = geometry::Parse('LINESTRING (100 100, 20 180, 180 180)');  
SELECT @g.ToString();  
```  
  
## <a name="see-also"></a>Consulte también  
 [STGeomFromText](../../t-sql/spatial-geometry/parse-geometry-data-type.md)   
 [Métodos de geometría estáticos ampliados](../../t-sql/spatial-geometry/extended-static-geometry-methods.md)  
  
  

