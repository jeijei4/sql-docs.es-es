---
title: Método getCharacterStream (java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerResultSet.getCharacterStream (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: cdddc572-05c1-480d-b3e5-28270001575c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 2b01b2aa7972404318ff4b229a999218be49e812
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80911691"
---
# <a name="getcharacterstream-method-javalangstring"></a>Método getCharacterStream (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el valor del nombre de la columna designada en la fila actual de este objeto [SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md) como un objeto java.io.Reader.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public java.io.Reader getCharacterStream(java.lang.String columnName)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *columnName*  
  
 Valor **String** que contiene el nombre de columna.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto Reader.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método getCharacterStream especifica este método getCharacterStream en la interfaz java.sql.ResultSet.  
  
 Este método solamente leerá tipos de datos de carácter Unicode de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] como nchar, nvarchar, nvarchar(max) y ntext. El resto de tipos de datos, incluso los tipos de carácter ASCII, producirán una excepción. Para leer los tipos de datos ASCII, utilice el método [getAsciiStream](../../../connect/jdbc/reference/getasciistream-method-sqlserverresultset.md).  
  
## <a name="see-also"></a>Consulte también  
 [Método getCharacterStream &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/getcharacterstream-method-sqlserverresultset.md)   
 [Miembros SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Clase SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
