---
title: Método getDriverVersion (SQLServerDatabaseMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDatabaseMetaData.getDriverVersion
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 3be84d65-af61-4c34-b052-74a5d488eaa9
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 1066be205916f23747da8fdd61a3ebf0784742ad
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80902101"
---
# <a name="getdriverversion-method-sqlserverdatabasemetadata"></a>Método getDriverVersion (SQLServerDatabaseMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el número de versión de este controlador JDBC.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public java.lang.String getDriverVersion()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Un valor **String** que contiene la versión del controlador JDBC.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método getDriverVersion especifica este método getDriverVersion en la interfaz java.sql.DatabaseMetaData.  
  
## <a name="see-also"></a>Consulte también  
 [Métodos SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-methods.md)   
 [Miembros SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-members.md)   
 [Clase SQLServerDatabaseMetaData](../../../connect/jdbc/reference/sqlserverdatabasemetadata-class.md)  
  
  
