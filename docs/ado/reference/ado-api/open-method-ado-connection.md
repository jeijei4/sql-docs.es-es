---
title: Open (método) (conexión de ADO) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
apitype: COM
f1_keywords:
- Connection15::raw_Open
- Connection15::Open
- _Connection::Open
helpviewer_keywords:
- Open method [ADO]
ms.assetid: 663defab-5545-4973-9036-24d5882c9737
author: rothja
ms.author: jroth
ms.openlocfilehash: 31ce05ce069e0eb3e7d6431b296f40824a8acd3a
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82762206"
---
# <a name="open-method-ado-connection"></a>Open (método) (conexión de ADO)
Abre una conexión a un origen de datos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
connection.Open ConnectionString, UserID, Password, Options  
```  
  
#### <a name="parameters"></a>Parámetros  
 *ConnectionString*  
 Opcional. Valor de **cadena** que contiene información de conexión. Vea la propiedad [ConnectionString](../../../ado/reference/ado-api/connectionstring-property-ado.md) para obtener más información sobre los valores válidos.  
  
 *UserID*  
 Opcional. Valor de **cadena** que contiene un nombre de usuario que se va a usar al establecer la conexión.  
  
 *Contraseña*  
 Opcional. Valor de **cadena** que contiene la contraseña que se va a utilizar para establecer la conexión.  
  
 *Opciones*  
 Opcional. Un valor [ConnectOptionEnum](../../../ado/reference/ado-api/connectoptionenum.md) que determina si este método debe devolver después de (sincrónicamente) o antes (asincrónicamente) que se establece la conexión.  
  
## <a name="remarks"></a>Observaciones  
 El uso del método **Open** en un objeto [Connection](../../../ado/reference/ado-api/connection-object-ado.md) establece la conexión física a un origen de datos. Una vez completado correctamente este método, la conexión está activa y puede emitir comandos en ella y procesar los resultados.  
  
 Use el argumento opcional *ConnectionString* para especificar una cadena de conexión que contenga una serie de instrucciones *argument* *= Value* separadas por punto y coma, o un recurso de archivo o directorio identificado con una dirección URL. La propiedad **ConnectionString** hereda automáticamente el valor utilizado para el argumento *ConnectionString* . Por lo tanto, puede establecer la propiedad **ConnectionString** del objeto de **conexión** antes de abrirla, o bien usar el argumento *ConnectionString* para establecer o invalidar los parámetros de conexión actuales durante la llamada al método **Open** .  
  
 Si pasa la información de usuario y contraseña en el argumento *ConnectionString* y en los argumentos opcionales de *userid* y *password* , los argumentos *userid* y *password* invalidarán los valores especificados en *ConnectionString*.  
  
 Cuando haya finalizado las operaciones en una **conexión**abierta, use el método [Close](../../../ado/reference/ado-api/close-method-ado.md) para liberar los recursos del sistema asociados. Al cerrar un objeto no se quita de la memoria; puede cambiar la configuración de sus propiedades y usar el método **Open** para abrirla de nuevo más adelante. Para eliminar completamente un objeto de la memoria, establezca la variable de objeto en *Nothing*.  
  
> [!NOTE]
>  **Uso del servicio de datos remotos** Cuando se usa en un objeto de **conexión** de cliente, el método **Open** no establece realmente una conexión con el servidor hasta que se abre un [conjunto de registros](../../../ado/reference/ado-api/recordset-object-ado.md) en el objeto de **conexión** .  
  
> [!NOTE]
>  Las direcciones URL que usan el esquema http invocarán automáticamente el [proveedor de Microsoft OLE DB para la publicación en Internet](../../../ado/guide/appendixes/microsoft-ole-db-provider-for-internet-publishing.md). Para obtener más información, consulte [direcciones URL absolutas y relativas](../../../ado/guide/data/absolute-and-relative-urls.md).  
  
## <a name="applies-to"></a>Se aplica a  
 [Objeto de conexión (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)  
  
## <a name="see-also"></a>Consulte también  
 [Ejemplo de los métodos Open y Close (VB)](../../../ado/reference/ado-api/open-and-close-methods-example-vb.md)   
 [Ejemplo de los métodos Open y Close (VBScript)](../../../ado/reference/ado-api/open-and-close-methods-example-vbscript.md)   
 [Ejemplo de los métodos Open y Close (VC + +)](../../../ado/reference/ado-api/open-and-close-methods-example-vc.md)   
 [Open (método) (record de ADO)](../../../ado/reference/ado-api/open-method-ado-record.md)   
 [Open (método) (conjunto de registros ADO)](../../../ado/reference/ado-api/open-method-ado-recordset.md)   
 [Open (método, secuencia de ADO)](../../../ado/reference/ado-api/open-method-ado-stream.md)   
 [Método OpenSchema](../../../ado/reference/ado-api/openschema-method.md)
