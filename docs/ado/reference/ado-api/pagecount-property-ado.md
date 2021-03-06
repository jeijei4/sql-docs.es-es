---
title: PageCount (propiedad) (ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Recordset15::PageCount
helpviewer_keywords:
- PageCount property [ADO]
ms.assetid: b601b56c-0ac4-44ee-bc91-c3d2d104f00a
author: rothja
ms.author: jroth
ms.openlocfilehash: 7ebb85eee8ea976f1ef078ebfe22eca195081bba
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82762009"
---
# <a name="pagecount-property-ado"></a>PageCount (propiedad, ADO)
Indica el número de páginas de datos que contiene el objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) .  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve un valor de **tipo Long** que indica el número de páginas del **conjunto de registros**.  
  
## <a name="remarks"></a>Observaciones  
 Use la propiedad **PageCount** para determinar el número de páginas de datos que se encuentran en el objeto de **conjunto de registros** . *Las páginas* son grupos de registros cuyo tamaño es igual al valor de la propiedad [pageSize](../../../ado/reference/ado-api/pagesize-property-ado.md) . Incluso si la última página está incompleta porque hay menos registros que el valor de **pageSize** , cuenta como página adicional en el valor de **PageCount** . Si el objeto de **conjunto de registros** no admite esta propiedad, el valor será-1 para indicar que **PageCount** es Indeterminista.  
  
 Vea las propiedades **pageSize** y [AbsolutePage](../../../ado/reference/ado-api/absolutepage-property-ado.md) para obtener más información sobre la funcionalidad de la página.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto de conjunto de registros (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de propiedades AbsolutePage, PageCount y PageSize (VB)](../../../ado/reference/ado-api/absolutepage-pagecount-and-pagesize-properties-example-vb.md)   
 [Ejemplo de propiedades AbsolutePage, PageCount y PageSize (VC + +)](../../../ado/reference/ado-api/absolutepage-pagecount-and-pagesize-properties-example-vc.md)   
 [Propiedad AbsolutePage (ADO)](../../../ado/reference/ado-api/absolutepage-property-ado.md)   
 [PageSize (propiedad, ADO)](../../../ado/reference/ado-api/pagesize-property-ado.md)   
 [Propiedad RecordCount (ADO)](../../../ado/reference/ado-api/recordcount-property-ado.md)
