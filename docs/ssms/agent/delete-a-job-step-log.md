---
title: Delete a Job Step Log
ms.custom: seo-lt-2019
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- job steps [SQL Server Agent]
- deleting job step logs
- logs [SQL Server], jobs
- removing job step logs
ms.assetid: ee20c6cd-0258-4550-bdb0-71e86a0fb330
author: markingmyname
ms.author: maghan
ms.reviewer: ''
monikerRange: = azuresqldb-mi-current || >= sql-server-2016 || = sqlallproducts-allversions
ms.openlocfilehash: 3a64356eb84ed0af8f387af0f2e4116289981d42
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85786746"
---
# <a name="delete-a-job-step-log"></a>Delete a Job Step Log
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

> [!IMPORTANT]  
> En [Instancia administrada de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance), la mayoría de las características de agente SQL Server son compatibles actualmente, aunque no todas. Vea [Diferencias de T-SQL en Instancia administrada de Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance-transact-sql-information#sql-server-agent) para obtener más información.

En este tema se describe cómo eliminar un registro de pasos de trabajo del Agente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
-   **Antes de empezar:**  
  
    [Limitaciones y restricciones](#Restrictions)  
  
    [Seguridad](#Security)  
  
-   **Para eliminar un registro de pasos de trabajo del Agente SQL Server, utilizando:**  
  
    [SQL Server Management Studio](#SSMS)  
  
    [Transact-SQL](#TSQL)  
  
    [objetos de administración de SQL Server](#SMO)  
  
## <a name="before-you-begin"></a><a name="BeforeYouBegin"></a>Antes de empezar  
  
### <a name="limitations-and-restrictions"></a><a name="Restrictions"></a>Limitaciones y restricciones  
Cuando se eliminan pasos de trabajo, sus registros de salida respectivos también se eliminan de forma automática.  
  
### <a name="security"></a><a name="Security"></a>Seguridad  
  
#### <a name="permissions"></a><a name="Permissions"></a>Permisos  
A menos que sea miembro del rol fijo de servidor **sysadmin** , solo podrá modificar los trabajos de su propiedad.  
  
## <a name="using-sql-server-management-studio"></a><a name="SSMS"></a>Usar SQL Server Management Studio  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a>Para eliminar un registro de paso de trabajo del Agente SQL Server  
  
1.  En el **Explorador de objetos** , conéctese a una instancia de [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion_md.md)]y, después, expándala.  
  
2.  Expanda **Agente SQL Server**, expanda **Trabajos**, haga clic con el botón derecho en el trabajo que desee modificar y haga clic en **Propiedades**.  
  
3.  En el cuadro de diálogo **Propiedades del trabajo** , elimine el paso de trabajo seleccionado.  
  
## <a name="using-transact-sql"></a><a name="TSQL"></a>Usar Transact-SQL  
  
#### <a name="to-delete-a-sql-server-agent-job-step-log"></a>Para eliminar un registro de paso de trabajo del Agente SQL Server  
  
1.  En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde_md.md)].  
  
2.  En la barra de Estándar, haga clic en **Nueva consulta**.  
  
3.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.  
  
    ```  
    -- removes the job step log for step 2 in the job Weekly Sales Data Backup  
    USE msdb ;  
    GO  
  
    EXEC dbo.sp_delete_jobsteplog  
        @job_name = N'Weekly Sales Data Backup',  
        @step_id = 2;  
    GO  
    ```  
  
Para más información, consulte [sp_delete_jobsteplog (Transact-SQL)](https://msdn.microsoft.com/e9ef4c99-abde-4038-b6a3-a25dcbaf0958).  
  
## <a name="using-sql-server-management-objects"></a><a name="SMO"></a>Usar Objetos de administración de SQL Server  
Use los métodos **DeleteJobStepLogs** de la clase **Job** mediante el lenguaje de programación de su elección, como Visual Basic, Visual C# o PowerShell. Para más información, consulte[Objetos de administración de SQL Server (SMO)](https://msdn.microsoft.com/library/ms162169.aspx).  
  
```  
-- Uses PowerShell to delete all job step log files that have ID values larger than 5.  
$srv = new-object Microsoft.SqlServer.Management.Smo.Server("(local)")  
$jb = $srv.JobServer.Jobs["Test Job"]  
$jb.DeleteJobStepLogs(5)  
```  
  
