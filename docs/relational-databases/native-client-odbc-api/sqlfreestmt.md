---
title: SQLFreeStmt | Microsoft Docs
ms.custom: ''
ms.date: 11/23/2015
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLFreeStmt function
ms.assetid: d9666d0b-3446-480e-bf1a-10b01213e411
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 62e168ac73de1e1755cb36f108f9905ca1c3cea7
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86003504"
---
# <a name="sqlfreestmt"></a>SQLFreeStmt
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Suelen   
      **SQLFreeStmt** no se recomienda en ODBC 3.0 y posterior. Sin embargo, si la aplicación necesita volver a usar la instrucción, debe seguir usando **SQLFreeStmt** con las opciones **SQL_RESET_PARAMS** y **SQL_UNBIND** ). También puede usar [SQLCloseCursor](../../relational-databases/native-client-odbc-api/sqlclosecursor.md), [SQLBindParameter](../../relational-databases/native-client-odbc-api/sqlbindparameter.md), [SQLBindCol](../../relational-databases/native-client-odbc-api/sqlbindcol.md), [SQLSetDescField](../../relational-databases/native-client-odbc-api/sqlsetdescfield.md)y [SQLFreeHandle](../../relational-databases/native-client-odbc-api/sqlfreehandle.md) para reemplazar o duplicar la función de **SQLFreeStmt** y debe utilizarlos en su lugar.  
  
 En general, es más eficaz reutilizar las instrucciones que eliminarlas y asignar otras nuevas. Sin embargo, en algunas situaciones, como la reutilización de instrucciones, se debe usar SQLFreeStmt.  
  
## <a name="see-also"></a>Consulte también  
 [SQLFreeStmt función)](https://go.microsoft.com/fwlink/?LinkId=59346)   
 [ODBC API Implementation Details](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
