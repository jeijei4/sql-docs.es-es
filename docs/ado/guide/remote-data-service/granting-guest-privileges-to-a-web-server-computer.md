---
title: Conceder privilegios de invitado a un equipo servidor Web | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- guest privileges in RDS [ADO]
ms.assetid: e851a22d-01bc-4eb0-bc42-92b8f65d1c63
author: rothja
ms.author: jroth
ms.openlocfilehash: a9a2145fdf106814647b4d9cca067c28db72f848
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82749589"
---
# <a name="granting-guest-privileges-to-a-web-server-computer"></a>Concesión de privilegios de invitado a un equipo del servidor web
La cuenta del servidor Web anónimo (IUSR_*ComputerName*) debe agregarse al grupo local invitados del equipo servidor web para usar RDS.  
  
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
### <a name="to-grant-guest-privileges-to-a-web-server-computer"></a>Para conceder privilegios de invitado a un equipo servidor Web  
  
1.  En el equipo de Microsoft Windows 2000 Server, haga clic en **Inicio**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administración de equipos**.  
  
2.  En el árbol de consola, en **usuarios y grupos locales**, haga clic en **grupos**.  
  
3.  Seleccione el grupo local **invitados** . En el menú **acción** , elija **propiedades**.  
  
4.  En el cuadro de diálogo **propiedades de invitados** , haga clic en **Agregar**.  
  
5.  Si la cuenta del servidor Web anónimo no aparece en la lista del cuadro de diálogo **Seleccionar usuarios o grupos** , escriba su nombre (IUSR_*ComputerName*) en el cuadro en blanco inferior y, a continuación, haga clic en **Agregar**.  
  
6.  Haga clic en **OK**.


