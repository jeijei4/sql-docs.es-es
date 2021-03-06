---
title: Objeto Key (ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Key
helpviewer_keywords:
- Key object [ADOX]
ms.assetid: 55f116fe-4d56-4892-bffe-0cdd6fc727c9
author: rothja
ms.author: jroth
ms.openlocfilehash: 3b1c14c19fe624de5a6b634cd1adebe018896011
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82746647"
---
# <a name="key-object-adox"></a>Objeto Key (ADOX)
Representa un campo de clave principal, externa o única de una tabla de base de datos.  
  
## <a name="remarks"></a>Comentarios  
 En el código siguiente se crea una nueva **clave**:  
  
```  
Dim obj As New Key  
```  
  
 Con las propiedades y las colecciones de un objeto de **clave** , puede:  
  
-   Identifique la clave con la propiedad [Name](../../../ado/reference/adox-api/name-property-adox.md) .  
  
-   Determine si la clave es principal, externa o única con la propiedad [Type](../../../ado/reference/adox-api/type-property-key-adox.md) .  
  
-   Obtenga acceso a las columnas de base de datos de la clave con la colección de [columnas](../../../ado/reference/adox-api/columns-collection-adox.md) .  
  
-   Especifique el nombre de la tabla relacionada con la propiedad [RelatedTable](../../../ado/reference/adox-api/relatedtable-property-adox.md) .  
  
-   Determine la acción realizada al eliminar o actualizar una clave principal con las propiedades [DeleteRule](../../../ado/reference/adox-api/deleterule-property-adox.md) y [UpdateRule](../../../ado/reference/adox-api/updaterule-property-adox.md) .  
  
 Esta sección contiene el siguiente tema.  
  
-   [Propiedades, métodos y eventos del objeto Key](../../../ado/reference/adox-api/key-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de las propiedades de método Append, tipo de clave, RelatedColumn, RelatedTable y UpdateRule (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Colección de columnas (ADOX)](../../../ado/reference/adox-api/columns-collection-adox.md)   
 [Colección de claves (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)
