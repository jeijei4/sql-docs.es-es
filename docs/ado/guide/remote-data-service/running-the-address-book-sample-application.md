---
title: Ejecución de la aplicación de ejemplo de libreta de direcciones | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- address book application scenario [ADO]
- RDS scenarios [ADO]
ms.assetid: 3a2644e9-d634-4ae6-a5b7-13fb7b317ec7
author: rothja
ms.author: jroth
ms.openlocfilehash: e3a2c971f952a7c3f13b058bb3937201d323746d
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82758991"
---
# <a name="running-the-address-book-sample-application"></a>Ejecución de la aplicación de ejemplo de la libreta de direcciones
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 Para ejecutar la aplicación de libreta de direcciones, siga este procedimiento.  
  
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
### <a name="to-run-this-application"></a>Para ejecutar esta aplicación  
  
1.  Asegúrese de que Microsoft SQL Server se está ejecutando. Haga clic en **Inicio**, seleccione **programas**, **Microsoft SQL Server 7,0**y, a continuación, haga clic en **Service Manager**. Si hay una flecha verde en el círculo blanco, SQL Server se está ejecutando. Si no lo es (habrá un cuadrado rojo en el círculo blanco), haga clic en **iniciar o continuar**.  
  
2.  En Microsoft Internet Explorer 4,0 o posterior, escriba la siguiente dirección:  
  
     **https://** *WebServer* **/RDS/AddressBook/AddrBook.asp**  
  
     donde *WebServer* es el nombre del servidor Web en el que están instalados los componentes de servidor RDS.  
  
3.  A continuación, puede probar varios escenarios en la aplicación de ejemplo de la libreta de direcciones, como buscar una persona según su nombre de correo electrónico, enumerar a todas las personas con el título "Administrador de programas" o editar los registros existentes. Haga clic en **Buscar** para rellenar la cuadrícula de datos con todos los nombres disponibles.  
  
## <a name="see-also"></a>Consulte también  
 [Objeto de enlace de datos de la libreta de direcciones](../../../ado/guide/remote-data-service/address-book-data-binding-object.md)




