---
title: Configuración de DataFactory para los modos SAFE o Unrestricted | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- DataFactory configuration in RDS [ADO]
ms.assetid: 8ff24805-dc7a-42ae-b600-5bad0e3f51b8
author: rothja
ms.author: jroth
ms.openlocfilehash: cff72ed7c02cb4f0e9dc2a719ee7e82b55e44408
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82750081"
---
# <a name="configuring-datafactory-for-safe-or-unrestricted-modes"></a>Configuración de DataFactory para los modos seguro o sin restricciones
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 De forma predeterminada, ADO se instala con una configuración "segura" de [RDSServer. DataFactory](../../../ado/reference/rds-api/datafactory-object-rdsserver.md) . El modo seguro para componentes de servidor RDS significa que se cumplen las siguientes condiciones:  
  
1.  El controlador es necesario con RDSServer. DataFactory (esto es obligatorio mediante una configuración de clave del registro).  
  
2.  El controlador predeterminado, MSDFMAP. handler, está registrado, presente en la lista de controladores seguros y marcado como controlador predeterminado.  
  
3.  El archivo MSDFMAP. ini se instala en el directorio de Windows. Debe configurar este archivo en función de sus necesidades, antes de utilizar RDS en el modo de tres niveles.  
  
 Opcionalmente, puede configurar una instalación de **DataFactory** sin restricciones. **DataFactory** se puede usar directamente sin el controlador personalizado. Los usuarios pueden seguir usando un controlador personalizado modificando las cadenas de conexión, pero no es necesario. Para obtener más información sobre las implicaciones del uso del objeto **RDSServer. DataFactory** , vea [proteger aplicaciones RDS](../../../ado/guide/remote-data-service/securing-rds-applications.md).  
  
 Se ha proporcionado el archivo de registro Handsafe. reg para configurar las entradas del registro del controlador para una configuración segura. Para ejecutar en modo seguro, ejecute Handsafe. reg.  
  
 Después de ejecutar Handsafe. reg, debe detener y reiniciar el servicio de publicación de World Wide Web en el servidor web; para ello, escriba los siguientes comandos en una ventana del símbolo del sistema: "NET STOP W3SVC" y "NET START W3SVC".  
  
## <a name="see-also"></a>Consulte también  
 [Personalización de DataFactory](../../../ado/guide/remote-data-service/datafactory-customization.md)   
 [Aspectos básicos de RDS](../../../ado/guide/remote-data-service/rds-fundamentals.md)



