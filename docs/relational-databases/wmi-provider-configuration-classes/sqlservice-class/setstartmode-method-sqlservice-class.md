---
title: Método SetStartMode (SqlService)
ms.custom: seo-lt-2019
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
apiname:
- SetStartMode Method (SqlService Class)
apilocation:
- sqlmgmproviderxpsp2up.mof
apitype: MOFDef
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 15cfa1eddcd9a32b51984d3833c288fc006d395b
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85888352"
---
# <a name="setstartmode-method-sqlservice-class"></a>Método SetStartMode (clase SqlService)
[!INCLUDE [SQL Server](../../../includes/applies-to-version/sqlserver.md)]
  Modifica el modo de inicio de la instancia del servicio.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
object.SetStartMode(StartMode)  
```  
  
## <a name="parts"></a>Partes  
 *object*  
 Objeto de la [clase SqlService](../../../relational-databases/wmi-provider-configuration-classes/sqlservice-class/sqlservice-class.md) que representa el servicio.  
  
#### <a name="parameters"></a>Parámetros  
 *StartMode*  
 Valor de **uint32** que especifica el modo de inicio de la instancia del servicio.  
  
 Los valores válidos son los siguientes:  
  
 Valor = 0. Boot: controlador de dispositivo iniciado por el cargador del sistema operativo. Este valor solamente es válido para servicios de controladores.  
  
 Valor = 1. System: controlador de dispositivo iniciado por el método **IoInitSystem** . Este valor solamente es válido para servicios de controladores.  
  
 Valor = 2. Automatic: servicio que el administrador de control de servicios iniciará automáticamente durante el inicio del sistema.  
  
 Valor = 3. Manual: servicio que el administrador de equipo iniciará cuando un proceso llame al método **StartService** .  
  
 Valor = 4. Disabled: el servicio ya no se puede iniciar.  
  
## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto  
 Valor de **uint32** que es igual a 0 si se modificó el servicio correctamente o igual a 1 si no se admite la solicitud. Cualquier otro número indica que hubo un error.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="see-also"></a>Consulte también  
 [Iniciar y detener servicios](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)  
  
  
