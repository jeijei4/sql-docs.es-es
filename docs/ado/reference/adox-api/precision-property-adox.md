---
title: Propiedad Precision (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Column::put_Precision
- _Column::PutPrecision
- _Column::GetPrecision
- _Column::get_Precision
- _Column::Precision
helpviewer_keywords:
- Precision property [ADOX]
ms.assetid: 0e0ecbbf-d7de-49d4-a128-5a519ecd54ba
author: rothja
ms.author: jroth
ms.openlocfilehash: 67512b74e4c2b869cb7b1f9397462ce5566557a8
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763726"
---
# <a name="precision-property-adox"></a>Precision (propiedad, ADOX)
Indica la precisión máxima de los valores de datos de la [columna](../../../ado/reference/adox-api/column-object-adox.md).  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece y devuelve un valor **Long** que es la precisión máxima de los valores de datos de la columna cuando la propiedad [Type](../../../ado/reference/adox-api/type-property-column-adox.md) es un tipo numérico. La **precisión** se omite para todos los demás tipos de datos.  
  
## <a name="remarks"></a>Observaciones  
 El valor predeterminado es cero (**0**).  
  
 Esta propiedad es de solo lectura para los objetos de [columna](../../../ado/reference/adox-api/column-object-adox.md) ya anexados a una colección.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto Column (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de código ADOX: ejemplo de propiedades NumericScale y Precision (VB)](../../../ado/reference/adox-api/adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Type (propiedad, Column) (ADOX)](../../../ado/reference/adox-api/type-property-column-adox.md)   
 [Objeto Column (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)
