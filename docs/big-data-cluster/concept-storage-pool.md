---
title: ¿Qué es el bloque de almacenamiento?
titleSuffix: SQL Server big data clusters
description: En este artículo se describe el bloque de almacenamiento en un clúster de macrodatos de SQL Server 2019.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 08/21/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: d7a9d3e9e16eb923e0954154b46362cdc88c0bff
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85730688"
---
# <a name="what-is-the-storage-pool-big-data-clusters-2019"></a>¿Qué es el bloque de almacenamiento ([!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)])?

[!INCLUDE[SQL Server 2019](../includes/applies-to-version/sqlserver2019.md)]

En este artículo se describe el papel del *bloque de almacenamiento de SQL Server* en un [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]. En las secciones siguientes se describen la arquitectura y la funcionalidad de un bloque de almacenamiento de SQL.

## <a name="storage-pool-architecture"></a>Arquitectura del bloque de almacenamiento

El bloque de almacenamiento consiste en nodos de almacenamiento que se componen de SQL Server en Linux, Spark y HDFS. Todos los nodos de almacenamiento de un clúster de macrodatos de SQL Server son miembros de un clúster de HDFS.

![Arquitectura del bloque de almacenamiento](media/concept-storage-pool/scale-big-data-on-demand.png)

## <a name="responsibilities"></a>Responsabilidades

Los nodos de almacenamiento se encargan de varios aspectos:

- Ingesta de datos a través de Spark.
- Almacenamiento de datos en HDFS (formato de texto delimitado y Parquet). HDFS también proporciona persistencia de datos, ya que los datos de HDFS se reparten por todos los nodos de almacenamiento del clúster de macrodatos de SQL.
- Acceso a datos a través de los puntos de conexión de HDFS y SQL Server.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)], vea los recursos siguientes:

- [¿Qué son los [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ver15.md)]?](big-data-cluster-overview.md)
- [Taller: Arquitectura de los [!INCLUDE[big-data-clusters-2019](../includes/ssbigdataclusters-ss-nover.md)] de Microsoft](https://github.com/Microsoft/sqlworkshops/tree/master/sqlserver2019bigdataclusters)
