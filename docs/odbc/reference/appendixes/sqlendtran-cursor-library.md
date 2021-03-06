---
title: SQLEndTran (biblioteca de cursores) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLEndTran function [ODBC], Cursor Library
ms.assetid: 92340b87-9084-4838-a509-e9ca22d5fd5c
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: c2277a67cd5410ea3c2a5d5b03b16d4533ed6ee1
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81304776"
---
# <a name="sqlendtran-cursor-library"></a>SQLEndTran (biblioteca de cursores)
> [!IMPORTANT]  
>  Esta característica se quitará en una versión futura de Windows. Evite usar esta característica en los nuevos trabajos de desarrollo y planee modificar las aplicaciones que actualmente la utilizan. Microsoft recomienda el uso de la funcionalidad de cursor del controlador.  
  
 En este tema se describe el uso de la función **SQLEndTran** en la biblioteca de cursores. Para obtener información general sobre **SQLEndTran**, consulte la [función SQLEndTran](../../../odbc/reference/syntax/sqlendtran-function.md).  
  
 La biblioteca de cursores no admite transacciones y pasa llamadas a **SQLEndTran** directamente al controlador. Sin embargo, la biblioteca de cursores admite los comportamientos commit y rollback del cursor devueltos por el origen de datos con los tipos de información SQL_CURSOR_ROLLBACK_BEHAVIOR y SQL_CURSOR_COMMIT_BEHAVIOR:  
  
-   En el caso de los orígenes de datos que conservan cursores entre transacciones, los cambios que se revierten en el origen de datos no se revierten en la memoria caché de la biblioteca de cursores. Para que la memoria caché coincida con los datos del origen de datos, la aplicación debe cerrar y volver a abrir el cursor.  
  
-   En el caso de los orígenes de datos que cierran los cursores en los límites de la transacción, la biblioteca de cursores cierra los cursores y elimina las cachés de todas las instrucciones de la conexión.  
  
-   En el caso de los orígenes de datos que eliminan instrucciones preparadas en los límites de las transacciones, la aplicación debe repreparar todas las instrucciones preparadas en la conexión antes de reejecutarlas.
