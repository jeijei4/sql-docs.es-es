---
title: Ordenar columnas | Microsoft Docs
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.monitor.sortcolumns.f1
ms.assetid: 66b44b6c-10a5-4e3f-a97b-7568609c88ac
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-mi-current||>=sql-server-2016||=sqlallproducts-allversions
ms.openlocfilehash: 0840b390e6a4771b5e92be75e560fb22f1822e05
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85728255"
---
# <a name="sort-columns"></a>Ordenar columnas
[!INCLUDE [SQL Server SQL MI](../../includes/applies-to-version/sql-asdbmi.md)]
  El cuadro de diálogo **Ordenar columnas** le permite ordenar las cuadrículas en el Monitor de replicación basado en una o más columnas. (También puede ordenar en una columna única haciendo clic en el encabezado de columna en la cuadrícula del Monitor de replicación). Por ejemplo, para ordenar suscripciones en la pestaña **Todas las suscripciones** basándose en el estado y después el tipo de conexión, siga estos pasos:  
  
1.  En la primera fila de la cuadrícula, seleccione **Estado** de la columna **Nombre de columna** y un valor de la columna **Criterio de ordenación**  
  
2.  En la segunda fila de la cuadrícula, seleccione **Tipo de conexión** de la columna **Nombre de columna** y un valor de la columna **Criterio de ordenación** .  

## <a name="options"></a>Opciones  
 **Nombre de la columna**  
 El nombre de la columna en la que desea ordenar. Puede ordenar en una o más columnas. No puede ordenar en las columnas **Rendimiento medio actual** o **Peor rendimiento actual** en la pestaña **Publicaciones** , debido a la manera en la que se calculan estos valores de columna.  
  
 **Criterio de ordenación**  
 Especifique un valor **Ascendente** o **Descendente**.  
  
 **Borrar todo**  
 Quite todas las filas de la cuadrícula de ordenación. Para quitar una fila única, seleccione la fila y presione la tecla Suprimir.  
  
## <a name="see-also"></a>Consulte también  
 [Supervisar la replicación](../../relational-databases/replication/monitor/monitoring-replication.md)  
  
  
