---
title: Agregar lógica comercial a los datos XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dbe-xml
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business logic [XML]
ms.assetid: 0877fb38-f1a2-43d8-86cf-4754be224dc1
caps.latest.revision: 17
author: craigg-msft
ms.author: craigg
manager: jhubbard
ms.openlocfilehash: bf3e24dd3fe06a06b26adcbfcbf9da57d5b6916a
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36106048"
---
# <a name="add-business-logic-to-xml-data"></a>Agregar lógica comercial a los datos XML
  La lógica de negocios se puede agregar a los datos XML de varias formas:  
  
-   Se pueden escribir restricciones de filas o columnas para forzar restricciones específicas de un dominio durante la inserción y modificación de datos XML.  
  
-   Es posible escribir un desencadenador en la columna XML que se active al insertar o actualizar valores en la columna. El desencadenador puede contener reglas de validación específicas de un dominio o rellenar tablas de propiedades.  
  
-   El motor de base de datos incluye la capacidad de ejecutar código administrado. Puede usar esta integración de Common Language Runtime (CLR) para escribir funciones en código administrado a las que pasar valores XML y usar capacidades de procesamiento XML proporcionadas por el espacio de nombres System.Xml. Un ejemplo es aplicar la transformación XSL a datos XML. Otra posibilidad es deserializar el XML en una o más clases administradas y operar con ellas mediante código administrado.  
  
-   Se pueden escribir procedimientos almacenados de Transact-SQL y funciones que inicien el procesamiento en la columna XML de acuerdo con las necesidades de la empresa.  
  
## <a name="example-applying-xsl-transformation"></a>Ejemplo: Aplicar transformación XSL  
 Considere la posibilidad de una función CLR **TransformXml()** que acepta un `xml` tipo de instancia y una transformación XSL almacenada en un archivo de datos, se aplica la transformación a los datos XML y, a continuación, devuelve el XML transformado en el resultado. A continuación, se muestra una función esquemática escrita en C#:  
  
```  
public static SqlXml TransformXml (SqlXml XmlData, string xslPath) {  
   // Load XSL transformation  
   XslCompiledTransform xform = new XslCompiledTransform();  
   XPathDocument xslDoc = new XPathDocument (xslPath);  
   xform.Load(xslDoc);  
  
   // Load XML data   
   XPathDocument xDoc = new XPathDocument (XmlData.CreateReader());  
  
   // Return the transformed value  
   MemoryStream xsltResult = new MemoryStream();  
   xform.Transform(xDoc, null, xsltResult);  
   SqlXml retSqlXml = new SqlXml(xsltResult);  
   return (retSqlXml);  
}   
```  
  
 Después de registrar el ensamblado y crear una función [!INCLUDE[tsql](../../includes/tsql-md.md)] definida por el usuario, **SqlXslTransform()** correspondiente a **TransformXml()**, se puede invocar la función desde Transact-SQL como se indica en la consulta siguiente:  
  
```  
SELECT SqlXslTransform (xCol, 'C:\MyFile\xsltransform.xsl')  
FROM    T  
WHERE  xCol.exist('/book/title/text()[contains(.,"custom")]') =1;  
```  
  
 El resultado de la consulta contiene un conjunto de filas del XML transformado.  
  
 La integración de CLR en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] amplía las posibilidades de descomponer datos XML en tablas o promoción de propiedades, y de consulta de datos XML usando clases administradas en el espacio de nombres System.Xml. Para obtener más información, vea [Datos XML &#40;SQL Server&#41;](xml-data-sql-server.md).  
  
  