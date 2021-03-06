---
title: sp_enumcustomresolvers (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_enumcustomresolvers
- sp_enumcustomresolvers_TSQL
helpviewer_keywords:
- sp_enumcustomresolvers
ms.assetid: 81bd0d3a-48dc-42b1-b662-c630f61fc630
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: ecff860e5dc101cc02b3e5fd7b97569510a8cf68
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891903"
---
# <a name="sp_enumcustomresolvers-transact-sql"></a>sp_enumcustomresolvers (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Devuelve una lista de todos los controladores de lógica de negocios y solucionadores personalizados disponibles registrados en el distribuidor. Este procedimiento almacenado se ejecuta en el publicador de cualquier base de datos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_enumcustomresolvers [ [ @distributor =] 'distributor']  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @distributor = ] 'distributor'`Es el nombre del distribuidor en el que se encuentra el solucionador personalizado. *Distributor* es de **tipo sysname y su**valor predeterminado es NULL. *Este parámetro ha quedado desusado y se retirará en versiones posteriores.*  
  
## <a name="result-sets"></a>Conjuntos de resultados  
  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**article_resolver**|**nvarchar(255)**|Nombre descriptivo del controlador de lógica de negocios o del solucionador de conflictos.|  
|**resolver_clsid**|**nvarchar(50)**|Identificador de clase (CLSID) del solucionador basado en COM. Para un controlador de lógica de negocios, esta columna devuelve un valor de CLSID de cero.|  
|**is_dotnet_assembly**|**bit**|Indica si el registro es para un controlador de lógica de negocios.<br /><br /> **0** = solucionador de conflictos basado en com<br /><br /> **1** = controlador de lógica de negocios|  
|**dotnet_assembly_name**|**nvarchar(255)**|Nombre del ensamblado de [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework que implementa el controlador de la lógica de negocios.|  
|**dotnet_class_name**|**nvarchar(255)**|Es el nombre de la clase que reemplaza <xref:Microsoft.SqlServer.Replication.BusinessLogicSupport.BusinessLogicModule> para implementar el controlador de lógica de negocios.|  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="remarks"></a>Comentarios  
 **sp_enumcustomresolvers** se utiliza en la replicación de mezcla.  
  
## <a name="permissions"></a>Permisos  
 Solo los miembros del rol fijo de servidor **sysadmin** y del rol fijo de base de datos **db_owner** pueden ejecutar **sp_enumcustomresolvers**.  
  
## <a name="see-also"></a>Consulte también  
 [Implementar un controlador de lógica de negocios para un artículo de mezcla](../../relational-databases/replication/implement-a-business-logic-handler-for-a-merge-article.md)   
 [Implementar un solucionador de conflictos personalizado para un artículo de mezcla](../../relational-databases/replication/implement-a-custom-conflict-resolver-for-a-merge-article.md)   
 [sp_lookupcustomresolver &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-lookupcustomresolver-transact-sql.md)   
 [sp_unregistercustomresolver &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-unregistercustomresolver-transact-sql.md)   
 [Procedimientos almacenados del sistema &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/system-stored-procedures-transact-sql.md)  
  
  
