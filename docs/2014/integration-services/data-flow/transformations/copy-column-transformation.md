---
title: Transformación Copiar columna | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- sql12.dts.designer.copycolumntrans.f1
helpviewer_keywords:
- columns [Integration Services], copying
- copying columns
- Copy Column transformation
ms.assetid: 1c72a313-9026-46bc-a57f-c6b3f47346f8
caps.latest.revision: 36
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 108876d1ae379eb348109af75fda4ac0b4d5b457
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36102890"
---
# <a name="copy-column-transformation"></a>Copiar columna, transformación
  La transformación Copiar columna crea columnas nuevas copiando columnas de entrada y agregando las columnas nuevas a la salida de transformación. En una fase posterior del flujo de datos se pueden aplicar distintas transformaciones a las copias de columnas. Por ejemplo, puede usar la transformación Copiar columna para crear una copia de una columna y después convertir los datos copiados a mayúsculas mediante la transformación Mapa de caracteres, o aplicar agregaciones a la nueva columna mediante la transformación Agregado.  
  
## <a name="configuration-of-the-copy-column-transformation"></a>Configuración de la transformación Copiar columna  
 Puede configurar la transformación Copiar columna especificando las columnas de entrada que desea copiar. Puede crear varias copias de una columna o crear copias de varias columnas en una operación.  
  
 Esta transformación tiene una entrada y una salida. No admite una salida de error.  
  
 Puede establecer propiedades a través del Diseñador [!INCLUDE[ssIS](../../../includes/ssis-md.md)] o mediante programación.  
  
 Para obtener más información acerca de las propiedades que puede establecer en el cuadro de diálogo **Editor de transformación Copiar columna** , vea [Copy Column Transformation Editor](../../copy-column-transformation-editor.md).  
  
 El cuadro de diálogo **Editor avanzado** indica las propiedades que se pueden establecer mediante programación. Para obtener más información acerca de las propiedades que puede establecer a través del cuadro de diálogo **Editor avanzado** o mediante programación, haga clic en uno de los temas siguientes:  
  
-   [Propiedades comunes](../../common-properties.md)  
  
-   [Propiedades personalizadas de transformación](transformation-custom-properties.md)  
  
 Para obtener más información sobre cómo establecer propiedades, vea [Establecer las propiedades de un componente de flujo de datos](../set-the-properties-of-a-data-flow-component.md).  
  
## <a name="see-also"></a>Vea también  
 [Flujo de datos](../data-flow.md)   
 [Transformaciones de Integration Services](integration-services-transformations.md)  
  
  