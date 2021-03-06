---
title: Cambios en el tipo de datos DateTime | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- time data type [ODBC]
- datetime data types [ODBC]
- date data type [ODBC]
- backward compatibility [ODBC], datetime data types
- timestamp data type [ODBC]
- compatibility [ODBC], datetime data types
ms.assetid: c38c79f9-8bb0-4633-ac86-542366c09a95
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 4f186047dd31aa2c4b66ec1ce73c8cb9fae31c04
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81304648"
---
# <a name="datetime-data-type-changes"></a>Cambia el tipo de datos de fecha y hora
En ODBC *3. x*, los identificadores de los tipos de datos de fecha, hora y marca de tiempo de SQL han cambiado de SQL_DATE, SQL_TIME y SQL_TIMESTAMP (con instancias de **#define** en el archivo de encabezado 9, 10 y 11) a SQL_TYPE_DATE, SQL_TYPE_TIME y SQL_TYPE_TIMESTAMP (con instancias de **#define** en el archivo de encabezado de 91, 92 y 93), respectivamente. Los identificadores de tipo de C correspondientes han cambiado de SQL_C_DATE, SQL_C_TIME y SQL_C_TIMESTAMP a SQL_C_TYPE_DATE, SQL_C_TYPE_TIME y SQL_C_TYPE_TIMESTAMP, respectivamente.  
  
 El tamaño de la columna y los dígitos decimales devueltos para los tipos de datos DateTime de SQL en ODBC *3. x* son los mismos que la precisión y la escala devueltas para ellos en ODBC *2. x*. Estos valores son diferentes de los valores de los campos de descriptor SQL_DESC_PRECISION y SQL_DESC_SCALE. (Para obtener más información, vea [tamaño de columna, dígitos decimales, longitud de octetos de transferencia y tamaño de presentación](../../../odbc/reference/appendixes/column-size-decimal-digits-transfer-octet-length-and-display-size.md)).  
  
 Estos cambios afectan a **SQLDescribeCol**, **SQLDescribeParam**y **SQLColAttribute**; **SQLBindCol**, **SQLBindParameter**y **SQLGetData**; y **SQLColumns**, **SQLGetTypeInfo**, **SQLProcedureColumns**, **SQLStatistics**y **SQLSpecialColumns**.  
  
 En la tabla siguiente se muestra cómo el administrador de controladores ODBC *3. x* realiza la asignación de los tipos de datos Date, Time y timestamp de C especificados en los argumentos *TargetType* de **SQLBindCol** y **SQLGetData** , o en el argumento *ValueType* de **SQLBindParameter**.  
  
|Tipo de datos<br /><br /> código escrito|aplicación *2. x* a<br /><br /> controlador *2. x*|aplicación *2. x* a<br /><br /> controlador *3. x*|aplicación *3. x* a<br /><br /> controlador *2. x*|aplicación *3. x* a<br /><br /> controlador *3. x*|  
|--------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|  
|SQL_C_DATE (9)|Sin asignación|SQL_C_TYPE_DATE (91)|Sin asignación [1]|SQL_C_TYPE_DATE (91)|  
|SQL_C_TYPE_DATE (91)|Error (de DM)|Error (de DM)|SQL_C_DATE (9)|Sin asignación [2]|  
|SQL_C_TIME (10)|Sin asignación|SQL_C_TYPE_TIME (92)|Sin asignación [1]|SQL_C_TYPE_TIME (92)|  
|SQL_C_TYPE_TIME (92)|Error (de DM)|Error (de DM)|SQL_C_TIME (10)|Sin asignación [2]|  
|SQL_C_TIMESTAMP (11)|Sin asignación|SQL_C_TYPE_TIMESTAMP (93)|Sin asignación [1]|SQL_C_TYPE_TIMESTAMP (93)|  
|SQL_C_TYPE_TIMESTAMP (93)|Error (de DM)|Error (de DM)|SQL_C_TIMESTAMP (11)|Sin asignación [2]|  
  
 [1] como resultado de esto, una aplicación ODBC *3. x* que trabaja con un controlador ODBC *2. x* puede usar los códigos de fecha, hora o marca de tiempo devueltos en los conjuntos de resultados devueltos por las funciones de catálogo.  
  
 [2] como resultado, una aplicación ODBC *3. x* que trabaja con un controlador ODBC *3. x* puede usar los códigos de fecha, hora o marca de tiempo devueltos en los conjuntos de resultados devueltos por las funciones de catálogo.  
  
 En la tabla siguiente se muestra cómo el administrador de controladores ODBC *3. x* realiza la asignación de los tipos de datos de fecha, hora y marca de tiempo de SQL especificados en el argumento *ParameterType* de **SQLBindParameter** o en el argumento *DataType* de **SQLGetTypeInfo**.  
  
|Tipo de datos<br /><br /> código escrito|aplicación *2. x* a<br /><br /> controlador *2. x*|aplicación *2. x* a<br /><br /> controlador *3. x*|aplicación *3. x* a<br /><br /> controlador *2. x*|aplicación *3. x* a<br /><br /> controlador *3. x*|  
|--------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|-----------------------------------|  
|SQL_DATE (9)|Sin asignación|SQL_TYPE_DATE (91)|Sin asignación [1]|SQL_TYPE_DATE (91)|  
|SQL_TYPE_DATE (91)|Error (de DM)|Error (de DM)|SQL_DATE (9)|Sin asignación [2]|  
|SQL_TIME (10)|Sin asignación|SQL_TYPE_TIME (92)|Sin asignación [1]|SQL_TYPE_TIME (92)|  
|SQL_TYPE_TIME (92)|Error (de DM)|Error (de DM)|SQL_TIME (10)|Sin asignación [2]|  
|SQL_TIMESTAMP (11)|Sin asignación|SQL_TYPE_TIMESTAMP (93)|Sin asignación [1]|SQL_TYPE_TIMESTAMP (93)|  
|SQL_TYPE_TIMESTAMP (93)|Error (de DM)|Error (de DM)|SQL_TIMESTAMP (11)|Sin asignación [2]|  
  
 [1] como resultado de esto, una aplicación ODBC *3. x* que trabaja con un controlador ODBC *2. x* puede usar los códigos de fecha, hora o marca de tiempo devueltos en los conjuntos de resultados devueltos por las funciones de catálogo.  
  
 [2] como resultado, una aplicación ODBC *3. x* que trabaja con un controlador ODBC *3. x* puede usar los códigos de fecha, hora o marca de tiempo devueltos en los conjuntos de resultados devueltos por las funciones de catálogo.
