---
title: Claves simétricas en bases de datos de usuario | Microsoft Docs
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 3333ab5b-2518-4753-a0a8-57df5e5af74f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: dd650742e2781388d0d0941b80c6c9a9d60a801c
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85727315"
---
# <a name="symmetric-keys-on-user-databases"></a>Claves simétricas en bases de datos de usuario
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  Esta regla comprueba si las claves que tienen una longitud de menos de 128 bytes no utilizan el algoritmo de cifrado RC2 o RC4.  
  
## <a name="best-practices-recommendations"></a>Prácticas recomendadas  
 Utilice AES de 128 bits o más para crear las claves simétricas para el cifrado de los datos. Si el sistema operativo no admite AES, utilice 3DES.  
  
## <a name="for-more-information"></a>Para obtener más información  
 [Elegir un algoritmo de cifrado](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md)  
  
## <a name="see-also"></a>Consulte también  
 [Supervisar y aplicar las prácticas recomendadas usando la administración basada en directivas](../../relational-databases/policy-based-management/monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
