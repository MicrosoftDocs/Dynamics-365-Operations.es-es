---
title: Ver, administrar y aprobar pedidos planificados
description: Este tema proporciona información sobre cómo ver, administrar y aprobar pedidos planificados en Optimización de planificación.
author: t-benebo
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b8c17ab3934ec7bfaed710c33515243290bb8e2a
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8468788"
---
# <a name="view-manage-and-approve-planned-orders"></a>Ver, administrar y aprobar pedidos planificados

[!include [banner](../../includes/banner.md)]

Este tema proporciona información sobre cómo ver, administrar y aprobar pedidos planificados en Optimización de planificación.

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a>Ver y administrar pedidos planificados

Puede ver y administrar los pedidos planificados en cualquier página de lista de pedidos planificados. Vaya a uno de los siguientes lugares, según el tipo de pedidos planificados con los que desee trabajar:

- Planificacion maestra \> Espacios de trabajo \> Planificacion maestra
- Planificación maestra \> Planificación maestra \> Pedidos planificados
- Vaya a Control de producción \> Pedidos de producción \> Pedidos de producción planificados
- Adquisición y abastecimiento \> Pedidos de compra \> Pedidos de producción planificados
- Gestión del inventario \> Pedidos de entrada \> Transferencias planificadas
- Gestión del inventario \> Pedidos de salida \> Transferencias planificadas

## <a name="view-and-edit-the-status-of-planned-orders"></a>Ver y editar el estado de los pedidos planificados

Puede usar el campo **Estado** de cada orden planificada para ayudar a realizar un seguimiento de su progreso o cambiar la forma en que se procesará una orden planificada. Están disponibles los siguientes valores de **Estado**:

- **No procesado**: cuando la planificación maestra genera pedidos planificados, se les da este estado. Los pedidos planificados que tienen este estado se eliminarán durante la siguiente ejecución de planificación.
- **Terminado**: este estado indica que la orden planificada se ha completado. Si decide no poner en firme un pedido planificado, puede cambiar manualmente su estado a *Finalizado*. Tenga en cuenta que el sistema trata los estados *No procesado* y *Completado* de la misma manera.
- **Aprobado**: este estado indica que la orden planificada está aprobada para confirmación. Si desea consolidar un pedido planificado, puede cambiar su estado a *Aprobado*. Si desea conservar las ediciones que se han realizado en una orden planificada, o si está planeando confirmar una orden planificada, cambie su estado a *Aprobado*. Las órdenes planificadas que tienen un estado de *Aprobado* se consideran suministros fijos y esperados por planificación maestra. Por lo tanto, no se modifican ni se eliminan durante las ejecuciones posteriores de la planificación maestra. Para lograr este comportamiento, la lógica de planificación copia los pedidos planificados con estado *Aprobado* desde la versión anterior del plan a la nueva versión del plan durante la planificación maestra. Tenga en cuenta que los pedidos planificados con estado *Aprobado* solo se consideran un suministro dentro del plan maestro específico.

Para cambiar el estado de una sola orden planificada, [abra cualquier página de lista de pedidos planificados](#view-planned-orders), abra el pedido y luego siga uno de estos pasos:

- En la ficha desplegable **General**, cambie el valor del campo **Estado**.
- En el panel de acciones, en la pestaña **Pedido planificado**, en el grupo **Proceso**, seleccione **Cambiar estado**.
- En el panel de acciones, seleccione **Aprobar** para marcar el pedido como aprobado.

Para cambiar el estado de varias órdenes planificadas al mismo tiempo, [abra cualquier página de lista de pedidos planificados](#view-planned-orders), seleccione la casilla para cada pedido que desee cambiar y luego siga uno de estos pasos:

- En el panel de acciones, en la pestaña **Pedido planificado**, en el grupo **Proceso**, seleccione **Cambiar estado**.
- En el panel de acciones, seleccione **Aprobar** para marcar los pedidos como aprobados.

## <a name="approve-planned-orders"></a>Aprobar pedidos planificados

La aprobación de pedidos planificados es un paso opcional en el proceso de crear un pedido confirmado a partir de un pedido planificado.

La siguiente ilustración muestra cómo puede utilizar el valor **Estado** que se asigna a cada orden planificada para implementar un flujo de trabajo de aprobación. Para implementar un proceso de aprobación, ajuste manualmente el valor **Estado** para cada orden planificada, como se describe en la sección anterior.

![Flujo de pedido planificado.](media/approved-planned-orders-1.png)

> [!TIP]
> Le recomendamos que apruebe cualquier pedido planificado modificado. De lo contrario, las ediciones se ignorarán y se sobrescribirán en la siguiente ejecución de planificación.

## <a name="additional-resources"></a>Recursos adicionales

- [Poner en firme pedidos planificados](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
