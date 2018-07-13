---
title: Exportar e importar objetos de minería de datos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- analysis-services
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- backing up databases [Analysis Services]
- exporting mining models
- exporting mining structures
- mining structures [Analysis Services], creating
- mining structures [DMX], exporting
- mining models [Analysis Services], migration
ms.assetid: 10a83b13-2640-4ff5-80c8-a35e1d692908
caps.latest.revision: 23
author: minewiskan
ms.author: owend
manager: craigg
ms.openlocfilehash: 4145ca6834a27b1159a0d2311f620085491343cf
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2018
ms.locfileid: "37173606"
---
# <a name="export-and-import-data-mining-objects"></a>Exportar e importar objetos de minería de datos
  Además de la funcionalidad incluida en [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] para crear copias de seguridad, restaurar y migrar soluciones, la minería de datos de SQL Server proporciona la capacidad de transferir rápidamente estructuras y modelos de minería de datos entre servidores diferentes usando Extensiones de minería de datos (DMX).  
  
 Si la solución de minería de datos usa datos relacionales en lugar de una base de datos multidimensional, transferencia de los modelos mediante el uso de `EXPORT` y `IMPORT` es mucho más rápida y sencilla que si usa la restauración de base de datos o implementa una solución completa.  
  
 En esta sección se ofrece información general sobre cómo transferir estructuras y modelos de minería de datos mediante instrucciones DMX. Para más información sobre la sintaxis, además de ejemplos, vea [EXPORT &#40;DMX&#41;](/sql/dmx/export-dmx) e [IMPORT &#40;DMX&#41;](/sql/dmx/import-dmx).  
  
> [!NOTE]  
>  Debe ser administrador de la base de datos o del servidor para exportar o importar objetos de una base de datos de Microsoft SQL Server Analysis Services.  
  
## <a name="exporting-data-mining-structures"></a>Exportar estructuras de minería de datos  
 Al exportar una estructura de minería de datos, la instrucción EXPORT exporta automáticamente todos los modelos asociados. Si desea controlar los objetos que se exportan, debe especificar cada uno de ellos por su nombre.  
  
 Si se ha procesado la estructura de minería de datos y se han almacenado los resultados en memoria caché, que es el comportamiento predeterminado, al exportar la estructura de minería de datos, la definición contiene un resumen de los datos en los que está basada dicha estructura. Para quitar este resumen, debe borrar la memoria caché asociada a la estructura de minería de datos realizando una `Process Clear Structure` operación. Para más información, consulte [Process a Mining Structure](process-a-mining-structure.md).  
  
### <a name="exporting-data-mining-models"></a>Exportar modelos de minería de datos  
 Puede usar el `WITH DEPENDENCIES` palabra clave para exportar el origen de datos y la definición de vista del origen de datos junto con el modelo de minería de datos y su estructura.  
  
 Cuando se exporta un modelo de minería de datos sin exportar sus dependencias, la instrucción EXPORT exportará la definición del modelo y su estructura, pero no la definición de los orígenes de datos. Como consecuencia, después de importar el modelo, podrá examinarlo inmediatamente, pero si desea volver a procesar el modelo de minería de datos en el servidor de destino o ejecutar consultas en los datos subyacentes, debe crear un origen de datos correspondiente en el servidor de destino.  
  
## <a name="importing-data-mining-structures-and-models"></a>Importar estructuras y modelos de minería de datos  
 Cuando se importa un objeto de minería de datos, dicho objeto se importa en el servidor y la base de datos a los que se está conectado al ejecutar la instrucción IMPORT. Si el archivo de importación incluye una base de datos que no existe en el servidor, se creará la base de datos.  
  
 También puede importar una estructura de minería de datos o modelo de minería de datos mediante el `Restore` comando. Los modelos o las estructuras se restaurarán en la base de datos que tenga el mismo nombre que la base de datos de la que se exportaron. Para más información, consulte [Restore Options](../multidimensional-models/restore-options.md).  
  
## <a name="remarks"></a>Notas  
 No puede importar un modelo o una estructura en un servidor si ya existe un modelo o una estructura con el mismo nombre en ese servidor. Tampoco puede exportar un objeto de minería de datos y, a continuación, modificar el nombre de dicho objeto en el archivo de exportación. Por consiguiente, para evitar conflictos de nombres, debería eliminar el objeto de minería de datos en el servidor de destino o cambiar el nombre del objeto de minería de datos antes de exportar la definición.  
  
## <a name="see-also"></a>Vea también  
 [Administración de las soluciones y los objetos de minería de datos](management-of-data-mining-solutions-and-objects.md)  
  
  