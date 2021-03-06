---
title: ADCPROP_UPDATERESYNC_ENUM | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- ADCPROP_UPDATERESYNC_ENUM
helpviewer_keywords:
- ADCPROP_UPDATERESYNC_ENUM [ADO]
ms.assetid: bc9e1a37-e969-47e9-8382-0bbfffa2034f
author: rothja
ms.author: jroth
ms.openlocfilehash: d27169aa9da35f84a1d91985f7f2d1a41035a100
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760711"
---
# <a name="adcprop_updateresync_enum"></a>ADCPROP_UPDATERESYNC_ENUM
Especifica si el método [UpdateBatch](../../../ado/reference/ado-api/updatebatch-method.md) va seguido de una operación de método [Resync](../../../ado/reference/ado-api/resync-method.md) implícita y, en caso afirmativo, el ámbito de esa operación.  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adResyncAll**|15|Invoca **Resync** con el valor combinado de todos los demás miembros de ADCPROP_UPDATERESYNC_ENUM.|  
|**adResyncAutoIncrement**|1|Predeterminada. Intenta recuperar el nuevo valor de identidad para las columnas que se incrementan o generan automáticamente en el origen de datos, como los campos Autonuméricos de Microsoft Jet o las columnas de identidad de Microsoft SQL Server.|  
|**adResyncConflicts**|2|Invoca la **resincronización** de todas las filas en las que se produjo un error en la operación de actualización o eliminación debido a un conflicto de simultaneidad.|  
|**adResyncInserts**|8|Invoca **Resync** para todas las filas insertadas correctamente. Sin embargo, los valores de columna de incremento automático no se vuelven a sincronizar. En su lugar, el contenido de las filas recién insertadas se vuelve a sincronizar según el valor de clave principal existente. Si la clave principal es un valor de incremento automático, **Resync** no recuperará el contenido de la fila deseada. Para incrementar automáticamente los valores de clave principal de incremento automático, llame a **UpdateBatch** con el valor combinado **adResyncAutoIncrement**  +  **adResyncInserts**.|  
|**adResyncNone**|0|No invoca la **resincronización**.|  
|**adResyncUpdates**|4|Invoca **Resync** para todas las filas actualizadas correctamente.|  
  
## <a name="applies-to"></a>Se aplica a  
 [Propiedad dinámica Update Resync (ADO)](../../../ado/reference/ado-api/update-resync-property-dynamic-ado.md)
