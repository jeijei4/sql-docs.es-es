---
title: Operaciones de la biblioteca de cursores | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- ODBC cursor library [ODBC], backward compatibility
- compatibility [ODBC], cursor library
- upgrading applications [ODBC], cursor library
- application upgrades [ODBC], cursor library
- backward compatibility [ODBC], cursor library
- cursor library [ODBC], backward compatibility
ms.assetid: 04d514b1-dc4d-4b84-bf35-60f4657ef1f6
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: a2297e72aacad7ea91b7af934a47bebbc61f0686
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81301622"
---
# <a name="cursor-library-operations"></a>Operaciones de la biblioteca de cursores
> [!IMPORTANT]  
>  Esta característica se quitará en una versión futura de Windows. Evite usar esta característica en los nuevos trabajos de desarrollo y planee modificar las aplicaciones que actualmente la utilizan. Microsoft recomienda el uso de la funcionalidad de cursor del controlador.  
  
 Si una aplicación que trabaja con un controlador ODBC *2. x* realiza llamadas a la biblioteca de cursores ODBC *3. x* , es posible que la aplicación pueda usar las características ODBC *3. x* que no son compatibles con el controlador ODBC *2. x* . Sin embargo, un escritor de aplicaciones debe tener cuidado al usar estas características. El uso de la biblioteca de cursores ODBC *3. x* no convierte un controlador ODBC *2. x* en un controlador ODBC *3. x* .
