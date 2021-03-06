---
title: 'C a SQL: Numeric | Microsoft Docs'
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- numeric data type [ODBC], converting
- data conversions from C to SQL types [ODBC], numeric
- converting data from c to SQL types [ODBC], numeric
ms.assetid: af4095ff-06c3-4b04-83bf-19f9ee098dc2
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: bbc0a994ef95f2deca29c8a4cbb06f3167b0433f
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81304736"
---
# <a name="c-to-sql-numeric"></a>C a SQL: Numeric
Los identificadores de los tipos de datos de ODBC C numéricos son:  
  
 SQL_C_STINYINT  
  
 SQL_C_SLONG  
  
 SQL_C_UTINYINT  
  
 SQL_C_ULONG  
  
 SQL_C_TINYINT  
  
 SQL_C_LONG  
  
 SQL_C_SSHORT  
  
 SQL_C_FLOAT  
  
 SQL_C_USHORT  
  
 SQL_C_DOUBLE  
  
 SQL_C_SHORT  
  
 SQL_C_NUMERIC  
  
 SQL_C_SBIGINT  
  
 SQL_C_UBIGINT  
  
 En la tabla siguiente se muestran los tipos de datos de ODBC SQL en los que se pueden convertir los datos numéricos de C. Para obtener una explicación de las columnas y los términos de la tabla, vea [convertir datos de C a tipos de datos de SQL](../../../odbc/reference/appendixes/converting-data-from-c-to-sql-data-types.md).  
  
|Identificador de tipo de SQL|Prueba|SQLSTATE|  
|-------------------------|----------|--------------|  
|SQL_CHAR<br /><br /> SQL_VARCHAR<br /><br /> SQL_LONGVARCHAR|Número de dígitos <= longitud de bytes de columna<br /><br /> Número de dígitos > longitud de bytes de columna|N/D<br /><br /> 22001|  
|SQL_WCHAR<br /><br /> SQL_WVARCHAR<br /><br /> SQL_WLONGVARCHAR|Número de caracteres <= longitud de caracteres de columna<br /><br /> Número de caracteres > longitud de caracteres de columna|N/D<br /><br /> 22001|  
|SQL_DECIMAL [b]<br /><br /> SQL_NUMERIC [b]<br /><br /> SQL_TINYINT [b]<br /><br /> SQL_SMALLINT [b]<br /><br /> SQL_INTEGER [b]<br /><br /> SQL_BIGINT [b]|Datos convertidos sin truncamiento o con truncado de dígitos fraccionarios<br /><br /> Datos convertidos con truncamiento de dígitos enteros|N/D<br /><br /> 22003|  
|SQL_REAL<br /><br /> SQL_FLOAT<br /><br /> SQL_DOUBLE|Los datos están dentro del intervalo del tipo de datos al que se va a convertir el número.<br /><br /> Los datos están fuera del intervalo del tipo de datos al que se está convirtiendo el número|N/D<br /><br /> 22003|  
|SQL_BIT|Los datos son 0 o 1<br /><br /> Los datos son mayores que 0, menores que 2 y no igual a 1<br /><br /> Los datos son menores que 0 o mayor o igual que 2|N/D<br /><br /> 22001<br /><br /> 22003|  
|SQL_INTERVAL_YEAR [a]<br /><br /> SQL_INTERVAL_MONTH [a]<br /><br /> SQL_INTERVAL_DAY [a]<br /><br /> SQL_INTERVAL_HOUR [a]<br /><br /> SQL_INTERVAL_MINUTE [a]<br /><br /> SQL_INTERVAL_SECOND [a]|Los datos no se truncan.<br /><br /> Datos truncados.|N/D<br /><br /> 22015|  
  
 [a] estas conversiones solo se admiten para los tipos de datos numéricos exactos (SQL_C_STINYINT, SQL_C_UTINYINT, SQL_C_SSHORT, SQL_C_USHORT, SQL_C_SLONG, SQL_C_ULONG o SQL_C_NUMERIC). No se admiten para los tipos de datos numéricos aproximados (SQL_C_FLOAT o SQL_C_DOUBLE). Los tipos de datos de C numéricos exactos no se pueden convertir en un tipo SQL de intervalo cuya precisión de intervalo no sea un campo único.  
  
 [b] para el caso "n/a", un controlador puede devolver opcionalmente SQL_SUCCESS_WITH_INFO y 01S07 cuando hay un truncamiento fraccionario.  
  
 El controlador omite el valor de longitud/indicador al convertir los datos de los tipos de datos de C numéricos y da por supuesto que el tamaño del búfer de datos es el tamaño del tipo de datos de C numérico. El valor de longitud/indicador se pasa en el argumento *StrLen_or_Ind* de **SQLPutData** y en el búfer especificado con el argumento *StrLen_or_IndPtr* en **SQLBindParameter**. El búfer de datos se especifica con el argumento *DataPtr* en **SQLPutData** y el argumento *ParameterValuePtr* en **SQLBindParameter**.
