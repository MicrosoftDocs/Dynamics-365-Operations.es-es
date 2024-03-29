---
title: Activos de entrada y de salida
description: En este artículo se explica cómo registrar activos de entrada y salida en Administración de activos.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: fd7482cfe943347840e9fb070151d66fbe5ef9ca
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016547"
---
# <a name="inbound-and-outbound-assets"></a>Activos de entrada y de salida

[!include [banner](../../includes/banner.md)]

 

Si la empresa emite trabajos de reparación o trabajos de mantenimiento en los activos que se reciben de otras ubicaciones o clientes, Administración de activos puede realizar un seguimiento de los activos de entrada que se encuentran de camino a la empresa y los activos de salida que se van a devolver.

> [!NOTE]
> Si desea usar los estados de ciclo de vida de entrada y salida para gestionar los activos que llegan y salen, debe configurar los estados y modelos de ciclo de vida de la solicitud de mantenimiento para que admitan estas acciones. Para obtener más información, consulte [Solicitudes de mantenimiento](/d365F-O/supply-chain/asset-management/manage-maintenance-requests/../manage-maintenance-requests/maintenance-request-overview).

La configuración de Administración de activos determina si puede trabajar con activos de entrada y de salida.

## <a name="register-assets-as-inbound"></a>Registrar activos como de entrada

1. Seleccione **Administración de activos** \> **Solicitudes de mantenimiento** \> **Solicitudes de mantenimiento activas**.
2. Seleccione la solicitud de mantenimiento.
3. Seleccione **Actualizar estado de solicitud de mantenimiento**.
4. Seleccione **Entrante** (u otro estado de ciclo de vida que haya creado para los activos de entrada) y, a continuación, seleccione **Aceptar**.

![Registrar activos como de entrada.](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a>Registrar los activos entrantes como recibidos

1. Seleccione **Administración de activos** \> **Entrante/saliente** \> **Activos entrantes**.
2. Seleccione el activo o la solicitud de mantenimiento.
3. Seleccione **Recibir activos**.
4. En el campo **Recibido**, especifique la fecha y la hora. A continuación seleccione **Aceptar**. El registro se eliminará de la página de lista **Activos de entrada**.

![Registrar los activos entrantes como recibidos.](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a>Registrar activos como de salida

Cuando haya completado el mantenimiento o el trabajo de reparación, puede registrar el activo como devuelto.

1. Seleccione **Administración de activos** \> **Solicitudes de mantenimiento** \> **Solicitudes de mantenimiento activas**.
2. Seleccione la solicitud de mantenimiento.
3. Seleccione **Actualizar estado de solicitud de mantenimiento**.
4. Seleccione **Saliente** (u otro estado de ciclo de vida que haya creado para los activos de salida) y, a continuación, seleccione **Aceptar**.

## <a name="register-outbound-assets-as-delivered"></a>Registrar activos de salida como entregados

1. Seleccione **Administración de activos** \> **Entrante/saliente** \> **Activos salientes**.
2. Seleccione el activo o la solicitud de mantenimiento.
3. Seleccione **Entregar activos**.
4. En el campo **Entregado**, especifique la fecha y la hora. A continuación seleccione **Aceptar**. El registro se eliminará de la página de lista **Activos de salida**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]