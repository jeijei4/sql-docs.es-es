---
title: Propiedad DataSource (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset20::DataSource
helpviewer_keywords:
- DataSource property [ADO]
ms.assetid: 300a702a-3544-48c5-b759-83b511fe97e0
author: rothja
ms.author: jroth
ms.openlocfilehash: cbaff4a2bf03e524018c0c8d1b163925aa40b3ea
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82763476"
---
# <a name="datasource-property-ado"></a>Propiedad de origen de datos (ADO)
Indica un objeto que contiene los datos que se van a representar como un objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) .  
  
## <a name="remarks"></a>Observaciones  
 Esta propiedad se usa para crear controles enlazados a datos con el entorno de datos. El entorno de datos mantiene colecciones de datos (orígenes de datos) que contienen objetos con nombre (miembros de datos) que se representarán como un objeto de **conjunto de registros** .  
  
 Las propiedades [DataMember](../../../ado/reference/ado-api/datamember-property.md) y **DataSource** deben usarse conjuntamente.  
  
 El objeto al que se hace referencia debe implementar la interfaz **IDataSource** y debe contener una interfaz **IRowset** .  
  
## <a name="usage"></a>Uso  
  
```  
Dim rs as New ADODB.Recordset  
rs.DataMember = "Command"     'Name of the rowset to bind to.  
Set rs.DataSource = myDE      'Name of the object containing an IRowset.  
```  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte también  
 [Propiedad DataMember](../../../ado/reference/ado-api/datamember-property.md)
