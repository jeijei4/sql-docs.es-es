---
title: sp_helpdb (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_helpdb
- sp_helpdb_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sp_helpdb
ms.assetid: 4c3e3302-6cf1-4b2b-8682-004049b578c3
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 3fda6aba2ce361e814a0196db6138b38f13ce359
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85899569"
---
# <a name="sp_helpdb-transact-sql"></a>sp_helpdb (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Presenta información acerca de una base de datos especificada o de todas las bases de datos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_helpdb [ [ @dbname= ] 'name' ]  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @dbname = ] 'name'`Es el nombre de la base de datos para la que se envía información. *Name* es de **tipo sysname**y no tiene ningún valor predeterminado. Si no se especifica *Name* , **sp_helpdb** informes en todas las bases de datos de la vista de catálogo **Sys. Databases** .  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|nombre de base de datos.|  
|**db_size**|**nvarchar (13)**|Tamaño total de la base de datos.|  
|**propietario**|**sysname**|Propietario de la base de datos, como **SA**.|  
|**DBID**|**smallint**|Id. de la base de datos.|  
|**created**|**nvarchar(11)**|Fecha de creación de la base de datos.|  
|**status**|**nvarchar (600)**|Lista de valores separados por comas de las opciones actualmente establecidas en la base de datos.<br /><br /> Las opciones con valores booleanos aparecen solamente si están habilitadas. Las opciones no booleanas se muestran con sus valores correspondientes en forma de *option_name* = *valor*.<br /><br /> Para obtener más información, vea [ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md).|  
|**compatibility_level**|**tinyint**|Nivel de compatibilidad de la base de datos: 60, 65, 70, 80 o 90.|  
  
 Si se especifica *Name* , hay un conjunto de resultados adicional que muestra la asignación de archivos para la base de datos especificada.  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**name**|**nchar(128)**|Nombre de archivo lógico.|  
|**ID**|**smallint**|Identificador de archivo.|  
|**filename**|**NCHAR (260)**|Nombre del archivo en el sistema operativo (nombre de archivo físico).|  
|**filegroup**|**nvarchar(128)**|Grupo al que pertenece el archivo.<br /><br /> NULL = El archivo es de registro. Nunca forma parte de un grupo de archivos.|  
|**size**|**nvarchar (18)**|Tamaño del archivo, en megabytes.|  
|**tamañomáximo**|**nvarchar (18)**|Tamaño máximo que puede alcanzar el archivo. El valor UNLIMITED en este campo indica que el archivo puede aumentar hasta que el disco esté lleno.|  
|**crezca**|**nvarchar (18)**|Incremento de crecimiento del archivo. Indica la cantidad de espacio que se agrega al archivo cada vez que se necesita espacio nuevo.|  
|**uso**|**VARCHAR (9)**|Uso del archivo. En el caso de un archivo de datos, el valor es **' solo datos '** y, para el archivo de registro, el valor es **' solo registro '**.|  
  
## <a name="remarks"></a>Comentarios  
 La columna **status** del conjunto de resultados informa de las opciones que se han establecido en on en la base de datos. La columna de **Estado** no muestra todas las opciones de base de datos. Para ver una lista completa de los valores actuales de las opciones de base de datos, use la vista de catálogo **Sys. Databases** .  
  
## <a name="permissions"></a>Permisos  
 Cuando se especifica una sola base de datos, se requiere la pertenencia al rol **Public** en la base de datos. Cuando no se especifica ninguna base de datos, se requiere la pertenencia al rol **Public** en la base de datos **maestra** .  
  
 Si no se puede tener acceso a una base de datos, **sp_helpdb** muestra el mensaje de error 15622 y toda la información acerca de la base de datos como se puede.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-returning-information-about-a-single-database"></a>A. Devolver información acerca de una sola base de datos  
 En el siguiente ejemplo se muestra información sobre la base de datos [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)].  
  
```sql  
EXEC sp_helpdb N'AdventureWorks2012';  
```  
  
### <a name="b-returning-information-about-all-databases"></a>B. Devolver información acerca de todas las bases de datos  
 En el ejemplo siguiente se muestra información acerca de todas las bases de datos del servidor donde se ejecuta [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
```sql  
EXEC sp_helpdb;  
GO  
```  
  
## <a name="see-also"></a>Consulte también  
 [Motor de base de datos procedimientos almacenados &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/database-engine-stored-procedures-transact-sql.md)   
 [ALTER DATABASE &#40;Transact-SQL&#41;](../../t-sql/statements/alter-database-transact-sql.md)   
 [CREATE DATABASE &#40;Transact-SQL de SQL Server&#41;](../../t-sql/statements/create-database-sql-server-transact-sql.md)   
 [sys.databases &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)   
 [Sys. database_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-database-files-transact-sql.md)   
 [Sys. grupos de archivos &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-filegroups-transact-sql.md)   
 [Sys. master_files &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-master-files-transact-sql.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
