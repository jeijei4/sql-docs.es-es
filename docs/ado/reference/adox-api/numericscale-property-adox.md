---
title: NumericScale (propiedad, ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- _Column::PutNumericScale
- _Column::GetNumericScale
- _Column::NumericScale
- _Column::put_NumericScale
- _Column::get_NumericScale
helpviewer_keywords:
- NumericScale property [ADOX]
ms.assetid: 573ee5d1-57c7-4a27-be79-a0e12944ad9b
author: rothja
ms.author: jroth
ms.openlocfilehash: a0a0090a24207e6faad1b14aa3cb5afd6091bc87
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763816"
---
# <a name="numericscale-property-adox"></a>NumericScale (propiedad, ADOX)
Indica la escala de un valor numérico de la columna.  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece y devuelve un valor de **byte** que es la escala de los valores de datos de la columna cuando la propiedad [Type](../../../ado/reference/adox-api/type-property-column-adox.md) es **adNumeric** o **adDecimal**. **NumericScale** se omite para todos los demás tipos de datos.  
  
## <a name="remarks"></a>Observaciones  
 El valor predeterminado es cero (0).  
  
 **NumericScale** es de solo lectura para los objetos de [columna](../../../ado/reference/adox-api/column-object-adox.md) ya anexados a una colección.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto Column (ADOX)](../../../ado/reference/adox-api/column-object-adox.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de código ADOX: ejemplo de propiedades NumericScale y Precision (VB)](../../../ado/reference/adox-api/adox-code-example-numericscale-and-precision-properties-example-vb.md)   
 [Type (propiedad, columna, ADOX)](../../../ado/reference/adox-api/type-property-column-adox.md)
