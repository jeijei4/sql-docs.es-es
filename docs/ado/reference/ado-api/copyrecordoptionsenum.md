---
title: CopyRecordOptionsEnum | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- CopyRecordOptionsEnum
helpviewer_keywords:
- CopyRecordOptionsEnum enumeration [ADO]
ms.assetid: 2fa4eec5-d50b-4fd3-8ae7-40af441ba12b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8dc32a3cfad89e479b2541819b7ff6ad1bb1a4ed
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760261"
---
# <a name="copyrecordoptionsenum"></a>CopyRecordOptionsEnum
Especifica el comportamiento del método [CopyRecord](../../../ado/reference/ado-api/copyrecord-method-ado.md) .  
  
|Constante|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**adCopyAllowEmulation**|4|Indica que el proveedor de *origen* intenta simular la copia mediante operaciones de descarga y carga si se produce un error en este método debido a que el *destino*se encuentra en un servidor diferente o se presta servicio a través de un proveedor diferente del *origen*. Tenga en cuenta que las diferentes capacidades del proveedor pueden entorpecer el rendimiento o perder datos.|  
|**adCopyNonRecursive**|2|Copia el directorio actual, pero ninguno de sus subdirectorios, al destino. La operación de copia no es recursiva.|  
|**adCopyOverWrite**|1|Sobrescribe el archivo o directorio si el *destino* apunta a un archivo o directorio existente.|  
|**adCopyUnspecified**|-1|Predeterminada. Realiza la operación de copia predeterminada: se produce un error en la operación si el archivo o directorio de destino ya existe y la operación se copia de forma recursiva.|  
  
## <a name="adowfc-equivalent"></a>Equivalente de ADO/WFC  
 Estas constantes no tienen equivalentes de ADO/WFC.  
  
## <a name="applies-to"></a>Se aplica a  
 [Método CopyRecord (ADO)](../../../ado/reference/ado-api/copyrecord-method-ado.md)
