---
title: ESTABLECER comando único | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SET UNIQUE command [ODBC]
ms.assetid: 1f69e31e-4599-47cc-ac89-b86fba8703c5
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 7d3d37509450d1305891100b37bfd1ad026166e8
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300845"
---
# <a name="set-unique-command"></a>CONJUNTO único comando
Especifica si los registros con valores de clave de índice duplicados se mantienen en un archivo de índice.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
SET UNIQUE ON | OFF  
```  
  
## <a name="arguments"></a>Argumentos  
 ACTIVAR  
 Especifica que cualquier registro con un valor de clave de índice duplicado no se incluya en el archivo de índice. En el archivo de índice solo se incluye el primer registro con el valor de clave de índice original.  
  
 Apagado  
 (Valor predeterminado). Especifica que los registros con valores de clave de índice duplicados se incluyen en el archivo de índice.  
  
## <a name="remarks"></a>Observaciones  
 Un archivo de índice conserva su configuración exclusiva al emitir REINDEX. Para obtener más información, vea [index](../../odbc/microsoft/index-command.md).
