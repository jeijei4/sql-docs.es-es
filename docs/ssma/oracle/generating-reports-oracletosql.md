---
title: Generación de informes (OracleToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Report Generation in Oracle Console, synchronize-target
- Report Generation in Oracle Console,refresh-from-database
- Report Generation in Oracle Console,write-summary-report-to
ms.assetid: ccad6262-01e1-447a-bd2b-c105154c80ce
author: Shamikg
ms.author: Shamikg
manager: shamikg
ms.openlocfilehash: 971d7e8dde2ae56da02205b50b2f6576a875bd70
ms.sourcegitcommit: 6fd8c1914de4c7ac24900fe388ecc7883c740077
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68264458"
---
# <a name="generating-reports-oracletosql"></a>Generación de informes (OracleToSQL)
Los informes de ciertas actividades realizadas con comandos se generan en la consola de SSMA en el nivel de árbol de objetos.  
  
Use el procedimiento siguiente para generar informes:  
  
1.  Especifique el parámetro **Write-Summary-Report-to** . El informe relacionado se almacena como el nombre de archivo (si se especifica) o en la carpeta que especifique. El nombre de archivo está predefinido por el sistema, como se mencionó en la ** &lt;tabla&gt; ** siguiente, donde n es el número de archivo único que se incrementa con un dígito con cada ejecución del mismo comando.  
  
    Los comandos de los informes Vis-à-vis son los siguientes:  
  
    ||||  
    |-|-|-|  
    |**SL. no.**|**Comando**|**Título del informe**|  
    |1|generar informe de evaluación|AssessmentReport&lt;n&gt;. LENGUAJE|  
    |2|Convert-Schema|SchemaConversionReport&lt;n&gt;. LENGUAJE|  
    |3|migrar datos|DataMigrationReport&lt;n&gt;. LENGUAJE|  
    |4|Convert-SQL-Statement|ConvertSQLReport&lt;n&gt;. LENGUAJE|  
    |5|sincronizar-destino|TargetSynchronizationReport&lt;n&gt;. LENGUAJE|  
    |6|actualizar desde la base de datos|SourceDBRefreshReport&lt;n&gt;. LENGUAJE|  
  
    > [!IMPORTANT]  
    > Un informe de salida es diferente del informe de evaluación. El primero es un informe sobre el rendimiento de un comando ejecutado, mientras que el segundo es un informe XML para el consumo mediante programación.  
  
    Para las opciones de comando para los informes de salida (desde SL. No. 2-4 arriba), consulte la sección [ejecución de la consola de SSMA &#40;OracleToSQL&#41;](../../ssma/oracle/executing-the-ssma-console-oracletosql.md) .  
  
2.  Indique el grado de detalle que desea en el informe de salida mediante la configuración del nivel de detalle del informe:  
  
    ||||  
    |-|-|-|  
    |**SL. no.**|**Comando y parámetro**|**Descripción de salida**|  
    |1|verbose = "false"|Genera un informe resumido de la actividad.|  
    |2|verbose = "true"|Genera un informe de estado resumido y detallado para cada actividad.|  
  
    > [!NOTE]  
    > La configuración de nivel de detalle del informe especificada anteriormente es aplicable a los comandos Generate-Assessment-Report, Convert-Schema, Migrate-Data, Convert-SQL-Statement.  
  
3.  Indique el grado de detalle que desea en los informes de errores mediante la configuración de informes de errores:  
  
    ||||  
    |-|-|-|  
    |**SL. no.**|**Comando y parámetro**|**Descripción de salida**|  
    |1|Informe-errores = "false"|No hay detalles de mensajes de error, ADVERTENCIA o información.|  
    |2|Informe-errores = "true"|Mensajes de error, ADVERTENCIA o información detallados.|  
  
    > [!NOTE]  
    > La configuración de informes de errores especificada anteriormente es aplicable a los comandos Generate-Assessment-Report, Convert-Schema, Migrate-Data, Convert-SQL-Statement.  
  
**Ejemplo:**  
  
```  
<generate-assessment-report  
  
   object-name="<object-name>"  
  
   object-type="<object-type>"  
  
   verbose="<true/false>"  
  
   report-erors="<true/false>"  
  
   write-summary-report-to="<file-name/folder-name>"  
  
   assessment-report-folder="<folder-name>"  
  
   assessment-report-overwrite="<true/false>"/>  
```  
  
### <a name="synchronize-target"></a>sincronizar-destino:  
El comando **Synchronize-Target** tiene el parámetro **Report-Errors-to** , que especifica la ubicación del informe de errores para la operación de sincronización. A continuación, un archivo por **el&lt;nombre&gt;TargetSynchronizationReport n. XML** se crea en la ubicación especificada, donde ** &lt;n&gt; ** es el número de archivo único que se incrementa con un dígito con cada ejecución del mismo comando.  
  
**Nota:** Si se especifica la ruta de acceso de la carpeta, el parámetro "Report-Errors-to" se convierte en un atributo opcional para el comando "Synchronize-target".  
  
```  
<!-- Example: Synchronize target entire Database with all attributes-->  
  
<synchronize-target  
  
   object-name="<object-name>"  
  
   on-error="report-total-as-warning/report-each-as-warning/fail-script"  
  
   report-errors-to="<file-name/folder-name>"/>  
```  
**nombre del objeto:** Especifica los objetos que se tienen en cuenta para la sincronización (también puede tener nombres de objeto individuales o un nombre de objeto de grupo).  
  
**error:** Especifica si se deben especificar errores de sincronización como advertencias o errores. Opciones disponibles para en caso de error:  
  
-   Informe-total como ADVERTENCIA  
  
-   Informe cada ADVERTENCIA  
  
-   error: script  
  
### <a name="refresh-from-database"></a>actualizar desde la base de datos:  
El comando **Refresh-from-Database** tiene el parámetro **Report-Errors-to** , que especifica la ubicación del informe de errores para la operación de actualización. A continuación, un archivo por **el&lt;nombre&gt;SourceDBRefreshReport n. XML** se crea en la ubicación especificada, donde ** &lt;n&gt; ** es el número de archivo único que se incrementa con un dígito con cada ejecución del mismo comando.  
  
**Nota:** Si se especifica la ruta de acceso de la carpeta, el parámetro "Report-Errors-to" se convierte en un atributo opcional para el comando "Synchronize-target".  
  
```  
<!-- Example: Refresh entire Schema (with all attributes)-->  
  
<refresh-from-database  
  
   object-name="<object-name>"  
  
   object-type ="<object-type>"  
  
   on-error="report-total-as-warning/report-each-as-warning/fail-script"  
  
   report-errors-to="<file-name/folder-name>"/>  
```  
**nombre del objeto:** Especifica los objetos que se tienen en cuenta para la actualización (también puede tener nombres de objeto individuales o un nombre de objeto de grupo).  
  
**error:** Especifica si se deben especificar errores de actualización como advertencias o errores. Opciones disponibles para en caso de error:  
  
-   Informe-total como ADVERTENCIA  
  
-   Informe cada ADVERTENCIA  
  
-   error: script  
  
## <a name="see-also"></a>Consulte también  
[Ejecutar la consola SSMA (Oracle)](https://msdn.microsoft.com/7228ccba-c69f-4b4c-8664-01a2750183c5)  
  
