---
title: Módulo de tarjeta de regalo
description: En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 70047376cec44523cc9cfe4df792bde23c776d8c
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261589"
---
# <a name="gift-card-module"></a>Módulo de tarjeta de regalo

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de tarjeta regalo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Las tarjetas de regalo son una forma común de pago y el módulo de tarjeta de regalo se puede usar en un módulo de pago para aceptar tarjetas de regalo. El módulo de tarjeta de regalo admite tarjetas de regalo Dynamics 365, SVS y Givex. Las tarjetas de regalo SVS y Givex se canjean a través del proveedor de pagos Adyen.

Para obtener más información sobre la compatibilidad con tarjetas de regalo externas como SVS y Givex, consulte [Soporte para tarjetas de regalo externas](./dev-itpro/gift-card.md)

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

## <a name="add-a-gift-card-module-to-a-page"></a>Agregar un módulo de tarjeta regalo a una página

Para obtener instrucciones sobre cómo agregar un módulo de tarjeta de regalo a una página de pago y configurar las propiedades requeridas, consulte [Módulo de pago](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Compatibilidad para tarjetas de regalo externas](./dev-itpro/gift-card.md)