---
title: Método getCharacterStream (long, long) (SQLServerNClob) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 5a8028bc-c877-4668-b662-0746d462040e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 69b626e84288764fbe1da34ac0a5e6430eaa8217
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80913151"
---
# <a name="getcharacterstream-method-long-long-sqlservernclob"></a>Método getCharacterStream (long, long) (SQLServerNClob)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera los datos **NCLOB** como un objeto **Reader** o como un flujo de caracteres con una posición y longitud especificadas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public java.io.Reader getCharacterStream(long pos,  
                                  long length)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *pos*  
  
 Un valor **long** que indica el desplazamiento al primer carácter del valor parcial que se va a recuperar.  
  
 *length*  
  
 Un valor **long** que indica la longitud en caracteres del valor parcial que se va a recuperar.  
  
## <a name="return-value"></a>Valor devuelto  
 Un objeto Reader que contiene los datos **NCLOB**.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método getCharacterStream especifica este método getCharacterStream en la interfaz java.sql.NClob.  
  
## <a name="see-also"></a>Consulte también  
 [Método getCharacterStream &#40;SQLServerNClob&#41;](../../../connect/jdbc/reference/getcharacterstream-method-sqlservernclob.md)   
 [Métodos SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-methods.md)   
 [Miembros SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-members.md)   
 [Clase SQLServerNClob](../../../connect/jdbc/reference/sqlservernclob-class.md)  
  
  
