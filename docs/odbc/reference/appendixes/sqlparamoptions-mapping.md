---
title: Asignación de SQLParamOptions | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- mapping deprecated functions [ODBC], SQLParamOptions
- SQLParamOptions function [ODBC], mapping
ms.assetid: 57ed65f6-9620-4738-b331-19d2a2b5cae4
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 3b083800b660b8ccd26da747e4caf745531188e5
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300565"
---
# <a name="sqlparamoptions-mapping"></a>Asignación de SQLParamOptions
Cuando una aplicación llama a **SQLParamOptions** a través de un controlador ODBC *3. x* , la llamada a  
  
```  
SQLParamOptions(hstmt, crow, piRow);  
```  
  
 se asignará a dos llamadas de **SQLSetStmtAttr** como se indica a continuación:  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_PARAMSET_SIZE, crow, 0);  
SQLSetStmtAttr(hstmt, SQL_ATTR_PARAMS_PROCESSED_PTR, piRow, 0);  
```
