---
title: Método updateNString (java.lang.String, java.lang.String) | Microsoft Docs
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
ms.assetid: 6daca03f-c60f-4842-b9e3-11d136e78312
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 325832acffb99c76819bd842bd2954b891900ed0
ms.sourcegitcommit: fe5c45a492e19a320a1a36b037704bf132dffd51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80920047"
---
# <a name="updatenstring-method-javalangstring-javalangstring"></a>Método updateNString (java.lang.String, java.lang.String)
[!INCLUDE[Driver_JDBC_Download](../../../includes/driver_jdbc_download.md)]

  Actualiza la columna designada con un valor **string** mediante el uso de la etiqueta de columna especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
public void updateNString(java.lang.String columnLabel,  
                          java.lang.String nString)  
```  
  
#### <a name="parameters"></a>Parámetros  
 *columnLabel*  
  
 Valor **string** que contiene la etiqueta de columna.  
  
 *nString*  
  
 Un objeto **String**.  
  
## <a name="exceptions"></a>Excepciones  
 [SQLServerException](../../../connect/jdbc/reference/sqlserverexception-class.md)  
  
## <a name="remarks"></a>Observaciones  
 El método updateNString especifica este método updateNString en la interfaz java.sql.ResultSet.  
  
 Este método pasa **String** de Java a columnas **nchar**, **nvarchar(max)** , **ntext** y **xml** seleccionadas. Si se utiliza este método en otras columnas de tipo de datos, se producirá una excepción.  
  
## <a name="see-also"></a>Consulte también  
 [updateNString (método) &#40;SQLServerResultSet&#41;](../../../connect/jdbc/reference/updatenstring-method-sqlserverresultset.md)   
 [Miembros SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-members.md)   
 [Clase SQLServerResultSet](../../../connect/jdbc/reference/sqlserverresultset-class.md)  
  
  
