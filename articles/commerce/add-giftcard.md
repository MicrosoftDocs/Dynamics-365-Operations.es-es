---
title: Módulo de tarjeta de regalo
description: En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c024cc1b16ca60b2277eba2d7045020c2e67c3a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206304"
---
# <a name="gift-card-module"></a>Módulo de tarjeta de regalo

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los módulos de tarjetas de regalo se pueden usar para en módulos de pago para aceptar tarjetas de pago, un método de pago habitual utilizado en transacciones de comercio electrónico. El módulo de tarjeta de regalo admite tarjetas de regalo Dynamics 365, SVS y Givex. Las tarjetas de regalo SVS y Givex se canjean a través del proveedor de pagos Adyen. Para obtener más información sobre la compatibilidad con tarjetas de regalo externas como SVS y Givex, consulte [Soporte para tarjetas de regalo externas](./dev-itpro/gift-card.md).

> [!NOTE]
> El soporte para canjear tarjetas de regalo SVS y Givex durante el proceso de pago está disponible en Dynamics 365 Commerce 10.0.11. 

Hay dos módulos de tarjetas de regalo disponibles:

- **Tarjeta de regalo**: este módulo se puede utilizar en una página de pago para canjear una tarjeta de regalo como oferta. 
- **Comprobación del saldo de la tarjeta de regalo**: este módulo se puede utilizar en cualquier página para comprobar el saldo de una tarjeta regalo. Este módulo está disponible en Commerce, versión 10.0.14 y posterior.

> [!NOTE]
> La compatibilidad con el módulo de verificación de saldo de la tarjeta de regalo está disponible en Dynamics 365 Commerce 10.0.14.

La siguiente imagen muestra un ejemplo de un módulo de tarjeta regalo en una página de finalización de compra.

![Ejemplo de un módulo de tarjeta regalo](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Propiedades del módulo

- **Mostrar campos adicionales** - Esta propiedad define qué campos se deben mostrar para las tarjetas de regalo además del número de la tarjeta de regalo, que siempre se muestra de forma predeterminada. Por ejemplo, algunas tarjetas de regalo admiten mostrar un número de identificación personal (PIN), y otras admiten mostrar un PIN y una fecha de vencimiento. Alternativamente, esta propiedad podría establecerse en "Ninguno", que solo mostraría el número de la tarjeta de regalo y ningún campo adicional.

Valores admitidos:
-   PIN
-   Fecha de caducidad
-   PIN y fecha de vencimiento 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Configuración del sitio para módulos de tarjetas de regalo

En el creador de sitios de Commerce bajo **Configuraciones del sitio \> Extensiones**, hay una configuración de módulo de tarjeta de regalo llamada **Tipo de tarjeta de regalo compatible**. Esta configuración admite tres valores:
- **Tarjeta de regalo de Dynamics 365** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Dynamics 365. Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.
- **Tarjetas de regalo SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo solo permite canjear tarjetas de regalo de Givex y SVS. Esta configuración se admite para usuarios anónimos y que hayan iniciado sesión en el sitio de comercio electrónico.
- **Tarjetas de regalo Dynamics 365, SVS y Givex** - Cuando se aplica esta configuración, el módulo de tarjeta de regalo permite canjear tarjetas de regalo de Dynamics 365, Givex y SVS. Esta configuración solo se admite para usuarios que hayan iniciado sesión en el sitio de comercio electrónico.

> [!IMPORTANT]
> Estos ajustes están disponibles en Dynamics 365 Commerce 10.0.11 y son necesarios solo si necesita soporte para tarjetas de regalo SVS o Givex. Si está actualizando desde una versión anterior de Dynamics 365 Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones sobre cómo actualizar el archivo appsettings.json, consulte [Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="add-a-gift-card-module-to-a-page"></a>Agregar un módulo de tarjeta regalo a una página

Para obtener instrucciones sobre cómo agregar un módulo de tarjeta de regalo a una página de pago y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Compatibilidad para tarjetas de regalo externas](./dev-itpro/gift-card.md)

[Actualizaciones de SDK y biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]