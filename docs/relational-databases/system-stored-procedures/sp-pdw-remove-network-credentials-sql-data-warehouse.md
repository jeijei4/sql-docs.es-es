---
title: sp_pdw_remove_network_credentials
titleSuffix: Azure SQL Data Warehouse
ms.date: 03/14/2017
ms.prod_service: sql-data-warehouse, pdw
ms.reviewer: ''
ms.service: sql-data-warehouse
ms.subservice: design
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: c12696a2-5939-402b-9866-8a837ca4c0a3
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.custom: seo-dt-2019
ms.openlocfilehash: be447109a1432fdf8c3f3ae4a44f34a2eed1fd46
ms.sourcegitcommit: 01297f2487fe017760adcc6db5d1df2c1234abb4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86196788"
---
# <a name="sp_pdw_remove_network_credentials-sql-data-warehouse"></a>sp_pdw_remove_network_credentials (SQL Data Warehouse)
[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

  Se quitan las credenciales de red almacenadas en [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] para tener acceso a un recurso compartido de archivos de red. Por ejemplo, use este procedimiento almacenado para quitar el permiso de [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] para realizar operaciones de copia de seguridad y restauración en un servidor que resida dentro de su propia red.  
  
 ![Icono de vínculo a temas](../../database-engine/configure-windows/media/topic-link.gif "Icono de vínculo de tema") [Convenciones de sintaxis de Transact-SQL &#40;Transact-SQL&#41;](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-- Syntax for Azure SQL Data Warehouse and Parallel Data Warehouse  
  
sp_pdw_remove_network_credentials 'target_server_name'  
```  
  
## <a name="arguments"></a>Argumentos  
 '*target_server_name*'  
 Especifica el nombre de host o la dirección IP del servidor de destino. Las credenciales para tener acceso a este servidor se quitarán de [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] . Esto no cambia ni quita ningún permiso en el servidor de destino real administrado por su propio equipo.  
  
 *target_server_name* se define como nvarchar (337).  
  
## <a name="return-code-values"></a>Valores de código de retorno  
 0 (correcto) o 1 (error)  
  
## <a name="permissions"></a>Permisos  
 Requiere el permiso **ALTER Server State** .  
  
## <a name="error-handling"></a>Tratamiento de errores  
 Se produce un error si la eliminación de credenciales no se realiza correctamente en el nodo de control y en todos los nodos de proceso.  
  
## <a name="general-remarks"></a>Notas generales  
 Este procedimiento almacenado quita las credenciales de red de la cuenta NetworkService para [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] . La cuenta NetworkService ejecuta cada instancia de SMP [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el nodo de control y los nodos de proceso. Por ejemplo, cuando se ejecuta una operación de copia de seguridad, el nodo de control y cada nodo de proceso utilizarán las credenciales de la cuenta NetworkService para tener acceso al servidor de destino.  
  
## <a name="metadata"></a>Metadatos  
 Para obtener una lista de todas las credenciales y comprobar las credenciales que se han quitado, use [Sys. dm_pdw_network_credentials &#40;&#41;de Transact-SQL ](../../relational-databases/system-dynamic-management-views/sys-dm-pdw-network-credentials-transact-sql.md).  
  
 Para agregar credenciales, use [sp_pdw_add_network_credentials &#40;SQL Data Warehouse&#41;](../../relational-databases/system-stored-procedures/sp-pdw-add-network-credentials-sql-data-warehouse.md).  
  
## <a name="examples-sssdwfull-and-sspdw"></a>Ejemplos: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] y [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
  
### <a name="a-remove-credentials-for-performing-a-database-backup"></a>A. Quitar credenciales para realizar una copia de seguridad de base de datos  
 En el ejemplo siguiente se quitan las credenciales de nombre de usuario y contraseña para obtener acceso al servidor de destino que tiene una dirección IP de 10.192.147.63.  
  
```  
EXEC sp_pdw_remove_network_credentials '10.192.147.63';  
```  
  
  

