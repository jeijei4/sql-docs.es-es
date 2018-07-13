---
title: Crear InfoSource para datos de transacción | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- integration-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: ab5f23e2-cd4e-4507-83d9-ac5ef721c171
caps.latest.revision: 9
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.openlocfilehash: c18c6edb21effe53c31e7885ec25025c94c4f1d2
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37162738"
---
# <a name="create-infosource-for-transaction-data"></a>Crear Infosource para datos de transacción
  Use el cuadro de diálogo **Crear InfoSource para los datos de transacción** para crear un InfoSource nuevo para los datos de transacción en el sistema SAP Netweaver BW.  
  
 Puede abrir el cuadro de diálogo **Crear InfoSource para los datos de transacción** desde la página **Administrador de conexiones** del **Editor de destino de SAP BW**. Para más información acerca del destino de SAP BW, consulte [SAP BW Destination](sap-bw-destination.md).  
  
> [!IMPORTANT]  
>  La documentación de Microsoft Connector 1.1 for SAP BW da por supuesto que se está familiarizado con el entorno SAP Netweaver BW. Para obtener más información acerca de SAP Netweaver BW, o sobre cómo configurar los objetos y los procesos de SAP Netweaver BW, vea la documentación de SAP.  
  
 **Para abrir el cuadro de diálogo Crear InfoSource para los datos de transacción**  
  
1.  En [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], abra el paquete de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] que contiene el destino SAP BW.  
  
2.  En la pestaña **Flujo de datos** , haga doble clic en el destino de SAP BW.  
  
3.  En **Editor de destino SAP BW**, haga clic en **Administrador de conexiones** para abrir la página **Administrador de conexiones** del editor.  
  
4.  En la página **Administrador de conexiones** , en el cuadro del grupo **Crear objetos de SAP BW** , seleccione **InfoSource**y, a continuación, haga clic en **Crear**.  
  
5.  En el cuadro de diálogo **Crear InfoSource** , seleccione **Datos transaccionales**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="general-options"></a>Opciones generales  
 **Nombre de InfoSource**  
 Permite escribir un nombre para el nuevo InfoSource.  
  
 **Descripción breve**  
 Permite escribir una descripción breve para el nuevo InfoSource.  
  
 **Descripción larga**  
 Permite escribir una descripción larga para el nuevo InfoSource.  
  
 **Sistema de origen**  
 Permite seleccionar el sistema de origen asociado al InfoSource.  
  
 **Guardar y activar**  
 Permite guardar y activar el nuevo InfoSource.  
  
## <a name="infosource-transfer-structure-options"></a>Opciones de la estructura de transferencia de InfoSource  
 La estructura de transferencia de InfoSource permite asociar columnas del flujo de datos a InfoSources.  
  
 **PipelineElement**  
 Permite mostrar la columna en la salida del flujo de datos que está conectada al destino de SAP BW.  
  
 **PipelineDataType**  
 Muestra el tipo de datos de [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] de la columna del flujo de datos.  
  
 **IObject - Buscar**  
 Permite asociar un InfoObject existente a la columna de flujo de datos de la fila actual. Para efectuar este tipo de asociación, haga clic en **Buscar**y, a continuación use el cuadro de diálogo **Buscar InfoObject** para seleccionar el InfoObject existente. Para obtener más información sobre este cuadro de diálogo, vea [Look Up InfoObject](look-up-infoobject.md).  
  
 Después de seleccionar un InfoObject existente, el componente rellena las columnas **InfoObject** y **Tipo** con los valores seleccionados.  
  
 **IObject - Nuevo**  
 Permite crear un InfoObject nuevo y asociarlo a la columna de flujo de datos de la fila actual. Para crear el InfoObject nuevo, haga clic en **Nuevo**y, a continuación, use el cuadro de diálogo **Crear nuevo InfoObject** para crear el InfoObject. Para obtener más información sobre este cuadro de diálogo, vea [Create New InfoObject](create-new-infoobject.md).  
  
 Después haber creado un InfoObject nuevo, el componente rellena las columnas **InfoObject** y **Tipo** con los valores nuevos.  
  
 **IObject - Quitar**  
 Permite quitar la asociación entre el InfoObject y la columna de flujo de datos de la fila actual. Para quitar esta asociación, haga clic en **Quitar**.  
  
 **InfoObject**  
 Permite mostrar el nombre del InfoObject que está asociado a la columna del flujo datos.  
  
 **Tipo**  
 Permite mostrar el tipo del InfoObject que está asociado a la columna del flujo datos. En la siguiente tabla se muestran los posibles valores para el tipo.  
  
|Valor|Descripción|  
|-----------|-----------------|  
|CHA|Características|  
|UNI|Unidades|  
|KYF|Cifras clave|  
|TIM|Características de tiempo|  
  
 **Campo de unidad**  
 Permite especificar las unidades que va a usar el InfoObject.  
  
## <a name="see-also"></a>Vea también  
 [Crear InfoSource](create-infosource.md)   
 [Ayuda F1 de Microsoft Connector 1.1 for SAP BW](../microsoft-connector-for-sap-bw-f1-help.md)  
  
  