---
title: Método insertRow (SQLServerResultSet) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.insertRow
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 363d1008-1396-4fc0-8e27-c9ba2499e7f1
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 194df3470eead10c0f32288f54b36a82e807e576
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80909931"
---
# <a name="insertrow-method-sqlserverresultset"></a>Método insertRow (SQLServerResultSet)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Agrega el contenido de la fila de inserción a este objeto [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) y a la base de datos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void insertRow()  
```  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método insertRow especifica este método insertRow en la interfaz java.sql.ResultSet.  
  
 Cuando se llama a este método, el cursor debe estar en la fila de inserción. Una vez se llame a este método, el cursor permanece en la fila de inserción y el conjunto de resultados permanece en modo de inserción.  
  
## <a name="see-also"></a>Consulte también  
 [Miembros SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Clase SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
