---
title: MSSQLSERVER_9002 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 9002 (Database Engine error)
ms.assetid: 2e50841f-2b99-45f4-aec5-aa4add70cbeb
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6e888a44cd96eeaa93f49c02128e48763b66a9ee
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85636642"
---
# <a name="mssqlserver_9002"></a>MSSQLSERVER_9002
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Detalles  
  
| Atributo | Value |  
| :-------- | :---- |  
|Nombre de producto|SQL Server|  
|Id. de evento|9002|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|LOG_IS_FULL|  
|Texto del mensaje|El registro de transacciones de la base de datos '%.*ls' está lleno. Para saber por qué no se puede volver a utilizar el espacio del registro, vea la columna log_reuse_wait_desc de sys.databases.|  
  
## <a name="explanation"></a>Explicación  
El registro de la base de datos se ha quedado sin espacio. En la columna **log_reuse_wait_desc** de **sys.databases** se describe por qué no se puede volver a utilizar el espacio del registro.  
  
## <a name="user-action"></a>Acción del usuario  
Use **sys.databases** para determinar la razón por la que el registro está lleno y solucione el problema. Para obtener más información, vea "Solucionar problemas de un registro de transacciones lleno (Error 9002)" en los Libros en pantalla de SQL Server.  
  
## <a name="see-also"></a>Consulte también  
[Solucionar problemas de un registro de transacciones lleno &#40;Error 9002 de SQL Server&#41;](~/relational-databases/logs/troubleshoot-a-full-transaction-log-sql-server-error-9002.md)  
[sys.databases &#40;Transact-SQL&#41;](~/relational-databases/system-catalog-views/sys-databases-transact-sql.md)  
  
