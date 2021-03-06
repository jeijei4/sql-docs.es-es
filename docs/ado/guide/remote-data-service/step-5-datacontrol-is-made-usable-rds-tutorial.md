---
title: 'Paso 5: DataControl se puede usar (tutorial de RDS) | Microsoft Docs'
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 11/09/2018
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- RDS tutorial [ADO], datacontrol made usable
ms.assetid: ed5c4a24-9804-4c85-817e-317652acb9b4
author: rothja
ms.author: jroth
ms.openlocfilehash: 71576df284f3345d1f72b4043e904ae39ab031d4
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764656"
---
# <a name="step-5-datacontrol-is-made-usable-rds-tutorial"></a>Paso 5: Habilitación del uso del control de datos (Tutorial de RDS)
El objeto de **conjunto de registros** devuelto está disponible para su uso. Puede examinarlo, desplazarse o editarlo como lo haría con cualquier otro **conjunto de registros**. Lo que puede hacer con el **conjunto de registros** depende de su entorno. Visual Basic y Visual C++ tienen controles visuales que pueden usar un **conjunto de registros** directa o indirectamente con la ayuda de un control de datos habilitado.  
  
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 Por ejemplo, si va a mostrar una página web en Microsoft Internet Explorer, es posible que desee mostrar los datos del objeto de **conjunto de registros** en un control visual. Los controles visuales de una página web no pueden tener acceso directamente a un objeto de **conjunto de registros** . Sin embargo, pueden tener acceso al objeto de **conjunto de registros** a través de [RDS. DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md). **Objeto RDS. DataControl** se puede usar con un control visual cuando su propiedad [SourceRecordset](../../../ado/reference/rds-api/recordset-sourcerecordset-properties-rds.md) está establecida en el objeto de **conjunto de registros** .  
  
 El objeto de control visual debe tener su parámetro **DATASRC** establecido en **RDS. DataControl**y su propiedad **DATAFLD** establecida en un campo de objeto de **conjunto de registros** (columna).  
  
 En este tutorial, establezca la propiedad **SourceRecordset** :  
  
```vb
Sub RDSTutorial5()  
   Dim DS as New RDS.DataSpace  
   Dim RS as ADODB.Recordset  
   Dim DC as New RDS.DataControl  
   Dim DF as Object  
   Set DF = DS.CreateObject("RDSServer.DataFactory", "https://yourServer")  
   Set RS = DF.Query ("DSN=Pubs", "SELECT * FROM Authors")  
   DC.SourceRecordset = RS         ' Visual controls can now bind to DC.  
...  
```  
  
## <a name="see-also"></a>Consulte también  
 [Paso 6: los cambios se envían al servidor (tutorial de RDS)](../../../ado/guide/remote-data-service/step-6-changes-are-sent-to-the-server-rds-tutorial.md)   
 [Tutorial de RDS (VBScript)](../../../ado/guide/remote-data-service/rds-tutorial-vbscript.md)   
