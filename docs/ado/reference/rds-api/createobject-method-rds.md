---
title: CreateObject (método) (RDS) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
helpviewer_keywords:
- CreateObject method [ADO]
ms.assetid: dec96be6-0b31-4953-9c9a-e962b5afcd18
author: rothja
ms.author: jroth
ms.openlocfilehash: 2b8cf7f5629158ccd1bdd74e30b7ba9bc5bb6942
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82762676"
---
# <a name="createobject-method-rds"></a>CreateObject (método) (RDS)
Crea el proxy para el objeto comercial de destino y devuelve un puntero a él. El proxy empaqueta y calcula las referencias de los datos en el código auxiliar del lado del servidor para las comunicaciones con el objeto comercial para enviar solicitudes y datos a través de Internet. En el caso de los objetos de componente en proceso, no se utiliza ningún proxy, solo se proporciona un puntero al objeto.  
  
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
## <a name="syntax"></a>Sintaxis  
 El servicio de datos remotos admite los siguientes protocolos: HTTP, HTTPS (HTTP sobre capa de sockets seguros), DCOM y en proceso.  
  
|Protocolo|Sintaxis|  
|--------------|------------|  
|HTTP|Set Object = DataSpace. CreateObject ("ProgId", "https \: //awebsrvr")|  
|HTTPS|Set Object = DataSpace. CreateObject ("ProgId", "https \: //awebsrvr")|  
|DCOM|Set Object = DataSpace. CreateObject ("ProgId", "COMPUTERNAME")|  
|En proceso|Set Object = DataSpace. CreateObject ("ProgId", "")|  
  
## <a name="parameters"></a>Parámetros  
 *Objeto*  
 Variable de objeto que se evalúa como un objeto que es el tipo especificado en *ProgID*.  
  
 *DataSpace*  
 Variable de objeto que representa un objeto [RDS. Objeto DataSpace](../../../ado/reference/rds-api/dataspace-object-rds.md) que se usa para crear una instancia del nuevo objeto.  
  
 *Programa*  
 Valor de **cadena** que contiene el identificador de programación que especifica un objeto comercial de servidor que implementa las reglas de negocios de la aplicación.  
  
 *awebsrvr* o *ComputerName*  
 Valor de **cadena** que representa una dirección URL que identifica el servidor web Internet Information Services (IIS) en el que se crea una instancia del objeto comercial del servidor.  
  
## <a name="remarks"></a>Observaciones  
 El *protocolo http* es el protocolo Web estándar. *Https* es un protocolo Web seguro. Utilice el *Protocolo DCOM* cuando ejecute una red de área local sin http. El protocolo *en proceso* es una biblioteca de vínculos dinámicos (dll) local. no usa una red.  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto DataSpace (RDS)](../../../ado/reference/rds-api/dataspace-object-rds.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo del método CreateObject, el método de consulta y el objeto DataFactory (VBScript)](../../../ado/reference/rds-api/datafactory-object-query-method-and-createobject-method-example-vbscript.md)   
 [Ejemplo del objeto DataSpace y del método CreateObject (VBScript)](../../../ado/reference/rds-api/dataspace-object-and-createobject-method-example-vbscript.md)   
 [Ejemplo del método CreateRecordset (RDS)](../../../ado/reference/rds-api/createrecordset-method-rds.md)


