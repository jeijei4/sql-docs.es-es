---
title: Administrador de conexiones de Azure Resource Manager | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL13.DTS.DESIGNER.AFPARMCM.F1
- SQL14.DTS.DESIGNER.AFPARMCM.F1
ms.assetid: 8ce8024f-153f-4066-b607-0d36fefc79ed
author: Lingxi-Li
ms.author: lingxl
ms.openlocfilehash: 06cf645c41c27ec3a2275e19856c8ba935da73c4
ms.sourcegitcommit: c8e1553ff3fdf295e8dc6ce30d1c454d6fde8088
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86913669"
---
# <a name="azure-resource-manager-connection-manager"></a>Administrador de conexiones de Azure Resource Manager

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


El **Administrador de conexiones de Azure Resource Manager** permite que un paquete SSIS administre los recursos de Azure con una [entidad de servicio](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).

El **Administrador de conexiones de Azure Resource Manager** es un componente de [Feature Pack de SQL Server Integration Services (SSIS) para Azure](../../integration-services/azure-feature-pack-for-integration-services-ssis.md).

Para crear y configurar un **Administrador de conexiones de Azure Resource Manager**, siga estos pasos:

1. En el cuadro de diálogo **Agregar administrador de conexiones SSIS**, seleccione **AzureResourceManager** y haga clic en **Agregar**.
2. En el cuadro de diálogo **Azure Resource Manager Connection Manager Editor** (Editor del Administrador de conexiones de Azure Resource Manager), especifique el **id. de aplicación**, la **clave de aplicación** y el **id. de inquilino** de la entidad de servicio. Para obtener más información acerca de estas propiedades, consulte [este](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal) artículo.
3. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.
4. Puede ver las propiedades del Administrador de conexiones que creó en la ventana **Propiedades** .
