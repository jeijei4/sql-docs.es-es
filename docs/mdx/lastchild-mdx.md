---
title: LastChild (MDX) | Microsoft Docs
ms.date: 06/04/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: mdx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 08f1f71497861ee1a946019ed547f40a0d6037ec
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68098540"
---
# <a name="lastchild-mdx"></a>LastChild (MDX)


  Devuelve el último elemento secundario de un miembro especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Member_Expression.LastChild   
```  
  
## <a name="arguments"></a>Argumentos  
 *Member_Expression*  
 Expresión MDX válida que devuelve un miembro.  
  
### <a name="example"></a>Ejemplo  
 El ejemplo siguiente devuelve el valor para septiembre de 2001, que es el último elemento secundario del primer trimestre fiscal del año fiscal 2002.  
  
```  
SELECT [Date].[Fiscal].[Fiscal Quarter].[Q1 FY 2002].LastChild ON 0  
FROM [Adventure Works]  
```  
  
## <a name="see-also"></a>Consulte también  
 [FirstChild &#40;&#41;MDX](../mdx/firstchild-mdx.md)   
 [Referencia de funciones MDX &#40;MDX&#41;](../mdx/mdx-function-reference-mdx.md)  
  
  
