---
title: Método wasNull (SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.wasNull
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: d37f80ef-d72c-4429-ada3-1d685bdab6d7
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4e1647f67f8967b1c5802061f829bcc8504fe557
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80919448"
---
# <a name="wasnull-method-sqlserverresultset"></a>Método wasNull (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Comprueba si la última lectura del valor dio como resultado un valor NULL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public boolean wasNull()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Es **true** si el último valor que se ha leído es NULL. De lo contrario, se devuelve el valor **False**.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método wasNull lo especifica el método wasNull en la interfaz java.sql.ResultSet.  
  
## <a name="see-also"></a>Consulte también  
 [Miembros SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Clase SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
