---
title: SQLTables (controlador ODBC de Visual FoxPro) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLTables function [ODBC], Visual FoxPro ODBC Driver
ms.assetid: 69e2a038-5def-423f-91aa-8756e069dd2a
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 5467fc8c1717d5ceb548b3950a0894fd2a1b4499
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81299294"
---
# <a name="sqltables-visual-foxpro-odbc-driver"></a>SQLTables (controlador ODBC de Visual FoxPro)
> [!NOTE]  
>  Este tema contiene información específica del controlador ODBC de Visual FoxPro. Para obtener información general sobre esta función, vea el tema correspondiente en referencia de la [API de ODBC](../../odbc/reference/syntax/odbc-api-reference.md).  
  
 Compatibilidad: completa  
  
 Conformidad con la API de ODBC: nivel 1  
  
 Devuelve la lista de nombres de tabla especificados por el parámetro en la instrucción **SQLTables** . Si no se especifica ningún parámetro, devuelve los nombres de tabla almacenados en el origen de datos actual. El controlador devuelve la información como un conjunto de resultados.  
  
 Las llamadas de tipo de enumeración no recibirán una entrada de conjunto de resultados para vistas remotas o vistas con parámetros locales. Sin embargo, una llamada a **SQLTables** con un especificador de nombre de tabla único encontrará una coincidencia para dicha vista si está presente con ese nombre; Esto permite que se use la API para comprobar los conflictos de nombres antes de la creación de una nueva tabla.  
  
> [!NOTE]  
>  El controlador ODBC de Visual FoxPro distingue entre [las](../../odbc/microsoft/visual-foxpro-terminology.md) tablas de base de datos y [las tablas disponibles](../../odbc/microsoft/visual-foxpro-terminology.md), incluso cuando ambos tipos de tablas se almacenan en el mismo directorio del sistema. Si el origen de datos es un directorio de tablas libres, el controlador ODBC de Visual FoxPro no cataloga ni devuelve los nombres de las tablas asociadas a una base de datos.  
  
 Para obtener más información, vea [SQLTables](../../odbc/reference/syntax/sqltables-function.md) en la *Referencia del programador de ODBC*.
