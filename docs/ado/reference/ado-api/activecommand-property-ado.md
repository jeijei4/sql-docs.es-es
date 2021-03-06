---
title: Propiedad ActiveCommand (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset20::ActiveCommand
helpviewer_keywords:
- ActiveCommand property [ADO]
ms.assetid: fb4088d5-5968-42d6-aeaa-3955046bb4da
author: rothja
ms.author: jroth
ms.openlocfilehash: b89876366c80d20bde110da9e9d86414873e86bc
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82747479"
---
# <a name="activecommand-property-ado"></a>Propiedad ActiveCommand (ADO)
Indica el objeto de [comando](../../../ado/reference/ado-api/command-object-ado.md) que creó el objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) asociado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve un **valor de tipo Variant** que contiene un objeto **Command** . El valor predeterminado es una referencia de objeto null.  
  
## <a name="remarks"></a>Comentarios  
 La propiedad **ActiveCommand** es de solo lectura.  
  
 Si un objeto de **comando** no se utilizó para crear el **conjunto de registros**actual, se devuelve una referencia de objeto **null** .  
  
 Utilice esta propiedad para buscar el objeto de **comando** asociado cuando solo se le proporciona el objeto de **conjunto de registros** resultante.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de la propiedad ActiveCommand (VB)](../../../ado/reference/ado-api/activecommand-property-example-vb.md)   
 [Ejemplo de la propiedad ActiveCommand (JScript)](../../../ado/reference/ado-api/activecommand-property-example-jscript.md)   
 [Ejemplo de la propiedad ActiveCommand (VC + +)](../../../ado/reference/ado-api/activecommand-property-example-vc.md)   
 [Objeto Command (ADO)](../../../ado/reference/ado-api/command-object-ado.md)
