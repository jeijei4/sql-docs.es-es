---
title: CursorLocationEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CursorLocationEnum
helpviewer_keywords:
- CursorLocationEnum enumeration [ADO]
ms.assetid: acb255ff-1734-4b70-89bb-aef862b4c63b
author: rothja
ms.author: jroth
ms.openlocfilehash: 278f69e504ed4af7589b7e2be2c281e5de5957fa
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760181"
---
# <a name="cursorlocationenum"></a>CursorLocationEnum
Especifica la ubicación del servicio de cursor.  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adUseClient**|3|Utiliza cursores del lado cliente proporcionados por una biblioteca de cursores local. Los servicios de cursor local a menudo permiten muchas características que los cursores proporcionados por el controlador pueden no, por lo que el uso de esta configuración puede proporcionar una ventaja con respecto a las características que se habilitarán. Por compatibilidad con versiones anteriores, también se admite el sinónimo **adUseClientBatch** .|  
|**adUseNone**|1|No utiliza los servicios de cursor. (Esta constante está obsoleta y aparece únicamente por razones de compatibilidad con versiones anteriores).|  
|**adUseServer**|2|Predeterminada. Utiliza cursores proporcionados por el proveedor de datos o el controlador. Estos cursores a veces son muy flexibles y permiten una mayor sensibilidad a los cambios realizados por otros usuarios en el origen de datos. Sin embargo, algunas características del [servicio de cursor de Microsoft para OLE DB](../../../ado/guide/data/the-microsoft-cursor-service-for-ole-db.md), como desasociar<br /><br /> Los objetos de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) no se pueden simular con los cursores del lado servidor y estas características no estarán disponibles con esta configuración.|  
  
## <a name="adowfc-equivalent"></a>Equivalente de ADO/WFC  
 Paquete: **com. ms. wfc. Data**  
  
|Constante|  
|--------------|  
|AdoEnums. CursorLocation. CLIENT|  
|AdoEnums. CursorLocation. NONE|  
|AdoEnums. CursorLocation. SERVER|  
  
## <a name="applies-to"></a>Se aplica a  
 [Propiedad CursorLocation (ADO)](../../../ado/reference/ado-api/cursorlocation-property-ado.md)
