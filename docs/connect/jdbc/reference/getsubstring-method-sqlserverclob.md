---
title: Método getSubString (SQLServerClob) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerClob.getSubString
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: bf915590-a883-4403-befa-5b5bb42f34d8
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: f5409040a5f7bb8cf7c03923da8ff976e4ab08ce
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80926180"
---
# <a name="getsubstring-method-sqlserverclob"></a>Método getSubString (SQLServerClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Devuelve una copia de la subcadena especificada en el objeto CLOB según la posición de inicio indicada y el número de caracteres que se van a copiar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public java.lang.String getSubString(long pos,  
                                     int length)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *pos*  
  
 El primer carácter de la subcadena que se va a extraer. El primer carácter está en la posición 1.  
  
 *length*  
  
 El número de caracteres consecutivos que se van a copiar.  
  
## <a name="return-value"></a>Valor devuelto  
 Un valor **String** que es la subcadena especificada en el objeto CLOB.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método getSubString especifica este método getSubString en la interfaz java.sql.Clob.  
  
 Si se intenta obtener un número de caracteres igual a cero a partir de un CLOB que sea NULL o de longitud cero, se obtiene una cadena vacía. Si se intentar obtener una longitud de caracteres cualquiera en alguna posición que no sea la posición 1 en un CLOB de longitud cero, se producirá una excepción relativa a la posición.  
  
## <a name="see-also"></a>Consulte también  
 [Métodos SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-methods.md)   
 [Miembros SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-members.md)   
 [Clase SQLServerClob](../../../connect/jdbc/reference/sqlserverclob-class.md)  
  
  
