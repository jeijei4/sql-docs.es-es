---
title: Método setCharacterStream (java.lang.String, java.io.Reader, int) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerCallableStatement.setCharacterStream
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 88a8e89e-8817-4161-85b1-9a9a2fd01cdb
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 0eefbe4265b81017e402b60547a8916d7a137bf4
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80929067"
---
# <a name="setcharacterstream-method-javalangstring-javaioreader-int"></a>Método setCharacterStream (java.lang.String, java.io.Reader, int)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece el parámetro designado en el objeto specifiedReader especificado, que es el número de caracteres especificado para la longitud.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public final void setCharacterStream(java.lang.String parameterName,  
                              java.io.Reader value,  
                              int length)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *parameterName*  
  
 Valor **string** que contiene el nombre del parámetro.  
  
 *value*  
  
 Un objeto Reader que contiene los datos Unicode.  
  
 *length*  
  
 Un valor **int** que indica la longitud en número de caracteres.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método setCharacterStream especifica este método setCharacterStream en la interfaz java.sql.CallableStatement.  
  
 Si la longitud del flujo es distinta a la especificada en el parámetro *length*, el controlador JDBC produce una excepción cuando la fila se actualiza o se inserta.  
  
 Si se desconoce la longitud del flujo, el parámetro *length* puede establecerse en -1 para indicar que el controlador debe aceptar el flujo independientemente de su longitud. Con sqljdbc4.jar, recomendamos utilizar el [Método setCharacterStream (java.lang.String, java.io.Reader)](../../../connect/jdbc/reference/setcharacterstream-method-java-lang-string-java-io-reader.md) de JDBC 4.0 cuando la aplicación desee actualizar la columna a partir de un flujo cuya longitud se desconozca.  
  
## <a name="see-also"></a>Consulte también  
 [Miembros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)   
 [Clase SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-class.md)  
  
  
