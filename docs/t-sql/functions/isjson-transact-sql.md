---
title: ISJSON (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/03/2020
ms.prod: sql
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- ISJSON
- ISJSON_TSQL
helpviewer_keywords:
- ISJSON function
- JSON, validating
ms.assetid: c836f3d3-3e17-44ae-92bf-f341918896c3
author: jovanpop-msft
ms.author: jovanpop
ms.reviewer: jroth
monikerRange: = azuresqldb-current||= azure-sqldw-latest||>= sql-server-2016||>= sql-server-linux-2017||= sqlallproducts-allversions
ms.openlocfilehash: c29bacf9d9342bcad526d46042203cb3e1848c64
ms.sourcegitcommit: 768f046107642f72693514f51bf2cbd00f58f58a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87112934"
---
# <a name="isjson-transact-sql"></a>ISJSON (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2016-asdb-asdw-xxx-md](../../includes/tsql-appliesto-ss2016-asdb-asdw-xxx-md.md)]

  Prueba si una cadena contiene un valor JSON válido.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```sql  
ISJSON ( expression )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Argumentos
 *expression*  
 Cadena que se va a comprobar.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve 1 si la cadena contiene un valor JSON válido; en caso contrario, devuelve 0. Devuelve null si *expression* es null.  
  
 No devuelve errores.  
  
## <a name="remarks"></a>Observaciones  
 **ISJSON** no comprueba la unicidad de las claves en el mismo nivel.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="example-1"></a>Ejemplo 1  
En el siguiente ejemplo se ejecuta un bloque de instrucciones de forma condicional si el valor del parámetro `@param` contiene un valor JSON válido.  
  
```sql  
DECLARE @param <data type>
SET @param = <value>

IF (ISJSON(@param) > 0)  
BEGIN  
     -- Do something with the valid JSON value of @param.  
END
```  
  
### <a name="example-2"></a>Ejemplo 2  
En el ejemplo siguiente, se devuelven las filas en las que la columna `json_col` contiene JSON válido.  
  
```sql  
SELECT id, json_col
FROM tab1
WHERE ISJSON(json_col) > 0 
```  
  
## <a name="see-also"></a>Consulte también  
 [Datos JSON &#40;SQL Server&#41;](../../relational-databases/json/json-data-sql-server.md)  
  
  
