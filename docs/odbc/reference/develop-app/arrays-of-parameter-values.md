---
title: Matrices de valores de parámetro | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- arrays of parameter values [ODBC]
- parameter arrays [ODBC]
ms.assetid: 9b572c5b-1dfe-40af-bebd-051548ab6d90
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: eb9389c769e3a7bb0c39959a559531e8051a7bec
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81298808"
---
# <a name="arrays-of-parameter-values"></a>Matrices de valores de parámetro
A menudo resulta útil para las aplicaciones pasar matrices de parámetros. Por ejemplo, si se usan matrices de parámetros y una instrucción **Insert** con parámetros, una aplicación puede insertar un número de filas a la vez. El uso de matrices tiene varias ventajas. En primer lugar, se reduce el tráfico de red porque los datos para muchas instrucciones se envían en un único paquete (si el origen de datos admite matrices de parámetros de forma nativa). En segundo lugar, algunos orígenes de datos pueden ejecutar instrucciones SQL con matrices más rápidas que la ejecución del mismo número de instrucciones SQL independientes. Por último, cuando los datos se almacenan en una matriz, como suele ser el caso de los datos de pantalla, la aplicación puede enlazar todas las filas de una columna determinada con una sola llamada a **SQLBindParameter** y actualizarlas ejecutando una única instrucción.  
  
 Desafortunadamente, no muchos orígenes de datos admiten matrices de parámetros. Sin embargo, un controlador puede emular matrices de parámetros ejecutando una instrucción SQL una vez para cada conjunto de valores de parámetro. Esto puede dar lugar a aumentos de velocidad, ya que el controlador puede preparar la instrucción que piensa ejecutar una vez para cada conjunto de parámetros. También podría dar lugar a un código de aplicación más sencillo.  
  
 Esta sección contiene los temas siguientes.  
  
-   [Las matrices de parámetros de enlace](../../../odbc/reference/develop-app/binding-arrays-of-parameters.md)  
  
-   [Utilizar matrices de parámetros](../../../odbc/reference/develop-app/using-arrays-of-parameters.md)
