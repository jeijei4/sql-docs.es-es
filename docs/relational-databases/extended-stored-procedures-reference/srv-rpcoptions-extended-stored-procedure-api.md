---
title: srv_rpcoptions (API de procedimiento almacenado extendido) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
apiname:
- srv_rpcoptions
apilocation:
- opends60.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcoptions
ms.assetid: dbcce5d1-d5a1-4379-9597-04e43af5923d
author: rothja
ms.author: jroth
ms.openlocfilehash: 4a4bc6bf4a8fe1b600ec7bd7b3ba1877023751db
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85755887"
---
# <a name="srv_rpcoptions-extended-stored-procedure-api"></a>srv_rpcoptions (API de procedimiento almacenado extendido)
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] Use la integración con CLR en su lugar.  
  
 Devuelve las opciones de tiempo de ejecución para el procedimiento almacenado remoto actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
DBUSMALLINT srv_rpcoptions ( SRV_PROC *  
srvproc   
);  
```  
  
## <a name="arguments"></a>Argumentos  
 *srvproc*  
 Es un puntero a la estructura SRV_PROC, que es el identificador de una conexión de cliente determinada (en este caso, el identificador que recibió el procedimiento almacenado remoto). La estructura contiene información que la biblioteca de API de procedimiento almacenado extendido usa para administrar la comunicación y los datos entre la aplicación y el cliente.  
  
## <a name="returns"></a>Devoluciones  
 Un mapa de bits que contiene las marcas en tiempo de ejecución combinadas en un OR lógico para el procedimiento almacenado remoto actual. Si no hay un procedimiento almacenado remoto actual, se devuelve 0 y se genera un mensaje.  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se describen las marcas de tiempo de ejecución.  
  
|Marca de tiempo de ejecución|Descripción|  
|--------------------|-----------------|  
|SRV_NOMETADATA|El cliente ha solicitado resultados sin información de metadatos. Esta marca solo se utiliza cuando el cliente se está comunicando con una instancia de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Una aplicación API de procedimiento almacenado extendido no puede omitir información de metadatos.|  
|SRV_RECOMPILE|El cliente ha solicitado volver a compilar el procedimiento almacenado remoto antes de ejecutarlo. Esta marca no se puede aplicar a una aplicación API de procedimiento almacenado extendido.|  
  
> [!IMPORTANT]  
>  Debe revisar minuciosamente el código fuente de los procedimientos almacenados extendidos y debe probar las DLL compiladas antes de instalarlas en el servidor de producción. Para obtener información acerca de la revisión y pruebas de seguridad, vea este [sitio web de Microsoft](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).  
  
  
