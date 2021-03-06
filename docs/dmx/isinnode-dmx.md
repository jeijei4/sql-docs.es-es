---
title: IsInNode (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 063c436f2e0d76ca891f332f25be385c2f16fdfa
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "86969678"
---
# <a name="isinnode-dmx"></a>IsInNode (DMX)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Indica si el nodo especificado contiene el caso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
IsInNode(<NodeID>)  
```  
  
## <a name="return-type"></a>Tipo de valor devuelto  
 Un tipo booleano.  
  
## <a name="remarks"></a>Observaciones  
 **IsInNode** solo se usa en [SELECT desde &#60;&#62; de modelo. Los casos &#40;DMX&#41;](../dmx/select-from-model-cases-dmx.md) y [seleccionar de &#60;Modelo&#62;. SAMPLE_CASES las consultas &#40;DMX&#41;](../dmx/select-from-model-sample-cases-dmx.md) .  
  
## <a name="examples"></a>Ejemplos  
 El ejemplo siguiente devuelve todos los casos que se han utilizado para crear el modelo que está asociado al nodo especificado en la función IsInNode.  
  
```  
Select * from [TM Decision Tree].Cases  
WHERE IsInNode('0')  
```  
  
## <a name="see-also"></a>Consulte también  
 [Referencia de funciones de extensiones de minería de datos &#40;DMX&#41;](../dmx/data-mining-extensions-dmx-function-reference.md)   
 [Funciones &#40;DMX&#41;](../dmx/functions-dmx.md)   
 [Funciones de predicción generales &#40;DMX&#41;](../dmx/general-prediction-functions-dmx.md)  
  
  
