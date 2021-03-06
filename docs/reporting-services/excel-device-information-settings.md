---
title: Configuración de la información del dispositivo Excel | Microsoft Docs
ms.date: 01/23/2020
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: reporting-services
ms.topic: conceptual
helpviewer_keywords:
- device information settings [Reporting Services], Excel rendering
- Excel [Reporting Services], rendering
ms.assetid: bb5f3566-f033-4470-be87-1f52fb7a4ab6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 7a83bcd79a50400888d5a973ad9a743db19b87b5
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2020
ms.locfileid: "76761829"
---
# <a name="excel-device-information-settings"></a>Configuración de la información del dispositivo Excel
  En la tabla siguiente se muestra la configuración de la información de los dispositivos para la representación en formato de [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)] .  
  
|Configuración|Value|  
|-------------|-----------|  
|**OmitDocumentMap**|Indica si omitir el mapa del documento para los informes que lo admiten. El valor predeterminado es **false**.|  
|**OmitFormulas**|Indica si omitir las fórmulas del informe representado. El valor predeterminado es **false**.|  
|**SimplePageHeaders**|Indica si el encabezado de página del informe se representa en el encabezado de página de Excel. El valor **false** indica que el encabezado de página se representa en la primera fila de la hoja de cálculo. El valor predeterminado es **false**.|  
|**DynamicImageDpi**|La resolución de imágenes dinámicas como gráficos, medidores y mapas. El valor predeterminado es **96**. (Disponible en Power BI Report Server [enero de 2020] y versiones posteriores)|  

  
## <a name="see-also"></a>Consulte también  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 [Pasar la configuración de información de dispositivo a las extensiones de representación](../reporting-services/report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md)   
 [Personalizar los parámetros de extensión de representación en RSReportServer.Config](../reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config.md)   
 [Referencia técnica &#40;SSRS&#41;](../reporting-services/technical-reference-ssrs.md)  
  
  
