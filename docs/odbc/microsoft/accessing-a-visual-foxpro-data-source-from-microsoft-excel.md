---
title: Obtener acceso a un origen de datos de Visual FoxPro desde Microsoft Excel | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- FoxPro ODBC driver [ODBC], Excel
- Visual FoxPro data [ODBC], Excel
- Visual FoxPro data [ODBC], accessing
- Visual FoxPro ODBC driver [ODBC], Excel
ms.assetid: 2c143020-0403-4592-80e0-84229f3d40be
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: b4afaeebb5b3a0d2430eafc6febf98f2fb9c16bf
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81302086"
---
# <a name="accessing-a-visual-foxpro-data-source-from-microsoft-excel"></a>Obtiene acceso a un origen de datos de Visual FoxPro desde Microsoft Excel
Si tiene Microsoft Query instalado, puede crear un origen de datos en Microsoft Excel que se conecte a los datos de Visual FoxPro.  
  
### <a name="to-access-visual-foxpro-data-from-microsoft-excel"></a>Para tener acceso a los datos de Visual FoxPro desde Microsoft Excel  
  
1.  Abra una hoja de cálculo de Microsoft Excel.  
  
2.  En el menú datos, elija obtener datos externos. Se abre Microsoft Query.  
  
3.  En el cuadro de diálogo Seleccionar origen de datos, haga clic en otros.  
  
4.  En el cuadro de diálogo orígenes de datos ODBC, haga clic en nuevo.  
  
5.  En el cuadro de diálogo Agregar origen de datos, seleccione Microsoft Visual FoxPro driver en el cuadro de lista controladores ODBC instalados y haga clic en Aceptar.  
  
6.  En el [cuadro de diálogo Configuración de ODBC Visual FoxPro](../../odbc/microsoft/odbc-visual-foxpro-setup-dialog-box.md), escriba el nombre del origen de datos, seleccione el tipo de base de datos, escriba la ruta de acceso a la base de datos o directorio y haga clic en Aceptar.  
  
     El nuevo nombre del origen de datos se muestra en el cuadro de texto escribir origen de datos del cuadro de diálogo orígenes de datos ODBC.  
  
7.  Haga clic en Aceptar.  
  
     El nuevo nombre del origen de datos se selecciona en el cuadro de texto orígenes de datos disponibles del cuadro de diálogo Seleccionar origen de datos.  
  
8.  Haga clic en Usar.  
  
 Ahora puede agregar tablas a la consulta abierta. Para obtener más información sobre cómo crear una consulta, vea [importar datos en Microsoft Excel desde una base de datos de Visual FoxPro](../../odbc/microsoft/importing-data-into-microsoft-excel-from-a-visual-foxpro-database.md).
