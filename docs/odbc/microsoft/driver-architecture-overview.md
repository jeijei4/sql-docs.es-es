---
title: Información general sobre la arquitectura de controladores | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- Visual FoxPro ODBC driver [ODBC], architecture
- FoxPro ODBC driver [ODBC], architecture
ms.assetid: ef5a91cd-158e-40bf-b5a8-8ba535c4705e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: cd55290e09fbd35f5a1559ce4209693ef8eaaf73
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81303466"
---
# <a name="driver-architecture-overview"></a>Información general de la arquitectura de controlador
El controlador ODBC de Microsoft Visual FoxPro es un controlador de 32 bits que permite abrir y consultar una base de datos de Microsoft Visual FoxPro o tablas de FoxPro a través de la interfaz de conectividad abierta de bases de datos (ODBC). Puede tener acceso a los datos de FoxPro mediante los siguientes tipos de aplicaciones:  
  
-   Una aplicación Microsoft Office, como Microsoft Excel o Microsoft Word, que utiliza Microsoft Query para comunicarse con ODBC.  
  
-   Aplicación escrita en Microsoft Visual C++ o C que usa la API del SDK de ODBC.  
  
-   Una aplicación escrita en Microsoft Visual Basic o Microsoft Visual Basic para Aplicaciones.  
  
 En cada caso, la solicitud de información usa la API de ODBC. El administrador de controladores ODBC funciona con el controlador ODBC de Visual FoxPro para abrir y recuperar datos de tablas y bases de datos de FoxPro.  
  
 La arquitectura se representa en el diagrama siguiente:  
  
 ![Muestra la arquitectura de controladores ODBC](../../odbc/microsoft/media/vfparch.gif "vfparch")  
  
 Esta sección contiene los temas siguientes.  
  
-   [Terminología de Visual FoxPro](../../odbc/microsoft/visual-foxpro-terminology.md)  
  
-   [Instalar y configurar el controlador ODBC de Visual FoxPro](../../odbc/microsoft/installing-and-configuring.md)  
  
-   [Con el controlador ODBC de Visual FoxPro](../../odbc/microsoft/using-the-visual-foxpro-odbc-driver.md)
