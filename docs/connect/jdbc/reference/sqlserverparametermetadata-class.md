---
title: Clase SQLServerParameterMetaData | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 546290e0-9411-4a2b-aa36-61251e70e9cf
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 99a81b89c0707d4d278a886bd7bbcbceb58d6068
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80923874"
---
# <a name="sqlserverparametermetadata-class"></a>Clase SQLServerParameterMetaData
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Representa los metadatos para los parámetros de instrucción preparados.  
  
 **Paquete:** com.microsoft.sqlserver.jdbc  
  
 **Extiende:** java.lang.Object  
  
 **Implementa:** java.sql.ParameterMetaData  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public class SQLServerParameterMetaData  
```  
  
## <a name="remarks"></a>Observaciones  
 Para recuperar los metadatos de parámetro, las instrucciones preparadas se ejecutan con SET FMT ONLY. Las instrucciones invocables llaman a sp_sproc_columns para recuperar nombres y metadatos para los parámetros de procedimiento.  
  
## <a name="see-also"></a>Consulte también  
 [Miembros SQLServerParameterMetaData](../../../connect/jdbc/reference/sqlserverparametermetadata-members.md)   
 [Referencia de API del controlador JDBC](../../../connect/jdbc/reference/jdbc-driver-api-reference.md)  
  
  
