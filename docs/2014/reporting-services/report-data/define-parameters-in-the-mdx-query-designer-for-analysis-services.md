---
title: Definir parámetros en el Diseñador de consultas MDX para Analysis Services (generador de informes y SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- parameters [Reporting Services], MDX
- Multidimensional Expressions [Reporting Services]
- Data Mining Prediction [Reporting Services]
- MDX [Reporting Services], defining parameters
- DMX [Reporting Services]
ms.assetid: 4ad1e5bc-f510-4752-b4f6-589e55317a90
caps.latest.revision: 34
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: c46a722ce7f06e816a6625297ab35c9f5548c236
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37179582"
---
# <a name="define-parameters-in-the-mdx-query-designer-for-analysis-services-report-builder-and-ssrs"></a>Definir parámetros en el diseñador de consultas MDX para Analysis Services (Generador de informes y SSRS)
  Si desea incluir parámetros en una consulta MDX para un origen de datos de [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] , debe agregar un parámetro de consulta a la consulta. En el diseñador de consultas MDX, puede agregar un parámetro de consulta tanto en el modo de diseño como en el modo de consulta mediante la especificación de un filtro. Después de definir la consulta con un parámetro de consulta, Reporting Services crea automáticamente un parámetro de informe y un conjunto de datos para proporcionar la lista de valores válidos. Esto permite al usuario especificar un valor que se pasa directamente a la consulta.  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
### <a name="to-define-a-query-parameter-in-mdx-in-design-mode"></a>Para definir un parámetro de consulta en MDX en el modo de diseño  
  
1.  En el panel datos de informe, haga doble clic en un conjunto de datos creado a partir de un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] tipo de origen de datos y, a continuación, haga clic en **consulta**. El diseñador de consultas MDX se abre en el modo de diseño.  
  
2.  Arrastre una dimensión hacia el área de filtro y colóquela en la primera celda de la columna **Dimensión** .  
  
3.  En la columna **Jerarquía** , elija un valor en la lista desplegable.  
  
4.  En la columna **Operador** , elija a un operador en la lista desplegable.  
  
5.  En la columna **Expresión de filtro** , seleccione valores individuales en la lista desplegable o haga clic en el miembro **Todos** para elegir todos los valores.  
  
6.  En la columna **Parámetros** , active la casilla para crear un parámetro de informe.  
  
7.  Haga clic en **Ejecutar**.  
  
     Después de ejecutar la consulta, haga clic en **Diseño** en la barra de herramientas para cambiar al modo de consulta y ver la consulta MDX que ha creado. Si desea continuar usando el modo de diseño para desarrollar la consulta, no cambie el texto de la consulta en el modo de consulta. Haga clic en **Diseño** para volver al modo de diseño.  
  
8.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     En el panel Datos de informe, expanda el nodo Parámetros para mostrar el parámetro de informe que se ha creado automáticamente para el filtro.  
  
     Para ver el conjunto de datos que proporciona los valores disponibles para el parámetro de informe, haga clic con el botón secundario en cualquier área en blanco del panel Datos de informe y, a continuación, haga clic en **Mostrar conjuntos de datos ocultos**. El panel Datos de informe muestra todos los conjuntos de datos del informe.  
  
### <a name="to-define-a-query-parameter-in-mdx-in-query-mode"></a>Para definir un parámetro de consulta en MDX en el modo de consulta  
  
1.  En el panel datos de informe, haga doble clic en un conjunto de datos creado a partir de un [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] tipo de origen de datos y, a continuación, haga clic en **consulta**. El diseñador de consultas MDX se abre en el modo de diseño.  
  
2.  En la barra de herramientas, haga clic en **Diseño** para cambiar al modo de consulta.  
  
3.  En la barra de herramientas del diseñador de consultas MDX, haga clic en **Parámetros de consulta** (![Icono del cuadro de diálogo Parámetros de consulta](../../analysis-services/media/iconqueryparameter.gif "Icono del cuadro de diálogo Parámetros de consulta")). Se abrirá el cuadro de diálogo Parámetros de consulta.  
  
4.  En la columna **Parámetro**, haga clic en **\<Escribir parámetro>** y luego escriba el nombre de un parámetro.  
  
5.  En la columna **Dimensión** , elija un valor en la lista desplegable.  
  
6.  En la columna **Jerarquía** , elija un valor en la lista desplegable.  
  
7.  En la columna **Valores múltiples** , active la casilla para crear un parámetro de varios valores.  
  
8.  En la lista desplegable de la columna **Predeterminado** , seleccione un valor o varios valores, dependiendo de lo que haya elegido en el paso 5.  
  
9. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
10. En la barra de herramientas del diseñador de consultas, haga clic en **Ejecutar**.  
  
11. [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
     En el panel Datos de informe, expanda el nodo Parámetros para mostrar el parámetro de informe que se ha creado automáticamente para el filtro.  
  
     Para ver el conjunto de datos que proporciona los valores disponibles para el parámetro de informe, haga clic con el botón secundario en cualquier área en blanco del panel Datos de informe y, a continuación, haga clic en **Mostrar conjuntos de datos ocultos**. El panel Datos de informe muestra todos los conjuntos de datos del informe.  
  
## <a name="see-also"></a>Vea también  
 [Tipo de conexión de Analysis Services para MDX &#40;SSRS&#41;](analysis-services-connection-type-for-mdx-ssrs.md)   
 [Interfaz de usuario del diseñador de consultas MDX de Analysis Services](analysis-services-mdx-query-designer-user-interface.md)  
  
  