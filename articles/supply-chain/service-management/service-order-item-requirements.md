---
title: Requisitos de artículos de pedido de servicio
description: Este artículo describe los requisitos de los artículos de la orden de servicio.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProjSalesItemReq
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 376cda6bbe1800611e6f24c347b9035469a30a14
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2022
ms.locfileid: "9015183"
---
# <a name="service-order-item-requirements"></a>Requisitos de artículos de pedido de servicio

[!include [banner](../includes/banner.md)]

Puede crear un pedido de servicio para administrar y realizar un seguimiento de los servicios que proporciona a sus clientes. Si necesita reservar artículos específicos para un pedido de servicio, puede crear requisitos de artículo de inventario para él. Un requisito de artículo se puede usar inmediatamente del inventario o bien, puede iniciar un pedido de producción para el artículo.

Si usa un requisito de artículo en lugar de una transacción de artículos, podrá planificar la entrega justo antes del uso real del artículo, crear un pedido de compras, incluir el artículo en el marco del acuerdo comercial e incluir el requisito de artículo en la planificación de producción.

Los requisitos de artículo para los pedidos de servicio se procesan a través de un proyecto. Para crear un requisito de artículo en un pedido de servicio, este último debe estar vinculado a un proyecto.

Cuando se crea un requisito de artículo para un pedido de servicio, se podrá ver inmediatamente en la sección **Proyecto** del pedido de servicio individual, o bien a través del formulario **Pedido de ventas**.

## <a name="view-an-item-requirement-from-a-service-order"></a>Ver un requisito de artículo desde un pedido de servicio

1. Vaya a **Gestión de servicio** \> **Pedidos de servicio** \> **Pedidos de servicio**.
1. Seleccione **Distribución** y, a continuación, seleccione **Requisito de artículo** para abrir el formulario **Requisitos de artículo** .
1. Seleccione la ficha **Proyecto** y compruebe el campo **Pedido de servicio** para ver los pedidos de servicio de los requisitos de artículo.

## <a name="delete-service-orders-with-item-requirements"></a>Eliminar pedidos de servicio con requisitos de artículo

Si un requisito de artículo se crea en un pedido de servicio, este último no se podrá eliminar. Deberá eliminar primero el requisito de artículo para poder eliminar el pedido de servicio.

1. Vaya a **Gestión de servicio** \> **Pedidos de servicio** \> **Pedidos de servicio**.
1. Seleccione **Distribución** y, a continuación, seleccione **Requisito de artículo** para abrir el formulario **Requisitos de artículo** . En este formulario se enumeran los requisitos de artículo creados en el pedido de servicio.
1. Seleccione el requisito de artículo que desea eliminar y seleccione **Eliminar**.

O bien

1. Vaya a **Gestión de proyectos y contabilidad** \> **Proyectos** \> **Todos los proyectos**.
1. Abra el proyecto con el pedido de servicio en el que se creó un requisito de artículo.
1. En el formulario **Proyectos**, en el panel derecho del formulario , seleccione **Requisitos de artículo**. Se abrirá el formulario **Requisitos de artículo**, en el que se enumeran los requisitos de artículo asociados con el proyecto seleccionado.
1. Seleccione el requisito de artículo que desea eliminar y seleccione **Eliminar**.

## <a name="see-also"></a>Consulte también

[Requisitos de artículo (formulario)](https://technet.microsoft.com/library/aa552021\(v=ax.60\))



[!INCLUDE[footer-include](../../includes/footer-banner.md)]