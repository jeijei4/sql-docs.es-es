---
title: Método getResponseBuffering (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.getResponseBuffering()
apilocation:
- SQLServerDataSource.getResponseBuffering()
apitype: Assembly
ms.assetid: 19585a93-88a4-415e-a20e-12ba58cddeaa
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7710a9c900867e273156690edc0d8961eb08c345
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80921878"
---
# <a name="getresponsebuffering-method-sqlserverdatasource"></a>Método getResponseBuffering (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Devuelve el método de almacenamiento en búfer de respuesta para este objeto [SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public java.lang.String getResponseBuffering()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto **String** que contiene un atributo **full** o **adaptive** en minúscula.  
  
## <a name="remarks"></a>Observaciones  
 El valor **full** se especifica mediante la lectura del resultado completo desde el servidor en el tiempo de ejecución.  
  
 El valor **adaptive** especifica que se almacenen en búfer los menos datos posibles cuando sea necesario. El valor **adaptive** es el modo de almacenamiento en búfer predeterminado.  
  
 Para más información sobre cómo utilizar el modo de almacenamiento en búfer de respuesta, vea [Empleo de almacenamiento en búfer adaptable](../../../connect/jdbc/using-adaptive-buffering.md).  
  
## <a name="see-also"></a>Consulte también  
 [Método setResponseBuffering &#40;SQLServerDataSource&#41;](../../../connect/jdbc/reference/setresponsebuffering-method-sqlserverdatasource.md)   
 [Miembros SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Clase SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
