---
title: CURRENT_TIMEZONE (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/18/2020
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- CURRENT_TIMEZONE)ID
- CURRENT_TIMEZONE_ID_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- current time zone id [SQL Server]
- current timezoneid [SQL Server]
- system time zone id[SQL Server]
- system timezone id[SQL Server]
- functions [SQL Server], time zone id
- functions [SQL Server], timezoneid
- timezoneid [SQL Server], functions
- time zone id [SQL Server], functions
- CURRENT_TIMEZONE_ID function [SQL Server]
author: MladjoA
ms.author: mlandzic
ms.openlocfilehash: 3cadc9cd33fd1cdabb96cf450ad09253fdd435d1
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85684624"
---
# <a name="current_timezone_id-transact-sql"></a>CURRENT_TIMEZONE_ID (Transact-SQL)

[!INCLUDE[Azure SQL Database Azure SQL Managed Instance](../../includes/applies-to-version/asdb-asdbmi.md)]

Esta función devuelve el id. de la zona horaria que observa un servidor o una instancia. Para Azure SQL Managed Instance, el valor devuelto se basa en la zona horaria de la propia instancia asignada durante la creación de la instancia, no en la zona horaria del sistema operativo subyacente.
  
> [!NOTE]  
> Para instancias de SQL Database individuales y agrupadas, la zona horaria siempre se establece en UTC y `CURRENT_TIMEZONE_ID` devuelve el id. de la zona horaria UTC.
  
## <a name="syntax"></a>Sintaxis  
  
```sql
CURRENT_TIMEZONE_ID ( )  
```
  
## <a name="arguments"></a>Argumentos

Esta función no toma ningún argumento.
  
## <a name="return-type"></a>Tipo de valor devuelto  

**varchar**
  
## <a name="remarks"></a>Observaciones  

`CURRENT_TIMEZONE_ID` es una función no determinista. Las vistas y las expresiones que hacen referencia a esta columna no se pueden indizar.
  
## <a name="example"></a>Ejemplo

El valor devuelto reflejará la configuración real de la zona horaria y el idioma del servidor o de la instancia.

```sql
SELECT CURRENT_TIMEZONE_ID();  
/* Returned:  
W. Europe Standard Time
*/
```  
  
## <a name="see-also"></a>Consulte también

[Zona horaria de Instancia administrada de SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-timezone)

[CURRENT_TIMEZONE()](https://docs.microsoft.com/sql/t-sql/functions/current-timezone-transact-sql)
