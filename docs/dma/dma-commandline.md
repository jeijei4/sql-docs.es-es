---
title: Ejecutar Data Migration Assistant desde la línea de comandos
description: Obtenga información acerca de cómo ejecutar Data Migration Assistant desde la línea de comandos para evaluar las bases de datos de SQL Server para la migración.
ms.custom: seo-lt-2019
ms.date: 05/06/2019
ms.prod: sql
ms.prod_service: dma
ms.reviewer: ''
ms.technology: dma
ms.topic: conceptual
keywords: ''
helpviewer_keywords:
- Data Migration Assistant, Command Line
ms.assetid: ''
author: rajeshsetlem
ms.author: rajpo
ms.openlocfilehash: 62626e8a9f3cfe5bf9272378b26e3bb0ab2f6b1a
ms.sourcegitcommit: 5a9ec5e28543f106bf9e7aa30dd0a726bb750e25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82925359"
---
# <a name="run-data-migration-assistant-from-the-command-line"></a>Ejecutar Data Migration Assistant desde la línea de comandos

Con la versión 2,1 y posteriores, al instalar Data Migration Assistant, también se instalará dmacmd. exe en *% ProgramFiles% \\ Microsoft Data Migration Assistant \\ *. Use dmacmd. exe para evaluar las bases de datos en modo desatendido y generar el resultado en un archivo JSON o CSV. Este método es especialmente útil al evaluar varias bases de datos o bases de datos de gran tamaño. 

> [!NOTE]
> Dmacmd. exe solo admite la ejecución de evaluaciones. En este momento no se admiten las migraciones.

## <a name="assessments-using-the-command-line-interface-cli"></a>Evaluaciones mediante la interfaz de la línea de comandos (CLI)

```
DmaCmd.exe /AssessmentName="string"
/AssessmentDatabases="connectionString1" \["connectionString2"\]
\[/AssessmentSourcePlatform="SourcePlatform"]
\[/AssessmentTargetPlatform="TargetPlatform"\]
/AssessmentEvaluateRecommendations|/AssessmentEvaluateCompatibilityIssues
\[/AssessmentOverwriteResult\]
/AssessmentResultJson="file"|/AssessmentResultCsv="file"
```

|Argumento  |Descripción  | Requerido (s/N)
|---------|---------|---------------|
| `/help or /?`     | Cómo usar el texto de ayuda de dmacmd. exe        | No
|`/AssessmentName`     |   Nombre del proyecto de evaluación   | S
|`/AssessmentDatabases`     | Lista delimitada por espacios de cadenas de conexión. El nombre de la base de datos (catálogo inicial) distingue mayúsculas de minúsculas. | S
|`/AssessmentSourcePlatform`     | Plataforma de origen para la evaluación: <br>Valores admitidos para la evaluación: SqlOnPrem, RdsSqlServer (valor predeterminado) <br>Valores admitidos para la evaluación de preparación de destino: SqlOnPrem, RdsSqlServer (valor predeterminado), Cassandra (versión preliminar)   | No
|`/AssessmentTargetPlatform`     | Plataforma de destino para la evaluación:  <br> Valores admitidos para la evaluación: AzureSqlDatabase, ManagedSqlServer, SqlServer2012, SqlServer2014, SqlServer2016, SqlServerLinux2017 y SqlServerWindows2017 (valor predeterminado)  <br> Valores admitidos para la evaluación de preparación de destino: ManagedSqlServer (valor predeterminado), CosmosDB (versión preliminar)   | No
|`/AssessmentEvaluateFeatureParity`  | Ejecutar reglas de paridad de características. Si la plataforma de origen es RdsSqlServer, la evaluación de la paridad de características no se admite para la plataforma de destino AzureSqlDatabase  | No
|`/AssessmentEvaluateCompatibilityIssues`     | Ejecutar reglas de compatibilidad  | S <br> (Se requiere AssessmentEvaluateCompatibilityIssues o AssessmentEvaluateRecommendations).
|`/AssessmentEvaluateRecommendations`     | Ejecutar recomendaciones de características        | S <br> (Se requiere AssessmentEvaluateCompatibilityIssues o AssessmentEvaluateRecommendations)
|`/AssessmentOverwriteResult`     | Sobrescribir el archivo de resultados    | No
|`/AssessmentResultJson`     | Ruta de acceso completa al archivo de resultados JSON     | S <br> (Se requiere AssessmentResultJson o AssessmentResultCsv)
|`/AssessmentResultCsv`    | Ruta de acceso completa al archivo de resultados CSV   | S <br> (Se requiere AssessmentResultJson o AssessmentResultCsv)
|`/AssessmentResultDma`    | Ruta de acceso completa al archivo de resultados de DMA   | No
|`/Action`    | Use SkuRecommendation para obtener recomendaciones de SKU. <br> Use AssessTargetReadiness para realizar la evaluación de preparación de destino. <br> Use AzureMigrateUpload para cargar todos los archivos de evaluación de DMA en el AzzessmentResultInputFolder para la carga masiva en Azure Migrate. uso del tipo de acción/Action = AzureMigrateUpload   | No
|`/SourceConnections`    | Lista delimitada por espacios de cadenas de conexión. El nombre de la base de datos (catálogo inicial) es opcional. Si no se proporciona ningún nombre de base de datos, se evalúan todas las bases de datos del origen.   | S <br> (Obligatorio si la acción es ' AssessTargetReadiness ')
|`/TargetReadinessConfiguration`    | Ruta de acceso completa al archivo XML que describe los valores para el nombre, las conexiones de origen y el archivo de resultados.   | S <br> (Se requiere TargetReadinessConfiguration o SourceConnections)
|`/FeatureDiscoveryReportJson`    | Ruta de acceso al informe JSON de detección de características. Si se genera este archivo, se puede usar para volver a ejecutar la evaluación de preparación de destino sin conectarse al origen. | No
|`/ImportFeatureDiscoveryReportJson`    | Ruta de acceso al informe JSON de detección de características creado anteriormente. En lugar de las conexiones de origen, se usará este archivo.   | No
|`/EnableAssessmentUploadToAzureMigrate`    | Permite cargar y publicar los resultados de la evaluación en Azure Migrate   | No
|`/AzureCloudEnvironment`    |Selecciona el entorno de nube de Azure al que conectarse, el valor predeterminado es nube pública de Azure. Valores admitidos: Azure (valor predeterminado), AzureChina, AzureGermany, AzureUSGovernment.   | No 
|`/SubscriptionId`    |Identificador de suscripción de Azure.   | S <br> (Obligatorio si se especifica el argumento EnableAssessmentUploadToAzureMigrate)
|`/AzureMigrateProjectName`    |Azure Migrate nombre del proyecto al que se van a cargar los resultados de la evaluación.   | S <br> (Obligatorio si se especifica el argumento EnableAssessmentUploadToAzureMigrate)
|`/ResourceGroupName`    |Azure Migrate nombre del grupo de recursos.   | S <br> (Obligatorio si se especifica el argumento EnableAssessmentUploadToAzureMigrate)
|`/AssessmentResultInputFolder`    |La ruta de acceso de la carpeta de entrada que contiene. Archivos de evaluación de DMA que se van a cargar en Azure Migrate.   | S <br> (Obligatorio si la acción es AzureMigrateUpload)



## <a name="examples-of-assessments-using-the-cli"></a>Ejemplos de evaluaciones mediante la CLI

**Dmacmd. exe**

  `Dmacmd.exe /? or DmaCmd.exe /help`

**Evaluación de una sola base de datos mediante la autenticación de Windows y reglas de compatibilidad en ejecución**

```
DmaCmd.exe /AssessmentName="TestAssessment"
/AssessmentDatabases="Server=SQLServerInstanceName;Initial
Catalog=DatabaseName;Integrated Security=true"
/AssessmentEvaluateCompatibilityIssues /AssessmentOverwriteResult
/AssessmentResultJson="C:\\temp\\Results\\AssessmentReport.json"
```

**Evaluación de una sola base de datos mediante la autenticación de SQL Server y la recomendación de características en ejecución**

```
DmaCmd.exe /AssessmentName="TestAssessment"
/AssessmentDatabases="Server=SQLServerInstanceName;Initial
Catalog=DatabaseName;User Id=myUsername;Password=myPassword;"
/AssessmentEvaluateRecommendations /AssessmentOverwriteResult
/AssessmentResultCsv="C:\\temp\\Results\\AssessmentReport.csv"
```

**Evaluación de una sola base de datos para la plataforma de destino SQL Server 2012, guardar los resultados en un archivo. JSON y. csv**

```
DmaCmd.exe /AssessmentName="TestAssessment"
/AssessmentDatabases="Server=SQLServerInstanceName;Initial
Catalog=DatabaseName;Integrated Security=true"
/AssessmentTargetPlatform="SqlServer2012"
/AssessmentEvaluateRecommendations /AssessmentOverwriteResult
/AssessmentResultJson="C:\\temp\\Results\\AssessmentReport.json"
/AssessmentResultCsv="C:\\temp\\Results\\AssessmentReport.csv"
```

**Evaluación de base de datos única para la plataforma de destino SQL Azure base de datos, guardar los resultados en un archivo. JSON y. csv**

```
DmaCmd.exe /AssessmentName="TestAssessment" 
/AssessmentDatabases="Server=SQLServerInstanceName;Initial
Catalog=DatabaseName;Integrated Security=true"
/AssessmentTargetPlatform="AzureSqlDatabaseV12"
/AssessmentEvaluateCompatibilityIssues /AssessmentEvaluateFeatureParity
/AssessmentOverwriteResult 
/AssessmentResultCsv="C:\\temp\\AssessmentReport.csv" 
/AssessmentResultJson="C:\\temp\\AssessmentReport.json"
```

**Evaluación de varias bases de datos**

```
DmaCmd.exe /AssessmentName="TestAssessment"
/AssessmentDatabases="Server=SQLServerInstanceName1;Initial
Catalog=DatabaseName1;Integrated Security=true"
"Server=SQLServerInstanceName1;Initial Catalog=DatabaseName2;Integrated
Security=true" "Server=SQLServerInstanceName2;Initial
Catalog=DatabaseName3;Integrated Security=true"
/AssessmentTargetPlatform="SqlServer2016"
/AssessmentEvaluateCompatibilityIssues /AssessmentOverwriteResult
/AssessmentResultCsv="C:\\temp\\Results\\AssessmentReport.csv"
/AssessmentResultJson="C:\\Results\\test2016.json"
```

**Evaluación de preparación de destino de una sola base de datos mediante la autenticación de Windows**

```
DmaCmd.exe /Action=AssessTargetReadiness 
/AssessmentName="TestAssessment" 
/SourceConnections="Server=SQLServerInstanceName;Initial Catalog=DatabaseName;Integrated Security=true" 
/AssessmentOverwriteResult 
/AssessmentResultJson="C:\temp\Results\AssessmentReport.json"
```

**Evaluación de preparación de destino de una sola base de datos mediante la autenticación de SQL Server**

```
DmaCmd.exe /Action=AssessTargetReadiness 
/AssessmentName="TestAssessment" 
/SourceConnections="Server=SQLServerInstanceName;Initial Catalog=DatabaseName;User Id=myUsername;Password=myPassword;" /AssessmentEvaluateRecommendations 
/AssessmentOverwriteResult 
/AssessmentResultJson="C:\temp\Results\AssessmentReport.json" 

```

**Evaluación de base de datos única para la plataforma de destino SQL Azure base de datos, guardar los resultados en un archivo. JSON y. csv**

```
DmaCmd.exe /AssessmentName="TestAssessment" 
/AssessmentDatabases="Server=SQLServerInstanceName;Initial
Catalog=DatabaseName;Integrated Security=true"
/AssessmentSourcePlatform="SqlOnPrem"
/AssessmentTargetPlatform="AzureSqlDatabase"
/AssessmentEvaluateCompatibilityIssues /AssessmentEvaluateFeatureParity
/AssessmentOverwriteResult 
/AssessmentResultCsv="C:\\temp\\AssessmentReport.csv" 
/AssessmentResultJson="C:\\temp\\AssessmentReport.json"

```

**Evaluación de preparación de destino de varias bases de datos**

```
DmaCmd.exe /Action=AssessTargetReadiness
/AssessmentName="TestAssessment"
/AssessmentSourcePlatform=SourcePlatform
/AssessmentTargetPlatform=TargetPlatform
/SourceConnections="Server=SQLServerInstanceName1;Initial Catalog=DatabaseName1;Integrated Security=true" "Server=SQLServerInstanceName1;Initial Catalog=DatabaseName2;Integrated Security=true" "Server=SQLServerInstanceName2;Initial Catalog=DatabaseName3;Integrated Security=true"
/AssessmentOverwriteResult  
/AssessmentResultJson="C:\Results\test2016.json"

(/AssessmentSourcePlatform and /AssessmentTargetPlatform are optional.)
```

**Evaluación de la preparación para todas las bases de datos de un servidor mediante la autenticación de Windows**

```
DmaCmd.exe /Action=AssessTargetReadiness
/AssessmentName="TestAssessment"
/SourceConnections="Server=SQLServerInstanceName;Integrated Security=true"
/AssessmentOverwriteResult
/AssessmentResultJson="C:\temp\Results\AssessmentReport.json"

```

**Evaluación de la preparación de destino mediante la importación del informe de detección de características creado anteriormente**

```
DmaCmd.exe /Action=AssessTargetReadiness
/AssessmentName="TestAssessment"
/ImportFeatureDiscoveryReportJson="c:\temp\feature_report.json" 
/AssessmentOverwriteResult
/AssessmentResultJson="C:\temp\Results\AssessmentReport.json"

```

**Evaluación de la preparación de destino mediante el archivo de configuración**

```
DmaCmd.exe /Action=AssessTargetReadiness 
/TargetReadinessConfiguration=.\Config.xml
```

Contenido del archivo de configuración cuando se usan conexiones de origen:

```
<?xml version="1.0" encoding="utf-8" ?>
<TargetReadinessConfiguration xmlns="http://microsoft.com/schemas/SqlServer/Advisor/TargetReadinessConfiguration">
  <AssessmentName>name</AssessmentName>
  <SourcePlatform>Source Platform</SourcePlatform> <!-- Optional. The default is SqlOnPrem -->
  <TargetPlatform>TargetPlatform</TargetPlatform> <!-- Optional. The default is ManagedSqlServer -->
  <SourceConnections>
    <SourceConnection>connection string 1</SourceConnection>
    <SourceConnection>connection string 2</SourceConnection>
    <!-- ... -->
    <SourceConnection>connection string n</SourceConnection>
  </SourceConnections>
  <AssessmentResultJson>path\to\file.json</AssessmentResultJson>
  <FeatureDiscoveryReportJson>path\to\featurediscoveryreport.json</FeatureDiscoveryReportJson>
  <OverwriteResult>true</OverwriteResult> <!-- or false -->
</TargetReadinessConfiguration>
```

Contenido del archivo de configuración al importar el informe de detección de características:

```
<TargetReadinessConfiguration xmlns="https://microsoft.com/schemas/SqlServer/Advisor/TargetReadinessConfiguration">
  <AssessmentName>name</AssessmentName>
  <ImportFeatureDiscoveryReportJson>path\to\featurediscoveryfile.json</ImportFeatureDiscoveryReportJson>
  <AssessmentResultJson>path\to\resultfile.json</AssessmentResultJson>
  <OverwriteResult>true</OverwriteResult><!-- or false -->
</TargetReadinessConfiguration>
```
**Evaluación y carga en Azure Migrate en la nube pública de Azure (valor predeterminado)**
```
DmaCmd.exe
/Action="Assess" 
/AssessmentSourcePlatform=SqlOnPrem 
/AssessmentTargetPlatform=ManagedSqlServer
/AssessmentEvaluateCompatibilityIssues 
/AssessmentEvaluateRecommendations 
/AssessmentEvaluateFeatureParity 
/AssessmentOverwriteResult 
/AssessmentName="assess-myDatabase"
/AssessmentDatabases="Server=myServer;Initial Catalog=myDatabase;Integrated Security=true" 
/AssessmentResultDma="C:\assessments\results\assess-1.dma"
/SubscriptionId="Subscription Id" 
/AzureMigrateProjectName="Azure Migrate project ame" 
/ResourceGroupName="Resource Group name" 
/AzureAuthenticationInteractiveAuthentication
/AzureAuthenticationTenantId="Azure Tenant Id"
/EnableAssessmentUploadToAzureMigrate

```
**Carga por lotes de archivos de evaluación de DMA en Azure Migrate en la nube pública de Azure (valor predeterminado)**
```
DmaCmd.exe 
/Action="AzureMigrateUpload" 
/AssessmentResultInputFolder="C:\assessments\results" 
/SubscriptionId="subscription Id" 
/AzureMigrateProjectName="Azure Migrate project name" 
/ResourceGroupName="Resource Group name" 
/AzureAuthenticationInteractiveAuthentication
/AzureAuthenticationTenantId="Azure Tenant Id"
/EnableAssessmentUploadToAzureMigrate

```
## <a name="azure-sql-databasemanaged-instance-sku-recommendations-using-the-cli"></a>Recomendaciones de SKU de instancia administrada y Azure SQL Database mediante la CLI

Estos comandos admiten recomendaciones para Azure SQL Database opciones de implementación de base de datos única y de instancia administrada.

```
.\DmaCmd.exe /Action=SkuRecommendation
/SkuRecommendationInputDataFilePath="C:\TestOut\out.csv"
/SkuRecommendationTsvOutputResultsFilePath="C:\TestOut\prices.tsv"
/SkuRecommendationJsonOutputResultsFilePath="C:\TestOut\prices.json"
/SkuRecommendationOutputResultsFilePath="C:\TestOut\prices.html"
/SkuRecommendationPreventPriceRefresh=true 
```

|Argumento  |Descripción  | Requerido (s/N)
|---------|---------|---------------|
|`/Action=SkuRecommendation` | Ejecutar evaluación de SKU mediante la línea de comandos DMA | S
|`/SkuRecommendationInputDataFilePath` | Ruta de acceso completa al archivo de contador de rendimiento recopilado del equipo que hospeda las bases de datos | S
|`/SkuRecommendationTsvOutputResultsFilePath` | Ruta de acceso completa al archivo de resultados TSV | S <br> (Requiere TSV o JSON o la ruta de acceso del archivo HTML)
|`/SkuRecommendationJsonOutputResultsFilePath` | Ruta de acceso completa al archivo de resultados JSON | S <br> (Requiere TSV o JSON o la ruta de acceso del archivo HTML)
|`/SkuRecommendationHtmlResultsFilePath` | Ruta de acceso completa al archivo de resultados HTML | S <br> (Requiere TSV o JSON o la ruta de acceso del archivo HTML)
|`/SkuRecommendationPreventPriceRefresh` | Impide que se produzca la actualización del precio. Use si se ejecuta en modo sin conexión (por ejemplo, true). | S <br> (Seleccione este argumento para precios estáticos o se deben seleccionar todos los argumentos siguientes para obtener los precios más recientes).
|`/SkuRecommendationCurrencyCode` | Moneda en la que se van a mostrar los precios (por ejemplo, "USD") | S <br> (Para los precios más recientes)
|`/SkuRecommendationOfferName` | El nombre de la oferta (por ejemplo, "MS-AZR-0003P"). Para obtener más información, consulte la página Detalles de la [oferta de Microsoft Azure](https://azure.microsoft.com/support/legal/offer-details/) . | S <br> (Para los precios más recientes)
|`/SkuRecommendationRegionName` | El nombre de la región (por ejemplo, "Westus") | S <br> (Para los precios más recientes)
|`/SkuRecommendationSubscriptionId` | Identificador de la suscripción. | S <br> (Para los precios más recientes)
|`/SkuRecommendationDatabasesToRecommend` | Lista separada por espacios de las bases de datos que se van a recomendar para (por ejemplo, "Database1" "Database2" "Database3"). Los nombres distinguen mayúsculas de minúsculas y deben ir entre comillas dobles. Si se omite, se proporcionan recomendaciones para todas las bases de datos. | No
|`/AzureAuthenticationTenantId` | El inquilino de autenticación. | S <br> (Para los precios más recientes)
|`/AzureAuthenticationClientId` | IDENTIFICADOR de cliente de la aplicación de AAD que se usa para la autenticación. | S <br> (Para los precios más recientes)
|`/AzureAuthenticationInteractiveAuthentication` | Establézcalo en true para mostrar la ventana. | S <br> (Para los precios más recientes) <br>(Seleccione una de las tres opciones de autenticación: opción 1)
|`/AzureAuthenticationCertificateStoreLocation` | Establezca en la ubicación del almacén de certificados (por ejemplo, "CurrentUser"). | S <br>(Para los precios más recientes) <br> (Seleccione una de las tres opciones de autenticación: opción 2)
|`/AzureAuthenticationCertificateThumbprint` | Establezca en la huella digital del certificado. | S <br> (Para los precios más recientes) <br>(Seleccione una de las tres opciones de autenticación: opción 2)
|`/AzureAuthenticationToken` | Establezca en el token de certificado. | S <br> (Para los precios más recientes) <br>(Seleccione una de las tres opciones de autenticación: opción 3)

## <a name="examples-of-sku-assessments-using-the-cli"></a>Ejemplos de evaluaciones de SKU mediante la CLI

**Dmacmd. exe**

`Dmacmd.exe /? or DmaCmd.exe /help`

**Azure SQL DB/recomendación de SKU de MI con actualización de precios (obtener los precios más recientes)-autenticación interactiva** 

```
.\DmaCmd.exe /Action=SkuRecommendation
/SkuRecommendationInputDataFilePath="C:\TestOut\out.csv"
/SkuRecommendationTsvOutputResultsFilePath="C:\TestOut\prices.tsv"
/SkuRecommendationJsonOutputResultsFilePath="C:\TestOut\prices.json"
/SkuRecommendationOutputResultsFilePath="C:\TestOut\prices.html"
/SkuRecommendationCurrencyCode=USD
/SkuRecommendationOfferName=MS-AZR-0044p
/SkuRecommendationRegionName=UKWest
/SkuRecommendationSubscriptionId=<Your Subscription Id>
/AzureAuthenticationClientId=<Your AzureAuthenticationClientId>
/AzureAuthenticationTenantId=<Your AzureAuthenticationTenantId>
/AzureAuthenticationInteractiveAuthentication=true 
```

**Azure SQL DB/recomendación de SKU de MI con actualización de precios (obtener los precios más recientes)-autenticación de certificados**

```
.\DmaCmd.exe /Action=SkuRecommendation
/SkuRecommendationInputDataFilePath="C:\TestOut\out.csv"
/SkuRecommendationTsvOutputResultsFilePath="C:\TestOut\prices.tsv"
/SkuRecommendationJsonOutputResultsFilePath="C:\TestOut\prices.json"
/SkuRecommendationOutputResultsFilePath="C:\TestOut\prices.html"
/SkuRecommendationCurrencyCode=USD
/SkuRecommendationOfferName=MS-AZR-0044p
/SkuRecommendationRegionName=UKWest
/SkuRecommendationSubscriptionId=<Your Subscription Id>
/AzureAuthenticationClientId=<Your AzureAuthenticationClientId>
/AzureAuthenticationTenantId=<Your AzureAuthenticationTenantId>
/AzureAuthenticationCertificateStoreLocation=<Your Certificate Store Location>
/AzureAuthenticationCertificateThumbprint=<Your Certificate Thumbprint>  
```

**Recomendación de Azure SQL DB SKU/MI con actualización de precios (obtener los precios más recientes)-autenticación de tokens y especificar las bases de datos que se recomiendan**
  
```
.\DmaCmd.exe /Action=SkuRecommendation
/SkuRecommendationInputDataFilePath="C:\TestOut\out.csv"
/SkuRecommendationTsvOutputResultsFilePath="C:\TestOut\prices.tsv"
/SkuRecommendationJsonOutputResultsFilePath="C:\TestOut\prices.json"
/SkuRecommendationOutputResultsFilePath="C:\TestOut\prices.html"
/SkuRecommendationCurrencyCode=USD
/SkuRecommendationOfferName=MS-AZR-0044p
/SkuRecommendationRegionName=UKWest
/SkuRecommendationDatabasesToRecommend=“TPCDS1G,EDW_3G,TPCDS10G”
/SkuRecommendationSubscriptionId=<Your Subscription Id>
/AzureAuthenticationClientId=<Your AzureAuthenticationClientId>
/AzureAuthenticationTenantId=<Your AzureAuthenticationTenantId>
/AzureAuthenticationToken=<Your Authentication Token> 
```

**Azure SQL DB/recomendación de SKU de MI sin actualización de precios (usar precios estáticos)** 
```
.\DmaCmd.exe /Action=SkuRecommendation
/SkuRecommendationInputDataFilePath="C:\TestOut\out.csv"
/SkuRecommendationTsvOutputResultsFilePath="C:\TestOut\prices.tsv"
/SkuRecommendationJsonOutputResultsFilePath="C:\TestOut\prices.json"
/SkuRecommendationOutputResultsFilePath="C:\TestOut\prices.html"
/SkuRecommendationPreventPriceRefresh=true  
```

## <a name="see-also"></a>Consulte también
- [Data Migration Assistant](https://aka.ms/get-dma) descargar.
- En el artículo se [identifican los Azure SQL Database SKU correctos para la base de datos local](https://aka.ms/dma-sku-recommend-sqldb).
