---
title: Crear órdenes de trabajo a partir de solicitudes de mantenimiento
description: En este tema se explica cómo crear una orden de trabajo a partir de una solicitud de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23039306bb827beb861eaacc3177f4917fabc8bf
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018105"
---
# <a name="create-work-orders-from-maintenance-requests"></a>Crear órdenes de trabajo a partir de solicitudes de mantenimiento

[!include [banner](../../includes/banner.md)]

 


Después de crear solicitudes de mantenimiento, puede convertirlas fácilmente en órdenes de trabajo. En este tema se describe la forma más rápida de trabajar con solicitudes de mantenimiento, actualiza varias solicitudes de mantenimiento al mismo tiempo y crear una orden de trabajo para varias solicitudes de mantenimiento a la vez. En **Solicitudes de mantenimiento activas** o en la página **Mis solicitudes de mantenimiento de ubicación técnica** también puede trabajar con una solicitud de mantenimiento a la vez y convertir una solicitud de mantenimiento en una orden de trabajo.

> [!NOTE]
> Cada solicitud de mantenimiento puede relacionarse únicamente con una orden de trabajo. Sin embargo, se pueden incluir varias solicitudes de mantenimiento en una orden de trabajo, aunque las solicitudes de mantenimiento tenga activos diferentes.

1. Seleccione **Administración de activos** \> **Común** \> **Solicitudes de mantenimiento** \> **Todas las solicitudes de mantenimiento**.
2. Antes de poder crear una orden de trabajo a partir de solicitudes de mantenimiento, debe seleccionar como mínimo un tipo de trabajo de mantenimiento para las solicitudes de mantenimiento, así como una variante y un comercio del tipo de trabajo de mantenimiento, si esta información es pertinente. En la vista de cuadrícula puede actualizar fácilmente la información de una solicitud de mantenimiento.
3. Cuando esté listo para crear una orden de trabajo, seleccione las solicitudes de mantenimiento que desea incluir en ella.

    - Si selecciona varias solicitudes de mantenimiento para convertirlas en una orden de trabajo, debe establecer los campos **Activo** y **Tipo de trabajo de mantenimiento** antes de crear la orden de trabajo.
    - Si selecciona una solicitud de mantenimiento para convertirla en una orden de trabajo, solo hay que establecer el campo **Activo** antes de crear la orden de trabajo. Sin embargo, al crear la orden de trabajo, puede seleccionar un tipo de trabajo de mantenimiento (así como una variante y un oficio relacionados con el tipo de trabajo de mantenimiento, si esta información es pertinente) en el cuadro de diálogo **Crear orden de trabajo**.

4. Seleccione **Orden de trabajo**.
5. En el cuadro de diálogo **Crear orden de trabajo**, establezca los valores de los campos y, a continuación, seleccione **Aceptar**.

    Una barra de mensajes le notificará cuando se haya creado un nueva orden de trabajo.

    Además, al crear una orden de trabajo basada en una solicitud de mantenimiento, si el activo relacionado con la solicitud de mantenimiento se incluye en un acuerdo de garantía, una barra de mensajes le notificará el acuerdo de garantía.

6. Seleccione **Administración de activos** \> **Común** \> **Órdenes de trabajo** \> **Todas las órdenes de trabajo**, y abra la nueva orden de trabajo.

    ![Abrir nueva orden de trabajo](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]