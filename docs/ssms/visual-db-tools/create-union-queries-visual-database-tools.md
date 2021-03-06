---
title: Crear consultas de UNIÓN
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- queries [SQL Server], types
- UNION queries
- Select query
- combining query results
- merged SELECT query [SQL Server]
ms.assetid: b5aafb1d-e4ed-4922-b790-56abc5ec551a
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.openlocfilehash: 9a7a274c092a98cbe63313f633ec37fc4377aa75
ms.sourcegitcommit: f3321ed29d6d8725ba6378d207277a57cb5fe8c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "86000013"
---
# <a name="create-union-queries-visual-database-tools"></a>Crear consultas UNION (Visual Database Tools)
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]
La palabra clave UNION permite incluir los resultados de dos instrucciones SELECT en una única tabla. Todas las filas devueltas desde la instrucción SELECT se combinan como resultado de la expresión UNION. Para ejemplos, consulte [Ejemplos de SELECT (Transact-SQL)](https://msdn.microsoft.com/9b9caa3d-e7d0-42e1-b60b-a5572142186c).  
  
> [!NOTE]  
> En el panel Diagrama solo puede aparecer una cláusula SELECT. Por tanto, cuando trabaje con la consulta UNION, el Diseñador de consultas ocultará el panel de operaciones de tablas.  
  
### <a name="to-create-a-merged-select-query"></a>Para crear una consulta SELECT mezclada  
  
1.  Abra una consulta o cree una nueva.  
  
2.  En el panel SQL, escriba una expresión UNION válida.  
  
    El ejemplo siguiente es una expresión UNION válida.  
  
    ```  
    SELECT ProductModelID, Name  
    FROM Production.ProductModel  
    UNION  
    SELECT ProductModelID, Name   
    FROM dbo.Gloves;  
    ```  
  
3.  En el menú **Diseñador de consultas** , haga clic en **Ejecutar SQL** para ejecutar la consulta.  
  
    El Diseñador de consultas da formato a su consulta UNION.  
  
## <a name="see-also"></a>Consulte también  
[Tipos de consulta admitidos](../../ssms/visual-db-tools/supported-query-types-visual-database-tools.md)  
[Temas de procedimientos de diseño de consultas y vistas](../../ssms/visual-db-tools/design-queries-and-views-how-to-topics-visual-database-tools.md)  
[Realizar operaciones básicas con consultas](../../ssms/visual-db-tools/perform-basic-operations-with-queries-visual-database-tools.md)  
[UNION (Transact-SQL)](https://msdn.microsoft.com/607c296f-8a6a-49bc-975a-b8d0c0914df7)