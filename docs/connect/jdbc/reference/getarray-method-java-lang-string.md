---
title: Método getArray (java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.getArray (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 4610cbaf-5638-4a66-bd83-70aefca40e58
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: da3009077e1befd4f685a362ad6e224f988a1d01
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80912191"
---
# <a name="getarray-method-javalangstring"></a>Método getArray (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el valor del parámetro designado como un objeto Array según el nombre de parámetro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public java.sql.Array getArray(java.lang.String sCol)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *sCol*  
  
 Objeto **String** que contiene el nombre del parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto Array.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método getArray especifica este método getArray en la interfaz java.sql.CallableStatement.  
  
## <a name="see-also"></a>Consulte también  
 [Método getArray &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/getarray-method-sqlservercallablestatement.md)   
 [Miembros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Clase SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
