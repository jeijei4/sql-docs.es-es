---
title: Creación de un conjunto de cambios
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cfad6f1c-9125-4896-b5f5-a4b9f9593cc4
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: db37dd8b4eed5c887cfceceb382fe57aa0d2fc33
ms.sourcegitcommit: 6be9a0ff0717f412ece7f8ede07ef01f66ea2061
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85812450"
---
# <a name="create-a-changeset-master-data-services"></a>Creación de un conjunto de cambios (Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  Un conjunto de cambios es una colección de cambios pendientes en los datos maestros. Si la entidad requiere aprobación para cambios, los cambios pendientes deben guardarse en un conjunto de cambios y luego enviarse para su aprobación por parte del administrador.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe disponer de permiso de acceso al área funcional Explorador. Para obtener más información, consulte [permisos del área funcional &#40;Master Data Services&#41;](../master-data-services/functional-area-permissions-master-data-services.md)  
  
-   Debe tener al menos acceso de lectura a la entidad o a uno de sus atributos.  
  
## <a name="to-create-a-local-changeset"></a>Para crear un conjunto de cambios local  
  
1.  En la [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Página principal, seleccione el modelo y la versión y, a continuación, haga clic en **Explorador**.  
  
2.  Haga clic en una entidad en el menú **Entidades** .  
  
3.  En el panel derecho, seleccione **Conjuntos de cambios** y haga clic en **Crear**.  
  
4.  Escriba un nombre para el conjunto de cambios y haga clic en **Guardar**.  
  
     El nombre del conjunto de cambios debe ser único dentro de un modelo.  
  
## <a name="to-create-a-changeset-for-approval"></a>Para crear un conjunto de cambios para aprobar  
  
1.  En la [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] Página principal, seleccione el modelo y la versión y, a continuación, haga clic en **Explorador**.  
  
2.  Haga clic en una entidad en el menú **Entidades** .  
  
3.  Realice cambios en la entidad y haga clic en**Aceptar**.  
  
4.  **Choose A changeset** (Elegir un conjunto de cambios).  
  
5.  Haga clic en **Nuevo**, escriba un nombre para el conjunto de cambios y haga clic en **Guardar**. El nombre del conjunto de cambios debe ser único dentro de un modelo.  
  
6.  Para utilizar un conjunto de cambios existente, haga clic en **Existente** y elija el conjunto de cambios en la lista. Solo están disponibles aquellos conjuntos de cambios que se encuentran en un estado de abierto o rechazado.  
  
## <a name="next-steps"></a>Pasos siguientes  
 [Aplicar y actualizar un conjunto de cambios &#40;Master Data Services&#41;](../master-data-services/apply-and-update-a-changeset-master-data-services.md)  
  
## <a name="see-also"></a>Consulte también  
 [Confirmar o enviar un conjunto de cambios &#40;Master Data Services&#41;](../master-data-services/commit-or-submit-a-changeset-master-data-services.md)   
 [Aprobación o rechazo de un conjunto de cambios &#40;Master Data Services&#41;](../master-data-services/approve-or-reject-a-changeset-master-data-services.md)  
  
  
