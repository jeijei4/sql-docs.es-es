---
title: sp_droppublication (Transact-SQL) | Microsoft Docs
description: Quita una publicación y su Agente de instantáneas asociado. Este procedimiento almacenado se ejecuta en el publicador de la base de datos de publicación.
ms.custom: ''
ms.date: 03/17/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- sp_droppublication_TSQL
- sp_droppublication
helpviewer_keywords:
- sp_droppublication
ms.assetid: b52b37e6-4fec-40cf-abba-7dce4ff395fd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 980b40421b51594ef0d687521ba9e436c2a16c4c
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85783827"
---
# <a name="sp_droppublication-transact-sql"></a>sp_droppublication (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Quita una publicación y su Agente de instantáneas asociado. Antes de quitar una publicación, es necesario quitar todas las suscripciones. Los artículos de la publicación se quitan automáticamente. Este procedimiento almacenado se ejecuta en el publicador de la base de datos de publicación.  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_droppublication [ @publication= ] 'publication'   
    [ , [ @ignore_distributor = ] ignore_distributor ]  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @publication = ] 'publication'`Es el nombre de la publicación que se va a quitar. *Publication* es de **tipo sysname**y no tiene ningún valor predeterminado. Si se especifica **All** , se quitan todas las publicaciones de la base de datos de publicación, excepto aquellas con suscripciones.  
  
`[ @ignore_distributor = ] ignore_distributor` [!INCLUDE[ssInternalOnly](../../includes/ssinternalonly-md.md)]  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="remarks"></a>Comentarios  
 **sp_droppublication** se utiliza en la replicación de instantáneas y en la replicación transaccional.  
  
 **sp_droppublication** quita recursivamente todos los artículos asociados a una publicación y, a continuación, quita la propia publicación. No se puede quitar una publicación si tiene una o más suscripciones. Para obtener información acerca de cómo quitar suscripciones, consulte [eliminar una suscripción de inserción](../../relational-databases/replication/delete-a-push-subscription.md) y [eliminar una suscripción de extracción](../../relational-databases/replication/delete-a-pull-subscription.md).  
  
 La ejecución de **sp_droppublication** para quitar una publicación no quita los objetos publicados de la base de datos de publicación ni los objetos correspondientes de la base de datos de suscripciones. Utilice DROP \<object> para quitar estos objetos manualmente si es necesario.  
  
## <a name="permissions"></a>Permisos  
 Solo los miembros del rol fijo de servidor **sysadmin** pueden ejecutar **sp_droppublication**.  
  
## <a name="examples"></a>Ejemplos  
 [!code-sql[HowTo#sp_droppublication](../../relational-databases/replication/codesnippet/tsql/sp-droppublication-trans_1.sql)]  
  
## <a name="see-also"></a>Consulte también  
 [Eliminar una publicación](../../relational-databases/replication/publish/delete-a-publication.md)   
 [sp_addpublication &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-addpublication-transact-sql.md)   
 [sp_changepublication &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-changepublication-transact-sql.md)   
 [sp_helppublication &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-helppublication-transact-sql.md)   
 [Procedimientos almacenados de replicación &#40;Transact-SQL&#41;](../../relational-databases/system-stored-procedures/replication-stored-procedures-transact-sql.md)  
  
  
