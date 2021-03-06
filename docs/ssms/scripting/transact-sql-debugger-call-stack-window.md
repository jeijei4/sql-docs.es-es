---
title: Ventana de pila de llamadas
titleSuffix: T-SQL debugger
ms.prod: sql
ms.technology: scripting
ms.topic: conceptual
helpviewer_keywords:
- Call Stack Window [Transact-SQL]
ms.assetid: ddb0b19c-87cd-4883-bcb8-ec09ffb30369
author: markingmyname
ms.author: maghan
ms.reviewer: ''
ms.custom: seo-lt-2019
ms.date: 12/04/2019
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 2c15e01a9555ceeacbbd741660cd19baba1f6842
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2020
ms.locfileid: "75243377"
---
# <a name="transact-sql-debugger---call-stack-window"></a>Depurador de Transact-SQL: ventana Pila de llamadas

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

La ventana **Pila de llamadas** muestra los módulos de la pila de llamadas y los tipos de datos y valores de los parámetros que se pasen a los módulos. [!INCLUDE[tsql](../../includes/tsql-md.md)] incluyen procedimientos almacenados, funciones y desencadenadores). Para mostrar la pila de llamadas, debe estar en modo de depuración.  

[!INCLUDE[ssms-old-versions](../../includes/ssms-old-versions.md)]

## <a name="task-list"></a>Lista de tareas

**Para tener acceso a la ventana Pila de llamadas**

- En el menú **Depurar** , haga clic en **Ventanas**y, a continuación, en **Pila de llamadas**.

**Para cambiar el marco de Pila de llamadas actual**

Puede utilizar cualquiera de los procedimientos siguientes para convertir un marco de pila en el marco actual:

- Haga clic con el botón derecho en el marco de pila y, después, haga clic en **Cambiar a marco**.

- Haga doble clic en el marco de pila.  

**Para ver el origen de un marco distinto del marco actual**

- Haga clic con el botón derecho en el marco de pila y, después, haga clic en **Ir al código fuente**.

## <a name="stack-frames"></a>Marcos de pila

Cada fila de la ventana **Pila de llamadas** se conoce como marco de pila y representa o bien una llamada de un archivo de script de [!INCLUDE[tsql](../../includes/tsql-md.md)] a un módulo o bien una llamada de un módulo a otro. El marco de pila inferior de la pantalla indica la línea de la ventana del Editor de consultas de [!INCLUDE[ssDE](../../includes/ssde-md.md)] que realizó la primera llamada en la pila. La fila superior indica la línea en la que el depurador pausó la ejecución y se identifica mediante una flecha amarilla en el margen izquierdo de la ventana. Cada fila intermedia indica el módulo y el número de línea del código fuente que llamó al marco de pila superior siguiente.  

Todas las expresiones de las ventanas **Variables locales**, **Inspección**e **Inspección rápida** se evalúan según el marco de pila actual. La ventana del Editor de consultas muestra el código para el marco actual. De forma predeterminada, este marco es el marco superior de la pila, en el que el depurador de [!INCLUDE[tsql](../../includes/tsql-md.md)] detuvo la ejecución. Al cambiar el marco de pila actual a otro marco, las expresiones en las ventanas **Variables locales**, **Inspección**e **Inspección rápida** se vuelven a evaluar en el contexto del nuevo marco y el código fuente del nuevo marco se muestra en la ventana del Editor de consultas.  
  
## <a name="columns"></a>Columnas

 **Nombre**  
 Muestra información sobre un módulo en la pila de llamadas.  
  
 En la fila inferior de la pila de llamadas, **Nombre** muestra la ventana de código fuente del Editor de consultas y el número de línea de la primera llamada en la pila. Para las otras filas, **Nombre** tiene el formato **módulo (instancia.baseDeDatos) (listaDeParámetros) númeroDeLínea**.  
  
 **módulo**  
 Es el nombre del procedimiento almacenado o función que llamó al marco siguiente.  
  
 **instancia.baseDeDatos**  
 Es la instancia del [!INCLUDE[ssDE](../../includes/ssde-md.md)] y la base de datos que contiene el módulo.  
  
 **listaDeParámetros**  
 Indica el tipo de datos, nombre y valor de cada parámetro que se pasa durante la llamada al módulo.  
  
 **LineNumber**  
 Para todas las filas excepto la fila superior, **númeroDeLínea** indica qué línea en el módulo llamó al marco. Para la fila superior, **númeroDeLínea** indica la línea en la que actualmente se centra el depurador.  
  
 **Lenguaje**  
 Muestra **Transact-SQL** para [!INCLUDE[tsql](../../includes/tsql-md.md)].  
  
## <a name="see-also"></a>Consulte también

- [Depurador de Transact-SQL](../../relational-databases/scripting/transact-sql-debugger.md)
- [Ver información del depurador de Transact-SQL](../../relational-databases/scripting/transact-sql-debugger-information.md)
- [Avanzar paso a paso por el código Transact-SQL](../../relational-databases/scripting/step-through-transact-sql-code.md)
