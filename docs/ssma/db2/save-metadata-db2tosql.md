---
title: Guardar metadatos (DB2ToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 9a76083e-4902-449e-b125-7e9259fc37f7
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 8fb0c8849ce56fd424a93234d8878b19e19b5bdd
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68060088"
---
# <a name="save-metadata-db2tosql"></a>Guardar metadatos (DB2ToSQL)
El cuadro de diálogo **guardar metadatos** le solicita que cargue los metadatos en el proyecto de SSMA antes de guardarlo. Esto le permite tener un archivo de proyecto completo que puede usar sin conexión y enviar a otras personas, como personal de soporte técnico.  
  
Para tener acceso al cuadro de diálogo **guardar metadatos** , guarde el proyecto. Si faltan metadatos, SSMA mostrará el cuadro de diálogo **guardar metadatos** .  
  
## <a name="options"></a>Opciones  
**Nombre**  
El nombre de cada base de datos del proyecto.  
  
**Estado**  
Indica si los metadatos se cargan en el proyecto de SSMA o si faltan metadatos.  
  
SSMA carga los metadatos en el proyecto según sea necesario. Los metadatos se cargan automáticamente al examinar los metadatos y convertir los esquemas.  
  
**Seleccionar todo**  
Selecciona todas las bases de datos de la lista.  
  
**Claridad**  
Desactiva la casilla para todas las bases de datos con metadatos que faltan. No puede desactivar la casilla si se han cargado los metadatos.  
  
**Guardar**  
Guarda el proyecto y carga los metadatos de las bases de datos seleccionadas que tienen metadatos que faltan.  
  
**Cancelar**  
Cancela la operación de guardar. Los metadatos que faltan no se cargan en el proyecto.  
  
