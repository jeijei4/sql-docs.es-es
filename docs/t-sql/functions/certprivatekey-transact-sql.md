---
title: CERTPRIVATEKEY (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 07/24/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: t-sql
ms.topic: language-reference
f1_keywords:
- CERTPRIVATEKEY
- CERTPRIVATEKEY_TSQL
dev_langs:
- TSQL
helpviewer_keywords:
- CERTPRIVATEKEY
ms.assetid: 33e0f01e-39ac-46da-94ff-fe53b1116df4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 4fd9302ae396ffd8c09dcd998e0827032b98d36b
ms.sourcegitcommit: 768f046107642f72693514f51bf2cbd00f58f58a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87111657"
---
# <a name="certprivatekey-transact-sql"></a>CERTPRIVATEKEY (Transact-SQL)
[!INCLUDE [SQL Server Azure SQL Database ](../../includes/applies-to-version/sql-asdb.md)]

Esta función devuelve la clave privada de un certificado en formato binario. Esta función toma tres argumentos.
-   Un identificador de certificado.  
-   Una contraseña de cifrado, que se usa para cifrar los bits de las claves privadas que devuelve la función. Este enfoque no expone las claves como texto no cifrado a los usuarios.  
-   Una contraseña de descifrado opcional. Se usa una contraseña de descifrado especificada para descifrar la clave privada del certificado. En caso contrario, se usa la clave maestra de base de datos.  
  
Solo los usuarios que tienen acceso a la clave privada del certificado pueden usar esta función. Esta función devuelve la clave privada en formato PVK.
  
## <a name="syntax"></a>Sintaxis  
  
```syntaxsql
CERTPRIVATEKEY   
    (  
          cert_ID   
        , ' encryption_password '   
      [ , ' decryption_password ' ]  
    )  
```  
  
[!INCLUDE[sql-server-tsql-previous-offline-documentation](../../includes/sql-server-tsql-previous-offline-documentation.md)]

## <a name="arguments"></a>Argumentos
*certificate_ID*  
**certificate_id** del certificado. Obtenga este valor de sys.certificates o de la función [CERT_ID &#40;Transact-SQL&#41;](../../t-sql/functions/cert-id-transact-sql.md). *cert_id* tiene el tipo de datos **int**.
  
*encryption_password*  
La contraseña utilizada para cifrar el valor binario devuelto.
  
*decryption_password*  
La contraseña utilizada para descifrar el valor binario devuelto.
  
## <a name="return-types"></a>Tipos de valores devueltos
**varbinary**
  
## <a name="remarks"></a>Observaciones  
Use **CERTENCODED** y **CERTPRIVATEKEY** juntos para devolver diferentes partes de un certificado en formato binario.
  
## <a name="permissions"></a>Permisos  
**CERTPRIVATEKEY** está disponible públicamente.
  
## <a name="examples"></a>Ejemplos  
  
```sql
CREATE DATABASE TEST1;  
GO  
USE TEST1  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = 'Use 5tr0ng P^55Words'  
GO  
CREATE CERTIFICATE Shipping04   
WITH SUBJECT = 'Sammamish Shipping Records',   
EXPIRY_DATE = '20401031';  
GO  
SELECT CERTPRIVATEKEY(CERT_ID('Shipping04'), 'jklalkaa/; uia3dd');  
```  
  
Vea el ejemplo B de [CERTENCODED &#40;Transact-SQL&#41;](../../t-sql/functions/certencoded-transact-sql.md) para ver un ejemplo más complejo en el que se usa **CERTPRIVATEKEY** y **CERTENCODED** para copiar un certificado en otra base de datos.
  
## <a name="see-also"></a>Consulte también
[Funciones de seguridad &#40;Transact-SQL&#41;](../../t-sql/functions/security-functions-transact-sql.md)  
[CREATE CERTIFICATE &#40;Transact-SQL&#41;](../../t-sql/statements/create-certificate-transact-sql.md)
[Funciones de seguridad &#40;Transact-SQL&#41;](../../t-sql/functions/security-functions-transact-sql.md)
[sys.certificates &#40;Transact-SQL&#41;](../../relational-databases/system-catalog-views/sys-certificates-transact-sql.md)
  
  
