---
title: Activos prestados
description: En este tema se describe cómo registrar activos prestados en la Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 355e3d3e0e952db14a03810145528f9701804ca2
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5022341"
---
# <a name="asset-loans"></a>Activos prestados

[!include [banner](../../includes/banner.md)]

 

Si su empresa recibe activos para trabajos de reparación o de mantenimiento de ubicaciones internas o de clientes, y si presta temporalmente activos a dichas ubicaciones o clientes, Administración de activos puede hacer un seguimiento de los activos prestados.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Registrar activos prestados en una solicitud de mantenimiento

1. Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.
2. Seleccione la solicitud de mantenimiento en la que desea registrar un activo prestado y, a continuación, seleccione **Editar**.
3. En la página **Solicitud**, seleccione **Enviar activo prestado**.
4. Seleccione el activo y especifique la fecha de devolución prevista.
5. Seleccione **Aceptar**.

> [!NOTE]
> - Solo puede enviar un activo prestado si está disponible un activo del mismo tipo.
> - El activo que preste debe tener una estado de ciclo de vida de activo que permita su uso como un activo prestado, como **InStorage**. Cuando se registra el activo prestado, el estado de ciclo de vida del activo se actualiza automáticamente **OnLoan**, por ejemplo.

Para ver una lista de todos los activos que ha prestado a otras ubicaciones o clientes, seleccione **Administración de activos** \> **Común** \> **Activo prestado** \> **Todos los activos prestados**. Si la casilla **Finalizado** está activada para un activo, significa que se ha registrado el activo como devuelto a su empresa.

![Administrar solicitudes de mantenimiento](media/06-manage-maintenance-requests.png)

En la página **Activos prestados activos** puede ver una lista de todos los activos prestados que aún no se han devuelto a su empresa.

## <a name="register-loan-assets-as-returned"></a>Registrar activos prestados como devueltos

1. Seleccione **Administración de activos** \> **Común** \> **Activo prestado** \> **Activos prestados activos**.
2. Seleccione el activo prestado que desea registrar como devuelto y, a continuación, seleccione **Devolver activo prestado**.
3. En el campo **Devuelto**, especifique la fecha y la hora.
4. Seleccione **Aceptar**.
5. Actualice la página de la lista **Activos prestados activos** y compruebe que el activo prestado ya no aparece en la lista.
