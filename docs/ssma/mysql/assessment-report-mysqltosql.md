---
title: Informe de evaluación (MySQLToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 5525d989-024c-402d-9e84-faa4721cc5b9
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: fb6d01bf9c02d0a7b96adf8e46eb354cd426db4d
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68139189"
---
# <a name="assessment-report-mysqltosql"></a>Informe de evaluación (MySQLToSQL)
La ventana Informe de evaluación muestra los resultados de la conversión de objetos de [!INCLUDE[tsql](../../includes/tsql-md.md)] base de datos a sintaxis y también puede ayudarle a calcular la complejidad y el costo de los proyectos de migración.  
  
Para tener acceso al informe de evaluación, seleccione los objetos que desea convertir en el explorador de metadatos de origen, haga clic con el botón derecho en **esquemas**y, después, seleccione **crear informe**.  
  
## <a name="options"></a>Opciones  
  
|||  
|-|-|  
|**Término**|**Definición**|  
|**Estadísticas de conversión**|Muestra las estadísticas de conversión por tipo de instrucción. Este panel está visible cuando se selecciona un objeto de grupo, como un esquema, o un objeto sin código en el panel izquierdo.|  
|**Objetos por categorías**|Muestra el número de objetos por categoría. Este panel solo es visible cuando se selecciona un objeto de grupo, como un esquema, o un objeto sin código en el panel izquierdo.|  
|**estadísticas**|Muestra las estadísticas de conversión del objeto seleccionado. Este panel solo es visible cuando se selecciona un objeto individual con código en el panel izquierdo. Es posible que tenga que expandir **estadísticas**, que se encuentra justo encima del panel **origen** , para ver este panel.|  
|**Origen**|Muestra el código de MySQL para el objeto seleccionado y resalta el código que no se [!INCLUDE[tsql](../../includes/tsql-md.md)]convirtió en. Este panel solo es visible cuando se selecciona un objeto individual con código en el panel izquierdo.<br /><br />Haga clic en los números de línea para establecer o Borrar marcadores. Use los botones situados en la parte superior del panel para navegar por el código.|  
|**Destino**|Muestra el código resultante [!INCLUDE[tsql](../../includes/tsql-md.md)] de la conversión para el objeto seleccionado y los mensajes de error para el código que no se ha convertido. Este panel solo es visible cuando se selecciona un objeto individual con código en el panel izquierdo.<br /><br />Haga clic en los números de línea para establecer o Borrar marcadores. Use los botones situados en la parte superior del panel para navegar por el código.|  
|**Panel Mensajes**|Muestra los errores, las advertencias y los mensajes informativos que se generaron al crear el informe de evaluación. Los mensajes se agrupan por número. Para ver el código que causó el error, haga clic en **errores**, **advertencias**o **información**, expanda la categoría de mensajes y, a continuación, haga clic en un mensaje.|  
  
