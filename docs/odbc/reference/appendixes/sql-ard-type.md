---
title: SQL_ARD_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- data types [ODBC], pseudo-type identifiers
- pseudo-type identifiers [ODBC], SQL_ARD_TYPE
- SQL_ARD_TYPE [ODBC]
ms.assetid: 8d87ca10-f955-4284-8689-e9f4cc31e7ae
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: d7e28d6babb7db8364697ae62092256396b44914
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81305036"
---
# <a name="sql_ard_type"></a>SQL_ARD_TYPE
El identificador de tipo de SQL_ARD_TYPE se usa para indicar que los datos de un búfer serán del tipo especificado en el campo SQL_DESC_CONCISE_TYPE de ARD. SQL_ARD_TYPE se escribe en el argumento *TargetType* de una llamada a **SQLGetData** en lugar de a un tipo de datos específico y permite que una aplicación cambie el tipo de datos del búfer cambiando el campo descriptor. Este valor une el tipo de datos del búfer * \*TargetValuePtr* al campo descriptor. (SQL_ARD_TYPE no se especifica en una llamada a **SQLBindCol** o **SQLBindParameter** porque el tipo del búfer enlazado ya está vinculado a los campos SQL_DESC_TYPE y SQL_DESC_CONCISE_TYPE y se puede cambiar en cualquier momento cambiando cualquiera de estos campos).  
  
 El identificador de tipo de SQL_ARD_TYPE se puede usar para especificar valores no predeterminados para la precisión inicial y los segundos de los tipos de datos de intervalo, y valores de precisión y escala para el tipo de datos SQL_C_NUMERIC. Para obtener más información, vea [invalidar la precisión predeterminada del principio y los segundos para tipos de datos de intervalo](../../../odbc/reference/appendixes/overriding-default-leading-and-seconds-precision-for-interval-data-types.md) e [invalidar la precisión y la escala predeterminadas para tipos de datos numéricos](../../../odbc/reference/appendixes/overriding-default-precision-and-scale-for-numeric-data-types.md), más adelante en este apéndice.
