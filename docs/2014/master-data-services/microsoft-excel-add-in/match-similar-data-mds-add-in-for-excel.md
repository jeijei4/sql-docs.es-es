---
title: Coincidir datos similares (Complemento MDS para Excel) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- master-data-services
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f6fd6fc1-3569-42a5-b6cb-87a921c88f3b
caps.latest.revision: 5
author: douglaslMS
ms.author: douglasl
manager: jhubbard
ms.openlocfilehash: 22d9e7f6a9d78093287c146f007a9a722343baea
ms.sourcegitcommit: 5dd5cad0c1bbd308471d6c885f516948ad67dfcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36107473"
---
# <a name="match-similar-data-mds-add-in-for-excel"></a>Coincidir datos similares (Complemento MDS para Excel)
  En el [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use la funcionalidad Data Quality Services (DQS) para buscar similitudes en los datos.  
  
 Para realizar este procedimiento, puede:  
  
-   Usar la base de conocimiento de Data Quality Services predeterminada o  
  
-   Crear su propia base de conocimiento DQS personalizada y directiva correspondiente. Para más información, consulte [Create a Matching Policy](../../data-quality-services/create-a-matching-policy.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Debe tener una hoja de cálculo activa que contenga los datos administrados por MDS. Para obtener más información, consulte [cargar datos de MDS en Excel](export-data-to-excel-from-master-data-services.md).  
  
-   Opcional. Puede combinar otros datos con datos administrados con MDS antes de comprobar las similitudes. Para obtener más información, consulte [Combinar datos &#40;Complemento MDS para Excel&#41;](combine-data-mds-add-in-for-excel.md).  
  
### <a name="to-find-similarities-by-using-the-default-knowledge-base"></a>Para buscar similitudes con la base de conocimiento predeterminada  
  
1.  En la hoja de cálculo que contiene datos administrados con MDS, en el grupo **Data Quality** , haga clic en **Datos de coincidencia**.  
  
2.  En el cuadro de diálogo **Datos de coincidencia** , en la lista **DQS de Knowledge Base** , seleccione **Datos de DQS (predeterminado)**.  
  
3.  Para cada columna que contenga los datos que desee buscar, agregue una fila en el cuadro de diálogo. Para obtener información sobre los campos en este cuadro de diálogo, vea [How to Set Matching Rule Parameters](../../data-quality-services/create-a-matching-policy.md#MatchingRules).  
  
4.  Cuando el total de todos los valores de peso sea igual al 100 por ciento, haga clic en **Aceptar**.  
  
### <a name="to-find-similarities-by-using-a-custom-knowledge-base"></a>Para buscar similitudes con una base de conocimiento personalizada  
  
1.  En la hoja de cálculo que contiene datos administrados con MDS, en el grupo **Data Quality** , haga clic en **Datos de coincidencia**.  
  
2.  En la lista **Base de conocimiento DQS** , seleccione el nombre de la base de conocimiento personalizada.  
  
3.  Para cada columna de la hoja de cálculo, seleccione un dominio DQS.  
  
4.  Cuando todos los dominios DQS se asignen a las columnas de la hoja de cálculo, haga clic en **Aceptar**.  
  
## <a name="next-steps"></a>Pasos siguientes  
  
-   Vea información adicional para determinar qué datos son similares. Para obtener más información, consulte [Columnas de coincidencia de calidad de datos &#40;Complemento MDS para Excel&#41;](data-quality-matching-columns-mds-add-in-for-excel.md).  
  
## <a name="see-also"></a>Vea también  
 [Calidad de los datos coincidentes en el complemento MDS para Excel](data-quality-matching-in-the-mds-add-in-for-excel.md)   
 [Coincidencia de datos](../../data-quality-services/data-matching.md)  
  
  