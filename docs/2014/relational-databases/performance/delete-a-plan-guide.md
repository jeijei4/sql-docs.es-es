---
title: Eliminación de una guía de plan | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: performance
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- plan guides [SQL Server], deleting
ms.assetid: aa4d3188-6927-43de-a3e3-90fc16eeaca7
caps.latest.revision: 6
author: MikeRayMSFT
ms.author: mikeray
manager: craigg
ms.openlocfilehash: 42cbef8a51b01f2f77baca8662c47594ed75b6d0
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37410344"
---
# <a name="delete-a-plan-guide"></a>Eliminar una guía de plan
  Puede eliminar (quitar) una guía de plan en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)]. Mediante [!INCLUDE[tsql](../../includes/tsql-md.md)], también puede eliminar todas las guías de plan de una base de datos.  
  
 **En este tema**  
  
-   **Antes de empezar:**  
  
     [Seguridad](#Security)  
  
-   **Para eliminar una guía de plan mediante:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="BeforeYouBegin"></a> Antes de empezar  
  
###  <a name="Security"></a> Seguridad  
  
####  <a name="Permissions"></a> Permissions  
 La eliminación de una guía de plan OBJECT requiere el permiso ALTER en el objeto (por ejemplo: función, procedimiento almacenado) al que hace referencia la guía de plan. Todas las demás guías de plan requieren el permiso ALTER DATABASE.  
  
##  <a name="SSMSProcedure"></a> Usar SQL Server Management Studio  
  
#### <a name="to-delete-a-plan-guide"></a>Para eliminar una guía de plan  
  
1.  Haga clic en el signo más para expandir la base de datos en que desea eliminar una guía de plan y, a continuación, haga clic en el signo más para expandir la carpeta **Programación** .  
  
2.  Haga clic en el signo más para expandir la carpeta **Guías de plan** .  
  
3.  Haga clic con el botón derecho en la guía de plan que quiera eliminar y seleccione **Eliminar**.  
  
4.  En el cuadro de diálogo **Eliminar objeto** , asegúrese de que está seleccionada la guía de plan correcta y haga clic en **Aceptar**.  
  
##  <a name="TsqlProcedure"></a> Usar Transact-SQL  
  
#### <a name="to-delete-a-single-plan-guide"></a>Para eliminar una guía de plan única  
  
1.  En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  En la barra de Estándar, haga clic en **Nueva consulta**.  
  
3.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.  
  
    ```  
    --Create a procedure on which to define the plan guide.  
    IF OBJECT_ID(N'Sales.GetSalesOrderByCountry', N'P') IS NOT NULL  
        DROP PROCEDURE Sales.GetSalesOrderByCountry;  
    GO  
    CREATE PROCEDURE Sales.GetSalesOrderByCountry   
        (@Country nvarchar(60))  
    AS  
    BEGIN  
        SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country;  
    END  
    GO  
    --Create the plan guide.  
    EXEC sp_create_plan_guide N'Guide3',  
        N'SELECT *  
        FROM Sales.SalesOrderHeader AS h   
        INNER JOIN Sales.Customer AS c ON h.CustomerID = c.CustomerID  
        INNER JOIN Sales.SalesTerritory AS t ON c.TerritoryID = t.TerritoryID  
        WHERE t.CountryRegionCode = @Country',  
        N'OBJECT',  
        N'Sales.GetSalesOrderByCountry',  
        NULL,  
        N'OPTION (OPTIMIZE FOR (@Country = N''US''))';  
    GO  
    --Drop the plan guide.  
    EXEC sp_control_plan_guide N'DROP', N'Guide3';  
    GO  
    ```  
  
#### <a name="to-delete-all-plan-guides-in-a-database"></a>Para eliminar todas las guías de plan de una base de datos  
  
1.  En el **Explorador de objetos**, conéctese a una instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)].  
  
2.  En la barra de Estándar, haga clic en **Nueva consulta**.  
  
3.  Copie y pegue el siguiente ejemplo en la ventana de consulta y haga clic en **Ejecutar**.  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    EXEC sp_control_plan_guide N'DROP ALL';  
    GO  
    ```  
  
 Para obtener más información, vea [sp_control_plan_guide &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-control-plan-guide-transact-sql).  
  
  