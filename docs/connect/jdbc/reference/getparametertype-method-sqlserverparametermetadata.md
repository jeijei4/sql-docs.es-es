---
title: Método getParameterType (SQLServerParameterMetaData) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerParameterMetaData.getParameterType
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: 638aca05-63e4-4d73-a9c8-e0442f775720
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: ff46f64ffef7c4c0d0438332720deff32a0c86ea
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80904573"
---
# <a name="getparametertype-method-sqlserverparametermetadata"></a>Método getParameterType (SQLServerParameterMetaData)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Recupera el tipo SQL del parámetro designado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public int getParameterType(int param)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *param*  
  
 Un valor **int** que indica el índice del parámetro.  
  
## <a name="return-value"></a>Valor devuelto  
 Un valor **int** que indica el código del tipo JDBC tal como queda definido en java.sql.Types.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método getParameterType especifica este método getParameterType en la interfaz java.sql.ParameterMetaData.  
  
## <a name="see-also"></a>Consulte también  
 [Métodos SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-methods.md)   
 [Miembros SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [Clase SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-class.md)  
  
  
