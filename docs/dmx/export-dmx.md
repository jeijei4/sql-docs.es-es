---
title: EXPORTAR (DMX) | Microsoft Docs
ms.date: 06/07/2018
ms.prod: sql
ms.technology: analysis-services
ms.custom: dmx
ms.topic: reference
ms.author: owend
ms.reviewer: owend
author: minewiskan
ms.openlocfilehash: 620bb13d50461e850cc08de1e1b1b71709d78c7c
ms.sourcegitcommit: 205de8fa4845c491914902432791bddf11002945
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "86971758"
---
# <a name="export-dmx"></a>EXPORT (DMX)
[!INCLUDE[ssas](../includes/applies-to-version/ssas.md)]

  Extrae un objeto de modelo o de estructura de minería de datos del servidor a un archivo de copia de seguridad de Analysis Services (.abf).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
EXPORT <object type> <object name>[, <object name>] [<object type> <object name>[, <object name] ] TO <filename> [WITH DEPENDENCIES]  
```  
  
## <a name="arguments"></a>Argumentos  
 *tipo de objeto*  
 Opcional. tipo del objeto que se va a exportar (modelo de minería de datos o estructura de minería de datos).  
  
 *nombre del objeto*  
 Opcional. Nombre del objeto que se va a exportar.  
  
 *filename*  
 Nombre y ubicación del archivo que se va a exportar como cadena.  
  
## <a name="remarks"></a>Observaciones  
 Si la instrucción especifica un modelo de minería de datos, el archivo resultante contendrá también una estructura de minería de datos asociada. Si la instrucción especifica **con dependencias**, todos los objetos necesarios para procesar el objeto (por ejemplo, el origen de datos y la vista del origen de datos) se incluyen en el archivo. ABF.  
  
 Debe ser un administrador de base de datos o de servidor para exportar o importar objetos de una [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] base de datos.  
  
## <a name="export-mining-structure-example"></a>Ejemplo de exportación de estructura de minería de datos  
 En el siguiente ejemplo se exportan las estructuras de minería de datos Targeted Mailing y Forecasting, y el modelo de minería de datos Association a una ubicación de archivos específica. Puesto que el modelo Association forma parte de la estructura de minería de datos Market Basket, también se exporta la estructura Market Basket. Los demás modelos de minería de datos que puedan existir como parte de la estructura de minería de datos Market Basket no se exportarán porque el modelo de asociación se exportó mediante el **modelo de minería**de datos, no la estructura de **minería de datos**.  
  
```  
EXPORT MINING STRUCTURE [Targeted Mailing], [Forecasting] MINING MODEL Association TO 'C:\TM_NEW.abf'  
```  
  
## <a name="export-mining-model-example"></a>Ejemplo de exportación de modelo de minería de datos  
 En el siguiente ejemplo se exporta el modelo de minería de datos Association a una ubicación de archivos especificada. Dado que la instrucción especifica **con las dependencias**, los objetos de origen de datos y de vista del origen de datos también se incluyen en el archivo. ABF.  
  
```  
EXPORT MINING MODEL [Association] TO 'C:\Association_NEW.abf' WITH DEPENDENCIES  
```  
  
## <a name="see-also"></a>Consulte también  
 [Extensiones de minería de datos &#40;DMX&#41; instrucciones de definición de datos](../dmx/dmx-statements-data-definition.md)   
 [Extensiones de minería de datos &#40;DMX&#41; instrucciones de manipulación de datos](../dmx/dmx-statements-data-manipulation.md)   
 [Referencia de instrucciones de extensiones de minería de datos &#40;DMX&#41;](../dmx/data-mining-extensions-dmx-statements.md)   
 [IMPORTAR &#40;DMX&#41;](../dmx/import-dmx.md)   
 [Exportar e importar objetos de minería de datos](https://docs.microsoft.com/analysis-services/data-mining/export-and-import-data-mining-objects)  
  
  
