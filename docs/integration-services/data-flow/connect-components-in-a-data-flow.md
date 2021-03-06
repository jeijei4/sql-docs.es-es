---
title: Conectar componentes de un flujo de datos | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- components [Integration Services], connections
- connections [Integration Services], data flow components
ms.assetid: 70616a58-8921-4218-85bf-f3e90c5a9dbf
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0a2a700b9c2729f72d719ec5537c815daddd3518
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86923591"
---
# <a name="connect-components-in-a-data-flow"></a>Conectar componentes de un flujo de datos

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Este procedimiento describe cómo conectar la salida de los componentes de un flujo de datos con otros componentes dentro del mismo flujo de datos.  
El flujo de datos de un paquete se genera en la superficie de diseño de la pestaña **Flujo de datos** en el Diseñador [!INCLUDE[ssIS](../../includes/ssis-md.md)] . Si un flujo de datos contiene dos componentes de flujo de datos, puede conectar ambos conectando la salida de un origen o transformación con la entrada de una transformación o destino. El conector entre dos componentes de flujo de datos se denomina ruta.  
  
 El siguiente diagrama muestra un flujo de datos simple con un componente de origen, dos transformaciones, un componente de destino y las rutas que los conectan.  
  
 ![Flujo de datos](../../integration-services/data-flow/media/mw-dts-08.gif "flujo de datos")  
  
 Una vez conectados dos componentes, puede ver los metadatos de los datos que se mueven por la ruta y las propiedades de la ruta en el **Editor de rutas de flujo de datos**. Para más información, consulte [Integration Services Paths](../../integration-services/data-flow/integration-services-paths.md).  
  
 También puede agregar visores de datos a las rutas. Un visor de datos permite ver los datos que se mueven entre los componentes de flujo de datos cuando se ejecuta el paquete.  
  
### <a name="connect-components-in-a-data-flow"></a>Conectar componentes de un flujo de datos  
  
1.  En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el paquete que desea.  
  
2.  En el Explorador de soluciones, haga doble clic en el paquete para abrirlo.  
  
3.  Haga clic en la pestaña **Flujo de control** y luego haga doble clic en la tarea Flujo de datos que contiene el flujo de datos donde quiere conectar componentes.  
  
4.  En la superficie de diseño de la pestaña **Flujo de datos** , seleccione la transformación u origen que desea conectar.  
  
5.  Arrastre la flecha verde de salida de una transformación o un origen a una transformación o a un destino. Algunos componentes de flujo de datos tienen salidas de error que se pueden conectar de la misma manera.  
  
    > [!NOTE]  
    >  Algunos componentes de flujo de datos pueden tener varias salidas y cada una de ellas se puede conectar con una transformación o destino diferente.  
  
6.  Para guardar el paquete actualizado, haga clic en **Guardar los elementos seleccionados**, en el menú **Archivo**.  
  
## <a name="see-also"></a>Consulte también  
 [Agregar o eliminar un componente en un flujo de datos](../../integration-services/data-flow/add-or-delete-a-component-in-a-data-flow.md)   
 [Depurar el flujo de datos](../../integration-services/troubleshooting/debugging-data-flow.md) [Flujo de datos](../../integration-services/data-flow/data-flow.md)  
  
  
