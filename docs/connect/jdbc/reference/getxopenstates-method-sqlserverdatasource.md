---
title: Método getXopenStates (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerDataSource.getXopenStates
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: de6fdf6b-8345-4490-b35e-7115b61e782e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c4367bd0df42400d2fd9352ae86dc43e4e98b801
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80910131"
---
# <a name="getxopenstates-method-sqlserverdatasource"></a>Método getXopenStates (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Devuelve un valor **boolean** que indica si está habilitada la conversión de estados SQL a estados conformes a XOPEN.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public boolean getXopenStates()  
```  
  
## <a name="return-value"></a>Valor devuelto  
 **true** si está habilitada la conversión de estados SQL a estados conformes a XOPEN. De lo contrario, se devuelve el valor **False**.  
  
## <a name="remarks"></a>Observaciones  
 Si la propiedad xopenStates se establece en **true**, el [!INCLUDE[jdbcNoVersion](../../../includes/jdbcnoversion_md.md)] convertirá los estados SQL en estados conformes a XOPEN. El valor predeterminado es **false**, que hace que el controlador JDBC genere códigos de estado de SQL 99. Si no se establece xopenStates, el método getXopenStates devuelve el valor predeterminado **false**.  
  
## <a name="see-also"></a>Consulte también  
 [Miembros SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Clase SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
