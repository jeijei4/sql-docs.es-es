---
title: Z (tipo de datos geometry) | Microsoft Docs
ms.custom: ''
ms.date: 08/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- Z (geometry Data Type)
- Z_(geometry_Data_Type)_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- Z (geometry Data Type)
ms.assetid: a62ed736-44df-4591-9109-ce90e1df9bd3
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 854a5afed2e6764cf9c5224a6c52a6f1284b9ba1
ms.sourcegitcommit: b57d98e9b2444348f95c83a24b8eea0e6c9da58d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86554913"
---
# <a name="z-geometry-data-type"></a>Z (tipo de datos geometry)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

El valor (elevación) Z de la instancia. La semántica del valor de elevación la define el usuario.
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
.Z  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="return-types"></a>Tipos de valor devuelto
 Tipo de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: **float**  
  
 Tipo de CLR: **SqlDouble**  
  
## <a name="remarks"></a>Observaciones  
 Si la instancia de geometry no es un punto, se asignará el valor NULL a esta propiedad, así como a cualquier instancia de **Point** para la que no se establezca dicha propiedad.  
  
 Esta propiedad es de solo lectura.  
  
 Las coordenadas z no se usan en los cálculos realizados por la biblioteca y, por lo tanto, no se incluirán en ninguno de dichos cálculos.  
  
## <a name="examples"></a>Ejemplos  
 En el ejemplo siguiente se crea una instancia de `Point` con valores Z (elevación) y M (medida), y se usa `Z` para capturar el valor Z de la instancia.  
  
```  
DECLARE @g geometry;  
SET @g = geometry::STGeomFromText('POINT(1 2 3 4)', 0);  
SELECT @g.Z;  
```  
  
## <a name="see-also"></a>Consulte también  
 [M &#40;tipo de datos geometry&#41;](../../t-sql/spatial-geometry/m-geometry-data-type.md)   
 [AsTextZM &#40;tipo de datos geometry&#41;](../../t-sql/spatial-geometry/astextzm-geometry-data-type.md)   
 [Métodos extendidos en instancias de geometry](../../t-sql/spatial-geometry/extended-methods-on-geometry-instances.md)  
  
  

