---
title: Seguridad y protección de Reporting Services | Microsoft Docs
ms.date: 08/26/2016
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- security [Reporting Services]
- Reporting Services, security
ms.assetid: 270075c5-bf12-4467-a775-abbda3d954a5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 189c0d314ba3f16b00ad570b3e0f9fbce9fa2f7e
ms.sourcegitcommit: 8ffc23126609b1cbe2f6820f9a823c5850205372
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81632425"
---
# <a name="reporting-services-security-and-protection"></a>Seguridad y protección de Reporting Services
  Puede usar la información de esta sección para obtener información acerca de las características de seguridad de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. También se explican en ella los modelos de autorización y los proveedores de autenticación que se admiten en [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)].  
  
## <a name="extended-protection-for-authentication"></a>Protección ampliada para la autenticación  
 A partir de [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], se admite la protección ampliada para autenticación. La característica de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] admite el uso del enlace de canal y del enlace de servicio para mejorar la protección de la autenticación. Las características de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tienen que usarse con un sistema operativo que admita la protección ampliada. Para más información, consulte [Extended Protection for Authentication with Reporting Services](../../reporting-services/security/extended-protection-for-authentication-with-reporting-services.md).  
  
## <a name="authentication-and-authorization"></a>Autenticación y autorización  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] proporciona diferentes tipos de autenticación para que los usuarios y las aplicaciones cliente se autentiquen en el servidor de informes. La utilización del tipo de autenticación adecuado para el servidor de informes permite a su organización lograr el nivel de seguridad necesario. Para más información, consulte [Authentication with the Report Server](../../reporting-services/security/authentication-with-the-report-server.md).  
  
 [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] también emplea roles y permisos para controlar el acceso de usuario al contenido del catálogo del servidor de informes (es decir, quién tiene acceso a qué y cómo puede obtener acceso). Para obtener más información, vea [Roles y permisos &#40;Reporting Services&#41;](../../reporting-services/security/roles-and-permissions-reporting-services.md).  
  
## <a name="related-tasks"></a>Related Tasks  
  
|Descripciones de las tareas|Vínculos|  
|-----------------------|-----------|  
|Configure la Seguridad de la capa de transporte (TLS), antes conocida como Capa de sockets seguros (SSL), para proteger las conexiones cliente con el servidor de informes.|[Configuración de conexiones TLS en un servidor de informes en modo nativo](../../reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server.md)|  
  
  
