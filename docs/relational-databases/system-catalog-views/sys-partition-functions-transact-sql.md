---
title: Sys. partition_functions (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sys.partition_functions_TSQL
- partition_functions
- sys.partition_functions
- partition_functions_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.partition_functions catalog view
ms.assetid: 96515727-728b-4bea-804a-36ce915b8b75
author: CarlRabeler
ms.author: carlrab
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 49a2f838010c0c1fab93e245849249f28059d405
ms.sourcegitcommit: 4d3896882c5930248a6e441937c50e8e027d29fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825000"
---
# <a name="syspartition_functions-transact-sql"></a>sys.partition_functions (Transact-SQL)
[!INCLUDE[tsql-appliesto-ss2008-asdb-asdw-pdw-md](../../includes/tsql-appliesto-ss2008-all-md.md)]

  Contiene una fila por cada función de partición en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**name**|**sysname**|Nombre de la función de partición. Es único en la base de datos.|  
|**function_id**|**int**|Identificador de función de partición Es único en la base de datos.|  
|**type**|**char(2)**|Tipo de función.<br /><br /> R = Intervalo|  
|**type_desc**|**nvarchar(60)**|Tipo de función.<br /><br /> RANGE|  
|**promedio**|**int**|Número de particiones creadas por la función.|  
|**boundary_value_on_right**|**bit**|Para la creación de particiones por intervalos.<br /><br /> 1 = El valor de límite está incluido en el intervalo RIGHT del límite.<br /><br /> 0 = LEFT.|  
|**is_system**||**Válido para** : [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] y versiones posteriores.<br /><br /> 1 = El objeto se usa para los fragmentos de índice de texto completo.<br /><br /> 0 = El objeto no se usa para los fragmentos de índice de texto completo.|  
|**create_date**|**datetime**|Fecha de creación de la función.|  
|**modify_date**|**datetime**|Fecha de la última modificación de la función mediante una instrucción ALTER.|  
  
## <a name="permissions"></a>Permisos  
 Debe pertenecer al rol **public** .  Para obtener más información, consulte [Metadata Visibility Configuration](../../relational-databases/security/metadata-visibility-configuration.md).  
  
## <a name="see-also"></a>Consulte también  
 [Vistas de catálogo de funciones de partición &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/partition-function-catalog-views-transact-sql.md)   
 [Vistas de catálogo &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/catalog-views-transact-sql.md)   
 [Sys. partition_range_values &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-range-values-transact-sql.md)   
 [sys.partition_parameters &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-partition-parameters-transact-sql.md)  
  
  
