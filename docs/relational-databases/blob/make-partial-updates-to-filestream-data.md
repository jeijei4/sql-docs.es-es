---
title: Realización de actualizaciones parciales de los datos FILESTREAM | Microsoft Docs
description: Descubra cómo usar el valor FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT para realizar actualizaciones parciales de los datos de FILESTREAM BLOB. Vea un ejemplo de una actualización parcial.
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
- FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT
ms.assetid: d6f7661e-6c14-4d31-9541-4520ca0f82b2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 133cbfadceaf782e72fe5a3b604e37e9d56f61f7
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85767945"
---
# <a name="make-partial-updates-to-filestream-data"></a>Realizar actualizaciones parciales de los datos FILESTREAM
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Una aplicación utiliza FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT para realizar actualizaciones parciales de los datos de FILESTREAM BLOB. La función [DeviceIoControl](https://go.microsoft.com/fwlink/?LinkId=105527) pasa este valor y el controlador que [OpenSqlFilestream](../../relational-databases/blob/access-filestream-data-with-opensqlfilestream.md) devuelve al controlador FILESTREAM. A continuación, el controlador obliga a hacer una copia del lado servidor de los datos FILESTREAM actuales en el archivo al que el controlador hace referencia. Si la aplicación emite el valor FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT una vez escrito el controlador, la última operación de escritura se conserva y se pierden las operaciones de escritura anteriores que se realizaron en el controlador.  
  
> [!NOTE]  
>  FILESTREAM se basa en el protocolo [SMB protocol](https://go.microsoft.com/fwlink/?LinkId=112454) para el acceso remoto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el valor `FSCTL_SQL_FILESTREAM_FETCH_OLD_CONTENT` para realizar una actualización parcial de un FILESTREAM BLOB insertado.  
  
> [!NOTE]  
>  Este ejemplo requiere la tabla y la base de datos habilitadas para FILESTREAM que se crean en [Crear una base de datos habilitada para FILESTREAM](../../relational-databases/blob/create-a-filestream-enabled-database.md) y [Crear una tabla para almacenar datos FILESTREAM](../../relational-databases/blob/create-a-table-for-storing-filestream-data.md).  
  
 [!code-cpp[FILESTREAM#FS_CPP_FSCTL](../../relational-databases/blob/codesnippet/cpp/make-partial-updates-to-_1.cpp)]  
  
## <a name="see-also"></a>Consulte también  
 [Obtener acceso a los datos FILESTREAM con OpenSqlFilestream](../../relational-databases/blob/access-filestream-data-with-opensqlfilestream.md)   
 [Crear aplicaciones cliente para datos FILESTREAM](../../relational-databases/blob/create-client-applications-for-filestream-data.md)  
  
  
