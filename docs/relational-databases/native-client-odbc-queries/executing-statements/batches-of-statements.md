---
title: Lotes de instrucciones | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: f90f2c73df0918e4bb709120513be82324e1b93a
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86001419"
---
# <a name="batches-of-statements"></a>Lotes de instrucciones
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Un lote de [!INCLUDE[tsql](../../../includes/tsql-md.md)] instrucciones contiene dos o más instrucciones, separadas por un punto y coma (;), integradas en una sola cadena que se pasa a la función **SQLExecDirect** o [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360). Por ejemplo:  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 Los lotes pueden ser más eficaces que el envío de instrucciones por separado porque el tráfico de red suele ser reducido. Use [SQLMoreResults](../../../relational-databases/native-client-odbc-api/sqlmoreresults.md) para situarse en el siguiente conjunto de resultados cuando termine con el conjunto de resultados actual.  
  
 Siempre pueden usarse lotes cuando los atributos de cursor de ODBC se establecen en los valores predeterminados de un cursor de solo avance y de solo lectura cuyo conjunto de filas tiene un tamaño de 1.  
  
 Si se ejecuta un lote al utilizar los cursores del servidor en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], el cursor del servidor se convierte implícitamente en un conjunto de resultados predeterminado. **SQLExecDirect** o **SQLExecute** devuelven SQL_SUCCESS_WITH_INFO, y una llamada a **SQLGetDiagRec** devuelve:  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a>Consulte también  
 [Ejecutar instrucciones &#40;ODBC&#41;](../../../relational-databases/native-client-odbc-queries/executing-statements/executing-statements-odbc.md)  
  
  
