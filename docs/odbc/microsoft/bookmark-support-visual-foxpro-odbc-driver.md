---
title: Compatibilidad con marcadores (controlador ODBC de Visual FoxPro) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- FoxPro ODBC driver [ODBC], bookmarks
- Visual FoxPro ODBC driver [ODBC], bookmarks
- bookmarks [ODBC]
ms.assetid: feb7ec20-3e0c-4a47-8feb-7dd9f23efdf6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: cacabc113547eaacf99ca94fc2f519ba962fcbd1
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81307706"
---
# <a name="bookmark-support-visual-foxpro-odbc-driver"></a>Compatibilidad con marcadores (controlador ODBC de Visual FoxPro)
El controlador ODBC de Visual FoxPro admite marcadores simples. Cuando se llama a [SQLGetInfo](../../odbc/microsoft/sqlgetinfo-visual-foxpro-odbc-driver.md) con el SQL_BOOKMARK_PERSISTENCE *InfoType*, el valor devuelto es SQL_BP_SCROLL.  
  
 Para obtener más información sobre los marcadores, vea [marcadores (ODBC)](../../odbc/reference/develop-app/bookmarks-odbc.md).
