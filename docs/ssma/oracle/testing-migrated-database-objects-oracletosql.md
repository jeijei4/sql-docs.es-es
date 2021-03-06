---
title: Probar objetos de base de datos migrados (OracleToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: f03ef5e1-66e6-4c84-ada2-252dd5ada82f
author: Shamikg
ms.author: Shamikg
manager: shamikg
ms.openlocfilehash: 858c564c965fe7105c86a3087923887097e4ddac
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68266479"
---
# <a name="testing-migrated-database-objects-oracletosql"></a>Pruebas con objetos de base de datos migrados (OracleToSQL)
[!INCLUDE[msCoName](../../includes/msconame_md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Migration Assistant for Oracle Tester (SSMA Tester) prueba automáticamente la conversión de objetos de base de datos y la migración de datos realizada por SSMA. Una vez finalizados todos los pasos de migración de SSMA, utilice SSMA Tester para comprobar que los objetos convertidos funcionan de la misma manera y que todos los datos se transfirieron correctamente.  
  
Puede probar los siguientes tipos de objeto con el evaluador de SSMA:  
  
-   Tablas  
  
-   Procedimientos almacenados, incluidos los procedimientos empaquetados.  
  
-   Funciones definidas por el usuario, incluidas las funciones empaquetadas.  
  
-   Vistas.  
  
-   Instrucciones independientes.  
  
SSMA Tester ejecuta los objetos seleccionados para las pruebas en Oracle y sus homólogos en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Después, compara los resultados según los criterios siguientes:  
  
-   ¿Los cambios en los datos de tabla son idénticos?  
  
-   ¿Son los valores de parámetros de salida para procedimientos y funciones idénticos?  
  
-   ¿Las funciones devuelven los mismos resultados?  
  
-   ¿Son idénticos los conjuntos de resultados?  
  
> [!NOTE]  
> Centra! No utilice nunca el evaluador de SSMA en sistemas de producción. Durante la ejecución del evaluador, se modifican los datos y el esquema de origen. Mientras tanto, la restauración completa del estado original puede ser imposible para algunos tipos de código probado.  
  
## <a name="prerequisites"></a>Prerrequisitos  
Si desea usar SSMA Tester, instale SSMA Oracle Extension Pack con la opción **install test Database** activada.  
  
Para habilitar la comparación de los datos de la tabla resultante, establezca la opción **generar columna ROWID** en **sí** antes de que se inicie la conversión del esquema. SSMA agregará una columna ROWID a todas las tablas durante la ejecución del comando **Convert Schema** .  
  
Además, compruebe lo siguiente:  
  
-   Las herramientas de cliente de Oracle se instalan [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en el equipo donde se ejecuta.  
  
-   Se ha habilitado la integración de Common Language Runtime (CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ) en el motor de base de datos.  
  
Tenga en cuenta que la versión actual de SSMA Tester no admite la ejecución en paralelo por parte de usuarios diferentes en el mismo servidor de origen o de destino.  
  
## <a name="getting-started"></a>Introducción  
[Crear casos de prueba &#40;OracleToSQL&#41;](../../ssma/oracle/creating-test-cases-oracletosql.md)  
  
## <a name="see-also"></a>Consulte también  
[Instalación de componentes de SSMA en SQL Server &#40;OracleToSQL&#41;](../../ssma/oracle/installing-ssma-components-on-sql-server-oracletosql.md)  
[Configuración del proyecto &#40;conversión&#41; &#40;OracleToSQL&#41;](../../ssma/oracle/project-settings-conversion-oracletosql.md)  
  
