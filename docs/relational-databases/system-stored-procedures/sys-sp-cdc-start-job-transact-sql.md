---
title: Sys. sp_cdc_start_job (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cdc_start_job
- sp_cdc_start_job_TSQL
- sys.sp_cdc_start_job_TSQL
- sys.sp_cdc_start_job
dev_langs:
- TSQL
helpviewer_keywords:
- sp_cdc_start_job
ms.assetid: cf443a67-7705-4799-9f39-0e3a6a8a0708
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4a87fca28491075c9a75945b7a452c02b270d95b
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85891048"
---
# <a name="syssp_cdc_start_job-transact-sql"></a>sys.sp_cdc_start_job (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Inicia una limpieza de captura datos modificados o un trabajo de captura de la base de datos actual.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sys.sp_cdc_start_job [ [ @job_type = ] 'job_type' ]  
```  
  
## <a name="arguments"></a>Argumentos  
`[ [ @job_type = ] 'job_type' ]`Tipo de trabajo que se va a agregar. *job_type* es de tipo **nvarchar (20)** y su valor predeterminado es **Capture**. Las entradas válidas son **Capture** y **Cleanup**.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="result-sets"></a>Conjuntos de resultados  
 None  
  
## <a name="remarks"></a>Observaciones  
 Un administrador puede utilizar sys.sp_cdc_start_job para iniciar explícitamente el trabajo de captura o el trabajo de limpieza.  
  
## <a name="permissions"></a>Permisos  
 Requiere pertenencia al rol fijo de base de datos db_owner.  
  
## <a name="examples"></a>Ejemplos  
  
### <a name="a-starting-a-capture-job"></a>A. Iniciar un trabajo de captura  
 En el siguiente ejemplo se inicia el trabajo de captura para la base de datos `AdventureWorks2012`. No es necesario especificar un valor para *job_type* porque el tipo de trabajo predeterminado es **Capture**.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sys.sp_cdc_start_job;  
GO  
```  
  
### <a name="b-starting-a-cleanup-job"></a>B. Iniciar un trabajo de limpieza  
 En el siguiente ejemplo se inicia un trabajo de limpieza para la base de datos `AdventureWorks2012`.  
  
```  
USE AdventureWorks2012;  
GO  
EXEC sys.sp_cdc_start_job @job_type = N'cleanup';  
```  
  
## <a name="see-also"></a>Consulte también  
 [DBO. cdc_jobs &#40;Transact-SQL&#41;](../../relational-databases/system-tables/dbo-cdc-jobs-transact-sql.md)   
 [Sys. sp_cdc_stop_job &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-cdc-stop-job-transact-sql.md)  
  
  
