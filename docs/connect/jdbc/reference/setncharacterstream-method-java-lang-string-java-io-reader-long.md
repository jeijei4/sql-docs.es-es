---
title: 'Método setNCharacterStream para el objeto Reader: long | Microsoft Docs'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: af9a1ba8-7980-43fa-88e5-14f6cc5e897c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: df5e8bf7e1d4bd1d8f355d7b324aab2537de4e34
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80924929"
---
# <a name="setncharacterstream-method-javalangstring-javaioreader-long"></a>Método setNCharacterStream (java.lang.String, java.io.Reader, long)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Establece el parámetro designado en el objeto Reader especificado, que es el número de caracteres indicado para la longitud.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public final void setNCharacterStream(java.lang.String parameterName,  
                     java.io.Reader value,  
                     long length)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *parameterName*  
  
 Un valor **String** que indica el nombre del parámetro.  
  
 *value*  
  
 Un objeto Reader.  
  
 *length*  
  
 Un valor **long** que indica el número de caracteres en el flujo.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método setNCharacterStream especifica este método setNCharacterStream en la interfaz java.sql.CallableStatement.  
  
 Este método se debe usar para los tipos de datos **NCHAR**, **NVARCHAR**, **NTEXT** y **XML**.  
  
 Si la longitud del flujo es distinta a la especificada en el parámetro *length*, el controlador JDBC produce una excepción cuando la fila se actualiza o se inserta.  
  
 Si se desconoce la longitud del flujo, el parámetro *length* puede establecerse en -1 para indicar que el controlador debe aceptar el flujo independientemente de su longitud. Con sqljdbc4.jar, se recomienda usar el método [setNCharacterStream &#40;java.lang.String, java.io.Reader&#41;](../../../connect/jdbc/reference/setncharacterstream-method-java-lang-string-java-io-reader.md) de JDBC 40 si la aplicación quiere actualizar la columna a partir de un flujo cuya longitud se desconoce.  
  
## <a name="see-also"></a>Consulte también  
 [Método setNCharacterStream &#40;SQLServerCallableStatement&#41;](../../../connect/jdbc/reference/setncharacterstream-method-sqlservercallablestatement.md)   
 [Miembros SQLServerCallableStatement](../../../connect/jdbc/reference/sqlservercallablestatement-members.md)  
  
  
