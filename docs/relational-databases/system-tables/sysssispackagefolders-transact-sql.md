---
title: sysssispackagefolders (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sysdtspackagefolders90
- sysdtspackagefolders90_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sysssispackagefolders system table
ms.assetid: ddc4833f-27bf-4610-b739-d257961d17ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c525b1b457c2bc9f505a83cc89a08a57c27e6279
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85881280"
---
# <a name="sysssispackagefolders-transact-sql"></a>sysssispackagefolders (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Contiene una fila por cada carpeta lógica de la jerarquía de carpetas que [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] utiliza. Estas carpetas se enumeran en el Explorador de objetos de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] al conectar con [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]. Una carpeta enumera paquetes que se guardan en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o en el sistema de archivos.  
  
 La columna **parentfolderid** describe la jerarquía de carpetas. La carpeta situada en la parte superior de la jerarquía de carpetas contiene un valor null en **parentfolderid**.  
  
 La columna **nombrecarpeta** contiene el nombre de las carpetas que aparecen en explorador de objetos.  
  
 Esta tabla se almacena en la base de datos **msdb** .  

  
|Nombre de la columna|Tipo de datos|Descripción|  
|-----------------|---------------|-----------------|  
|**folderId**|**uniqueidentifier**|Identificador único global (GUID) de la carpeta.|  
|**parentfolderid**|**uniqueidentifier**|GUID de la carpeta primaria.|  
|**nombreDeCarpeta**|**sysname**|Nombre de la carpeta. Este nombre aparece en la jerarquía de carpetas de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].|  
  
  
