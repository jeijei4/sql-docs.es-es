---
title: Método getMaxFieldSize (SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.getMaxFieldSize
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: ed7bbcb8-660b-4e9b-8241-e216c42826f9
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: dc1fd6ebd8c526762bca61b97f6fbb01f4ee93ff
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80906941"
---
# <a name="getmaxfieldsize-method-sqlserverstatement"></a>Método getMaxFieldSize (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el número máximo de bytes que se pueden devolver para valores de columna de caracteres y binarios en un objeto [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) que haya generado este objeto [ISQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public final int getMaxFieldSize()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Un valor **int** que indica el número máximo de bytes que puede contener una columna; es 0 si no hay límites.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 Este método getMaxFieldSize especifica este método getMaxFieldSize en la interfaz java.sql.Statement.  
  
## <a name="see-also"></a>Consulte también  
 [Métodos SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-methods.md)   
 [Clase SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
