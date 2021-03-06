---
title: Objeto DataSpace (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- DataSpace object [RDS]
ms.assetid: 9194bffa-5bdf-4dff-af86-f7158c23bfa7
author: rothja
ms.author: jroth
ms.openlocfilehash: 8e0340eb56ec2b72c0f917f33a639ed5227d2c0b
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82752570"
---
# <a name="dataspace-object-rds"></a>Objeto DataSpace (RDS)
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 Crea proxies del lado cliente para objetos comerciales personalizados ubicados en el nivel intermedio.  
  
 El servicio de datos remoto necesita servidores proxy de objetos empresariales para que los componentes del lado cliente puedan comunicarse con los objetos empresariales ubicados en el nivel intermedio. Los proxies facilitan el empaquetado, desempaquetado y transporte (serialización) de los datos del [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) de la aplicación a través de los límites del proceso o del equipo.  
  
 El servicio de datos remotos utiliza **RDS. **Método [CreateObject](../../../ado/reference/rds-api/createobject-method-rds.md) del objeto DataSpace para crear servidores proxy de objeto comercial. El proxy de objeto comercial se crea dinámicamente cada vez que se crea una instancia de su equivalente de objeto comercial de nivel intermedio. El servicio de datos remotos admite los siguientes protocolos: HTTP, HTTPS (sockets seguros HTTP), DCOM y en proceso (los componentes de cliente y el objeto comercial residen en el mismo equipo).  
  
> [!NOTE]
>  RDS se comporta de manera "sin estado" cuando el **objeto RDS. **El objeto DataSpace usa los protocolos http o https. Es decir, cualquier información interna sobre una solicitud de cliente se descarta después de que el servidor devuelva una respuesta.  
  
> [!NOTE]
>  Aunque el objeto comercial parece existir durante la vigencia del proxy del objeto comercial, el objeto comercial solo existe hasta que se envía una respuesta a una solicitud. Cuando se emite una solicitud (es decir, se invoca un método en el objeto comercial), el proxy abre una nueva conexión al servidor y el servidor crea una nueva instancia del objeto comercial. Una vez que el objeto comercial responde a la solicitud, el servidor destruye el objeto comercial y cierra la conexión.  
  
> [!NOTE]
>  Este comportamiento significa que no se pueden pasar datos de una solicitud a otra mediante una propiedad o una variable de objeto comercial. Debe emplear algún otro mecanismo, como un archivo o un argumento de método, para conservar los datos de estado.  
  
 IDENTIFICADOR de clase del **objeto RDS. **El objeto DataSpace es BD96C556-65A3-11D0-983A-00C04FC29E36.  
  
 El objeto **DataSpace** es seguro para el scripting.  
  
 Esta sección contiene el siguiente tema.  
  
-   [Eventos, métodos y propiedades del objeto DataSpace (RDS)](../../../ado/reference/rds-api/dataspace-object-rds-properties-methods-and-events.md)  
  
## <a name="see-also"></a>Consulte también  
 [DataSpace y el ejemplo del método CreateObject (VBScript)](../../../ado/reference/rds-api/dataspace-object-and-createobject-method-example-vbscript.md)


