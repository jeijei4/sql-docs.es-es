---
title: Selección avanzada de objetos (SybaseToSQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.technology: ssma
ms.topic: conceptual
ms.assetid: d2baa90f-1b77-47ce-988d-1910c7c74103
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 3745a7599f986073d1b759b46fe33dd741d62b09
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68083551"
---
# <a name="advanced-object-selection-sybasetosql"></a>Selección avanzada de objetos (SybaseToSQL)
El cuadro de diálogo **sección de objeto avanzado** permite filtrar los objetos de base de datos mediante cadenas y subcadenas en el nombre del objeto y, a continuación, seleccionar o anular la selección de esos objetos. SSMA realiza operaciones de conversión y migración en objetos seleccionados.  
  
Para obtener acceso a este cuadro de diálogo, haga clic con el botón derecho en un explorador de metadatos y seleccione **selección avanzada de objetos**.  
  
Cuando abra por primera vez el cuadro de diálogo, haga clic en **Mostrar elementos de subcategorías** para mostrar todos los objetos que tienen metadatos cargados en el proyecto. Después, puede escribir cadenas para filtrar los elementos. Por ejemplo, escriba la cadena "Company" para mostrar todos los elementos cuyos nombres incluyan esa cadena.  
  
Antes de utilizar este cuadro de diálogo, puede forzar a SSMA para cargar todos los metadatos, ya sea convirtiendo los esquemas o guardando el proyecto.  
  
## <a name="options"></a>Opciones  
**Comprobar todos los elementos**  
Agrega una marca de verificación junto a todos los elementos. Estos elementos se seleccionarán inmediatamente en el explorador de metadatos.  
  
**Desactivar todos los elementos**  
Quita la marca de verificación junto a todos los elementos. Estos elementos se borrarán inmediatamente en el explorador de metadatos.  
  
**Modo de vista de lista**  
Muestra los elementos filtrados en una lista.  
  
**Modo de vista de tabla**  
Muestra los elementos filtrados en una tabla.  
  
**Solo se muestran los elementos cargados**  
Alterna la presentación de categorías o elementos. Cuando se selecciona este botón, SSMA muestra todos los elementos que coinciden con los criterios de filtro y los que se cargaron previamente. Cuando no se selecciona este botón, SSMA muestra las carpetas de categorías.  
  
**Filter**  
Escriba la cadena que desea utilizar para filtrar elementos. Por ejemplo, para buscar todos los elementos disponibles que contengan la cadena "ID" en el nombre del elemento, escriba la cadena "ID" en el cuadro de **filtro** .  
  
Si los elementos coinciden con los criterios de filtro, las categorías o elementos aparecerán a medida que se escribe la cadena. Para ver los elementos coincidentes, se recomienda hacer clic en el botón **solo elementos cargados mostrados** .  
  
**Borrar filtro**  
Borra el cuadro de **filtro** .  
  
