---
title: Método getFloat (java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.getFloat (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: b6492341-fdc2-449c-9d03-95a5dadf1bb0
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ae411181007b573eb1b38681872b7d4bff36be24
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80924777"
---
# <a name="getfloat-method-javalangstring"></a>Método getFloat (java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el valor del parámetro designado como un objeto **float** en el lenguaje de programación Java según el nombre de parámetro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public float getFloat(java.lang.String sCol)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *sCol*  
  
 Objeto **String** que contiene el nombre del parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 Un valor **float**.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método getFloat especifica este método getFloat en la interfaz java.sql.CallableStatement.  
  
 Este método devuelve todos los tipos de datos basados en número con fidelidad **float** de Java.  
  
## <a name="see-also"></a>Consulte también  
 [Método getFloat &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/getfloat-method-sqlservercallablestatement.md)   
 [Miembros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Clase SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
