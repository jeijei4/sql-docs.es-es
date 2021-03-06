---
title: Usar SQLConfigDatasource con el controlador ODBC para Oracle | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- SQLConfigDataSource function [ODBC], ODBC driver for Oracle
ms.assetid: e535d1ef-aff9-4ae7-a3ed-ef4ca2584289
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 718e444d63e0d4cf3821c0c03eb851732ed5b4e4
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "81292775"
---
# <a name="using-sqlconfigdatasource-with-the-odbc-driver-for-oracle"></a>Utilizando SQLConfigDatasource con el controlador ODBC para Oracle
> [!IMPORTANT]  
>  Esta característica se quitará en una versión futura de Windows. Evite utilizar esta característica en nuevos trabajos de desarrollo y tenga previsto modificar las aplicaciones que actualmente la utilizan. En su lugar, utilice el controlador ODBC proporcionado por Oracle.  
  
 En la tabla siguiente se enumeran los valores válidos de **SQLConfigDatasource** para Microsoft ODBC driver for Oracle, versión 1,0 (Msorcl10. dll) y Microsoft ODBC driver for Oracle, versión 2,0 (Msorcl32. dll).  
  
> [!NOTE]  
>  El controlador Msorcl10. dll (versión 1,0) admite todas las configuraciones, excepto **Server**. El controlador Msorcl32. dll (versión 2,0 y posteriores) admite todos los valores de configuración.  
  
 El controlador omite algunas opciones de configuración, pero **SQLConfigDatasource**las acepta. Incluir estos valores en la cadena de conexión ODBC es la única manera en que se aceptarán en tiempo de ejecución. Una configuración omitida no se almacenará en el registro cuando **SQLConfigDatasource** crea el origen de datos.  
  
 En la tabla siguiente, *A/N* significa cualquier cadena alfanumérica válida hasta la longitud máxima permitida. *Max Len* (longitud máxima) es la longitud de cadena máxima permitida que acepta la configuración, incluido el carácter de terminador de cadena.  
  
|Configuración|Longitud máxima|Valor predeterminado|Valores válidos|Descripción|  
|-------------|-------------|-------------------|------------------|-----------------|  
|BufferSize|7|65535|1000|Tamaño mínimo del búfer de captura de hasta 65535 bytes|  
|CatalogCap|2|1|0 o 1|Si es 1, los identificadores no comillas se convertirán a mayúsculas en las funciones de catálogo.|  
|Property|128|""|A/N|Cadena de conexión Método necesario para especificar el nombre del servidor con el controlador Msorcl10. dll.|  
|Descripción|256|""|A/N|Descripción.|  
|DSN|33|""|A/N|Nombre del origen de datos.|  
|GuessTheColDef|4|0|A/N|Devuelve un valor distinto de cero para las columnas sin escala definida por Oracle.|  
|NumberFloat|2|""|0 o 1|Si es 0, las columnas FLOAT se tratan como SQL_FLOAT. Si es 1, las columnas FLOAT se tratan como SQL_DOUBLE.|  
|PWD|30|""|A/N|Password.|  
|RDOSupport|2|""|0 o 1|Permite a RDO llamar a los procedimientos de Oracle.|  
|Observaciones|2|0|0 o 1|Incluya comentarios en las funciones de catálogo.|  
|RowLimit|4|""|de 0 a 99|Número máximo de filas devueltas por una instrucción SELECT. Una cadena de longitud cero indica que no se aplica ningún límite.|  
|Server (servidor)|128|""|A/N|Nombre del servidor de Oracle.|  
|SynonymColumns|2|1|0 o 1|Incluya sinónimos en SQLColumns.|  
|SystemTable|2|""|0 o 1|Si es 0, no se mostrarán las tablas del sistema. Si es 1, se mostrarán las tablas del sistema.|  
|TranslationDLL|33|""|A/N|Nombre de Translation. dll.|  
|TranslationName|33|""|A/N|Nombre de la traducción.|  
|TranslationOption|33|""|A/N|Opción de traducción.|  
|TxnCap|2|""|A/N|Con capacidad de transacción. Si es 0, el controlador informa de que no admite transacciones. Si es 1, el controlador informa de que es capaz de realizar transacciones.|  
|UID|30|""|A/N|Nombre de usuario.|
