---
title: Ver informes de casos de prueba (SybaseToSQL) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
helpviewer_keywords:
- Tester Component,Test Case Reports
ms.assetid: cb75d281-43ef-4f4a-b754-2c4ee3b62ae7
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 8a6d45f7e621f9b6516d4cc1211a8627174ae9b3
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "67944607"
---
# <a name="viewing-test-case-reports-sybasetosql"></a>Visualización de informes de casos de prueba (SybaseToSQL)
El informe caso de prueba muestra los resultados de la comprobación de la prueba y la información general de las pruebas. En caso de que se produzca un error en la prueba, también se muestra información sobre los datos que no coinciden en los objetos comprobados.  
  
## <a name="report-structure"></a>Estructura del informe  
En la parte superior del informe se muestran estas estadísticas:  
  
-   El número total de objetos probados y el número de objetos para los que la prueba se realizó correctamente.  
  
-   El número total de tablas comprobadas y claves externas, y el número de tablas y claves externas que coinciden correctamente.  
  
-   La hora de inicio, la hora de finalización del caso de prueba y el tiempo total necesario para la ejecución.  
  
El resto del informe muestra información en cuatro categorías:  
  
**Errores de requisitos previos**  
Muestra los errores que se produjeron en el paso de **requisitos previos** . Normalmente, se omite.  
  
**Inicial**  
Muestra el estado de ejecución como **correcto** o **error**.  
  
**Resultado de objetos de prueba**  
Comparación de los resultados (éxito o error) y las discrepancias que ha detectado SSMA Tester en caso de error.  
  
**Finalización**  
Muestra el estado de ejecución como **correcto** o **error**.  
  
## <a name="see-also"></a>Consulte también  
[Ejecutar casos de prueba &#40;SybaseToSQL&#41;](../../ssma/sybase/running-test-cases-sybasetosql.md)  
[Probar objetos de base de datos migrados &#40;SybaseToSQL&#41;](../../ssma/sybase/testing-migrated-database-objects-sybasetosql.md)  
  
