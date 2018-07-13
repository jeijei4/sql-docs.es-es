---
title: Coloca las actualizaciones (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology: native-client
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- SQLSetPos function
- SQLSetCursorName function
- ODBC applications, cursors
- cursors [ODBC], positioned updates
- positioned updates [ODBC]
- ODBC cursors, positioned updates
ms.assetid: ff404e02-630f-474d-b5d4-06442b756991
caps.latest.revision: 32
author: MightyPen
ms.author: genemi
manager: craigg
ms.openlocfilehash: c5c6f1874c84c294aba4bbf167de69adcabc4da4
ms.sourcegitcommit: f8ce92a2f935616339965d140e00298b1f8355d7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2018
ms.locfileid: "37410060"
---
# <a name="positioned-updates-odbc"></a>Actualizaciones por posición (ODBC)
  ODBC admite dos métodos para realizar actualizaciones por posición en un cursor:  
  
-   **SQLSetPos**  
  
-   Cláusula WHERE CURRENT OF  
  
 El enfoque más común es usar **SQLSetPos**. Tiene las opciones siguientes.  
  
 SQL_POSITION  
 Sitúa el cursor en una fila específica del conjunto de filas actual.  
  
 SQL_REFRESH  
 Actualiza las variables de programa enlazadas a las columnas del conjunto de resultados mediante los valores de la fila en la que está situado el cursor actualmente.  
  
 SQL_UPDATE  
 Actualiza la fila actual del cursor mediante los valores almacenados en las variables de programa que están enlazadas a las columnas del conjunto de resultados.  
  
 SQL_DELETE  
 Elimina la fila actual del cursor.  
  
 **SQLSetPos** puede utilizarse con cualquier instrucción conjunto de resultados cuando los atributos de cursor de identificador de instrucción están configurados para utilizar cursores de servidor. Las columnas del conjunto de resultados deben estar enlazadas a variables de programa. Tan pronto como la aplicación captura una fila llama a **SQLSetPos**(SQL_POSTION) para colocar el cursor en la fila. A continuación, la aplicación podría llamar a SQLSetPos(SQL_DELETE) para eliminar la fila actual, o puede mover los nuevos valores de datos a las variables de programa enlazadas y llamar a SQLSetPos(SQL_UPDATE) para actualizar la fila actual.  
  
 Pueden actualizar o eliminar cualquier fila del conjunto de filas con las aplicaciones **SQLSetPos**. Una llamada a **SQLSetPos** es una buena alternativa para crear y ejecutar una instrucción SQL. **SQLSetPos** opera en el conjunto de filas actual y se puede usar solo después de llamar a [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).  
  
 Tamaño del conjunto de filas se establece mediante una llamada a [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) con un argumento de atributo de SQL_ATTR_ROW_ARRAY_SIZE. **SQLSetPos** usa un nuevo tamaño del conjunto de filas, pero solo después de llamar a **SQLFetch** o **SQLFetchScroll**. Por ejemplo, si se cambia el tamaño del conjunto de filas, **SQLSetPos** se llama y, a continuación, **SQLFetch** o **SQLFetchScroll** se llama. La llamada a **SQLSetPos** utiliza el tamaño del conjunto de filas anterior, pero **SQLFetch** o **SQLFetchScroll** usa el nuevo tamaño del conjunto de filas.  
  
 La primera fila del conjunto de filas es el número de fila 1. El argumento RowNumber de **SQLSetPos** debe identificar una fila del conjunto de filas; es decir, su valor debe ser en el intervalo comprendido entre 1 y el número de filas que se han capturado recientemente. Esto valor puede ser menor que el tamaño del conjunto de filas. Si RowNumber es 0, la operación se aplica a cada fila del conjunto de filas.  
  
 La operación de eliminación de **SQLSetPos** hace que el origen de datos de eliminar una o varias filas seleccionadas de una tabla. Para eliminar filas con **SQLSetPos**, la aplicación llama a **SQLSetPos** con Operation establecido en SQL_DELETE y RowNumber establecido en el número de la fila a eliminar. Si RowNumber es 0, se eliminan todas las filas del conjunto de filas.  
  
 Después de **SQLSetPos** devuelve la fila eliminada es la fila actual y su estado es SQL_ROW_DELETED. La fila no se puede usar en cualquier operación de colocación adicional, como las llamadas a [SQLGetData](../native-client-odbc-api/sqlgetdata.md) o **SQLSetPos**.  
  
 Cuando elimina todas las filas del conjunto de filas (RowNumber es igual a 0), la aplicación puede impedir que el controlador elimine determinadas filas utilizando la matriz de operación de fila al igual que la operación de actualización de **SQLSetPos**.  
  
 Cada fila que se elimina debe ser una fila que exista en el conjunto de resultados. Si los búferes de la aplicación se rellenaron con los valores capturados, y si se ha mantenido una matriz de estado de fila, sus valores en cada una de estas posiciones de fila no deben ser SQL_ROW_DELETED, SQL_ROW_ERROR ni SQL_ROW_NOROW.  
  
 Las actualizaciones por posición también se pueden realizar utilizando la cláusula WHERE CURRENT OF en instrucciones UPDATE, DELETE e INSERT. WHERE CURRENT OF requiere un nombre de cursor que ODBC generará cuando la [SQLGetCursorName](../native-client-odbc-api/sqlgetcursorname.md) se llama a la función, o que se puede especificar mediante una llamada a **SQLSetCursorName**. A continuación, se incluyen los pasos generales utilizados para ejecutar una actualización WHERE CURRENT OF en una aplicación ODBC:  
  
-   Llame a **SQLSetCursorName** para establecer un nombre para el identificador de instrucción de cursor.  
  
-   Genere una instrucción SELECT con una cláusula FOR UPDATE OF y ejecútela.  
  
-   Llame a **SQLFetchScroll** para recuperar un conjunto de filas o **SQLFetch** para recuperar una fila.  
  
-   Llame a **SQLSetPos** (SQL_POSITION) para colocar el cursor en la fila.  
  
-   Compilar y ejecutar una instrucción UPDATE con una cláusula WHERE CURRENT OF utilizando el nombre del cursor establecido con **SQLSetCursorName**.  
  
 Como alternativa, podría llamar a **SQLGetCursorName** después de ejecutar la instrucción SELECT en lugar de llamar **SQLSetCursorName** antes de ejecutar la instrucción SELECT. **SQLGetCursorName** devuelve un nombre de cursor predeterminado asignado por ODBC si no establece un nombre de cursor mediante **SQLSetCursorName**.  
  
 **SQLSetPos** es preferible a WHERE OF actual cuando se utilizan cursores de servidor. Si utiliza un cursor estático actualizable con la biblioteca de cursores ODBC, la biblioteca de cursores implementa las actualizaciones WHERE CURRENT OF agregando una cláusula WHERE con los valores de clave de la tabla subyacente. Esto puede dar lugar a actualizaciones no deseadas si las claves de la tabla no son únicas.  
  
## <a name="see-also"></a>Vea también  
 [Uso de cursores &#40;ODBC&#41;](using-cursors-odbc.md)  
  
  