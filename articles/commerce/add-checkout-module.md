---
title: Módulo de finalización de compra
description: En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0d022ad98603b489a133a5b9f2326677e9ebb307
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780523"
---
# <a name="checkout-module"></a>Módulo de finalización de compra

[!include [banner](includes/banner.md)]

En este tema se describe cómo agregar un módulo de finalización de compra a una página y establecer las propiedades necesarias.

Un módulo de finalización de compra es un contenedor especial que hospeda todos los módulos necesarios para crear un pedido. Presenta un flujo detallado que un cliente usa para introducir toda la información pertinente para realizar una compra. Captura la dirección de envío, el método de envío y la información de facturación. También proporciona un resumen del pedido y otra información relacionada con un pedido del cliente.

Un módulo de finalización de compra representa datos a partir del id. del carro. Este id. del carro se guarda como cookie del explorador. Se requiere un id. de carro para representar información en el módulo de finalización de compra, como los artículos del pedido, el importe total y los descuentos. 

La siguiente imagen muestra un ejemplo de un módulo de finalización de compra en una página de finalización de compra.

![Ejemplo de módulo de finalización de compra.](./media/Checkout.PNG)

## <a name="checkout-module-properties"></a>Propiedades del módulo de finalización de compra

Un módulo de finalización de compra muestra un resumen del pedido y proporciona la funcionalidad necesaria para realizar un pedido. Para reunir toda la información del cliente necesaria para poder realizar un pedido, hay que agregar módulos adicionales al módulo de finalización de compra. Por lo tanto, los minoristas tienen la flexibilidad de agregar módulos personalizados al flujo de finalización de compra, o de excluir módulos, según sus requisitos.

| Nombre de la propiedad | Valores | Descripción |
|----------------|--------|-------------|
| Encabezado de Finalizar compra | Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado para el módulo de finalización de compra. |
| Encabezado de Resumen del pedido | Texto del encabezado | Un encabezado para la sección de resumen de pedido del módulo. |
| Encabezado de artículos de línea del carro | Texto del encabezado | Un encabezado para artículos de línea del carro que se muestran en el módulo de finalización de compra. |
| Mostrar los gastos de envío del artículo de línea | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, se mostrarán los gastos de envío aplicables a artículos de línea en las líneas del carro. Si la característica **Carga de encabezado sin prorrateo** está activada en la sede de Commerce, el cargo de envío se aplicará en el nivel de encabezado, no en el nivel de línea. Esta característica se agregó en la versión 10.0.13 de Commerce. |

## <a name="modules-that-can-be-used-in-the-checkout-module"></a>Módulos que se pueden usar en el módulo de finalización de compra

- **Dirección de envío**: este módulo permite que un cliente agregue o seleccione la dirección de envío para un pedido. Para obtener más información sobre este módulo, consulte [Módulo de dirección de envío](ship-address-module.md).

    La siguiente imagen muestra un ejemplo de un módulo de dirección de envío en una página de finalización de compra.

    ![Ejemplo de un módulo de dirección de envío.](./media/ecommerce-shippingaddress.PNG)

- **Opciones de entrega**: este módulo permite a un cliente seleccionar un modo de entrega para un pedido. Para obtener más información sobre este módulo, consulte [Módulo de opciones de entrega](delivery-options-module.md).

    La siguiente imagen muestra un ejemplo de un módulo de opciones de entrega en una página de finalización de compra.
 
    ![Ejemplo de un módulo de opciones de entrega.](./media/ecommerce-deliveryoptions.PNG)

- **Contenedor de secciones de finalización de compra:** este módulo es un contenedor que puede colocar varios módulos dentro para crear una sección dentro del flujo de finalización de compra. Por ejemplo, puede colocar todos los módulos relacionados con pagos dentro de este contenedor para que aparezcan como una sección. Este módulo solo afecta al diseño del flujo.

- **Tarjeta regalo**: este módulo permite a un cliente pagar por un pedido con una tarjeta regalo. Para obtener más información sobre este módulo, consulte [Módulo de tarjeta regalo](add-giftcard.md).

- **Puntos de fidelización:** este módulo permite a un cliente pagar por un pedido mediante puntos de fidelización. Ofrece un resumen de puntos disponibles y puntos de caducidad, y permite al cliente seleccionar el número de puntos que se canjearán. Si el cliente no ha iniciado sesión o no es un cliente de fidelización, o si el importe total del carro es 0 (cero), este módulo se oculta automáticamente.

- **Pago**: este módulo permite a un cliente pagar un pedido con una tarjeta de crédito o débito. Los clientes también pueden proporcionar una dirección de facturación para la opción de pago que seleccionen. Para obtener más información sobre este módulo, consulte [Módulo de pago](payment-module.md).

    La siguiente imagen muestra un ejemplo de módulos de tarjeta regalo, puntos de fidelidad y pago en una página de finalización de compra.

    ![Ejemplo de módulos de tarjeta regalo, puntos de fidelidad y pago en una página de finalización de compra.](./media/ecommerce-payments.PNG)

- **Información de contacto:** este módulo permite a un cliente agregar o cambiar la información de contacto (dirección de correo electrónico) para un pedido.

- **Bloque de texto**: este módulo contiene cualquier mensajería controlada por el sistema de gestión de contenidos (CMS). Por ejemplo, es posible que contenga un mensaje que indique "Para problemas con el pedido, póngase en contacto con 1-800-Fabrikam". 

- **Términos y condiciones de pago**: este módulo muestra texto enriquecido que contiene los términos y condiciones, y una casilla que el cliente puede seleccionar. La casilla es opcional y configurable. La entrada la captura el módulo y se puede usar como comprobación antes de desencadenar la realización del pedido, pero no se incluye en la información de resumen del pedido. Este módulo se puede agregar al contenedor de finalización de compra, al contenedor de sección de finalización de compra o al espacio de términos y condiciones, según las necesidades empresariales. Si se agrega al contenedor de finalización de compra o al espacio del contenedor de la sección de finalización de compra, aparecerá como un paso en el proceso de finalización de compra. Si se agrega al espacio de términos y condiciones, aparecerá cerca del botón de realización del pedido.

    La siguiente imagen muestra un ejemplo del módulo de términos y condiciones en una página de finalización de compra.

    ![Ejemplo de términos y condiciones en una página de finalización de compra.](./media/ecommerce-checkout-terms.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

La mayor parte de la información de finalización del pago, como la dirección de envío y el método de envío, se almacena en el carro y se procesa como parte del pedido. La única excepción es la información de la tarjeta de crédito. Esta información se procesa directamente mediante el conector de pagos de Adyen. El pago está autorizado, pero no se cobra hasta que se completa el pedido.

## <a name="add-a-checkout-module-to-a-page-and-set-the-required-properties"></a>Agregue un módulo de finalización de compra a una página y establezca las propiedades necesarias

Para agregar un módulo de finalización del pago a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo, **Seleccionar fragmento**, seleccione el módulo **Finalización de compra**.
1. En **Nombre del fragmento**, introduzca el nombre **Fragmento de finalización de compra** y luego seleccione **Aceptar**.
1. Seleccione el espacio **Módulo de finalización de compra**.
1. En el panel de propiedades de la derecha, seleccione el símbolo del lápiz, introduzca el texto del encabezado en el campo y luego seleccione el símbolo de marca de verificación.
1. En el espacio **Información de finalización de compra**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione los módulos **Dirección de Envío**, **Opciones de entrega**, **Contenedor de sección de finalización de compra** e **Información del contacto** y luego seleccione **Aceptar**.
1. En el módulo **Contenedor de sección de finalización de compra**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulo**, seleccione los módulos **Tarjeta regalo**, **Fidelidad** y **Pago** y, a continuación, **Aceptar**. De esta manera, asegúrese de que todos los métodos de pago aparecen juntos en una sección.
1. En el espacio **Términos y condiciones**, agregue un módulo **Términos y condiciones de finalización de compra** si es necesario. En el panel de propiedades del módulo, configure el texto de los términos y las condiciones según corresponda.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar el fragmento. Es posible que los módulos que no tienen un contexto de carro no se representen en la vista previa.
1. Seleccione **Finalizar edición** para comprobar en el fragmento y luego seleccione **Publicar** para publicarlo.
1. Cree una plantilla que use el nuevo fragmento de finalización de compra.
1. Cree una página de finalización de compra que use la nueva plantilla.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
