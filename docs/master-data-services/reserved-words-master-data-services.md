---
title: Palabras reservadas
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- reserved words [Master Data Services]
- Master Data Services, reserved words
ms.assetid: 88afd0d0-4362-4394-8357-4e65388fc0fc
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 78dcf9320312f93dd08495f21bf0f6cc1b71516b
ms.sourcegitcommit: 6be9a0ff0717f412ece7f8ede07ef01f66ea2061
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85811470"
---
# <a name="reserved-words-master-data-services"></a>Palabras reservadas (Master Data Services)

[!INCLUDE [SQL Server - Windows only ASDBMI  ](../includes/applies-to-version/sql-windows-only-asdbmi.md)]

  En [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], al crear objetos del modelo o miembros, algunas palabras no se pueden usar. Su uso puede producir errores.  
  
> [!NOTE]  
>  También debe limitar el uso de caracteres especiales (símbolos, guiones, etc.).  
  
-   [Modelos](../master-data-services/reserved-words-master-data-services.md#models)  
  
-   [Entidades](../master-data-services/reserved-words-master-data-services.md#entities)  
  
-   [Jerarquías explícitas](../master-data-services/reserved-words-master-data-services.md#exhierarchies)  
  
-   [Atributos](../master-data-services/reserved-words-master-data-services.md#attributes)  
  
-   [Miembros](../master-data-services/reserved-words-master-data-services.md#members)  
  
##  <a name="models"></a><a name="models"></a>Modelos  
 Si crea un modelo con el nombre establecido en **Name** o **Code**, no seleccione **Crear entidad con el mismo nombre que el modelo** porque **Name** o **Code** no se puede usar para el nombre de una entidad.  
  
##  <a name="entities"></a><a name="entities"></a>Jurídica  
 Para los nombres de entidad, no puede usar **Name** o **Code**.  
  
##  <a name="explicit-hierarchies"></a><a name="exhierarchies"></a>Jerarquías explícitas  
 Para los nombres de jerarquía explícita, no puede utilizar **Name** o **Code**.  
  
##  <a name="attributes"></a><a name="attributes"></a>Sus  
  
-   **ID**  
  
-   **Código**  
  
-   **EnterUserName**  
  
-   **LastChgUserName**  
  
-   **Name**  
  
-   **EnterDTM**  
  
-   **EnterUserID**  
  
-   **EnterUserName**  
  
-   **LastChgDTM**  
  
-   **LastChgUserID**  
  
-   **Status_ID**  
  
-   **ValidationStatus_ID**  
  
-   **Version_ID**  
  
##  <a name="members"></a><a name="members"></a>Registrados  
 Para los miembros, no puede usar **MDMMemberStatus**, **MDMUnused**o **ROOT** para el valor de atributo **Code** .  
  
## <a name="see-also"></a>Consulte también  
 [Introducción a Master Data Services &#40;MDS&#41;](../master-data-services/master-data-services-overview-mds.md)  
  
  
