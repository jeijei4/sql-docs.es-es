---
title: CursorTypeEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CursorTypeEnum
helpviewer_keywords:
- CursorTypeEnum enumeration [ADO]
ms.assetid: ffc6e245-4471-42ae-84dd-e85bddfce983
author: rothja
ms.author: jroth
ms.openlocfilehash: 0af12cbad09990add1e5f42c05a68a0d249377fa
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763496"
---
# <a name="cursortypeenum"></a>CursorTypeEnum
Especifica el tipo de cursor utilizado en un objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) .  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adOpenDynamic**|2|Utiliza un cursor dinámico. Las adiciones, cambios y eliminaciones de otros usuarios son visibles y se permiten todos los tipos de movimiento a través del **conjunto de registros** , excepto los marcadores, si el proveedor no los admite.|  
|**adOpenForwardOnly**|0|Predeterminada. Utiliza un cursor de solo avance. Es idéntico a un cursor estático, salvo que solo puede desplazarse hacia delante por los registros. Esto mejora el rendimiento cuando se necesita hacer un solo paso a través de un **conjunto de registros**.|  
|**adOpenKeyset**|1|Utiliza un cursor de conjunto de claves. Como un cursor dinámico, con la excepción de que no se pueden ver los registros que otros usuarios agregan, aunque los registros eliminados por otros usuarios no son accesibles desde el **conjunto de registros**. Los cambios de datos realizados por otros usuarios siguen siendo visibles.|  
|**adOpenStatic**|3|Utiliza un cursor estático, que es una copia estática de un conjunto de registros que puede usar para buscar datos o generar informes. Las adiciones, cambios o eliminaciones de otros usuarios no son visibles.|  
|**adOpenUnspecified**|-1|No especifica el tipo de cursor.|  
  
## <a name="adowfc-equivalent"></a>Equivalente de ADO/WFC  
 Paquete: **com. ms. wfc. Data**  
  
|Constante|  
|--------------|  
|AdoEnums. CursorType. DYNAMIC|  
|AdoEnums. CursorType. FORWARDONLY|  
|AdoEnums. CursorType. KEYSET|  
|AdoEnums. CursorType. STATIC|  
|AdoEnums. CursorType. no especificado|  
  
## <a name="applies-to"></a>Se aplica a  
 [Propiedad CursorType (ADO)](../../../ado/reference/ado-api/cursortype-property-ado.md)
