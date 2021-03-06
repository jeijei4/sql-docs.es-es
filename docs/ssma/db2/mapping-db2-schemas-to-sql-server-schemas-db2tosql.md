---
title: Asignación de esquemas de DB2 a esquemas de SQL Server (DB2ToSQL) | Microsoft Docs
ms.prod: sql
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.technology: ssma
ms.topic: conceptual
ms.assetid: 05ff7bd4-e60b-4f48-a893-bc2346aa9a8a
author: Shamikg
ms.author: Shamikg
ms.openlocfilehash: 50845a9bdf3c3185d7b69bb86a75b2a3d332ef6b
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "68074175"
---
# <a name="mapping-db2-schemas-to-sql-server-schemas-db2tosql"></a>Asignación de esquemas de DB2 a esquemas de SQL Server (DB2ToSQL)
En DB2, cada base de datos tiene uno o más esquemas. De forma predeterminada, SSMA migra todos los objetos de un esquema DB2 a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] una base de datos denominada para el esquema. Sin embargo, puede personalizar la asignación entre las bases de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] y los esquemas DB2.  
  
## <a name="db2-and-sql-server-schemas"></a>Esquemas de DB2 y SQL Server  
Una base de datos DB2 contiene esquemas. Una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] contiene varias bases de datos, cada una de las cuales puede tener varios esquemas.  
  
El concepto de DB2 de un esquema se asigna [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] al concepto de una base de datos y a uno de sus esquemas. Por ejemplo, DB2 podría tener un esquema denominado **HR**. Una instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podría tener una base de datos denominada **HR**y, dentro de esa base de datos, los esquemas. Un esquema es el esquema **DBO** (o el propietario de la base de datos). De forma predeterminada, el **HR** del esquema DB2 se asignará [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] a la base de datos y el esquema **HR. DBO**. SSMA hace referencia a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] la combinación de base de datos y esquema como esquema.  
  
Puede modificar la asignación entre DB2 y [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] los esquemas.  
  
## <a name="modifying-the-target-database-and-schema"></a>Modificar la base de datos y el esquema de destino  
En SSMA, puede asignar un esquema DB2 a cualquier esquema disponible [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
**Para modificar la base de datos y el esquema**  
  
1.  En el explorador de metadatos DB2, seleccione **esquemas**.  
  
    La pestaña **asignación de esquema** también está disponible cuando se selecciona una base de datos individual, la carpeta **esquemas** o los esquemas individuales. La lista de la pestaña **asignación de esquema** está personalizada para el objeto seleccionado.  
  
2.  En el panel derecho, haga clic en la pestaña **asignación de esquema** .  
  
    Verá una lista de todos los esquemas de DB2, seguidos de un valor de destino. Este destino se denota en una notación de dos partes (*Database. Schema*) [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la que se migrarán los objetos y los datos.  
  
3.  Seleccione la fila que contiene la asignación que desea cambiar y, a continuación, haga clic en **modificar**.  
  
    En el cuadro de diálogo **elegir esquema de destino** , puede buscar el esquema y la base de datos de destino disponibles o escribir la base de datos y el nombre de esquema en el cuadro de texto en una notación de dos partes (Database. Schema) y, a continuación, hacer clic en **Aceptar**.  
  
4.  El destino cambia en la pestaña **asignación de esquema** .  
  
**Modos de asignación**  
  
-   Asignar a SQL Server  
  
Puede asignar una base de datos de origen a cualquier base de datos de destino. De forma predeterminada, la base de datos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] de origen se asigna a la base de datos de destino con la que se ha conectado mediante SSMA. Si la base de datos de destino que se está asignando no existe en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], se le mostrará un mensaje que indica que la base de datos o **el esquema no existen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en los metadatos de destino. Se creará durante la sincronización. ¿Desea continuar? "** Haga clic en Sí. Del mismo modo, puede asignar un esquema a un esquema no existente [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] en la base de datos de destino que se creará durante la sincronización.  
  
## <a name="reverting-to-the-default-database-and-schema"></a>Revertir a la base de datos y el esquema predeterminados  
Si personaliza la asignación entre un esquema DB2 y un [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] esquema, puede revertir la asignación a los valores predeterminados.  
  
**Para revertir a la base de datos y el esquema predeterminados**  
  
1.  En la pestaña asignación de esquema, seleccione cualquier fila y haga clic en **Restablecer valores predeterminados** para revertir a la base de datos y el esquema predeterminados.  
  
## <a name="next-steps"></a>Pasos a seguir  
Si desea analizar la conversión de objetos DB2 en [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] objetos, puede usar el informe de migración de [datos (SSMA Common)](https://msdn.microsoft.com/bbfb9d88-5a98-4980-8d19-c5d78bd0d241).  
  
## <a name="see-also"></a>Consulte también  
[Conexión a SQL Server &#40;DB2eToSQL&#41;](../../ssma/db2/connecting-to-sql-server-db2etosql.md)  
[Migrar bases de datos DB2 a SQL Server &#40;DB2ToSQL&#41;](../../ssma/db2/migrating-db2-databases-to-sql-server-db2tosql.md)  
  
