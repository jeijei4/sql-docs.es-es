---
title: Validar XML con la tarea XML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- XML validation
- XML, validating
ms.assetid: 224fc025-c21f-4d43-aa9d-5ffac337f9b0
caps.latest.revision: 6
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: 8ea74ad195b97541147c3d1b19dc01c5033b962c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37182833"
---
# <a name="validate-xml-with-the-xml-task"></a>Validate XML with the XML Task
  Validar documentos XML y obtenga la salida de error enriquecida habilitando la `ValidationDetails` propiedad de la tarea XML.  
  
 La siguiente captura de pantalla muestra el **Editor de la tarea XML** con la configuración necesaria para la validación de XML con la salida de error completa.  
  
 ![Propiedades de la tarea XML en el Editor de la tarea XML](../media/xmltaskproperties.jpg "XML task properties in the XML Task Editor")  
  
 Antes de la `ValidationDetails` propiedad estaba disponible, validación de XML mediante la tarea XML devuelve solo un resultado true o false, sin información sobre errores o sus ubicaciones. Ahora, al establecer `ValidationDetails` en true, la salida de archivo contiene información detallada sobre cada error, incluido el número de línea y la posición. Puede usar esta información para comprender, buscar y corregir errores en documentos XML.  
  
 La funcionalidad de validación de XML se escala fácilmente en el caso de documentos XML grandes y un gran número de errores. Puesto que el propio archivo de salida está en formato XML, puede consultar y analizar la salida. Por ejemplo, si la salida contiene un gran número de errores, puede agruparlos mediante una consulta [!INCLUDE[tsql](../../../includes/tsql-md.md)] , como se describe en este tema.  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] ([!INCLUDE[ssIS](../../includes/ssis-md.md)]) introdujo la `ValidationDetails` propiedad [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Service Pack 2. También está disponible en la propiedad [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] y en SQL Server 2016.  
  
## <a name="sample-output-for-xml-thats-valid"></a>Ejemplo de salida de un archivo XML que no es válido  
 Este es un ejemplo de archivo de salida con los resultados de validación de un archivo XML válido.  
  
```xml  
  
<root xmlns:ns="http://schemas.microsoft.com/xmltools/2002/xmlvalidation">  
    <metadata>  
        <result>true</result>  
        <errors>0</errors>  
        <warnings>0</warnings>  
        <startTime>2015-05-28T10:27:22.087</startTime>  
        <endTime>2015-05-28T10:29:07.007</endTime>  
        <xmlFile>d:\Temp\TestData.xml</xmlFile>  
        <xsdFile>d:\Temp\TestSchema.xsd</xsdFile>  
    </metadata>  
    <messages />  
</root>  
```  
  
## <a name="sample-output-for-xml-thats-not-valid"></a>Ejemplo de salida de un archivo XML que no es válido  
 Este es un ejemplo de archivo de salida con los resultados de validación de un archivo XML que contiene un pequeño número de errores. El texto de los elementos \<error> se ha justificado para mejorar la legibilidad.  
  
```xml  
  
<root xmlns:ns="http://schemas.microsoft.com/xmltools/2002/xmlvalidation">  
    <metadata>  
        <result>false</result>  
        <errors>2</errors>  
        <warnings>0</warnings>  
        <startTime>2015-05-28T10:45:09.538</startTime>  
        <endTime>2015-05-28T10:45:09.558</endTime>  
        <xmlFile>C:\Temp\TestData.xml</xmlFile>  
        <xsdFile>C:\Temp\TestSchema.xsd</xsdFile>  
    </metadata>  
    <messages>  
        <error line="5" position="26">The 'ApplicantRole' element is invalid - The value 'wer3' is invalid  
    according to its datatype 'ApplicantRoleType' - The Enumeration constraint failed.</error>  
        <error line="16" position="28">The 'Phone' element is invalid - The value 'we3056666666' is invalid  
     according to its datatype 'phone' - The Pattern constraint failed.</error>  
    </messages>  
</root>  
```  
  
## <a name="analyze-xml-validation-output-with-a-transact-sql-query"></a>Analizar la salida de validación XML con una consulta de Transact-SQL  
 Si la salida de validación XML contiene un gran número de errores, puede usar una consulta de [!INCLUDE[tsql](../../../includes/tsql-md.md)] para cargar la salida en [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]. Luego, puede analizar la lista de errores con todas las funcionalidades del lenguaje T-SQL, como WHERE, GROUP BY, ORDER BY, JOIN, etc.  
  
```tsql  
DECLARE @xml XML;  
  
SELECT @xml = XmlDoc     
FROM OPENROWSET (BULK N'C:\Temp\XMLValidation_2016-02-212T10-41-00.xml', SINGLE_BLOB) AS Tab(XmlDoc);  
  
-- Query # 1, flat list of errors  
-- convert to relational/rectangular  
;WITH XMLNAMESPACES ('http://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS  
(  
SELECT col.value('@line','INT') AS line  
     , col.value('@position','INT') AS position  
     , col.value('.','VARCHAR(1024)') AS error  
FROM @XML.nodes('/root/messages/error') AS tab(col)  
)  
SELECT * FROM rs;  
-- WHERE error LIKE ‘%whatever_string%’  
  
-- Query # 2, count of errors grouped by the error message  
-- convert to relational/rectangular  
;WITH XMLNAMESPACES ('http://schemas.microsoft.com/xmltools/2002/xmlvalidation' AS ns), rs AS  
(  
SELECT col.value('@line','INT') AS line  
     , col.value('@position','INT') AS position  
     , col.value('.','VARCHAR(1024)') AS error  
FROM @XML.nodes('/root/messages/error') AS tab(col)  
)  
SELECT COALESCE(error,'Total # of errors:') AS [error], COUNT(*) AS [counter]  
FROM rs  
GROUP BY GROUPING SETS ((error), ())  
ORDER BY 2 DESC, COALESCE(error, 'Z');  
  
```  
  
 Este es el resultado de [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] de la segunda consulta de ejemplo que se muestra en el texto anterior.  
  
 ![Consulta para agrupar errores de XML en Management Studio](../media/queryforxmlerrors.jpg "Query to group XML errors in Management Studio")  
  
## <a name="see-also"></a>Vea también  
 [Tarea XML](xml-task.md)   
 [Editor de la tarea XML &#40;página General&#41;](../xml-task-editor-general-page.md)  
  
  