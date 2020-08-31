---
title: Módulo de dirección de envío
description: En este tema se trata el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 380d268ec0ba64367f090c31408eac1c54d0ff17
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661450"
---
# <a name="shipping-address-module"></a>Módulo de dirección de envío

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

En este tema se describe el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

El módulo de dirección de envío permite a los clientes agregar o seleccionar la dirección de envío para un pedido durante el flujo de finalización de compra. Si un cliente inicia sesión, se muestran las direcciones que se guardaron anteriormente para ese cliente, de forma que las pueda seleccionar. El cliente también puede agregar una dirección nueva. El módulo de dirección de envío se usa para todos los artículos de un pedido que requieren envío.

Los formatos de dirección de envío se pueden definir en la sede de Commerce para cada país o región, y el módulo de dirección de envío aplica las reglas específicas del país o la región.

Cuando los clientes especifican una dirección de envío durante el proceso de finalización de compra, tienen la opción de guardar la dirección como una dirección principal. Esta opción solo se muestra si un cliente ha iniciado sesión.

Aunque el módulo de dirección de envío no proporcione la validación de la dirección, esta funcionalidad se puede implementar a través de la personalización.

La siguiente ilustración muestra un ejemplo de un nuevo módulo de dirección de envío en una página de finalización de compra.

![Ejemplo de módulo de dirección de envío en una página de finalización de compra](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Propiedades del módulo

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera | Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado opcional para el módulo de dirección de envío. |
| Mostrar tipo de dirección | **Verdadero** o **Falso** | Si esta propiedad opcional se establece en **Verdadero**, se mostrará un tipo de dirección, como **Domicilio** o **Empresa**. Si no se especifica ningún tipo de dirección, la dirección se guardará automáticamente como de **Tipo**=**Otro**. |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Agregar un módulo de dirección de envío a una página de finalización de compra y establecer las propiedades necesarias

Un módulo de dirección de envío solo se puede agregar a un módulo de finalización de compra. Para obtener más información sobre cómo configurar el módulo de dirección de envío y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)
