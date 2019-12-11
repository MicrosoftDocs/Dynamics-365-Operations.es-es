---
title: Módulo de finalización de compra
description: En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4b810441fd25d41ee0893b119b4f7d91e7435d21
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697092"
---
# <a name="checkout-module"></a>Módulo de finalización de compra

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.

## <a name="overview"></a>Visión general

Un módulo de finalización de compra es un contenedor especial que hospeda todos los módulos necesarios para crear un pedido. Un módulo de finalización de pago puede incluir módulos que administren la dirección de envío, los métodos de envío, la información de facturación, el resumen de pedidos y otra información relacionada con un pedido de cliente. Presenta un flujo detallado que un cliente usa para introducir toda la información pertinente para realizar una compra.

Un módulo de finalización de compra representa datos a partir del id. del carro. Este id. del carro se guarda como cookie del explorador. Se requiere un id. de carro para representar información en el módulo de finalización de compra, como los artículos del pedido, el importe total y los descuentos.

## <a name="checkout-module-properties"></a>Propiedades del módulo de finalización de compra

Un módulo de finalización de compra hospeda un conjunto de módulos en él. Una propiedad de ancho le permite especificar si los artículos del módulo de finalización de compra deben ajustarse a su ancho o rellenar la pantalla.

Un módulo de finalización de compra tiene varias franjas, como una franja **Información de finalización de la compra**, una franja **Resumen del pedido** y una franja **Realizar pedido**. Cada franja admite un conjunto de módulos que aparecerán en un diseño específico de la página. Por ejemplo, la franja **Información de finalización de compra** contiene todos los módulos que se requieren para desencadenar una finalización de compra, como módulos para la dirección de envío y el método de pago. La franja **Resumen del pedido** muestra un resumen del pedido y admite la acción para realizar el pedido. La franja **Realizar pedido** también admite la acción para realizar el pedido. Los módulos Realizar pedido se pueden definir en dos franjas para optimizar el proceso de realizar pedidos desde varias plataformas.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Módulos que se pueden usar en el módulo de finalización de compra

- **Dirección de envío**: este módulo permite que un cliente agregue o seleccione la dirección de envío para un pedido. Si el cliente ha iniciado sesión, se muestran las direcciones que se guardaron anteriormente para ese cliente. El cliente puede seleccionar a continuación entre esas direcciones. El cliente también puede agregar una dirección nueva. La dirección de envío se usa para todos los artículos del pedido que requieren envío. No se puede personalizar para artículos de línea individuales. Los formatos de dirección de envío se definen para cada país o región, y las reglas específicas de país o región se aplican por este módulo. Aunque este módulo no proporcione la validación de la dirección, la validación de la dirección se puede implementar a través de la personalización. Si el pedido solo incluye artículos que se recogerán en la tienda, este módulo se oculta automáticamente.
- **Opciones de entrega**: este módulo permite a un cliente seleccionar una opción de entrega para un pedido. Las opciones de entrega se basan en la dirección de envío. Si cambia la dirección de envío, las opciones de entrega se deben recuperar de nuevo. Si el pedido solo incluye artículos que se recogerán en la tienda, este módulo se oculta automáticamente.
- **Contenedor de secciones de finalización de compra:** este módulo es un contenedor que puede colocar varios módulos dentro para crear una sección dentro del flujo de finalización de compra. Por ejemplo, puede colocar todos los módulos relacionados con pagos dentro de este contenedor para que aparezcan como una sección. Este módulo solo afecta al diseño del flujo.
- **Tarjeta regalo**: este módulo permite a un cliente pagar por un pedido con una tarjeta regalo. Solo admite tarjetas regalos de Microsoft Dynamics 365 Commerce. Se pueden aplicar una o más tarjetas regalo a un pedido. Si el saldo de la tarjeta regalo no cubre el importe del carro, la tarjeta regalo se puede combinar con otro método de pago. Las tarjetas regalo solo se pueden canjear si el cliente ha iniciado sesión.
- **Puntos de fidelización:** este módulo permite a un cliente pagar por un pedido mediante puntos de fidelización. Ofrece un resumen de puntos disponibles y puntos de caducidad, y permite al cliente seleccionar el número de puntos que se canjearán. Si el cliente no ha iniciado sesión o no es un cliente de fidelización, o si el importe total del carro es 0 (cero), este módulo se oculta automáticamente.
- **Tarjeta de crédito**: este módulo permite a un cliente pagar por un pedido con una tarjeta de crédito. Si el importe total del carro se cubre con puntos de fidelización o una tarjeta regalo, o es 0 (cero), este módulo se oculta automáticamente. La integración de la tarjeta de crédito la proporciona el connector de pagos de Adyen. Para obtener más información acerca de cómo usar este conector, consulte [Conector de pagos de Adyen](https://).
- **Dirección de facturación**: este módulo permite a un cliente proporcionar información de facturación. Adyen procesa esta información, junto con la información de la tarjeta de crédito. Este módulo incluye una opción que permite a los clientes usar su dirección de facturación como la dirección de envío.
- **Información de contacto:** este módulo permite a un cliente agregar o cambiar la información de contacto (dirección de correo electrónico) para un pedido.
- **Realizar pedido:** este módulo permite a un cliente realizar un pedido.
- **Bloque de enriquecimiento de contenido:** este módulo contiene cualquier mensajería controlada por el sistema de gestión de contenidos (CMS). Por ejemplo, es posible que contenga un mensaje que indique “Para problemas con el pedido, póngase en contacto con 1-800-FABRIKAM”. 
- **Resumen del pedido:** este módulo muestra el desglose de costes de un pedido.
- **Elementos de línea de pedido:** este módulo muestra un resumen de los artículos que se incluirán en un pedido.

## <a name="retail-server-interaction"></a>Interacción con Retail Server

La mayor parte de la información de finalización del pago, como la dirección de envío y el método de envío, se almacena en el carro y se procesa como parte del pedido. La única excepción es la información de la tarjeta de crédito. Esta información se procesa directamente mediante el conector de pagos de Adyen. El pago se autoriza pero no se carga.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Agregue un módulo de finalización del pago a una página nueva y establezca las propiedades necesarias.

Para agregar un módulo de finalización del pago a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Fragmento \> Nuevo fragmento** y asigne al nuevo fragmento el nombre **Fragmento de finalización de compra**.
1. Agregue un módulo de finalización de compra al fragmento.
1. Agregue un encabezado al módulo de finalización de compra.
1. En la franja **Información de la finalización de compra**, agregue la dirección de envío, las opciones de entrega, el contenedor de la sección de finalización de compra y los módulos de información de contacto. Debe haber ahora cuatro secciones en la franja **Información de finalización de compra**.
1. En el módulo de contenedor de la sección de finalización de compra, agregue los módulos de la tarjeta regalo, los puntos de fidelización y la tarjeta de crédito. De esta manera, asegúrese de que todos los métodos de pago aparecen juntos en una sección.
1. En la franja **Resumen del pedido**, agregue los módulos de resumen del pedido, realizar pedido y bloque de enriquecimiento de contenido.
1. En el módulo del bloque de enriquecimiento de contenido, agregue el texto siguiente: **Para preguntas sobre el pedido, póngase en contacto con 1-800-FABRIKAM.**
1. En la franja **Realizar pedido**, agregue un módulo de realizar pedido.
1. Seleccione **Guardar**. Es posible que algunos módulos no se representen en la vista previa, porque no tienen un contexto de carro.
1. Proteja el fragmento y publíquelo.
1. Cree una plantilla que use el nuevo fragmento de finalización de compra.
1. Cree una página de finalización de compra que use la nueva plantilla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
