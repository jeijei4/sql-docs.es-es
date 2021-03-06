---
title: Conectando directamente con los controladores | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- connecting to driver [ODBC], SQLDriverConnect
- connecting to data source [ODBC], SqlDriverConnect
- SQLDriverConnect function [ODBC], connecting directly to drivers
- connecting to driver [ODBC], drivers
ms.assetid: f86e198f-a088-4401-9106-aa62a0eb8f6e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d6aacb5d3df985949e04cdd47a9fe460cddbde6a
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81299085"
---
# <a name="connecting-directly-to-drivers"></a>Conectar directamente a los controladores
Como se explicó en [elegir un origen de datos o un controlador](../../../odbc/reference/develop-app/choosing-a-data-source-or-driver.md), anteriormente en esta sección, algunas aplicaciones no quieren usar un origen de datos. En su lugar, quieren conectarse directamente a un controlador. **SQLDriverConnect** proporciona una forma para que la aplicación se conecte directamente a un controlador sin especificar un origen de datos. Conceptualmente, se crea un origen de datos temporal en tiempo de ejecución.  
  
 Para conectarse directamente a un controlador, la aplicación especifica la palabra clave **driver** en la cadena de conexión en lugar de la palabra clave **DSN** . El valor de la palabra clave **driver** es la descripción del controlador devuelto por **SQLDrivers**. Por ejemplo, supongamos que un controlador tiene el controlador Paradox de Descripción y requiere el nombre de un directorio que contenga los archivos de datos. Para conectarse a este controlador, es posible que la aplicación use cualquiera de las siguientes cadenas de conexión:  
  
```  
DRIVER={Paradox Driver};Directory=C:\PARADOX;  
DRIVER={Paradox Driver};  
```  
  
 Con la primera cadena, el controlador no necesitaría información adicional. Con la segunda cadena, el controlador necesitaría solicitar el nombre del directorio que contiene los archivos de datos.
