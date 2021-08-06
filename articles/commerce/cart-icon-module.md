---
title: Módulo de icono de carro
description: En este tema se trata el modulo de icono de carro y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d9e3850d98e716d1bbea2017f6e8c9d75f19adc9
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638010"
---
# <a name="cart-icon-module"></a>Módulo de icono de carro

[!include [banner](includes/banner.md)]

En este tema se trata el modulo de icono de carro y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

El módulo de icono de carrito representa el carrito en el módulo de encabezado de la página y muestra la cantidad de artículos en el carrito. El módulo del ícono del carrito también muestra un resumen del carrito (también conocido como mini carrito) cuando el ícono del carrito está suspendido. El mini carrito proporciona al usuario un resumen de los artículos en el carrito sin tener que navegar a la página del carrito. Además, también permite al usuario ir directamente a la página de pago si está satisfecho con el resumen. Esto reduce la cantidad de navegaciones de la página y agiliza el pago. 

La siguiente imagen muestra un ejemplo de un módulo de icono de carro que muestra un mini carro en el encabezado Fabrikam.

![Ejemplo de un módulo de icono de carro.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propiedades del módulo

- **Mostrar mini carrito** - Cuando es verdadera, esta propiedad permite que se muestre un resumen del carrito (mini carrito) cuando se pasa el icono del carrito. Esta funcionalidad solo es compatible con los puertos de vista de escritorio.

## <a name="module-properties-in-the-adventure-works-theme"></a>Propiedades del módulo en el tema Adventure Works

En el tema Adventure Works, el módulo de icono de carrito incluye dos ranuras adicionales para el mini carrito. Estas ranuras se incluyen como una extensión de definición de módulo.

- **Promociones de carrito vacío** - Esta ranura tiene un módulo de bloque de contenido. Cuando el carrito está vacío, se muestra el módulo de bloque de contenido especificado. El módulo de bloque de contenido se puede utilizar para promociones, contenido de marketing y enlaces a páginas de categorías, para ayudar a los clientes a continuar su viaje de compras.
- **Contenido promocional** - Este espacio se puede utilizar para mostrar promociones, como "Envío gratuito en pedidos superiores a $100". Los módulos de bloque de contenido, bloque de texto y lista de imágenes se pueden usar en la ranura de contenido promocional.

La siguiente imagen muestra un ejemplo de un módulo de icono de carrito en el tema Adventure Works que muestra contenido promocional en el mini carrito.

![Ejemplo de un módulo de icono de carrito en el tema Adventure Works](./media/AW_minicart.PNG)

> [!IMPORTANT]
> Las ranuras del tema de Adventure Works están disponible a partir del lanzamiento de la versión 10.0.20 de Dynamics 365 Commerce.

## <a name="add-a-cart-icon-module-to-a-page"></a>Agregar un módulo de icono de carrito a una página

Para agregar un módulo de icono de carrito, consulte [Módulo de encabezado](author-header-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
