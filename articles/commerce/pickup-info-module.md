---
title: Módulo de información de recogida
description: En este artículo se trata el modulo de información de recogida y se describe la forma de agregarlo a las páginas de finalización de la compra en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 57633b7a23e581278ec0bc09ea146f5453570c4e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288416"
---
# <a name="pickup-information-module"></a>Módulo de información de recogida

[!include [banner](includes/banner.md)]

En este artículo se trata el modulo de información de recogida y se describe la forma de agregarlo a las páginas de finalización de la compra en Microsoft Dynamics 365 Commerce.

El módulo de información de recogida se puede utilizar en un módulo de finalización del pedido para mostrar la información de recogida de pedidos. Los clientes pueden ver las fechas de recogida disponibles y los intervalos de tiempo, y luego seleccionar una hora adecuada para recoger su pedido. Por ejemplo, un cliente puede elegir recoger un pedido a las 15:00 horas del 21 de marzo en la tienda de San Francisco.

Las franjas horarias de recogida para las tiendas adecuadas deben configurarse en la sede de Commerce. Para obtener más información, vea [Crear y actualizar franjas horarias para la recogida del cliente](dev-itpro/pickup-timeslots.md).

Si se crea un módulo de información de recogida en una página de finalización del pedido, pero no se definen franjas horarias para la tienda seleccionada para la recogida, el módulo mostrará información, pero el usuario no podrá seleccionar ninguna franja horaria. Los intervalos de tiempo son opcionales y no son necesarios para realizar un pedido.

Si se seleccionan varios artículos para recoger en varias tiendas, el módulo de información de recogida permitirá al usuario seleccionar un intervalo de tiempo para cada tienda, siempre que haya franjas horarias disponibles para ello.

> [!NOTE]
> El soporte para franjas horarias y el módulo de información de recogida de la página de finalización del pedido está disponible en Dynamics 365 Commerce, versión 10.0.15 y posteriores.

La siguiente ilustración muestra un ejemplo de selección de franjas horarias a través del módulo de información de recogida en una página de finalización del pedido.

![Ejemplo de módulo de información de la recogida en una página de finalización de compra.](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a>Propiedades del módulo

- **Encabezado**: especifique un encabezado para el módulo.

## <a name="show-time-slot-information-after-an-order-is-placed"></a>Mostrar información sobre la franja horaria después de realizar un pedido

Después de realizar un pedido, la información sobre la franja horaria seleccionada se puede ver en el [módulo de confirmación del pedido](order-confirmation-module.md) y el [módulo de detalles del pedido](account-management.md#order-details-page). Ambos módulos tienen una propiedad **Mostrar información de franja horaria**. Antes de que puedan mostrar la franja horaria seleccionada durante el proceso del pedido, esta propiedad debe establecerse en **True**.

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a>Añadir un módulo de información de recogida para la finalización de compra

Para obtener instrucciones sobre cómo agregar un módulo de información de recogida a una página de finalización de la compra y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).

La siguiente ilustración muestra un ejemplo de una página de finalización de compra de comercio electrónico que incluye franjas horarias para artículos de línea de recogida.

![Ejemplo de una página de finalización de compra de comercio electrónico que incluye franjas horarias para artículos de línea de recogida.](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>Recursos adicionales

[Crear y actualizar franjas horarias para la recogida del cliente](dev-itpro/pickup-timeslots.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de detalles del pedido](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
