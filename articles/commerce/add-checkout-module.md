---
title: Módulo de finalización de compra
description: En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: 3805c0faabc8afc3decffb924b7f25332ff1ab16
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025400"
---
# <a name="checkout-module"></a>Módulo de finalización de compra


[!include [banner](includes/banner.md)]

En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.

## <a name="overview"></a>Visión general

Un módulo de finalización de compra es un contenedor especial que hospeda todos los módulos necesarios para crear un pedido. Presenta un flujo detallado que un cliente usa para introducir toda la información pertinente para realizar una compra. Captura la dirección de envío, el método de envío y la información de facturación. También proporciona un resumen del pedido y otra información relacionada con un pedido del cliente.

Un módulo de finalización de compra representa datos a partir del id. del carro. Este id. del carro se guarda como cookie del explorador. Se requiere un id. de carro para representar información en el módulo de finalización de compra, como los artículos del pedido, el importe total y los descuentos.

## <a name="checkout-module-properties"></a>Propiedades del módulo de finalización de compra

Un módulo de finalización de compra muestra un resumen del pedido y proporciona la funcionalidad necesaria para realizar un pedido. Para reunir toda la información del cliente necesaria para poder realizar un pedido, hay que agregar módulos adicionales al módulo de finalización de compra. Por lo tanto, los minoristas tienen la flexibilidad de agregar módulos personalizados al flujo de finalización de compra, o de excluir módulos, según sus requisitos.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Módulos que se pueden usar en el módulo de finalización de compra

- **Dirección de envío**: este módulo permite que un cliente agregue o seleccione la dirección de envío para un pedido. Si el cliente ha iniciado sesión, se muestran las direcciones que se guardaron anteriormente para ese cliente. El cliente puede seleccionar a continuación entre esas direcciones. El cliente también puede agregar una dirección nueva. La dirección de envío se usa para todos los artículos del pedido que requieren envío. No se puede personalizar para artículos de línea individuales. Los formatos de dirección de envío se definen para cada país o región, y las reglas específicas de país o región se aplican por este módulo. Aunque este módulo no proporcione la validación de la dirección, la validación de la dirección se puede implementar a través de la personalización. Si el pedido solo incluye artículos que se recogerán en la tienda, este módulo se oculta automáticamente.
- **Opciones de entrega**: este módulo permite a un cliente seleccionar una opción de entrega para un pedido. Las opciones de entrega se basan en la dirección de envío. Si cambia la dirección de envío, las opciones de entrega se deben recuperar de nuevo. Si el pedido solo incluye artículos que se recogerán en la tienda, este módulo se oculta automáticamente.
- **Contenedor de secciones de finalización de compra:** este módulo es un contenedor que puede colocar varios módulos dentro para crear una sección dentro del flujo de finalización de compra. Por ejemplo, puede colocar todos los módulos relacionados con pagos dentro de este contenedor para que aparezcan como una sección. Este módulo solo afecta al diseño del flujo.
- **Tarjeta regalo**: este módulo permite a un cliente pagar por un pedido con una tarjeta regalo. Solo admite tarjetas regalos de Microsoft Dynamics 365 Commerce. Se pueden aplicar una o más tarjetas regalo a un pedido. Si el saldo de la tarjeta regalo no cubre el importe del carro, la tarjeta regalo se puede combinar con otro método de pago. Las tarjetas regalo solo se pueden canjear si el cliente ha iniciado sesión.
- **Puntos de fidelización:** este módulo permite a un cliente pagar por un pedido mediante puntos de fidelización. Ofrece un resumen de puntos disponibles y puntos de caducidad, y permite al cliente seleccionar el número de puntos que se canjearán. Si el cliente no ha iniciado sesión o no es un cliente de fidelización, o si el importe total del carro es 0 (cero), este módulo se oculta automáticamente.
- **Pago**: este módulo permite a un cliente pagar un pedido con una tarjeta de crédito. Si el importe total del carro se cubre con puntos de fidelización o una tarjeta regalo, o es 0 (cero), este módulo se oculta automáticamente. La integración de la tarjeta de crédito la proporciona el connector de pagos de Adyen para este módulo. Para obtener más información acerca de cómo usar este conector, consulte [Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md).
- **Dirección de facturación**: este módulo permite a un cliente proporcionar información de facturación. Adyen procesa esta información, junto con la información de la tarjeta de crédito. Este módulo incluye una opción que permite a los clientes usar su dirección de facturación como la dirección de envío.
- **Información de contacto:** este módulo permite a un cliente agregar o cambiar la información de contacto (dirección de correo electrónico) para un pedido.
- **Bloque de texto**: este módulo contiene cualquier mensajería controlada por el sistema de gestión de contenidos (CMS). Por ejemplo, es posible que contenga un mensaje que indique "Para problemas con el pedido, póngase en contacto con 1-800-Fabrikam". 

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

La mayor parte de la información de finalización del pago, como la dirección de envío y el método de envío, se almacena en el carro y se procesa como parte del pedido. La única excepción es la información de la tarjeta de crédito. Esta información se procesa directamente mediante el conector de pagos de Adyen. El pago se autoriza pero no se carga.

## <a name="add-a-checkout-module-to-a-new-page-and-set-the-required-properties"></a>Agregue un módulo de finalización del pago a una página nueva y establezca las propiedades necesarias.

Para agregar un módulo de finalización del pago a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Fragmento \> Nuevo fragmento** y asigne al nuevo fragmento el nombre **Fragmento de finalización de compra**.
1. Agregue un módulo de finalización de compra al fragmento.
1. Agregue un encabezado al módulo de finalización de compra.
1. Agregue la dirección de envío, las opciones de entrega, el contenedor de la sección de finalización de compra y los módulos de información de contacto. 
1. En el módulo de contenedor de la sección de finalización de compra, agregue los módulos de la tarjeta regalo, los puntos de fidelización y pago. De esta manera, asegúrese de que todos los métodos de pago aparecen juntos en una sección.
1. Guarde el fragmento y muestre una vista. Es posible que los módulos que no tienen un contexto de carro no se representen en la vista previa.
1. Termine de editar el fragmento y publíquelo.
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
