---
title: Seleccionar un paquete | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql13.dts.designer.selectapackage.f1
helpviewer_keywords:
- Select a Package dialog box
ms.assetid: 92b47a2b-21b5-460a-885d-6cc4bb567249
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1045623c5eabe80a66a9320cb8425b47788d950d
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86921152"
---
# <a name="select-a-package"></a>Seleccionar un paquete

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


  Utilice el cuadro de diálogo **Seleccionar un paquete** para especificar el paquete desde el que la tarea Cola de mensajes puede recibir mensajes.  
  
## <a name="static-options"></a>Opciones estáticas  
 **Ubicación**  
 Especifique la ubicación del paquete. Esta propiedad presenta las opciones indicadas en la siguiente tabla.  
  
|Value|Descripción|  
|-----------|-----------------|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|Establezca la ubicación de una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. La selección de este valor muestra las opciones dinámicas, **Servidor**, **Utilizar autenticación de Windows**, **Utilizar autenticación de SQL Server**, **Nombre de usuario**y **Contraseña**.|  
|Archivo DTSX|Establezca la ubicación de un archivo DTSX. La selección de este valor muestra la opción dinámica **Nombre de archivo**.|  
  
## <a name="location-dynamic-options"></a>Opciones dinámicas de ubicación  
  
### <a name="location--sql-server"></a>Ubicación = SQL Server  
 **Nombre del paquete**  
 Seleccione un paquete que esté almacenado en el servidor especificado.  
  
 **Server**  
 Proporcione un nombre de servidor o seleccione un servidor de la lista.  
  
 **Utilizar autenticación de Windows**  
 Haga clic en esta opción para utilizar la autenticación de Windows.  
  
 **Utilizar autenticación de SQL Server**  
 Haga clic en esta opción para usar la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Nombre de usuario**  
 Si está usando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , proporcione un nombre de usuario para usarlo cuando inicie sesión en el servidor.  
  
 **Contraseña**  
 Si está usando la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , proporcione una contraseña.  
  
### <a name="location--dtsx-file"></a>Ubicación = archivo DTSX  
 **Nombre de archivo**  
 Proporcione la ruta de acceso a un paquete, o bien haga clic en el botón Examinar **(…)** y busque el paquete.  
  
## <a name="see-also"></a>Consulte también  
 [Tarea Cola de mensajes](../../integration-services/control-flow/message-queue-task.md)  
  
  
