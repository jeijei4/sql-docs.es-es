---
title: Tipos de bloqueos | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- AdLockBatchOptimistic [ADO]
- AdLockReadOnly [ADO]
- AdLockUnspecified [ADO]
- locks [ADO], types
- AdLockOptimistic [ADO]
- AdLockPessimistic [ADO]
ms.assetid: 12a978c0-b8a0-4ef0-87f0-a43c13659272
author: rothja
ms.author: jroth
ms.openlocfilehash: f734b1eeaaba460169e3c8932d90fc31de6d23c2
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82759041"
---
# <a name="types-of-locks"></a>Tipos de bloqueos
## <a name="adlockbatchoptimistic"></a>adLockBatchOptimistic  
 Indica actualizaciones de Batch optimistas. Necesario para el modo de actualización por lotes.  
  
 Muchas aplicaciones capturan un número de filas a la vez y, a continuación, necesitan realizar actualizaciones coordinadas que incluyan el conjunto completo de filas que se van a insertar, actualizar o eliminar. Con los cursores de lotes, solo se necesita un recorrido de ida y vuelta al servidor, lo que mejora el rendimiento de las actualizaciones y reduce el tráfico de red. Mediante una biblioteca de cursores de proceso por lotes, puede crear un cursor estático y, a continuación, desconectarse del origen de datos. En este momento puede realizar cambios en las filas y, posteriormente, volver a conectarse y publicar los cambios en el origen de datos de un lote.  
  
## <a name="adlockoptimistic"></a>adLockOptimistic  
 Indica que el proveedor utiliza los registros de bloqueo de bloqueo optimista solo cuando se llama al método **Update** . Esto significa que existe la posibilidad de que otro usuario pueda cambiar los datos entre el momento en que se edita el registro y al llamar a **Update**, lo que crea conflictos. Utilice este tipo de bloqueo en situaciones en las que las posibilidades de una colisión son bajas o donde las colisiones se pueden resolver fácilmente.  
  
## <a name="adlockpessimistic"></a>adLockPessimistic  
 Indica un bloqueo pesimista, registro por registro. El proveedor hace lo necesario para garantizar la correcta modificación de los registros, normalmente mediante el bloqueo de los registros en el origen de datos inmediatamente antes de la edición. Por supuesto, esto significa que los registros no están disponibles para otros usuarios una vez que empiece a editar, hasta que libere el bloqueo mediante una llamada a **Update.** Use este tipo de bloqueo en un sistema en el que no se pueda permitir que se realicen cambios simultáneos en los datos, como en un sistema de reserva.  
  
## <a name="adlockreadonly"></a>adLockReadOnly  
 Indica los registros de solo lectura. No se pueden modificar los datos. Un bloqueo de solo lectura es el tipo de bloqueo "más rápido", ya que no requiere que el servidor mantenga un bloqueo en los registros.  
  
## <a name="adlockunspecified"></a>adLockUnspecified  
 No especifica un tipo de bloqueo.
