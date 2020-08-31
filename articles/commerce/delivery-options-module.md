---
title: Módulo de opciones de entrega
description: En este tema se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 60449e9492c8e831b4ec6b2896f1ab471ef9d499
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661224"
---
# <a name="delivery-options-module"></a>Módulo de opciones de entrega

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

En este tema se tratan los módulos de opciones de entrega y se explica cómo configurarlos en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Los módulos de opciones de entrega permiten a los clientes seleccionar un modo de entrega, como envío o recogida, para su pedido en línea. Se requiere una dirección de envío para determinar el modo de entrega. Si cambia la dirección de envío, las opciones de entrega se deben recuperar de nuevo. Si el pedido solo incluye artículos que se recogerán en una tienda, este módulo se oculta automáticamente.

Para obtener información sobre cómo configurar los modos de entrega, consulte [Configuración de canales en línea](channel-setup-online.md) y [Configurar modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Cada modo de entrega puede tener un cargo asociado. Para obtener más información sobre cómo configurar cargos para una tienda en línea, consulte [Cargos automáticos avanzados omnicanal](omni-auto-charges.md).

En la versión 10.0.13 de Commerce, el módulo de opciones de entrega se ha actualizado para admitir las características **Cargos de encabezado sin prorrateo** y **Envío como cargo de línea**. Si el prorrateo está desactivado, se espera que el flujo de trabajo de comercio electrónico no permita un modo mixto de entrega para los artículos del carro (es decir, algunos artículos se seleccionan para envío, pero otros se seleccionan para recogida). La característica **Cargos de encabezado sin prorrateo** requiere que se active la marca **Habilitar modo de entrega coherente en el canal** en la sede de Commerce. Cuando esa marca está activada, los cargos de envío se aplicarán en el nivel de encabezado o en el nivel de línea, según la configuración de la sede de Commerce.

El tema Fabrikam admite un modo de entrega mixto, en el que algunos artículos se seleccionan para envío y otros se seleccionan para recogida. En este modo, los cargos de envío se prorratearán para todos los artículos seleccionados para el modo de envío. Para que funcione un modo mixto de entrega, primero debe configurar la característica **Cargos de encabezado con prorrateo** en la sede de Commerce. Para obtener más información sobre esta configuración, consulte [Prorratear los cargos de encabezado para que coincidan con las líneas de ventas](pro-rate-charges-matching-lines.md).

Si se aplican cargos de envío a los artículos de línea, se pueden mostrar en la línea del carro para cada artículo. Esta funcionalidad requiere que se active la propiedad **Mostrar los cargos de envío del artículo de línea** tanto para el módulo de carro como para el módulo de finalización de compra. Para obtener más información, consulte [Módulo de carro](add-cart-module.md) y [Módulo de finalización de compra](add-checkout-module.md).

La siguiente ilustración muestra un ejemplo de un módulo de opciones de entrega en una página de finalización de compra.

![Ejemplo de módulo de opciones de entrega en una página de finalización de compra](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Propiedades del módulo de opciones de entrega

| Propiedad | Valores | Descripción |
|----------|--------|-------------|
| Cabecera | Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado opcional para el módulo de opciones de entrega. |
| Nombre de clase CSS personalizado | Texto | Nombre de clase de hojas de estilo en cascada personalizadas (CSS) que se utilizará para representar este módulo, si corresponde. |
| Filtrar opción de modo de entrega | **No filtrar** o **Modos sin envío** | Un valor que especifica si el módulo de opciones de entrega debe filtrar todos los modos de entrega que no son de envío. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Agregar un módulo de opciones de entrega a una página de finalización de compra y establecer las propiedades necesarias

Un módulo de opciones de entrega solo se puede agregar a un módulo de finalización de compra. Para obtener más información sobre cómo configurar el módulo de opciones de entrega y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)

[Configuración de canal en línea](channel-setup-online.md)

[Cargos automáticos avanzados omnicanal](omni-auto-charges.md)

[Prorratear los cargos de encabezado para que coincidan con las líneas de ventas](pro-rate-charges-matching-lines.md)

[Configurar modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
