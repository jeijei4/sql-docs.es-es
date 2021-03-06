---
title: IClientVirtualDeviceSet2::GetBufferHandle
titlesuffix: SQL Server VDI reference
description: En este artículo se proporciona una referencia para el comando IClientVirtualDeviceSet2::GetBufferHandle.
ms.date: 08/30/2019
ms.prod: sql
ms.prod_service: backup-restore
ms.technology: backup-restore
ms.topic: reference
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: cf187379aaa664e536710859e08bf084b14657d1
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85896898"
---
# <a name="iclientvirtualdeviceset2getbufferhandle-vdi"></a>IClientVirtualDeviceSet2::GetBufferHandle (VDI)

[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]

Es posible que algunas aplicaciones requieran más de un proceso para operar en los búferes devueltos por **IClientVirtualDevice2::GetCommand**. En esos casos, el proceso que recibe el comando puede usar **GetBufferHandle** para obtener un identificador independiente del proceso que identifica el búfer. Este identificador se puede comunicar a cualquier otro proceso que también tenga abierto el mismo conjunto de dispositivos virtuales. Después, ese proceso usaría IClientVirtualDeviceSet2::MapBufferHandle para obtener la dirección del búfer. Es probable que la dirección que obtenga sea distinta a la de su asociado, ya que cada proceso puede asignar búferes en direcciones diferentes.

## <a name="syntax"></a>Sintaxis

```c
HRESULT IClientVirtualDeviceSet2::GetBufferHandle (
   BYTE*         pBuffer,
   DWORD*      pBufferHandle
);
```

## <a name="parameters"></a>Parámetros

*pBuffer* Es la dirección de un búfer que se obtiene de un comando de lectura o escritura.

*pBufferHandle* Se devuelve un identificador único para el búfer.

## <a name="return-value"></a>Valor devuelto

|Valor devuelto | Explicación |
|---|---|
| NOERROR | La función se ha realizado correctamente. |
| VD_E_PROTOCOL | El conjunto de dispositivos virtuales no está abierto actualmente. |
| VD_E_INVALID | pBuffer no es una dirección válida. |

## <a name="remarks"></a>Observaciones

El proceso que invoca la función GetBufferHandle es responsable de invocar IClientVirtualDevice2::CompleteCommand cuando se complete la transferencia de datos.

## <a name="next-steps"></a>Pasos siguientes

Para más información, vea la [información general de la referencia de interfaces de dispositivo virtual de SQL Server](reference-virtual-device-interface.md).