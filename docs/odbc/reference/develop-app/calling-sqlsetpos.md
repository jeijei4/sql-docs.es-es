---
title: Llamar a SQLSetPos | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- compatibility [ODBC], SQLSetPos
- SQLSetPos function [ODBC], calling
- upgrading applications [ODBC], SQLSetPos
- backward compatibility [ODBC], SqlSetPos
- application upgrades [ODBC], SQLSetPos
ms.assetid: 846354b8-966c-4c2c-b32f-b0c8e649cedd
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 46cfbb4e2e6b60f620cd7e38272bf9308ece91bc
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81306246"
---
# <a name="calling-sqlsetpos"></a>Llamar a SQLSetPos
En ODBC *2. x*, el puntero a la matriz de estado de fila era un argumento de **SQLExtendedFetch**. La matriz de estado de fila se actualizó más adelante mediante una llamada a **SQLSetPos**. Algunos controladores han confiado en el hecho de que esta matriz no cambia entre **SQLExtendedFetch** y **SQLSetPos**. En ODBC *3. x*, el puntero a la matriz de estado es un campo de descriptor y, por tanto, la aplicación puede cambiarlo fácilmente para que apunte a una matriz diferente. Esto puede ser un problema cuando una aplicación ODBC *3. x* está trabajando con un controlador ODBC *2. x* , pero está llamando a **SQLSetStmtAttr** para establecer el puntero de estado de la matriz y está llamando a **SQLFetchScroll** para capturar datos. El administrador de controladores lo asigna como una secuencia de llamadas a **SQLExtendedFetch**. En el código siguiente, normalmente se produciría un error cuando el administrador de controladores asigna la segunda llamada a **SQLSetStmtAttr** al trabajar con un controlador ODBC *2. x* :  
  
```  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_STATUS_PTR, rgfRowStatus, 0);  
SQLFetchScroll(hstmt, fFetchType, iRow);  
SQLSetStmtAttr(hstmt, SQL_ATTR_ROW_STATUS_PTR, rgfRowStat1, 0);  
SQLSetPos(hstmt, iRow, fOption, fLock);  
```  
  
 El error se producirá si no hay ninguna manera de cambiar el puntero de estado de fila en ODBC *2. x* entre las llamadas a **SQLExtendedFetch**. En su lugar, el administrador de controladores realiza los pasos siguientes cuando se trabaja con un controlador ODBC *2. x* :  
  
1.  Inicializa una marca interna del administrador de controladores *fSetPosError* en true.  
  
2.  Cuando una aplicación llama a **SQLFetchScroll**, el administrador de controladores establece *fSetPosError* en false.  
  
3.  Cuando la aplicación llama a **SQLSetStmtAttr** para establecer SQL_ATTR_ROW_STATUS_PTR, el administrador de controladores establece *fSetPosError* igual toTRUE.  
  
4.  Cuando la aplicación llama a **SQLSetPos**, con *FSETPOSERROR* igual a true, el administrador de controladores genera SQL_ERROR con SQLSTATE HY011 (el atributo no se puede establecer ahora) para indicar que la aplicación intentó llamar a **SQLSetPos** después de cambiar el puntero de estado de fila, pero antes de llamar a **SQLFetchScroll**.
