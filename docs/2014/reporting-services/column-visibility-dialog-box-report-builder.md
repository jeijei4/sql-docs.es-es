---
title: Cuadro de diálogo visibilidad de columna (generador de informes) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- "10127"
ms.assetid: 0c030cab-6087-45a5-99f0-c7bd693f20a1
caps.latest.revision: 12
author: douglaslM
ms.author: douglasl
manager: mblythe
ms.openlocfilehash: b5fbdc627473f449007af6dadcc73fcc69efc46f
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36199083"
---
# <a name="column-visibility-dialog-box-report-builder"></a>Cuadro de diálogo Visibilidad de columna (Generador de informes)
  Use el cuadro de diálogo **Visibilidad de columna** para mostrar u ocultar la columna seleccionada cuando se ejecuta el informe por primera vez o para usar otro elemento de informe para activar o desactivar la visibilidad de la columna.  
  
## <a name="options"></a>Opciones  
 **Cuando se ejecute inicialmente el informe**  
 Seleccione una opción para indicar cómo se muestra el elemento de informe inicialmente en el informe.  
  
 **Mostrar**  
 Elija esta opción para mostrar la columna.  
  
 **Ocultar**  
 Elija esta opción para ocultar la columna.  
  
 **Mostrar u ocultar en función de una expresión**  
 Elija esta opción para modificar la visibilidad inicial por medio de una expresión.  
  
 Escriba una expresión que se evalúa como un `Boolean` valo `True` para ocultar el elemento y `False` para mostrar el elemento. Haga clic en el botón Expresión (*fx*) para editar la expresión.  
  
 **Este elemento de informe puede alternar la presentación**  
 Elija esta opción para mostrar una imagen de alternancia que permita que el usuario muestre u oculte esta columna en un visor de informes HTML.  
  
 Escriba o seleccione el nombre de un cuadro de texto del informe en el que aparezca una imagen de alternancia, por ejemplo, Textbox1. El cuadro de texto que elija debe estar en el ámbito actual o en el ámbito contenedor de este elemento de informe. Por ejemplo, para alternar la visibilidad de las filas asociadas a un grupo secundario, seleccione un cuadro de texto de una fila asociada al grupo primario. Para alternar la visibilidad de un gráfico, seleccione un cuadro de texto que esté en el mismo ámbito contenedor que el gráfico; por ejemplo, un rectángulo o el cuerpo del informe.  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de expresiones &#40;Generador de informes y SSRS&#41;](report-design/expression-examples-report-builder-and-ssrs.md)   
 [Agregar una acción de expandir y contraer a un elemento &#40;Generador de informes y SSRS&#41;](report-design/add-an-expand-or-collapse-action-to-an-item-report-builder-and-ssrs.md)   
 [Imágenes &#40;el generador de informes SSRS&#41;](report-design/images-report-builder-and-ssrs.md)   
 [Ayuda del Generador de informes para cuadros de diálogo, paneles y asistentes](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md)   
 [Cuadro de diálogo de Propiedades de la imagen, General &#40;Generador de informes y SSRS&#41;](../../2014/reporting-services/image-properties-dialog-box-general-report-builder-and-ssrs.md)  
  
  