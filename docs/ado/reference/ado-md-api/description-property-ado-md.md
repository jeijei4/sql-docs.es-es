---
title: Propiedad Description (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Member::Description
- Level::Description
- CubeDef::Description
- Hierarchy::Description
- Description
- Dimension::Description
helpviewer_keywords:
- Description property [ADO MD]
ms.assetid: 6d626d35-0bf3-4f24-9934-ad9c9c91273a
author: rothja
ms.author: jroth
ms.openlocfilehash: b7a338d3e157c39389a7f6911dd04d9c5fb25740
ms.sourcegitcommit: 216f377451e53874718ae1645a2611cdb198808a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87242515"
---
# <a name="description-property-ado-md"></a>Description (propiedad) (ADO MD)
Devuelve una explicación de texto del objeto actual.  
  
## <a name="return-values"></a>Valores devueltos  
 Devuelve una **cadena** y es de solo lectura.  
  
## <a name="remarks"></a>Observaciones  
 En el caso de los objetos [miembro](../../../ado/reference/ado-md-api/member-object-ado-md.md) , la **Descripción** solo se aplica a los miembros Measure y formula. **Description** devuelve una cadena vacía ("") para todos los demás tipos de miembros. Para obtener más información sobre los distintos tipos de miembros, vea la propiedad [Type](../../../ado/reference/ado-md-api/type-property-ado-md.md) .  
  
 Esta propiedad solo se admite en los objetos **member** que pertenezcan a un objeto [LEVEL](../../../ado/reference/ado-md-api/level-object-ado-md.md) . Se produce un error cuando se hace referencia a esta propiedad desde objetos **member** que pertenecen a un objeto [Position](../../../ado/reference/ado-md-api/position-object-ado-md.md) .  
  
## <a name="applies-to"></a>Se aplica a  

:::row:::
    :::column:::
        [Objeto CubeDef (ADO MD)](../../../ado/reference/ado-md-api/cubedef-object-ado-md.md)  
        [Objeto de dimensión (ADO MD)](../../../ado/reference/ado-md-api/dimension-object-ado-md.md)  
    :::column-end:::
    :::column:::
        [Objeto Hierarchy (ADO MD)](../../../ado/reference/ado-md-api/hierarchy-object-ado-md.md)  
        [Objeto Level (ADO MD)](../../../ado/reference/ado-md-api/level-object-ado-md.md)  
    :::column-end:::
    :::column:::
        [Objeto de miembro (ADO MD)](../../../ado/reference/ado-md-api/member-object-ado-md.md)  
    :::column-end:::
:::row-end:::
