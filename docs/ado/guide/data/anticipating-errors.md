---
title: Previsión de errores | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- anticipating errors [ADO]
- errors [ADO], preventing
- preventing errors [ADO]
ms.assetid: ea1d4a97-58c3-476b-a496-cc80db2a90d5
author: rothja
ms.author: jroth
ms.openlocfilehash: f28a6dc9d79ba59229609cbde94642e31274b9eb
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2020
ms.locfileid: "82761261"
---
# <a name="anticipating-errors"></a>Anticipación de errores
La prevención de errores es al menos tan importante como el control de errores. Esta sección final contiene una breve lista de las precauciones que puede llevar a cabo la aplicación para ayudar a que se produzcan errores menos probables.  
  
 Compruebe el estado de los objetos comprobando el valor de la propiedad **State** antes de intentar realizar una operación con esos objetos. Por ejemplo, si la aplicación utiliza una **conexión**global, compruebe su propiedad **Estado** para ver si ya está abierta antes de llamar al método **Open** .  
  
-   Cualquier programa que acepte datos de un usuario debe incluir código para validar los datos antes de enviarlos al almacén de datos. No se puede confiar en el almacén de datos, en el proveedor, en ADO o incluso en el lenguaje de programación para notificarle de problemas. Debe comprobar todos los bytes especificados por los usuarios, asegurándose de que los datos son del tipo correcto para su campo y de que los campos obligatorios no están vacíos.  
  
 Compruebe los datos antes de intentar escribir datos en el almacén de datos. La forma más fácil de hacerlo es controlar el evento **WillMove** o el evento **WillUpdateRecordset** . Para obtener una explicación más completa del control de eventos de ADO, vea [controlar eventos de ADO](../../../ado/guide/data/handling-ado-events.md).  
  
 Asegúrese de que los objetos de **conjunto de registros** no superan los límites del **conjunto de registros** antes de intentar desplace el puntero de registro. Si intenta **MoveNext** cuando **EOF** es true o **MovePrev** cuando **BOF** es true, se producirá un error. Si realiza cualquiera de los métodos **Move** cuando **EOF** y **BOF** son true, se generará un error.  
  
 También se producirán errores si intenta realizar **operaciones como buscar y** **Buscar** en un **conjunto de registros**vacío.
