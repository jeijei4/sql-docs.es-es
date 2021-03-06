---
title: Quitar un procedimiento almacenado extendido
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- deleting extended stored procedures
- removing extended stored procedures
- extended stored procedures [SQL Server], removing
- dropping extended stored procedures
ms.assetid: 7827e574-3f59-4279-9a9b-532582e041cb
author: rothja
ms.author: jroth
ms.custom: seo-dt-2019
ms.openlocfilehash: 4ec666e49ccc6da12e14f7f1c85ce6eda4b6a4d0
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85723406"
---
# <a name="removing-an-extended-stored-procedure-from-sql-server"></a>Quitar un procedimiento almacenado extendido de SQL Server
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] En su lugar, utilice la integración con CLR.  
  
 Para quitar cada función de procedimiento almacenado extendido en un archivo DLL de procedimiento almacenado extendido definido por el usuario, un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Administrador del sistema debe ejecutar el **sp_dropextendedproc** procedimiento almacenado del sistema, especificando el nombre de la función y el nombre del archivo dll en el que reside dicha función. Por ejemplo, este comando quita la función **xp_hello**, ubicada en un archivo DLL denominado xp_hello.dll, de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] :  
  
```  
sp_dropextendedproc 'xp_hello'  
```  
  
 A partir de [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] , **sp_dropextendedproc** no quita los procedimientos almacenados extendidos del sistema. En su lugar, el administrador del sistema debe denegar el permiso EXECUTe para el procedimiento almacenado extendido al rol **Public** .  
  
## <a name="see-also"></a>Consulte también  
 [sp_dropextendedproc &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql.md)  
  
  
