---
title: Tablas duplicadas | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: table-view-index, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- tables [SQL Server], duplicating
- duplicating tables
- table copying [SQL Server]
ms.assetid: c6b07423-d1e5-4e5e-8681-5088921f5df3
author: stevestein
ms.author: sstein
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 45fabf20b18fb0f3227f99ab2a6b5270e245562a
ms.sourcegitcommit: 58158eda0aa0d7f87f9d958ae349a14c0ba8a209
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "72907312"
---
# <a name="duplicate-tables"></a>Tablas duplicadas
[!INCLUDE[tsql-appliesto-ss2016-all-md](../../includes/tsql-appliesto-ss2016-all-md.md)]

  Puede duplicar una tabla existente en [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mediante [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] o [!INCLUDE[tsql](../../includes/tsql-md.md)] si crea una nueva tabla y, a continuación, copia la información de columna de una tabla existente.  
  
> [!IMPORTANT]  
>  Esta operación solo duplica la estructura de la tabla, pero no duplica ninguna fila de la tabla.  
  
 **En este tema**  
  
-   **Antes de empezar:**  
  
     [Seguridad](#Security)  
  
-   **Para duplicar una tabla con:**  
  
     [SQL Server Management Studio](#SSMSProcedure)  
  
     [Transact-SQL](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Antes de comenzar  
  
###  <a name="security"></a><a name="Security"></a> Seguridad  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permisos  
 Requiere el permiso CREATE TABLE en la base de datos de destino.  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> Uso de SQL Server Management Studio  
  
#### <a name="to-duplicate-a-table"></a>Para duplicar una tabla  
  
1.  Asegúrese de que está conectado a la base de datos en la que desea crear la tabla y de que la base de datos está seleccionada en el Explorador de objetos.  
  
2.  En el Explorador de objetos, haga clic con el botón derecho en **Tablas** y, luego, haga clic en **Nueva tabla**.  
  
3.  En el Explorador de objetos, haga clic con el botón derecho en la tabla que quiera copiar y, depués, haga clic en **Diseño**.  
  
4.  Seleccione las columnas de la tabla existente y haga clic en **Copiar** en el menú **Edición**.  
  
5.  Vuelva a la ventana nueva y seleccione la primera fila.  
  
6.  En el menú **Edición** , haga clic en **Pegar**.  
  
7.  En el menú **Archivo** , haga clic en **Guardar**_nombre de tabla_.  
  
8.  En el cuadro de diálogo **Elegir nombre** , escriba un nombre para la tabla nueva y haga clic en **Aceptar**.  

##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> Usar Transact-SQL  
  
#### <a name="to-duplicate-a-table-in-query-editor"></a>Para duplicar una tabla en el editor de consultas  
  
1.  Asegúrese de que está conectado a la base de datos en la que desea crear la tabla y de que la base de datos está seleccionada en el Explorador de objetos.  
  
2.  Haga clic con el botón derecho en la tabla que quiera duplicar, seleccione **Incluir tabla como**, seleccione **CREATE to**y, por último, **Nueva ventana del Editor de consultas**.  
  
3.  Cambie el nombre de la tabla.  
  
4.  Quite las columnas que no se necesiten en la nueva tabla.  
  
5.  Haga clic en **Ejecutar**.  
  
  
