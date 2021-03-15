---
title: Módulo de icono de carro
description: En este tema se trata el modulo icono de carrito y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 138c256b56593c4fafb20050a97e614fa584597c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4997835"
---
# <a name="cart-icon-module"></a>Módulo de icono de carro

[!include [banner](includes/banner.md)]

En este tema se trata el modulo icono de carrito y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

El módulo de icono de carrito representa el carrito en el módulo de encabezado de la página y muestra la cantidad de artículos en el carrito. El módulo del ícono del carrito también muestra un resumen del carrito (también conocido como mini carrito) cuando el ícono del carrito está suspendido. El mini carrito proporciona al usuario un resumen de los artículos en el carrito sin tener que navegar a la página del carrito. Además, también permite al usuario ir directamente a la página de pago si está satisfecho con el resumen. Esto reduce la cantidad de navegaciones de la página y agiliza el pago. 

> [!NOTE]
> La compatibilidad con el módulo de icono de carro está disponible en Dynamics 365 Commerce 10.0.11.

La siguiente imagen muestra un ejemplo de un módulo de icono de carro que muestra un mini carro en el encabezado Fabrikam.

![Ejemplo de un módulo de icono de carro](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propiedades del módulo

- **Mostrar mini carrito** - Cuando es verdadera, esta propiedad permite que se muestre un resumen del carrito (mini carrito) cuando se pasa el icono del carrito. Esta funcionalidad solo es compatible con los puertos de vista de escritorio.

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