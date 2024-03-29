---
title: Módulo de dirección de envío
description: En este artículo se trata el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/11/2021
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
ms.openlocfilehash: 48e6909b4dac9722830a83ec3a63a58876768d7e
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275015"
---
# <a name="shipping-address-module"></a>Módulo de dirección de envío

[!include [banner](includes/banner.md)]

En este artículo se describe el modulo de dirección de envío y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.

El módulo de dirección de envío permite a los clientes agregar o seleccionar la dirección de envío para un pedido durante el flujo de finalización de compra. Si un cliente inicia sesión, se muestran las direcciones que se guardaron anteriormente para ese cliente, de forma que las pueda seleccionar. El cliente también puede agregar una dirección nueva. El módulo de dirección de envío se usa para todos los artículos de un pedido que requieren envío.

Los formatos de dirección de envío se pueden definir en la sede de Commerce para cada país o región, y el módulo de dirección de envío aplica las reglas específicas del país o la región.

Cuando los clientes especifican una dirección de envío durante el proceso de finalización de compra, tienen la opción de guardar la dirección como una dirección principal. Esta opción solo se muestra si un cliente ha iniciado sesión.

Aunque el módulo de dirección de envío no proporcione la validación de la dirección, esta funcionalidad se puede implementar a través de la personalización.

La siguiente ilustración muestra un ejemplo de un nuevo módulo de dirección de envío en una página de finalización de compra.

![Ejemplo de módulo de dirección de envío en una página de finalización de compra.](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Propiedades del módulo

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera | Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado opcional para el módulo de dirección de envío. |
| Mostrar tipo de dirección | **Verdadero** o **Falso** | Si esta propiedad opcional se establece en **Verdadero**, se mostrará un tipo de dirección, como **Domicilio** o **Empresa**. Si no se especifica ningún tipo de dirección, la dirección se guardará automáticamente como de **Tipo**=**Otro**. |
| Habilitar la sugerencia automática| **Verdadero** o **Falso** | Si esta propiedad opcional se establece en **Verdadero**, se proporcionarán sugerencias de direcciones automáticas. Estas sugerencias llevan tecnología de Bing Maps. Para obtener información sobre cómo configurar la integración de Bing Maps para su sitio, consulte [Módulo selector de tienda](store-selector.md). Esta característica está disponible en la versión 10.0.15 de Commerce.|
|Opciones de sugerencias automáticas| Un número| Si las sugerencias de direcciones automáticas están habilitadas, puede especificar opciones adicionales, como el número máximo de sugerencias que se deben proporcionar.|

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Agregar un módulo de dirección de envío a una página de finalización de compra y establecer las propiedades necesarias

Un módulo de dirección de envío solo se puede agregar a un módulo de finalización de compra. Para obtener más información sobre cómo configurar el módulo de dirección de envío y agregarlo a una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)

[Módulo de selector de tienda](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
