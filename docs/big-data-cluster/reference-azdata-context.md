---
title: Referencia de azdata context
titleSuffix: SQL Server big data clusters
description: Artículo de referencia de los comandos azdata context.
author: MikeRayMSFT
ms.author: mikeray
ms.reviewer: mihaelab
ms.date: 11/04/2019
ms.topic: reference
ms.prod: sql
ms.technology: big-data-cluster
ms.openlocfilehash: f2716a8176124539aa7caf382193359ff5435aa6
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2020
ms.locfileid: "74820994"
---
# <a name="azdata-context"></a>azdata context

[!INCLUDE[tsql-appliesto-ssver15-xxxx-xxxx-xxx](../includes/tsql-appliesto-ssver15-xxxx-xxxx-xxx.md)]  

En el artículo siguiente se proporciona una referencia de los comandos `context` de la herramienta `azdata`. Para más información sobre otros comandos `azdata`, vea la [referencia de azdata](reference-azdata.md).

## <a name="commands"></a>Comandos:
|     |     |
| --- | --- |
[azdata context list](#azdata-context-list) | Muestra los contextos disponibles en el perfil de usuario.
[azdata context delete](#azdata-context-delete) | Elimina del perfil de usuario el contexto con el espacio de nombres especificado.
[azdata context set](#azdata-context-set) | Establece el contexto con el espacio de nombres especificado como contexto activo en el perfil de usuario.
## <a name="azdata-context-list"></a>azdata context list
Puede establecer o eliminar cualquiera de ellos con `azdata context set` o `azdata context delete`. Para iniciar sesión en un nuevo contexto, use `azdata login`.
```bash
azdata context list [--active -a] 
  ```
### <a name="examples"></a>Ejemplos
Muestra todos los contextos disponibles en el perfil de usuario.
```bash
azdata context list
```
Muestra el contexto activo en el perfil de usuario.
```bash
azdata context list --active
```
### <a name="optional-parameters"></a>Parámetros opcionales
#### `--active -a`
Muestra solo el contexto activo actualmente.
### <a name="global-arguments"></a>Argumentos globales
#### `--debug`
Aumente el nivel de detalle de registro para mostrar todos los registros de depuración.
#### `--help -h`
Muestre este mensaje de ayuda y salga.
#### `--output -o`
Formato de salida.  Valores permitidos: json, jsonc, table y tsv.  Valor predeterminado: json.
#### `--query -q`
Cadena de consulta de JMESPath. Para obtener más información y ejemplos, vea [http://jmespath.org/](http://jmespath.org/).
#### `--verbose`
Aumente el nivel de detalle de registro. Use --debug para obtener registros de depuración completos.
## <a name="azdata-context-delete"></a>azdata context delete
Si el contexto eliminado está activo, el usuario deberá establecer un nuevo contexto activo. Para ver los contextos disponibles que se pueden establecer o eliminar, use `azdata context list`.
```bash
azdata context delete --namespace -n 
    ```
### Examples
Deletes contextNamespace from the user profile.
```bash
azdata context delete -n contextNamespace
```
### <a name="required-parameters"></a>Parámetros obligatorios
#### `--namespace -n`
Espacio de nombres del contexto que quiere eliminar.
### <a name="global-arguments"></a>Argumentos globales
#### `--debug`
Aumente el nivel de detalle de registro para mostrar todos los registros de depuración.
#### `--help -h`
Muestre este mensaje de ayuda y salga.
#### `--output -o`
Formato de salida.  Valores permitidos: json, jsonc, table y tsv.  Valor predeterminado: json.
#### `--query -q`
Cadena de consulta de JMESPath. Para obtener más información y ejemplos, vea [http://jmespath.org/](http://jmespath.org/).
#### `--verbose`
Aumente el nivel de detalle de registro. Use --debug para obtener registros de depuración completos.
## <a name="azdata-context-set"></a>azdata context set
Para ver los contextos disponibles que se pueden establecer, use `azdata context list`. Si no aparece ningún contexto, debe iniciar sesión para crear un contexto en su perfil de usuario con `azdata login`. La entidad donde inicie sesión se convertirá en el contexto activo. Si inicia sesión en varias entidades, puede cambiar entre contextos activos con este comando. Para ver el contexto activo actualmente, use `azdata context list --active`.
```bash
azdata context set --namespace -n 
 ```
### <a name="examples"></a>Ejemplos
Establece contextNamespace como contexto activo en el perfil de usuario.
```bash
azdata context set -n contextNamespace
```
### <a name="required-parameters"></a>Parámetros obligatorios
#### `--namespace -n`
Espacio de nombres del contexto que quiere establecer.
### <a name="global-arguments"></a>Argumentos globales
#### `--debug`
Aumente el nivel de detalle de registro para mostrar todos los registros de depuración.
#### `--help -h`
Muestre este mensaje de ayuda y salga.
#### `--output -o`
Formato de salida.  Valores permitidos: json, jsonc, table y tsv.  Valor predeterminado: json.
#### `--query -q`
Cadena de consulta de JMESPath. Para obtener más información y ejemplos, vea [http://jmespath.org/](http://jmespath.org/).
#### `--verbose`
Aumente el nivel de detalle de registro. Use --debug para obtener registros de depuración completos.

## <a name="next-steps"></a>Pasos siguientes

Para obtener más información sobre otros comandos de `azdata`, vea [Referencia de azdata](reference-azdata.md). Para obtener más información sobre cómo instalar la herramienta `azdata`, vea [Instalación de azdata para administrar clústeres de macrodatos de SQL Server 2019](deploy-install-azdata.md).
