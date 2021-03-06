---
title: Método prepareStatement (java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 02/07/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLServerConnection.prepareStatement (java.lang.String)
apilocation:
- sqljdbc.jar
apitype: Assembly
ms.assetid: e825765c-eb55-4800-951b-f3495da36641
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4b17c514a293f4566c3408e364acccbab721e1ce
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923137"
---
# <a name="preparestatement-method-javalangstring"></a>Método prepareStatement (java.lang.String)

Crea un objeto [SQLServerPreparedStatement](./sqlserverpreparedstatement-class.md) para enviar las instrucciones SQL parametrizadas a la base de datos.

## <a name="syntax"></a>Sintaxis

```
public java.sql.PreparedStatement prepareStatement(java.lang.String sql)
```

#### <a name="parameters"></a>Parámetros
*sql*

Un valor **String** que contiene la instrucción SQL.

## <a name="return-value"></a>Valor devuelto
Un objeto PreparedStatement.

## <a name="exceptions"></a>Excepciones  
[SQLServerException](./sqlserverexception-class.md)

## <a name="remarks"></a>Observaciones
El método prepareStatement especifica este método prepareStatement en la interfaz java.sql.Connection.

## <a name="see-also"></a>Consulte también

[Método prepareStatement &#40;SQLServerConnection&#41;](./preparestatement-method-sqlserverconnection.md)

[Miembros SQLServerConnection](./sqlserverconnection-members.md)

[Clase SQLServerConnection](./sqlserverconnection-class.md)
