---
title: sp_changesubscription (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 10/28/2015
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: language-reference
f1_keywords:
- changesubscription
- sp_changesubscription
- changesubscription_TSQL
- sp_changesubscription_TSQL
helpviewer_keywords:
- sp_changesubscription
ms.assetid: f9d91fe3-47cf-4915-b6bf-14c9c3d8a029
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b33103bc84e6354e99ac04e73fa20a0f99725a6a
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85771385"
---
# <a name="sp_changesubscription-transact-sql"></a>sp_changesubscription (Transact-SQL)
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]

  Cambia las propiedades de una suscripción de inserción transaccional o de instantáneas o de una suscripción de extracción relacionada con la replicación transaccional de actualización en cola. Para cambiar las propiedades de todos los demás tipos de suscripciones de extracción, utilice [sp_change_subscription_properties &#40;&#41;de Transact-SQL ](../../relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql.md). **sp_changesubscription** se ejecuta en el publicador de la base de datos de publicación.  
  
> [!IMPORTANT]  
>  Al configurar un publicador con un distribuidor remoto, los valores suministrados para todos los parámetros, incluidos *job_login* y *job_password*, se envían al distribuidor como texto sin formato. Antes de ejecutar este procedimiento almacenado, se recomienda cifrar la conexión entre el publicador y su distribuidor remoto. Para obtener más información, vea [Habilitar conexiones cifradas en el motor de base de datos &#40;Administrador de configuración de SQL Server&#41;](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md).  
  
 ![Icono de vínculo de tema](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
sp_changesubscription [ @publication = ] 'publication'  
        , [ @article = ] 'article'  
        , [ @subscriber = ] 'subscriber'  
        , [ @destination_db = ] 'destination_db'  
        , [ @property = ] 'property'  
        , [ @value = ] 'value'  
    [ , [ @publisher = ] 'publisher' ]  
```  
  
## <a name="arguments"></a>Argumentos  
`[ @publication = ] 'publication'`Es el nombre de la publicación que se va a cambiar. *Publication*es de **tipo sysname**y no tiene ningún valor predeterminado  
  
`[ @article = ] 'article'`Es el nombre del artículo que se va a cambiar. *article* es de **tipo sysname**y no tiene ningún valor predeterminado.  
  
`[ @subscriber = ] 'subscriber'`Es el nombre del suscriptor. *Subscriber* es de **tipo sysname**y no tiene ningún valor predeterminado.  
  
`[ @destination_db = ] 'destination_db'`Es el nombre de la base de datos de suscripciones. *destination_db* es de **tipo sysname**y no tiene ningún valor predeterminado.  
  
`[ @property = ] 'property'`Es la propiedad que se va a cambiar para la suscripción especificada. *Property* es de tipo **nvarchar (30)** y puede ser uno de los valores de la tabla.  
  
`[ @value = ] 'value'`Es el nuevo valor de la *propiedad*especificada. el *valor* es **nvarchar (4000)** y puede ser uno de los valores de la tabla.  
  
|Propiedad|Valor|Descripción|  
|--------------|-----------|-----------------|  
|**distrib_job_login**||Inicio de sesión de la cuenta de [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows en la que se ejecuta el agente.|  
|**distrib_job_password**||Contraseña de la cuenta de Windows con la que se ejecuta el agente.|  
|**subscriber_catalog**||Catálogo que debe utilizarse al establecer una conexión con el proveedor OLE DB. Esta propiedad solo es válida para suscriptores que no sean de [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .|  
|**subscriber_datasource**||Nombre del origen de datos tal y como lo entiende el proveedor OLE DB. *Esta propiedad solo es válida para* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *Suscriptores.*|  
|**subscriber_location**||Ubicación de la base de datos tal y como la interpreta el proveedor OLE DB. *Esta propiedad solo es válida para* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *Suscriptores.*|  
|**subscriber_login**||Nombre de inicio de sesión del suscriptor.|  
|**subscriber_password**||Contraseña segura para el inicio de sesión que se ha proporcionado.|  
|**subscriber_security_mode**|**1**|Se utiliza la autenticación de Windows para la conexión con el suscriptor.|  
||**0**|Se utiliza la autenticación de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para la conexión con el suscriptor.|  
|**subscriber_provider**||Identificador de programación único (PROGID) mediante el cual se registra el proveedor OLE DB para los orígenes de datos que no son de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. *Esta propiedad solo es válida para* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *Suscriptores.*|  
|**subscriber_providerstring**||Cadena de conexión específica del proveedor OLE DB que identifica el origen de datos. *Esta propiedad solo es válida para* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] *Suscriptores.*|  
|**subscriptionstreams**||Es el número de conexiones permitidas por Agente de distribución para aplicar lotes de cambios en paralelo a un suscriptor. Los publicadores admiten un intervalo de valores de **1** a **64** [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Esta propiedad debe ser **0** para suscriptores que no sean de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , publicadores de Oracle o suscripciones punto a punto.|  
|**subscriber_type**|**1**|Servidor del origen de datos ODBC|  
||**3**|Proveedor OLE DB|  
|**memory_optimized**|**bit**|Indica que la suscripción admite tablas con optimización para memoria. *memory_optimized* es de **bits**, donde 1 es igual a true (la suscripción admite las tablas optimizadas en memoria).|  
  
`[ @publisher = ] 'publisher'`Especifica un publicador que no es de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . *Publisher* es de **tipo sysname y su**valor predeterminado es NULL.  
  
> [!NOTE]  
>  no se debe especificar el *publicador* para un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] publicador.  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 **0** (correcto) o **1** (error)  
  
## <a name="remarks"></a>Comentarios  
 **sp_changesubscription** se utiliza en la replicación de instantáneas y transaccional.  
  
 **sp_changesubscription** solo se puede usar para modificar las propiedades de las suscripciones de inserción o las suscripciones de extracción implicadas en la replicación transaccional de actualización en cola. Para cambiar las propiedades de todos los demás tipos de suscripciones de extracción, utilice [sp_change_subscription_properties &#40;&#41;de Transact-SQL ](../../relational-databases/system-stored-procedures/sp-change-subscription-properties-transact-sql.md).  
  
 Después de cambiar un inicio de sesión o una contraseña de agente, debe detener y reiniciar el agente para que el cambio surta efecto.  
  
## <a name="permissions"></a>Permisos  
 Solo los miembros del rol fijo de servidor **sysadmin** o del rol fijo de base de datos **db_owner** pueden ejecutar **sp_changesubscription**.  
  
## <a name="see-also"></a>Consulte también  
 [sp_addsubscription &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-addsubscription-transact-sql.md)   
 [sp_dropsubscription &#40;&#41;de Transact-SQL](../../relational-databases/system-stored-procedures/sp-dropsubscription-transact-sql.md)  
  
  
