---
title: ¿Qué son los grupos de datos?
titleSuffix: SQL Server big data clusters
description: En este artículo, se describe el grupo de datos en un clúster de macrodatos de SQL Server 2019.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 08/21/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: 547f3e14d0e73b944cc7bde31f657dbf4ad49d41
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85773659"
---
# <a name="what-are-data-pools-in-a-sql-server-big-data-cluster"></a>¿Qué son los grupos de datos en un clúster de macrodatos de SQL Server?

[!INCLUDE[SQL Server 2019](../includes/applies-to-version/sqlserver2019.md)]

En este artículo, se describe la función de los *grupos de datos de SQL Server* en un [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]. En las secciones siguientes, se describen la arquitectura y las funciones de un grupo de datos SQL.

Este vídeo de 5 minutos presenta grupos de datos y muestra cómo consultar los datos de los grupos de datos:

> [!VIDEO https://channel9.msdn.com/Shows/Data-Exposed/Querying-Data-from-Big-Data-Cluster-Data-Pool/player?WT.mc_id=dataexposed-c9-niner]

## <a name="data-pool-architecture"></a>Arquitectura de un grupo de datos

Un grupo de datos está formado por una o más instancias de grupos de datos de SQL Server. Las instancias del grupo de datos SQL proporcionan un almacenamiento de SQL Server persistente para el clúster. Se usa un grupo de datos para ingerir datos a partir de consultas SQL o trabajos de Spark. Para ofrecer un mejor rendimiento en conjuntos de datos de gran tamaño, los datos de un grupo de datos se distribuyen en particiones en todas las instancias del grupo de datos SQL que sean miembros.

## <a name="scale-out-data-marts"></a>Data marts de escalado horizontal

Los grupos de datos permiten la creación de data marts de escalado horizontal, donde los datos externos de varios orígenes se ingieren en el grupo de datos. Como los datos se distribuyen en varias instancias de grupos de datos, las consultas paralelas en los datos recopilados son más eficientes.

![Data mart de escalado horizontal](media/concept-data-pool/data-virtualization-improvements.png)

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)], vea los recursos siguientes:

- [¿Qué son los [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]?](big-data-cluster-overview.md)
- [Taller: Arquitectura de los [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)] de Microsoft](https://github.com/Microsoft/sqlworkshops/tree/master/sqlserver2019bigdataclusters)
