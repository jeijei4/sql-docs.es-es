---
title: Sys. database_filestream_options (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- database_filestream_options
- sys.database_filestream_options_TSQL
- database_filestream_options_TSQL
- sys.database_filestream_options
dev_langs:
- TSQL
helpviewer_keywords:
- sys.database_filestream_options catalog view
ms.assetid: 3383c607-0bbc-456a-ab37-7230f4cbf0e9
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 2cb185c2cec6bd2a7104384b3b75e14e2de4167f
ms.sourcegitcommit: f7ac1976d4bfa224332edd9ef2f4377a4d55a2c9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85887932"
---
# <a name="sysdatabase_filestream_options-transact-sql"></a>sys.database_filestream_options (Transact-SQL)
[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Muestra información sobre el nivel de acceso no transaccional a los datos de FILESTREAM en los objetos FileTable habilitados. Contiene una fila por cada base de datos de la instancia de SQL Server.  
  
 Para más información sobre FileTables, vea [FileTables &#40;SQL Server&#41;](../../relational-databases/blob/filetables-sql-server.md).  
  
  
|Columna|Tipo|Descripción|  
|------------|----------|-----------------|  
|**database_id**|**int**|El Id. de la base de datos. Este valor es único dentro de la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].|  
|**directory_name**|**nvarchar(255)**|El directorio de base de datos para todos los espacios de nombres FileTable.|  
|**non_transacted_access**|**tinyint**|El nivel de acceso no transaccional a los datos de FILESTREAM habilitados. El nivel de acceso se establece mediante la opción NON_TRANSACTED_ACCESS de la instrucción **Create Database** o **ALTER DATABASE** .<br /><br /> Esta configuración tiene uno de los siguientes valores:<br /><br /> 0: no habilitado. Este es el valor predeterminado. Este nivel se establece al proporcionar **el valor para** la opción **NON_TRANSACTED_ACCESS** .<br /><br /> 1: acceso de solo lectura. Este nivel se establece proporcionando el valor **READ_ONLY** para la opción **NON_TRANSACTED_ACCESS** .<br /><br /> 3-acceso completo. Este nivel se establece proporcionando el valor **completo** de la opción **NON_TRANSACTED_ACCESS** .<br /><br /> 5: en transición a READONLY<br /><br /> 6-en transición a desactivado|  
|**non_transacted_access_desc**|**nvarchar(60)**|La descripción del nivel de acceso no transaccional identificado en non_transacted_access.<br /><br /> Esta configuración tiene uno de los siguientes valores:<br /><br /> NINGUNO: este es el valor predeterminado.<br /><br /> READ_ONLY<br /><br /> FULL<br /><br /> IN_TRANSITION_TO_READ_ONLY<br /><br /> IN_TRANSITION_TO_OFF|  
  
## <a name="see-also"></a>Consulte también  
 [Habilitar los requisitos previos de FileTables](../../relational-databases/blob/enable-the-prerequisites-for-filetable.md)  
  
  
