---
title: CREATE MEASURE (instrucción, MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 3bac5d7d067186e2b84277a5c0dc02cd31cba011
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "86967386"
---
# <a name="mdx-data-definition---create-measure"></a>Definición de datos de MDX: CREATE MEASURE


  Crea una medida en un modelo tabular.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
CREATE MEASURE Table_Name[Measure_Name] = DAX_Expression  
[; CREATE MEASURE ...n]  
  
```  
  
## <a name="arguments"></a>Argumentos  
 *Table_Name*  
 Literal de cadena válido que proporciona el nombre de la tabla donde se creará la medida.  
  
 *Measure_Name*  
 Literal de cadena válida que proporciona un nombre de medida.  
  
 *DAX_Expression*  
 Expresión DAX válida que devuelve un solo valor escalar.  
  
## <a name="remarks"></a>Observaciones  
 El *Measure_Name* debe ir entre paréntesis.  
  
 La instrucción CREATE MEASURE solo se puede usar dentro de una definición de script MDX; Vea el [elemento MdxScript &#40;ASSL&#41;](https://docs.microsoft.com/analysis-services/assl/objects/mdxscript-element-assl?view=asallproducts-allversions).  
  
 También puede definir un miembro calculado para su uso en una sola consulta. Para definir un miembro calculado limitado a una sola consulta, use la cláusula WITH de la instrucción SELECT. Para obtener más información, vea [crear medidas en MDX](https://docs.microsoft.com/analysis-services/multidimensional-models/mdx/mdx-building-measures).  
  
## <a name="see-also"></a>Consulte también  
 [Instrucciones de definición de datos de MDX &#40;MDX&#41;](../mdx/mdx-data-definition-statements-mdx.md)  
  
  
