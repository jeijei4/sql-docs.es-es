---
title: Método executeBatch (SQLServerStatement) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerStatement.executeBatch
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: fb034f63-2532-4da8-a1b0-bc125734585a
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 46b738dfe180b6d137b47042a9b9db517cb3b93c
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80922045"
---
# <a name="executebatch-method-sqlserverstatement"></a>Método executeBatch (SQLServerStatement)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Envía un lote de comandos a la base de datos para que se ejecute. Si todos los comandos se ejecutan correctamente, devuelve una matriz de recuentos de actualizaciones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public int[] executeBatch()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Una matriz de **int** que contiene los recuentos de la actualización.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
 java.sql.BatchUpdateException  
  
## <a name="remarks"></a>Observaciones  
 El método executeBatch especifica este método executeBatch en la interfaz java.sql.Statement.  
  
 Después de enviar los comandos a la base de datos, este método borra cualquier comando del lote.  
  
## <a name="see-also"></a>Consulte también  
 [Miembros SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-members.md)   
 [Clase SQLServerStatement](../../../connect/jdbc/reference/sqlserverstatement-class.md)  
  
  
