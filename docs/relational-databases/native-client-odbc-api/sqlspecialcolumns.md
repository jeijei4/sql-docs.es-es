---
title: SQLSpecialColumns | Microsoft Docs
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
apitype: DLLExport
helpviewer_keywords:
- SQLSpecialColumns function
ms.assetid: dffe02ed-8f79-4c9a-af34-98130bbe5462
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 24661c0937c0af83d39831b60b535bd58ebcc626
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86012383"
---
# <a name="sqlspecialcolumns"></a>SQLSpecialColumns
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

  Cuando se solicitan identificadores de fila (*IdentifierType* SQL_BEST_ROWID), **SQLSpecialColumns** devuelve un conjunto de resultados vacío (ninguna fila de datos) para cualquier ámbito solicitado distinto de SQL_SCOPE_CURROW. El conjunto de resultados generado indica que las columnas solamente son válidas dentro de este ámbito.  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] no admite pseudocolumnas para identificadores. El conjunto de resultados de **SQLSpecialColumns** identificará todas las columnas como SQL_PC_NOT_PSEUDO.  
  
 **SQLSpecialColumns** se puede ejecutar en un cursor estático. Si se intenta ejecutar **SQLSpecialColumns** en un cursor actualizable (dinámico o controlado por conjunto de claves), devuelve SQL_SUCCESS_WITH_INFO para indicar que el tipo de cursor ha cambiado.  
  
## <a name="sqlspecialcolumns-support-for-enhanced-date-and-time-features"></a>SQLSpecialColumns admite características mejoradas de fecha y hora  
 Para obtener información sobre los valores devueltos para las columnas DATA_TYPE, TYPE_NAME, COLUMN_SIZE, BUFFER_LENGTH y DECIMAL_DIGTS para tipos de fecha y hora, vea [Catalog Metadata](../../relational-databases/native-client-odbc-date-time/metadata-catalog.md).  
  
 Para obtener más información general, consulte [mejoras de fecha y hora &#40;ODBC&#41;](../../relational-databases/native-client-odbc-date-time/date-and-time-improvements-odbc.md).  
  
## <a name="sqlspecialcolumns-support-for-large-clr-udts"></a>Compatibilidad con SQLSpecialColumns para el UDT CLR grandes  
 **SQLSpecialColumns** admite tipos definidos por el usuario (UDT) CLR grandes. Para obtener más información, vea [tipos CLR grandes definidos por el usuario &#40;ODBC&#41;](../../relational-databases/native-client/odbc/large-clr-user-defined-types-odbc.md).  
  
## <a name="see-also"></a>Consulte también  
 [SQLSpecialColumns función)](https://go.microsoft.com/fwlink/?LinkId=59371)   
 [ODBC API Implementation Details](../../relational-databases/native-client-odbc-api/odbc-api-implementation-details.md)  
  
  
