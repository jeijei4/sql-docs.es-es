---
title: Sys. sp_rda_deauthorize_db (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/10/2016
ms.prod: sql
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: language-reference
f1_keywords:
- sys.sp_rda_deauthorize_db
- sys.sp_rda_deauthorize_db_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- sys.sp_rda_deauthorize_db stored procedure
ms.assetid: 2e362e15-2cd5-4856-9f0b-54df56b0866b
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bc01f07e3a07200970066e6ed505b29b3ccb9c09
ms.sourcegitcommit: 703968b86a111111a82ef66bb7467dbf68126051
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "86053409"
---
# <a name="syssp_rda_deauthorize_db-transact-sql"></a>Sys. sp_rda_deauthorize_db (Transact-SQL)
[!INCLUDE [sqlserver2016](../../includes/applies-to-version/sqlserver2016.md)]

  Quita la conexión autenticada entre una base de datos habilitada para Stretch local y la base de datos de Azure remota. Ejecute **sp_rda_deauthorize_db** cuando no se pueda tener acceso a la base de datos remota o en un estado incoherente y desee cambiar el comportamiento de la consulta para todas las tablas habilitadas para stretch en la base de datos.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
sp_rda_deauthorize_db   
```  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o >0 (error)  
  
## <a name="permissions"></a>Permisos  
 Requiere permisos de db_owner.  
  
## <a name="remarks"></a>Observaciones  
 Después de ejecutar **sp_rda_deauthorize_db** , se producirá un error en todas las consultas de bases de datos y tablas habilitadas para Stretch. Es decir, el modo de consulta se establece en Disabled. Para salir de este modo, realice una de las siguientes acciones.  
  
-   Ejecute [Sys. sp_rda_reauthorize_db &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sys-sp-rda-reauthorize-db-transact-sql.md) para volver a conectar con la base de datos remota de Azure. Esta operación restablece automáticamente el modo de consulta en LOCAL_AND_REMOTE, que es el comportamiento predeterminado de Stretch Database. Es decir, las consultas devuelven los resultados de los datos locales y remotos.  
  
-   Ejecute [Sys. sp_rda_set_query_mode &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-set-query-mode-transact-sql.md) con el argumento LOCAL_ONLY para permitir que las consultas sigan ejecutándose solo con datos locales.  
  
## <a name="see-also"></a>Consulte también  
 [Sys. sp_rda_set_query_mode &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-set-query-mode-transact-sql.md)   
 [Sys. sp_rda_reauthorize_db &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sys-sp-rda-reauthorize-db-transact-sql.md)   
 [Stretch Database](../../sql-server/stretch-database/stretch-database.md)  
  
  
