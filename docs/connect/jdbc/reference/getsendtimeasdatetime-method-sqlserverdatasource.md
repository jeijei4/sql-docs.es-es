---
title: Método getSendTimeAsDatetime (SQLServerDataSource) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 02287122-5dc1-455d-987f-95fd9a69d503
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 018d40464d6461cb4182daf5f93139e322517870
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80929208"
---
# <a name="getsendtimeasdatetime-method-sqlserverdatasource"></a>Método getSendTimeAsDatetime (SQLServerDataSource)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Este método se agregó en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] JDBC Driver 3.0.  
  
 Devuelve el valor de la propiedad de conexión **SendTimeAsDatetime**.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public boolean getSendTimeAsDatetime();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Es **true** si los valores de java.sql.Time se enviarán al servidor como un tipo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]datetime**de**. Es **false** si los valores de java.sql.Time se enviarán al servidor como un tipo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]time**de**.  
  
## <a name="remarks"></a>Observaciones  
 Consulte [Establecimiento de las propiedades de conexión](../../../connect/jdbc/setting-the-connection-properties.md) para más información sobre la propiedad de conexión **sendTimeAsDatetime**.  
  
 Con [SQLServerDataSource.setSendTimeAsDatetime](../../../connect/jdbc/reference/setsendtimeasdatetime-method-sqlserverdatasource.md) puede establecer mediante programación la propiedad de conexión **sendTimeAsDatetime**.  
  
 Para más información, vea [Configurar el modo en que los valores java.sql.Time se envían al servidor](../../../connect/jdbc/configuring-how-java-sql-time-values-are-sent-to-the-server.md).  
  
## <a name="see-also"></a>Consulte también  
 [Miembros SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-members.md)   
 [Clase SQLServerDataSource](../../../connect/jdbc/reference/sqlserverdatasource-class.md)  
  
  
