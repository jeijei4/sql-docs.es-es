---
title: Objeto Cellset (ADO MD) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Cellset
helpviewer_keywords:
- Cellset object [ADO MD]
ms.assetid: 5e2452c0-cac0-49b2-8099-836c35794d50
author: rothja
ms.author: jroth
ms.openlocfilehash: e50fb60fbde205171c066380a2c2023d485a5a09
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82761773"
---
# <a name="cellset-object-ado-md"></a>Objeto de conjunto de celdas (ADO MD)
Representa los resultados de una consulta multidimensional. Es una colección de celdas seleccionadas de cubos u otros celdas.  
  
## <a name="remarks"></a>Observaciones  
 Los datos de un conjunto de **celdas** se recuperan mediante acceso directo de tipo matriz. Puede explorar en profundidad hasta un miembro específico para obtener datos sobre ese miembro. Por ejemplo, el código siguiente devuelve el título del primer miembro en la primera posición del primer eje de un elemento Cellset denominado `cst` :  
  
```  
cst.Axes(0).Positions(0).Members(0).Caption  
```  
  
## <a name="remarks"></a>Observaciones  
 No hay ninguna noción de celda actual dentro de un Cellset. En su lugar, la propiedad [Item](../../../ado/reference/ado-md-api/item-property-ado-md-cellset.md) recupera un objeto [Cell](../../../ado/reference/ado-md-api/cell-object-ado-md.md) específico del objeto Cellset. Los argumentos de la propiedad **Item** determinan qué celda se recupera. Puede especificar el valor ordinal único de una celda. También puede recuperar las celdas usando sus números de posición a lo largo de cada eje del Cellset. Para obtener más información sobre cómo recuperar celdas, vea la propiedad [Item](../../../ado/reference/ado-md-api/item-property-ado-md-cellset.md) .  
  
 Con las colecciones, los métodos y las propiedades de un objeto **Cellset** , puede hacer lo siguiente:  
  
-   Asociar una conexión abierta a un objeto **Cellset** estableciendo su propiedad [ActiveConnection](../../../ado/reference/ado-md-api/activeconnection-property-ado-md.md) .  
  
-   Ejecutar y recuperar los resultados de una consulta multidimensional con el método [Open](../../../ado/reference/ado-md-api/open-method-ado-md.md) .  
  
-   Recupera una **celda** del objeto **Cellset** con la propiedad [Item](../../../ado/reference/ado-md-api/item-property-ado-md-cellset.md) .  
  
-   Devuelve los objetos de [eje](../../../ado/reference/ado-md-api/axis-object-ado-md.md) que definen el conjunto de **celdas** con la colección de [ejes](../../../ado/reference/ado-md-api/axes-collection-ado-md.md) .  
  
-   Recupera información sobre las dimensiones utilizadas para filtrar los datos del **Cellset** con la propiedad [FilterAxis](../../../ado/reference/ado-md-api/filteraxis-property-ado-md.md) .  
  
-   Devuelve o especifica la consulta utilizada para definir el **Cellset** con la propiedad [source](../../../ado/reference/ado-md-api/source-property-ado-md.md) .  
  
-   Devuelve el estado actual del **Cellset** (abierto, cerrado, en ejecución o en conexión) con la propiedad [State](../../../ado/reference/ado-md-api/state-property-ado-md.md) .  
  
-   Cierre un **Cellset** abierto con el método [Close](../../../ado/reference/ado-md-api/close-method-ado-md.md) .  
  
-   Recupere la información específica del proveedor sobre el conjunto de **celdas** con la colección de [propiedades](../../../ado/reference/ado-api/properties-collection-ado.md) de ADO estándar.  
  
 Esta sección contiene el siguiente tema.  
  
-   [Propiedades, métodos y eventos](../../../ado/reference/ado-md-api/cellset-object-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de Cellset (VB)](../../../ado/reference/ado-md-api/cellset-example-vb.md)   
 [Colección axes (ADO MD)](../../../ado/reference/ado-md-api/axes-collection-ado-md.md)   
 [Objeto Cell (ADO MD)](../../../ado/reference/ado-md-api/cell-object-ado-md.md)   
 [Connection (objeto) (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)   
 [Colección de propiedades (ADO)](../../../ado/reference/ado-api/properties-collection-ado.md)
