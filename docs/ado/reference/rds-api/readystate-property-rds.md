---
title: Propiedad ReadyState (RDS) | Microsoft Docs
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- ReadyState property [ADO]
ms.assetid: 5be75bc7-1171-4440-a37e-c8cc6b5cd865
author: rothja
ms.author: jroth
ms.openlocfilehash: c5e1eb89c0e4c7dcbef736d2968a4ffd97a37b93
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82751217"
---
# <a name="readystate-property-rds"></a>Propiedad ReadyState (RDS)
Indica el progreso de un objeto [DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) a medida que recupera los datos en su objeto de [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) .  
  
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="settings-and-return-values"></a>Configuración y valores devueltos  
 Establece o devuelve uno de los valores siguientes.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|**adcReadyStateLoaded**|La consulta actual todavía se está ejecutando y no se ha capturado ninguna fila. El **conjunto de registros** del objeto **DataControl** no está disponible para su uso.|  
|**adcReadyStateInteractive**|Un conjunto inicial de filas recuperadas por la consulta actual se ha almacenado en el **conjunto de registros** del objeto **DataControl** y están disponibles para su uso. Todavía se están capturando las filas restantes.|  
|**adcReadyStateComplete**|Todas las filas recuperadas por la consulta actual se han almacenado en el conjunto de **registros** del objeto **DataControl** y están disponibles para su uso.<br /><br /> Este estado también existirá si se ha anulado una operación debido a un error o si el objeto de **conjunto de registros** no se ha inicializado.|  
  
> [!NOTE]
>  Cada archivo ejecutable del lado cliente que utiliza estas constantes debe proporcionar declaraciones para ellas. Puede cortar y pegar las declaraciones de constantes que desee del archivo Adcvbs. Inc, que se encuentra en la carpeta de instalación predeterminada de la biblioteca RDS.  
  
## <a name="remarks"></a>Observaciones  
 Use el evento [onreadystatechange](../../../ado/reference/rds-api/onreadystatechange-event-rds.md) para supervisar los cambios en la propiedad **ReadyState** durante una operación de consulta asincrónica. Esto es más eficaz que comprobar periódicamente el valor de la propiedad.  
  
 Si se produce un error durante una operación asincrónica, la propiedad **ReadyState** cambia a **adcReadyStateComplete**, la [propiedad State](../../../ado/reference/ado-api/state-property-ado.md) cambia de **adStateExecuting** a **adStateClosed**y la propiedad [valor](../../../ado/reference/ado-api/value-property-ado.md) del objeto de **conjunto de registros** no sigue siendo *nada*.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto DataControl (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de la propiedad ReadyState (VBScript)](../../../ado/reference/rds-api/readystate-property-example-vbscript.md)   
 [Método CANCEL (RDS)](../../../ado/reference/rds-api/cancel-method-rds.md)   
 [Propiedad ExecuteOptions (RDS)](../../../ado/reference/rds-api/executeoptions-property-rds.md)


