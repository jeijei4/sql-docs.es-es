---
title: MSSQLSERVER_33027 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 33027 (Database Engine error)
ms.assetid: bfdc626e-7958-4511-987d-3b687824e8af
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1c11ade3e23f2d520e17cdb2f981ec725633d273
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85723605"
---
# <a name="mssqlserver_33027"></a>MSSQLSERVER_33027
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Detalles  
  
| Atributo | Value |  
| :-------- | :---- |  
|Nombre de producto|SQL Server|  
|Id. de evento|33027|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|SEC_CRYPTOPROV_CANTLOADDLL|  
|Texto del mensaje|No se pudo cargar el proveedor de servicios criptográficos '%.*ls' debido a una firma Authenticode o una ruta de archivo no válida. Revise los mensajes de otros errores anteriores.|  
  
## <a name="explanation"></a>Explicación  
SQL Server no ha podido utilizar el proveedor de servicios criptográficos enumerado en el mensaje de error porque SQL Server no ha podido cargar la DLL. O el nombre no es válido o la firma Authenticode no es válida.  
  
## <a name="user-action"></a>Acción del usuario  
Compruebe que el archivo está presente y SQL Server tiene permiso de acceso a esa ubicación. Compruebe el registro de errores para ver posibles mensajes relacionados adicionales. De lo contrario, póngase en contacto con el proveedor de servicios criptográficos para obtener más información.  
  
