---
title: Limitaciones de la cláusula ORDER BY | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC SQL grammar, ORDER BY clause limitations
- ORDER BY clause limitations [ODBC]
ms.assetid: fd4ddc7c-9c7e-4a0c-a781-e5427dfb2e18
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: e80fcf8b1f2e3e83182e3278b63bdb856c7189fe
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81292935"
---
# <a name="order-by-clause-limitations"></a>ORDEN por cláusula limitaciones
Si una instrucción SELECT contiene una cláusula GROUP BY y una cláusula ORDER BY, la cláusula ORDER BY solo puede contener una columna en el conjunto de resultados o una expresión en la cláusula GROUP BY.
