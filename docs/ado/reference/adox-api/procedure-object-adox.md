---
title: Procedure (objeto, ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Procedure
helpviewer_keywords:
- Procedure object [ADOX]
ms.assetid: 927bcf3e-32f5-4a80-98d3-600779f0732e
author: rothja
ms.author: jroth
ms.openlocfilehash: 4a56088e47a9f794f1862ef87bf142a8d3ab12c4
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763696"
---
# <a name="procedure-object-adox"></a>Objeto Procedure (ADOX)
Representa un procedimiento almacenado. Cuando se usa junto con el objeto de [comando](../../../ado/reference/ado-api/command-object-ado.md) de ADO, el objeto de **procedimiento** se puede utilizar para agregar, eliminar o modificar procedimientos almacenados.  
  
## <a name="remarks"></a>Observaciones  
 El objeto de **procedimiento** permite crear un procedimiento almacenado sin necesidad de conocer o utilizar la sintaxis de "Create procedure" del proveedor.  
  
 Con las propiedades de un objeto de **procedimiento** , puede:  
  
-   Identifique el procedimiento con la propiedad [Name](../../../ado/reference/adox-api/name-property-adox.md) .  
  
-   Especifique el objeto **Command** de ADO que se puede utilizar para crear o ejecutar el procedimiento con la propiedad [Command](../../../ado/reference/adox-api/command-property-adox.md) .  
  
-   Devuelve información de fecha con las propiedades [DateCreated](../../../ado/reference/adox-api/datecreated-property-adox.md) y [DateModified](../../../ado/reference/adox-api/datemodified-property-adox.md) .  
  
 Esta sección contiene el siguiente tema.  
  
-   [Propiedades, métodos y eventos del objeto Procedure](../../../ado/reference/adox-api/procedure-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de propiedades Command y CommandText (VB)](../../../ado/reference/adox-api/command-and-commandtext-properties-example-vb.md)   
 [Ejemplo de propiedad de comando, colección de parámetros (VB)](../../../ado/reference/adox-api/parameters-collection-command-property-example-vb.md)   
 [Ejemplo de método Append de procedimientos (VB)](../../../ado/reference/adox-api/procedures-append-method-example-vb.md)   
 [Ejemplo de método Delete de procedimientos (VB)](../../../ado/reference/adox-api/procedures-delete-method-example-vb.md)   
 [Colección de procedimientos (ADOX)](../../../ado/reference/adox-api/procedures-collection-adox.md)
