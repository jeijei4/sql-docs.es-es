---
title: MSSQLSERVER_41399 | Microsoft Docs
ms.custom: ''
ms.date: 04/04/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: supportability
ms.topic: language-reference
helpviewer_keywords:
- 41399 (Database Engine error)
ms.assetid: 5e5acb07-16ca-4329-8210-cd2bab0c904f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 42de242bfa6c0c7da361e91b37938f6e560c04f6
ms.sourcegitcommit: da88320c474c1c9124574f90d549c50ee3387b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85715459"
---
# <a name="mssqlserver_41399"></a>MSSQLSERVER_41399
 [!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]
  
## <a name="details"></a>Detalles  
  
| Atributo | Value |  
| :-------- | :---- |  
|Nombre de producto|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|Id. de evento|41399|  
|Origen de eventos|MSSQLSERVER|  
|Componente|SQLEngine|  
|Nombre simbólico|MAX_SORT_ROW_WIDTH_EXCEEDED|  
|Texto del mensaje|La operación de ordenación es demasiado compleja. Consulte los Libros en pantalla de SQL Server para obtener más información.|  
  
## <a name="explanation"></a>Explicación  
Ordenar el resultado de las operaciones de combinación y agregación aumenta la complejidad de la operación de ordenación, ya que aumenta el tamaño de la fila en el búfer de ordenación. Este error indica que el tamaño de la fila es mayor que el tamaño máximo admitido por el operador sort en los procedimientos almacenados compilados de forma nativa. Tenga en cuenta que el tamaño de una fila en el búfer de ordenación solo lo determinan el número de combinaciones y el número y el tipo de funciones de agregado. El tamaño de las filas de las tablas base no afecta al tamaño de la fila en e búfer.  
  
## <a name="user-action"></a>Acción del usuario  
Reduzca la complejidad de la consulta quitando combinaciones o funciones de agregado.  
  
## <a name="see-also"></a>Consulte también  
[OLTP en memoria &#40;optimización en memoria&#41;](~/relational-databases/in-memory-oltp/in-memory-oltp-in-memory-optimization.md)  
  
