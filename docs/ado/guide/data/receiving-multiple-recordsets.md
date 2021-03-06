---
title: Recibir varios conjuntos de registros | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- receiving multiple Recordsets [ADO]
- Recordset object [ADO], receiving multiple Recordsets
ms.assetid: 2a7ad7a6-f00d-4355-b0b5-d0ab957b0566
author: rothja
ms.author: jroth
ms.openlocfilehash: 12aa80b918d11dad07119a26da3da8f27ef82cdb
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82759111"
---
# <a name="receiving-multiple-recordsets"></a>Recibir varios conjuntos de registros
El [proveedor de Microsoft OLE DB para SQL Server](../../../ado/guide/appendixes/microsoft-ole-db-provider-for-sql-server.md) admite la devolución de varios objetos de **conjunto de registros** para un único comando que contiene varias instrucciones SQL, un **conjunto de registros** por cada instrucción SQL. El orden en el que se devuelven los **conjuntos de registros**sigue el orden en el que se colocan las instrucciones SQL en el texto del comando.  
  
 El proveedor de OLE DB de Microsoft para SQL Server también devuelve varios conjuntos de comandos a ADO cuando el comando contiene una cláusula COMPUTE. Por ejemplo, un comando que contenga la siguiente instrucción SQL devolverá los resultados en dos objetos de **conjunto de registros** : uno para el conjunto de filas de (*ProductID*, *ProductName*, *UnitPrice*) y el otro para el precio medio de todos los productos de la tabla.  
  
```  
SELECT ProductID, ProductName, UnitPrice   
  FROM PRODUCTS   
  COMPUTE AVG(UnitPrice)  
```  
  
 Puede usar el método **Recordset. NextRecordset** para enumerar los dos objetos.  
  
 Para obtener más información, vea [NextRecordset](../../../ado/reference/ado-api/nextrecordset-method-ado.md).
