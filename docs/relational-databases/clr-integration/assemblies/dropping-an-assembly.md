---
title: Quitar un ensamblado | Microsoft Docs
description: Puede eliminar o quitar un ensamblado en SQL Server cuando ya no lo necesite. Utilice DROP ASSEMBLy para quitar un ensamblado y sus archivos asociados.
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- removing assemblies
- DROP ASSEMBLY statement
- assemblies [CLR integration], removing
- dropping assemblies
ms.assetid: 03481034-dc91-4488-ab24-ba44243e2690
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ba96bfa4f5f8f0dc5bfc95296a75499d1ec34f5
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887803"
---
# <a name="dropping-an-assembly"></a>Quitar un ensamblado
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  Es posible eliminar o quitar ensamblados registrados en [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mediante la instrucción CREATE ASSEMBLY cuando la funcionalidad que proporcionan ya no se necesita. Cuando se quita un ensamblado se quita el propio ensamblado y todos sus archivos asociados, como los archivos de depuración, de la base de datos. Para quitar un ensamblado, use la instrucción DROP ASSEMBLY con la sintaxis siguiente:  
  
```  
DROP ASSEMBLY MyDotNETAssembly  
```  
  
 DROP ASSEMBLY no interfiere con ningún código que haga referencia al ensamblado que se está ejecutando en estos momentos, pero después de que se ejecute DROP ASSEMBLY, cualquier intento de invocar al código del ensamblado generará errores.  
  
 DROP ASSEMBLY devuelve un error si hay otro ensamblado en la base de datos que hace referencia al ensamblado o si se utiliza en procedimientos, desencadenadores, tipos definidos por el usuario (UDT), agregados definidos por el usuario (UDA) o funciones de CLR (Common Language Runtime) en la base de datos actual. Utilice en primer lugar las instrucciones DROP AGGREGATE, DROP FUNCTION, DROP PROCEDURE, DROP TRIGGER y DROP TYPE para eliminar cualquier objeto de base de datos administrado incluido en el ensamblado.  
  
## <a name="removing-a-udt-from-the-database"></a>Quitar un UDT de la base de datos  
 La instrucción DROP TYPE quita un UDT de la base de datos actual. Una vez quitado un UDT, puede utilizar la instrucción DROP ASSEMBLY para quitar el ensamblado de la base de datos.  
  
 Se producen errores en la instrucción DROP TYPE si hay objetos que dependen del UDT, como en las situaciones siguientes:  
  
-   Tablas de la base de datos que contienen columnas definidas mediante el UDT.  
  
-   Funciones, procedimientos almacenados o desencadenadores que usan variables o parámetros del UDT creados en la base de datos con la cláusula WITH SCHEMABINDING.  
  
### <a name="finding-udt-dependencies"></a>Buscar dependencias UDT  
 Debe quitar primero todos los objetos dependientes y, a continuación, ejecutar la instrucción DROP TYPE. La siguiente [!INCLUDE[tsql](../../../includes/tsql-md.md)] consulta busca todas las columnas y parámetros que usan un UDT en la base de datos **AdventureWorks** .  
  
```  
USE Adventureworks;  
SELECT o.name AS major_name, o.type_desc AS major_type_desc  
     , c.name AS minor_name, c.type_desc AS minor_type_desc  
     , at.assembly_class  
  FROM (  
        SELECT object_id, name, user_type_id, 'SQL_COLUMN' AS type_desc  
          FROM sys.columns  
     UNION ALL  
        SELECT object_id, name, user_type_id, 'SQL_PROCEDURE_PARAMETER'  
          FROM sys.parameters  
     ) AS c  
  JOIN sys.objects AS o  
    ON o.object_id = c.object_id  
  JOIN sys.assembly_types AS at  
    ON at.user_type_id = c.user_type_id;   
```  
  
## <a name="see-also"></a>Consulte también  
 [Administrar ensamblados de integración CLR](../../../relational-databases/clr-integration/assemblies/managing-clr-integration-assemblies.md)   
 [Modificar un ensamblado](../../../relational-databases/clr-integration/assemblies/altering-an-assembly.md)   
 [Crear un ensamblado](../../../relational-databases/clr-integration/assemblies/creating-an-assembly.md)   
 [DROP Aggregate &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-aggregate-transact-sql.md)   
 [FUNCIÓN DROP &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-function-transact-sql.md)   
 [DROP PROCEDURE &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-procedure-transact-sql.md)   
 [DROP TRIGGER &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-trigger-transact-sql.md)   
 [DROP TYPE &#40;Transact-SQL&#41;](../../../t-sql/statements/drop-type-transact-sql.md)  
  
  
