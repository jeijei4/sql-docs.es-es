---
title: Propiedad direction | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Parameter::Direction
helpviewer_keywords:
- Direction property
ms.assetid: d5732578-3434-4dcd-a9f7-db1abd1b3b94
author: rothja
ms.author: jroth
ms.openlocfilehash: 2e3f098c0f0351a4439b9bb6fb6256209ea3e1ad
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82757181"
---
# <a name="direction-property"></a>Propiedad Direction
Indica si el [parámetro](../../../ado/reference/ado-api/parameter-object.md) representa un parámetro de entrada, un parámetro de salida, una entrada y un parámetro de salida, o si el parámetro es el valor devuelto de un procedimiento almacenado.  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece o devuelve un valor de [ParameterDirectionEnum](../../../ado/reference/ado-api/parameterdirectionenum.md) .  
  
## <a name="remarks"></a>Observaciones  
 Utilice la propiedad **Direction** para especificar cómo se pasa un parámetro a un procedimiento o desde él. La propiedad **Direction** es de lectura/escritura; Esto le permite trabajar con proveedores que no devuelven esta información o establecer esta información cuando no desea que ADO realice una llamada adicional al proveedor para recuperar información de parámetros.  
  
 No todos los proveedores pueden determinar la dirección de los parámetros en sus procedimientos almacenados. En estos casos, debe establecer la propiedad **Direction** antes de ejecutar la consulta.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto Parameter](../../../ado/reference/ado-api/parameter-object.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de las propiedades ActiveConnection, CommandText, CommandTimeout, CommandType, size y Direction (VB)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vb.md)   
 [Ejemplo de las propiedades ActiveConnection, CommandText, CommandTimeout, CommandType, size y Direction (VC + +)](../../../ado/reference/ado-api/activeconnection-commandtext-commandtimeout-commandtype-size-example-vc.md)   
 [Ejemplo de las propiedades ActiveConnection, CommandText, CommandTimeout, CommandType, size y Direction (JScript)](../../../ado/reference/ado-api/activeconnection-commandtext-timeout-type-size-example-jscript.md)
