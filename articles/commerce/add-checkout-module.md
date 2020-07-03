---
title: Módulo de finalización de compra
description: En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: bd1d66fc39872019fc38dbbfb56dc3015d57d0dd
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411227"
---
# <a name="checkout-module"></a>Módulo de finalización de compra


[!include [banner](includes/banner.md)]

En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.

## <a name="overview"></a>Visión general

Un módulo de finalización de compra es un contenedor especial que hospeda todos los módulos necesarios para crear un pedido. Presenta un flujo detallado que un cliente usa para introducir toda la información pertinente para realizar una compra. Captura la dirección de envío, el método de envío y la información de facturación. También proporciona un resumen del pedido y otra información relacionada con un pedido del cliente.

Un módulo de finalización de compra representa datos a partir del id. del carro. Este id. del carro se guarda como cookie del explorador. Se requiere un id. de carro para representar información en el módulo de finalización de compra, como los artículos del pedido, el importe total y los descuentos. 

La siguiente imagen muestra un ejemplo de un módulo de finalización de compra en una página de finalización de compra.

![Ejemplo de módulo de finalización de compra](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Propiedades del módulo de finalización de compra

Un módulo de finalización de compra muestra un resumen del pedido y proporciona la funcionalidad necesaria para realizar un pedido. Para reunir toda la información del cliente necesaria para poder realizar un pedido, hay que agregar módulos adicionales al módulo de finalización de compra. Por lo tanto, los minoristas tienen la flexibilidad de agregar módulos personalizados al flujo de finalización de compra, o de excluir módulos, según sus requisitos.

### <a name="modules-that-can-be-used-in-the-checkout-module"></a>Módulos que se pueden usar en el módulo de finalización de compra

- **Dirección de envío**: este módulo permite que un cliente agregue o seleccione la dirección de envío para un pedido. Si el cliente ha iniciado sesión, se muestran las direcciones que se guardaron anteriormente para ese cliente. El cliente puede seleccionar a continuación entre esas direcciones. El cliente también puede agregar una dirección nueva. La dirección de envío se usa para todos los artículos del pedido que requieren envío. No se puede personalizar para artículos de línea individuales. Los formatos de dirección de envío se definen para cada país o región, y las reglas específicas de país o región se aplican por este módulo. Aunque este módulo no proporcione la validación de la dirección, la validación de la dirección se puede implementar a través de la personalización. Si el pedido solo incluye artículos que se recogerán en la tienda, este módulo se oculta automáticamente.

    La siguiente imagen muestra un ejemplo de un módulo de dirección de envío en una página de finalización de compra.

    ![Ejemplo de un módulo de dirección de envío](./media/ecommerce-shippingaddress.PNG)

- **Opciones de entrega**: este módulo permite a un cliente seleccionar una opción de entrega para un pedido. Las opciones de entrega se basan en la dirección de envío. Si cambia la dirección de envío, las opciones de entrega se deben recuperar de nuevo. Si el pedido solo incluye artículos que se recogerán en la tienda, este módulo se oculta automáticamente.

    La siguiente imagen muestra un ejemplo de un módulo de opciones de entrega en una página de finalización de compra.

    ![Ejemplo de un módulo de opciones de entrega](./media/ecommerce-deliveryoptions.PNG)

- **Contenedor de secciones de finalización de compra:** este módulo es un contenedor que puede colocar varios módulos dentro para crear una sección dentro del flujo de finalización de compra. Por ejemplo, puede colocar todos los módulos relacionados con pagos dentro de este contenedor para que aparezcan como una sección. Este módulo solo afecta al diseño del flujo.
- **Tarjeta regalo**: este módulo permite a un cliente pagar por un pedido con una tarjeta regalo. Solo admite tarjetas regalos de Microsoft Dynamics 365 Commerce. Se pueden aplicar una o más tarjetas regalo a un pedido. Si el saldo de la tarjeta regalo no cubre el importe del carro, la tarjeta regalo se puede combinar con otro método de pago. Las tarjetas regalo solo se pueden canjear si el cliente ha iniciado sesión.
- **Puntos de fidelización:** este módulo permite a un cliente pagar por un pedido mediante puntos de fidelización. Ofrece un resumen de puntos disponibles y puntos de caducidad, y permite al cliente seleccionar el número de puntos que se canjearán. Si el cliente no ha iniciado sesión o no es un cliente de fidelización, o si el importe total del carro es 0 (cero), este módulo se oculta automáticamente.
- **Pago**: este módulo permite a un cliente pagar un pedido con una tarjeta de crédito. Si el importe total del carro se cubre con puntos de fidelización o una tarjeta regalo, o es 0 (cero), este módulo se oculta automáticamente. La integración de la tarjeta de crédito la proporciona el connector de pagos de Adyen para este módulo. Para obtener más información acerca de cómo usar este conector, consulte [Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md).
- **Dirección de facturación**: este módulo permite a un cliente proporcionar información de facturación. Adyen procesa esta información, junto con la información de la tarjeta de crédito. Este módulo incluye una opción que permite a los clientes usar su dirección de facturación como la dirección de envío.

    La siguiente imagen muestra un ejemplo de tarjeta de regalo, puntos de fidelidad, pago y módulos de dirección de facturación en una página de finalización de compra.

    ![Ejemplo de módulos de tarjeta de regalo, puntos de fidelidad, pago y dirección de facturación](./media/ecommerce-payments.PNG)

- **Información de contacto:** este módulo permite a un cliente agregar o cambiar la información de contacto (dirección de correo electrónico) para un pedido.

- **Bloque de texto**: este módulo contiene cualquier mensajería controlada por el sistema de gestión de contenidos (CMS). Por ejemplo, es posible que contenga un mensaje que indique "Para problemas con el pedido, póngase en contacto con 1-800-Fabrikam". 

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

La mayor parte de la información de finalización del pago, como la dirección de envío y el método de envío, se almacena en el carro y se procesa como parte del pedido. La única excepción es la información de la tarjeta de crédito. Esta información se procesa directamente mediante el conector de pagos de Adyen. El pago se autoriza pero no se carga.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Agregue un módulo de finalización de compra a una página y establezca las propiedades necesarias

Para agregar un módulo de finalización del pago a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Fragmentos de página** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo, **Nuevo fragmento de página**, seleccione el módulo **Finalización de compra**.
1. En **Nombre del fragmento de página**, introduzca el nombre **Fragmento de finalización de compra** y luego seleccione **Aceptar**.
1. Seleccione el espacio **Módulo de finalización de compra**.
1. En el panel de propiedades de la derecha, seleccione el símbolo del lápiz, introduzca el texto del encabezado en el campo y luego seleccione el símbolo de marca de verificación.
1. En el espacio **Información de finalización de compra**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione los módulos **Dirección de Envío**, **Opciones de entrega**, **Contenedor de sección de finalización de compra** e **Información del contacto** y luego seleccione **Aceptar**.
1. En el módulo **Contenedor de sección de finalización de compra**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione los módulos **Tarjeta regalo**, **Fidelidad** y **Pago** y, a continuación, **Aceptar**. De esta manera, asegúrese de que todos los métodos de pago aparecen juntos en una sección.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar el fragmento. Es posible que los módulos que no tienen un contexto de carro no se representen en la vista previa.
1. Seleccione **Finalizar edición** para comprobar en el fragmento y luego seleccione **Publicar** para publicarlo.
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
