---
title: Activos prestados
description: En este artículo se describe cómo registrar activos prestados en la Administración de activos.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectLoanSend, EntAssetObjectLoanListPage, EntAssetObjectLoanReturn, EntAssetObjectLoanInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f70b29ef69b80160f108e6f53edda12b86c2c9db
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015765"
---
# <a name="asset-loans"></a>Activos prestados

[!include [banner](../../includes/banner.md)]

 

Si su empresa recibe activos para trabajos de reparación o de mantenimiento de ubicaciones internas o de clientes, y si presta temporalmente activos a dichas ubicaciones o clientes, Administración de activos puede hacer un seguimiento de los activos prestados.

## <a name="register-asset-loans-on-a-maintenance-request"></a>Registrar activos prestados en una solicitud de mantenimiento

1. Seleccione **Administración de activos** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.
2. Seleccione la solicitud de mantenimiento en la que desea registrar un activo prestado y, a continuación, seleccione **Editar**.
3. En la página **Solicitud**, seleccione **Enviar activo prestado**.
4. Seleccione el activo y especifique la fecha de devolución prevista.
5. Seleccione **Aceptar**.

> [!NOTE]
> - Solo puede enviar un activo prestado si está disponible un activo del mismo tipo.
> - El activo que preste debe tener una estado de ciclo de vida de activo que permita su uso como un activo prestado, como **InStorage**. Cuando se registra el activo prestado, el estado de ciclo de vida del activo se actualiza automáticamente **OnLoan**, por ejemplo.

Para ver una lista de todos los activos que ha prestado a otras ubicaciones o clientes, seleccione **Administración de activos** \> **Activo prestado** \> **Todos los activos prestados**. Si la casilla **Finalizado** está activada para un activo, significa que se ha registrado el activo como devuelto a su empresa.

![Administrar solicitudes de mantenimiento.](media/06-manage-maintenance-requests.png)

En la página **Activos prestados activos** puede ver una lista de todos los activos prestados que aún no se han devuelto a su empresa.

## <a name="register-loan-assets-as-returned"></a>Registrar activos prestados como devueltos

1. Seleccione **Administración de activos** \> **Activo prestado** \> **Activos prestados activos**.
2. Seleccione el activo prestado que desea registrar como devuelto y, a continuación, seleccione **Devolver activo prestado**.
3. En el campo **Devuelto**, especifique la fecha y la hora.
4. Seleccione **Aceptar**.
5. Actualice la página de la lista **Activos prestados activos** y compruebe que el activo prestado ya no aparece en la lista.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]