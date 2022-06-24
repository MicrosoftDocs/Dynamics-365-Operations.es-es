---
title: Pedidos de servicio
description: Este artículo proporciona información sobre cómo trabajar con pedidos de servicio.
author: sorenva
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 606a1e3df72f8a76dab477bb1dd961b6df16f3cf
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882384"
---
# <a name="service-orders"></a>Pedidos de servicio

[!include [banner](../includes/banner.md)]

Un pedido de servicio representa una visita realizada por un técnico de servicio al sitio del cliente en una fecha concreta. Cada pedido de servicio consta de una o más líneas de pedido de servicio. Las líneas de pedido de servicio representan las horas de trabajo que debe llevar a cabo el técnico de servicio, así como la relación de artículos, gastos y cuotas.

Se pueden vincular tareas y objetos a una línea de pedido de servicio. A continuación, podrá agrupar las líneas de pedido de servicios por tareas o por objetos. También puede vincular los artículos que se incluyen en el inventario a las líneas de pedido de servicio.

## <a name="create-service-orders"></a>Creación de pedidos de servicio

Puede crear pedidos de servicio en base a un acuerdo de servicio y a las líneas contenidas en éste. Sin embargo, solo puede crear pedidos de servicio asociados a un acuerdo de servicio durante el período especificado en el contrato. Por ejemplo, si un acuerdo de servicio tiene validez durante el año 2011, puede crear pedidos de servicio para dicho acuerdo del 1 de enero al 31 de diciembre de 2011.

También puede crear pedidos de servicio de forma individual, sin asociarlos a un acuerdo de servicio. Estos pedidos de servicio se pueden usar para gestionar visitas imprevistas o aisladas. Por ejemplo, en el mes de marzo su cliente desea que se realice un servicio en dos de sus equipos, aparte de los ya especificados en el acuerdo de servicio. Para esta tarea, cree pedidos de servicio, aunque sin asociarlos a un acuerdo.


> [!NOTE]
> Para crear pedidos de servicio que no estén asociadas a un acuerdo de servicio, debe activar la casilla **Permitir sin acuerdo de servicio** en la página **Parámetros de la gestión de servicio**.

### <a name="scenario"></a>Situación

El siguiente ejemplo describe otra situación en la que resulta útil crear un pedido de servicio que no esté asociado a un acuerdo de servicio.

El distribuidor de la empresa recibe una solicitud de servicio de emergencia para resolver un problema relacionado con un ascensor. No hay tiempo para configurar un acuerdo ni un proyecto para el servicio. Por lo tanto, el distribuidor crea un pedido de servicio directamente en la página **Pedidos de servicio**, vincula el pedido de servicio a un proyecto existente y crea las líneas de pedido de servicio. El distribuidor también crea una relación de tareas u objetos para un pedido de servicio existente con el fin de registrar el trabajo que no está relacionado con el acuerdo de servicio. Para obtener más información, vea [Crear pedidos de servicio manualmente](create-service-orders-manually.md) y [Crear relaciones de tareas de servicio](create-service-task-relations.md).

## <a name="monitor-the-progress-of-service-orders"></a>Supervisión del progreso de los pedido de servicio

Para supervisar el progreso de un pedido de ventas a través de los diferentes equipos y procesos de trabajo, puede configurar un sistema de etapas y códigos de motivos para los pedidos de servicio. Puede especificar las acciones habilitadas para cada etapa. Para obtener más información acerca de códigos de motivo, vea [Crear códigos de motivo](create-reason-codes.md).

### <a name="example"></a>Ejemplo

Es el distribuidor quien aprueba un pedido de servicio. El distribuidor actualiza la etapa del pedido de servicio y especifica un código de motivo que indique que el pedido se ha comunicado al técnico del servicio. El técnico va al sitio del cliente y realiza el pedido.

## <a name="specify-item-requirements-for-service-orders"></a>Especificar requisitos de artículo para pedidos de servicio

Puede especificar los artículos del inventario que son necesarios para los pedidos de servicio. Sin embargo, el pedido de servicio se debe asociar a un proyecto. Los requisitos de artículo para los pedidos de servicio se procesan a través de un proyecto. 

### <a name="example"></a>Ejemplo

Los pedidos de servicio creados a partir del acuerdo de servicio los procesa el distribuidor. En el primer pedido de servicio, el distribuidor se da cuenta de que el técnico necesita una pieza de repuesto importante que no está disponible en el inventario. Por lo tanto, el distribuidor crea un requisito de artículo para la pieza de repuesto directamente desde el pedido de servicio.

## <a name="move-and-post-lines"></a>Mover y registrar líneas

Un técnico de servicio regresa de una visita y, a continuación, modifica y actualiza las líneas del pedido de servicio. Durante la visita, el técnico realizó un trabajo de servicio programado para la siguiente visita. Por lo tanto, el técnico debe mover las líneas de la siguiente visita de servicio a la actual. Después, registra el pedido de servicio. Para obtener más información, vea [Mover líneas de pedido de servicio](move-service-order-lines.md).

## <a name="cancel-service-orders"></a>Cancelar pedidos de servicio

Uno de los restantes pedidos de servicio generados para el mes de enero se vuelve obsoleto debido a la cancelación de dicho trabajo. Por lo tanto, el distribuidor de servicio cancela el pedido. Para obtener más información, vea [Cancelar pedidos de servicio](cancel-service-orders.md).

## <a name="post-from-projects"></a>Registrar desde proyectos

Al final de cada semana, el distribuidor desea registrar todos los pedidos de servicio vinculados a un proyecto concreto. Por lo tanto, el distribuidor ubica el proyecto correspondiente en la página **Proyectos** y registra los pedidos de servicio que se hayan completado. Para obtener más información, vea [Registrar pedidos de servicio (formulario de clase)](https://technet.microsoft.com/library/aa574685\(v=ax.60\)).

## <a name="delete-service-orders"></a>Eliminar pedidos de servicio

Durante la segunda mitad del año, el cliente decide que las visitas se producen con muy poca frecuencia. Debe crear una serie nueva de visitas de servicio más frecuentes para el tiempo restante del acuerdo de servicio. Por lo tanto, debe eliminar los pedidos de servicio existentes y crear otros nuevos. Para obtener más información, vea [Eliminar pedidos de servicio](delete-service-orders.md).

## <a name="see-also"></a>Consulte también

[Pedidos de servicio (formulario)](https://technet.microsoft.com/library/aa554361\(v=ax.60\))

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]