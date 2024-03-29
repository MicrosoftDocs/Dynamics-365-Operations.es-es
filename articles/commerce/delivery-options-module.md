---
title: Módulo de opciones de entrega
description: En este artículo se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: c3fb60c61878fc790a44178fabc8a7be5809806b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268457"
---
# <a name="delivery-options-module"></a>Módulo de opciones de entrega

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.

Los módulos de opciones de entrega permiten a los clientes seleccionar un modo de entrega, como envío o recogida, para su pedido en línea. Se requiere una dirección de envío para determinar el modo de entrega. Si cambia la dirección de envío, las opciones de entrega se deben recuperar de nuevo. Si el pedido solo incluye artículos que se recogerán en una tienda, este módulo se oculta automáticamente.

Para obtener información sobre cómo configurar los modos de entrega, consulte [Configuración de canales en línea](channel-setup-online.md) y [Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Cada modo de entrega puede tener un cargo asociado. Para obtener más información sobre cómo configurar cargos para una tienda en línea, consulte [Cargos automáticos avanzados omnicanal](omni-auto-charges.md).

En la versión 10.0.13 de Commerce, el módulo de opciones de entrega se ha actualizado para admitir las características **Cargos de encabezado sin prorrateo** y **Envío como cargo de línea**. Si el prorrateo está desactivado, se espera que el flujo de trabajo de comercio electrónico no permita un modo mixto de entrega para los artículos del carro (es decir, algunos artículos se seleccionan para envío, pero otros se seleccionan para recogida). La característica **Cargos de encabezado sin prorrateo** requiere que se active la marca **Habilitar modo de entrega coherente en el canal** en la sede de Commerce. Cuando la marca de característica está activada, los cargos de envío se aplicarán en el nivel de encabezado o en el nivel de línea, según la configuración de la sede de Commerce.

El tema Fabrikam admite un modo de entrega mixto, en el que algunos artículos se seleccionan para envío y otros se seleccionan para recogida. En este modo, los cargos de envío se prorratearán para todos los artículos seleccionados para el modo de envío. Para que funcione un modo mixto de entrega, primero debe configurar la característica **Cargos de encabezado con prorrateo** en la sede de Commerce. Para obtener más información sobre esta configuración, consulte [Prorratear los cargos de encabezado para que coincidan con las líneas de ventas](pro-rate-charges-matching-lines.md).

Si se aplican cargos de envío a los artículos de línea, se pueden mostrar en la línea del carro para cada artículo. Esta funcionalidad requiere que se active la propiedad **Mostrar los cargos de envío del artículo de línea** tanto para el módulo de carro como para el módulo de finalización de compra. Para obtener más información, consulte [Módulo de carro](add-cart-module.md) y [Módulo de finalización de compra](add-checkout-module.md).

La siguiente ilustración muestra un ejemplo de un módulo de opciones de entrega en una página de finalización de compra.

![Ejemplo de módulo de opciones de entrega en una página de finalización de compra.](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Propiedades del módulo de opciones de entrega

| Propiedad | Valores | Descripción |
|----------|--------|-------------|
| Cabecera | Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado opcional para el módulo de opciones de entrega. |
| Nombre de clase CSS personalizado | Texto | Nombre de clase de hojas de estilo en cascada personalizadas (CSS) que se utilizará para representar este módulo, si corresponde. |
| Filtrar opción de modo de entrega | **No filtrar** o **Modos sin envío** | Un valor que especifica si el módulo de opciones de entrega debe filtrar todos los modos de entrega que no son de envío. |
| Seleccionar automáticamente una opción de entrega | **No filtrar**, **Seleccionar automáticamente la opción de entrega y mostrar el resumen** o **Seleccionar automáticamente la opción de entrega y no mostrar el resumen** | Esta propiedad aplica automáticamente la primera opción de entrega disponible a la finalización de la compra, sin necesidad de que el usuario la seleccione. Debe usarse solo si hay una opción de entrega disponible. Esta propiedad se admite desde la versión 10.0.19 de Commerce. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Agregar un módulo de opciones de entrega a una página de finalización de compra y establecer las propiedades necesarias

Un módulo de opciones de entrega solo se puede agregar a un módulo de finalización de compra. Para obtener más información sobre cómo configurar el módulo de opciones de entrega y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).

> [!NOTE]
> Es posible que experimente un control de entrega incoherente o que no vea cargos de nivel de encabezado no prorrateados en su canal de comercio electrónico. Para obtener instrucciones sobre cómo solucionar estos problemas, consulte [Habilitar el control del modo de entrega coherente en canales de comercio electrónico](consistent-delivery-mode-handling.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)

[Configuración de canal en línea](channel-setup-online.md)

[Cargos automáticos avanzados omnicanal](omni-auto-charges.md)

[Prorratear los cargos de encabezado para que coincidan con las líneas de ventas](pro-rate-charges-matching-lines.md)

[Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
