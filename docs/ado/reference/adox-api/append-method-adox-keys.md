---
title: Append (método) (claves ADOX) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Keys::Append
- Keys::raw_Append
helpviewer_keywords:
- Append method [ADOX]
ms.assetid: 215a5391-f422-42ec-99ea-4e6fbb5d3d64
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d4797344958391dca278e23be2efafa6d1b3f69
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82764036"
---
# <a name="append-method-adox-keys"></a>Append (método) (claves ADOX)
Agrega un nuevo objeto [clave](../../../ado/reference/adox-api/key-object-adox.md) a la colección de [claves](../../../ado/reference/adox-api/keys-collection-adox.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
Keys.Append Key [,KeyType] [,Column] [,RelatedTable] [,RelatedColumn]  
```  
  
#### <a name="parameters"></a>Parámetros  
 *Clave*  
 Objeto de **clave** que se va a anexar o el nombre de la clave que se va a crear y anexar.  
  
 *KeyType*  
 Opcional. Valor **largo** que especifica el tipo de clave. El parámetro *clave* corresponde a la propiedad [Type](../../../ado/reference/adox-api/type-property-key-adox.md) de un objeto **key** .  
  
 *Columna*  
 Opcional. Valor de **cadena** que especifica el nombre de la columna que se va a indizar. El parámetro *Columns* corresponde al valor de la propiedad [Name](../../../ado/reference/adox-api/name-property-adox.md) de un objeto [Column](../../../ado/reference/adox-api/column-object-adox.md) .  
  
 *RelatedTable*  
 Opcional. Valor de **cadena** que especifica el nombre de la tabla relacionada. El parámetro *RelatedTable* corresponde al valor de la propiedad **Name** de un objeto [TABLE](../../../ado/reference/adox-api/table-object-adox.md) .  
  
 *RelatedColumn*  
 Opcional. Valor de **cadena** que especifica el nombre de la columna relacionada para una clave externa. El parámetro *RelatedColumn* corresponde al valor de la propiedad **Name** de un objeto [Column](../../../ado/reference/adox-api/column-object-adox.md) .  
  
## <a name="remarks"></a>Comentarios  
 El parámetro *Columns* puede tomar el nombre de una columna o una matriz de nombres de columna.  
  
## <a name="applies-to"></a>Se aplica a  
 [Colección de claves (ADOX)](../../../ado/reference/adox-api/keys-collection-adox.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de las propiedades de método Append, tipo de clave, RelatedColumn, RelatedTable y UpdateRule (VB)](../../../ado/reference/adox-api/keys-append-method-key-type-relatedcolumn-relatedtable-example-vb.md)   
 [Append (método) (columnas ADOX)](../../../ado/reference/adox-api/append-method-adox-columns.md)   
 [Append (método) (grupos ADOX)](../../../ado/reference/adox-api/append-method-adox-groups.md)   
 [Append (método) (índices ADOX)](../../../ado/reference/adox-api/append-method-adox-indexes.md)   
 [Append (método) (procedimientos ADOX)](../../../ado/reference/adox-api/append-method-adox-procedures.md)   
 [Append (método) (tablas ADOX)](../../../ado/reference/adox-api/append-method-adox-tables.md)   
 [Append (método) (usuarios ADOX)](../../../ado/reference/adox-api/append-method-adox-users.md)   
 [Append (método) (vistas ADOX)](../../../ado/reference/adox-api/append-method-adox-views.md)
