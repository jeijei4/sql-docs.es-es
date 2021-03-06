---
title: 'Paso 4: el servidor devuelve el conjunto de registros (tutorial de RDS) | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS tutorial [ADO], server returns Recordset
ms.assetid: 3d1855c4-419c-4810-b5ea-6c874b5e2905
author: rothja
ms.author: jroth
ms.openlocfilehash: ce53c987a43ed208a4d7120fb3655b3a3acd5083
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764666"
---
# <a name="step-4-server-returns-the-recordset-rds-tutorial"></a>Paso 4: Devolución del conjunto de registros por parte del servidor (Tutorial de RDS)
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 RDS convierte el objeto de **conjunto de registros** recuperado en un formulario que se puede devolver al cliente (es decir, *calcula las referencias* del **conjunto de registros**). La forma exacta de la conversión y cómo se envía depende de si el servidor está en Internet o en una intranet, una red de área local o es una biblioteca de vínculos dinámicos. Sin embargo, este detalle no es crítico; lo único que importa es que RDS devuelve el **conjunto de registros** al cliente.  
  
 En el lado cliente, se devuelve un objeto de **conjunto de registros** y se asigna a una variable local.  
  
```vb
Sub RDSTutorial4()  
   Dim DS as New RDS.DataSpace  
   Dim RS as ADODB.Recordset  
   Dim DF as Object  
   Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer")  
   Set RS = DF.Query("DSN=Pubs", "SELECT * FROM Authors")  
...  
```  
  
## <a name="see-also"></a>Consulte también  
 [Paso 5: DataControl se puede usar (tutorial de RDS)](../../../ado/guide/remote-data-service/step-5-datacontrol-is-made-usable-rds-tutorial.md)   
 [Tutorial de RDS (VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
