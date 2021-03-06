---
title: Query (método) (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- Query method [ADO]
ms.assetid: 20f2480f-3758-405d-a379-05a0dce74796
author: rothja
ms.author: jroth
ms.openlocfilehash: b3025f37b47cd545e7e7cde127e96740077ab961
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82751497"
---
# <a name="query-method-rds"></a>Método Query (RDS)
Utiliza una cadena de consulta SQL válida para devolver un [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md).  
  
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Set Recordset = DataFactory.Query(Connection, Query)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *DataRecordsets*  
 Variable de objeto que representa un objeto de **conjunto de registros** .  
  
 *DataFactory*  
 Variable de objeto que representa un objeto [RDSServer. DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) .  
  
 *Connection*  
 Valor de **cadena** que contiene la información de conexión del servidor. Esto es similar a la propiedad [Connect](../../../ado/reference/rds-api/connect-property-rds.md) .  
  
 *Consultar*  
 **Cadena** que contiene la consulta SQL.  
  
## <a name="remarks"></a>Comentarios  
 La consulta debe utilizar el dialecto SQL del servidor de bases de datos. Se devuelve un estado de resultado si se produce un error con la consulta que se ha ejecutado. El método de **consulta** no realiza ninguna comprobación de sintaxis en la cadena de **consulta** .  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto DataFactory (RDSServer)](../../../ado/reference/rds-api/datafactory-object-rdsserver.md)  
  
## <a name="see-also"></a>Consulte también  
 [Objeto DataFactory, método de consulta y ejemplo del método CreateObject (VBScript)](../../../ado/reference/rds-api/datafactory-object-query-method-and-createobject-method-example-vbscript.md)


