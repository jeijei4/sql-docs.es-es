---
title: Ejemplo de la propiedad ReadyState (VBScript) | Microsoft Docs
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.prod: sql
ms.prod_service: connectivity
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- ReadyState property [ADO], VBScript example
ms.assetid: e3e18da4-0511-4ece-a35d-699978bc28c6
author: rothja
ms.author: jroth
ms.openlocfilehash: 7a3d39355a95b46170ab3f7a5b24cd43582ecac3
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82755512"
---
# <a name="readystate-property-example-vbscript"></a>Ejemplo de la propiedad ReadyState (VBScript)
> [!IMPORTANT]
>  A partir de Windows 8 y Windows Server 2012, los componentes de servidor RDS ya no se incluyen en el sistema operativo Windows (consulte la guía de compatibilidad de Windows 8 y [Windows server 2012](https://www.microsoft.com/download/details.aspx?id=27416) para obtener más detalles). Los componentes de cliente RDS se quitarán en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. Las aplicaciones que utilizan RDS deben migrar al [servicio de datos de WCF](https://go.microsoft.com/fwlink/?LinkId=199565).  
  
 En el ejemplo siguiente se muestra cómo leer la propiedad [ReadyState](../../../ado/reference/rds-api/readystate-property-rds.md) de [RDS. Objeto DataControl](../../../ado/reference/rds-api/datacontrol-object-rds.md) en tiempo de ejecución en el código de VBScript. **ReadyState** es una propiedad de solo lectura.  
  
 Para probar este ejemplo, corte y pegue este código entre las \< etiquetas Body> y \< /Body> de un documento HTML normal y asígnele el nombre **RDSReadySt. asp**. Use **Buscar** para buscar el archivo adovbs. Inc y colóquelo en el directorio que piensa usar. El script ASP identificará el servidor.  
  
```  
<!-- BeginReadyStateVBS -->  
<%@ Language=VBScript %>  
<!--#include file="adovbs.inc"-->  
<html>  
<head>  
    <meta name="VI60_DefaultClientScript"  content=VBScript>  
    <meta name="GENERATOR" content="Microsoft Visual Studio 6.0">  
    <title>RDS.DataControl ReadyState Property</title>  
<style>  
<!--  
body {  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;  
   BACKGROUND-COLOR:white;  
   COLOR:black;  
    }  
.thead {  
   background-color: #008080;   
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
   color: white;  
   }  
.thead2 {  
   background-color: #800000;   
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
   color: white;  
   }  
.tbody {   
   text-align: center;  
   background-color: #f7efde;  
   font-family: 'Verdana','Arial','Helvetica',sans-serif;   
   font-size: x-small;  
    }  
-->  
</style>  
</head>  
  
<body>  
<H1>RDS.DataControl ReadyState Property</H1>  
<H2>RDS API Code Examples </H2>  
<HR>  
<!-- RDS.DataControl with parameters set at design time -->  
<OBJECT classid="clsid:BD96C556-65A3-11D0-983A-00C04FC29E33" ID=RDS>  
   <PARAM NAME="SQL" VALUE="Select * from Orders">  
   <PARAM NAME="SERVER" VALUE="https://<%=Request.ServerVariables("SERVER_NAME")%>">  
   <PARAM NAME="CONNECT" VALUE="Provider=SQLOLEDB;Integrated Security=SSPI;Initial Catalog=Northwind">  
   <PARAM NAME="ExecuteOptions" VALUE="2">   
   <PARAM NAME="FetchOptions" VALUE="3">  
</OBJECT>  
  
<TABLE DATASRC=#RDS>  
<TBODY>  
  <TR>  
    <TD><SPAN DATAFLD="OrderID"></SPAN></TD>  
  </TR>  
</TBODY>  
</TABLE>  
  
<Script Language="VBScript">  
  
   Sub Window_OnLoad  
  
      Select Case RDS.ReadyState  
         case 2   'adcReadyStateLoaded  
          MsgBox "Executing Query"  
         case 3   'adcReadyStateInteractive  
          MsgBox "Fetching records in background"  
         case 4   'adcReadyStateComplete  
          MsgBox "All records fetched"  
      End Select  
  
   End Sub  
</Script>  
  
</body>  
</html>  
<!-- EndReadyStateVBS -->  
```  
  
## <a name="see-also"></a>Consulte también  
 [Objeto DataControl (RDS)](../../../ado/reference/rds-api/datacontrol-object-rds.md)   
 [Propiedad ReadyState (RDS)](../../../ado/reference/rds-api/readystate-property-rds.md)


