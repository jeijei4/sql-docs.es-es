---
title: Conformidad con atributos | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data sources [ODBC], conformance levels
- ODBC drivers [ODBC], conformance levels
- conformance levels [ODBC], attribute
- attribute conformance levels [ODBC]
ms.assetid: 34fea100-10f9-46d5-bc50-3aa867b70f24
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b2880a35f4bdc997cc037cdd0d60720267ff4a58
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81306406"
---
# <a name="attribute-conformance"></a>Conformidad de atributo
En la tabla siguiente se indica el nivel de conformidad de cada atributo de entorno ODBC, donde está bien definido.  
  
|Función|Nivel de cumplimiento|  
|--------------|-----------------------|  
|SQL_ATTR_CONNECTION_POOLING|--[1]|  
|SQL_ATTR_CP_MATCH|--[1]|  
|SQL_ATTR_ODBC_VER|Principal|  
|SQL_ATTR_OUTPUT_NTS|--[1]|  
  
 [1] se trata de una característica opcional y, como tal, no forma parte de los niveles de cumplimiento.  
  
 En la tabla siguiente se indica el nivel de cumplimiento de cada atributo de conexión ODBC, donde está bien definido.  
  
|Función|Nivel de cumplimiento|  
|--------------|-----------------------|  
|SQL_ATTR_ACCESS_MODE|Principal|  
|SQL_ATTR_ASYNC_ENABLE|Nivel 1/nivel 2 [1]|  
|SQL_ATTR_AUTO_IPD|Nivel 2|  
|SQL_ATTR_AUTOCOMMIT|Nivel 1|  
|SQL_ATTR_CONNECTION_DEAD|Nivel 1|  
|SQL_ATTR_CONNECTION_TIMEOUT|Nivel 2|  
|SQL_ATTR_CURRENT_CATALOG|Nivel 2|  
|SQL_ATTR_LOGIN_TIMEOUT|Nivel 2|  
|SQL_ATTR_ODBC_CURSORS|Principal|  
|SQL_ATTR_PACKET_SIZE|Nivel 2|  
|SQL_ATTR_QUIET_MODE|Principal|  
|SQL_ATTR_TRACE|Principal|  
|SQL_ATTR_TRACEFILE|Principal|  
|SQL_ATTR_TRANSLATE_LIB|Principal|  
|SQL_ATTR_TRANSLATE_OPTION|Principal|  
|SQL_ATTR_TXN_ISOLATION|Nivel 1/nivel 2 [2]|  
  
 [1] las aplicaciones que admiten asincronía de nivel de conexión (necesario para el nivel 1) deben admitir la configuración de este atributo en SQL_TRUE llamando a **SQLSetConnectAttr**; no es necesario establecer el atributo en un valor distinto de su valor predeterminado a través de **SQLSetStmtAttr**. Las aplicaciones que admiten asincronía de nivel de instrucción (necesario para el nivel 2) deben admitir la configuración de este atributo en SQL_TRUE con cualquiera de las funciones.  
  
 [2] para el cumplimiento de la interfaz de nivel 1, el controlador debe admitir un valor además del valor predeterminado definido por el controlador (disponible mediante una llamada a **SQLGetInfo** con la opción SQL_DEFAULT_TXN_ISOLATION). En el caso del cumplimiento de la interfaz de nivel 2, el controlador también debe admitir SQL_TXN_SERIALIZABLE.  
  
 En la tabla siguiente se indica el nivel de cumplimiento de cada atributo de instrucción ODBC, donde está bien definido.  
  
|Función|Nivel de cumplimiento|  
|--------------|-----------------------|  
|SQL_ATTR_APP_PARAM_DESC|Principal|  
|SQL_ATTR_APP_ROW_DESC|Principal|  
|SQL_ATTR_ASYNC_ENABLE|Nivel 1/nivel 2 [1]|  
|SQL_ATTR_CONCURRENCY|Nivel 1/nivel 2 [2]|  
|SQL_ATTR_CURSOR_SCROLLABLE|Nivel 1|  
|SQL_ATTR_CURSOR_SENSITIVITY|Nivel 2|  
|SQL_ATTR_CURSOR_TYPE|Núcleo/nivel 2 [3]|  
|SQL_ATTR_ENABLE_AUTO_IPD|Nivel 2|  
|SQL_ATTR_FETCH_BOOKMARK_PTR|Nivel 2|  
|SQL_ATTR_IMP_PARAM_DESC|Principal|  
|SQL_ATTR_IMP_ROW_DESC|Principal|  
|SQL_ATTR_KEYSET_SIZE|Nivel 2|  
|SQL_ATTR_MAX_LENGTH|Nivel 1|  
|SQL_ATTR_MAX_ROWS|Nivel 1|  
|SQL_ATTR_METADATA_ID|Principal|  
|SQL_ATTR_NOSCAN|Principal|  
|SQL_ATTR_PARAM_BIND_OFFSET_PTR|Principal|  
|SQL_ATTR_PARAM_BIND_TYPE|Principal|  
|SQL_ATTR_PARAM_OPERATION_PTR|Principal|  
|SQL_ATTR_PARAM_STATUS_PTR|Principal|  
|SQL_ATTR_PARAMS_PROCESSED_PTR|Principal|  
|SQL_ATTR_PARAMSET_SIZE|Principal|  
|SQL_ATTR_QUERY_TIMEOUT|Nivel 2|  
|SQL_ATTR_RETRIEVE_DATA|Nivel 1|  
|SQL_ATTR_ROW_ARRAY_SIZE|Principal|  
|SQL_ATTR_ROW_BIND_OFFSET_PTR|Principal|  
|SQL_ATTR_ROW_BIND_TYPE|Principal|  
|SQL_ATTR_ROW_NUMBER|Nivel 1|  
|SQL_ATTR_ROW_OPERATION_PTR|Nivel 1|  
|SQL_ATTR_ROW_STATUS_PTR|Principal|  
|SQL_ATTR_ROWS_FETCHED_PTR|Principal|  
|SQL_ATTR_SIMULATE_CURSOR|Nivel 2|  
|SQL_ATTR_USE_BOOKMARKS|Nivel 2|  
  
 [1] las aplicaciones que admiten asincronía de nivel de conexión (necesario para el nivel 1) deben admitir la configuración de este atributo en SQL_TRUE llamando a **SQLSetConnectAttr**; no es necesario establecer el atributo en un valor distinto de su valor predeterminado a través de **SQLSetStmtAttr**. Las aplicaciones que admiten asincronía de nivel de instrucción (necesario para el nivel 2) deben admitir la configuración de este atributo en SQL_TRUE con cualquiera de las funciones.  
  
 [2] para el cumplimiento de la interfaz de nivel 2, el controlador debe admitir SQL_CONCUR_READ_ONLY y al menos otro valor.  
  
 [3] para el cumplimiento de la interfaz de nivel 1, el controlador debe admitir SQL_CURSOR_FORWARD_ONLY y al menos otro valor. En el caso del cumplimiento de la interfaz de nivel 2, el controlador debe admitir todos los valores definidos en este documento.
