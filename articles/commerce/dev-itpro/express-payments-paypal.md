---
title: Configurar pagos exprés para PayPal
description: Este artículo describe cómo configurar pagos exprés para PayPal para habilitar capacidades de pago más rápidas en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b69b7384992fb86370ff6881824a7d2c9a77d2c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905291"
---
# <a name="configure-express-payments-for-paypal"></a>Configurar pagos exprés para PayPal

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar pagos exprés para PayPal para habilitar capacidades de pago más rápidas en Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Términos clave

| Condición | Description |
|---|---|
| Cartera de PayPal | La experiencia del cliente y la integración que son compatibles con el conector de PayPal. También se conoce como el botón de PayPal. |
| Cartera | Un tipo de pago que no incluye características de pago tradicionales, como el rango del número de identificación bancaria (BIN) y la fecha de vencimiento, que se utilizan para diferenciar los tipos de tarjetas de crédito y débito. |
| Pago exprés | Un módulo de Commerce que admite un comportamiento de pago más rápido cuando se utilizan métodos de pago admitidos. Este artículo abarca el uso del módulo de pago express con PayPal. |

Dynamics 365 Commerce ofrece una integración lista para usar para la Cartera de PayPal. Cuando se configura Dynamics 365 Payment Connector para PayPal, el botón de PayPal aparece como un método de pago seleccionable durante la finalización del pago del pedido en línea. Cuando los usuarios seleccionan PayPal, se les indica que completen su pago directamente a través de PayPal y luego regresan a la tienda en línea para completar su pedido. El pago del carro de PayPal permite a los clientes usar la información de su cuenta de pago para completar previamente el formulario de finalización de la compra, de modo que puedan completar el proceso de finalización de la compra más rápidamente.

Commerce ha agregado un módulo de pago exprés para facilitar los pagos exprés. El módulo de pago exprés se puede usar en un fragmento que se puede incluir en una página de pago o carro. Cuando se configura PayPal, se utiliza la misma referencia de conector de Dynamics 365 Payment Connector para PayPal tanto para la opción de pago exprés como para la opción de pago regular.

## <a name="paypal-checkout-in-commerce"></a>Pago de PayPal en Commerce

### <a name="prerequisites"></a>Requisitos previos

Configure la Cartera de PayPal para su entorno como se describe en el [Conector de pagos de Dynamics 365 para PayPal](../paypal.md).

Si está utilizando PayPal como una opción en el flujo de finalización de la compra regular (donde los usuarios especifican manualmente la información de su cuenta sin usar las acciones de completado previamente de pago exprés), siga las instrucciones de configuración en el [Módulo de pago](../payment-module.md).

### <a name="payment-express-module-with-paypal"></a>Módulo de pago express con PayPal

El módulo de pago exprés funciona con métodos de pago compatibles para ofrecer a los clientes del sitio la opción de finalizar el pago más rápidamente completando previamente la información de su cuenta de servicio de pago durante el proceso de finalización de la compra. El módulo de pago exprés usa el conector de pago configurado para completar rellenar previamente el formulario de pago con los detalles de la cuenta de usuario, como la dirección, la información de contacto y el método de pago seleccionado.

Cuando se utiliza la finalización de compra de pago exprés de PayPal, y un usuario selecciona el botón de PayPal en la sección de pago exprés de la página de finalización de compra, se abre una ventana de pago iFrame de pago de PayPal. A continuación, el usuario inicia sesión en su cuenta de PayPal para usar la dirección de envío, la dirección de facturación, la dirección de correo electrónico y el método de pago de PayPal de su cuenta que elija para pagar la transacción.

Una vez que el usuario completa la acción en la ventana de PayPal, se le dirige de nuevo a la página de finalización de la compra del sitio de Commerce, donde el formulario de de finalización de la compra se completa automáticamente con sus detalles seleccionados. En el flujo exprés de pago, la primera opción de entrega que esté disponible para la dirección de envío que se devuelve se completará previamente para el usuario. Luego, el usuario tiene la opción de revisar el pedido y cambiar los detalles del pedido antes de seleccionar **Realizar pedido** para finalizar el pedido.

### <a name="add-the-payment-express-module-with-paypal-to-a-fragment"></a>Agregar el módulo de pago exprés con PayPal a un fragmento

Para agregar el módulo de pago exprés con PayPal a un fragmento del generador de sitios de Commerce, siga estos pasos.

1. Ir a su sitio.
1. En el panel de navegación izquierdo, seleccione **Fragmentos** y después seleccione **Nuevo**.
1. En el cuadro de diálogo **Nuevo fragmento**, busque y seleccione el módulo **Pago exprés** y luego, bajo **Nombre del fragmento**, escriba un nombre para el fragmento (por ejemplo, **Finalización de compra exprés**).
1. Seleccione **Aceptar** para crear el fragmento.
1. En la vista de esquema, seleccione la franja del módulo de pago exprés que creó.
1. En el panel de propiedades, seleccione **Encabezado**.
1. En el cuadro de diálogo **Título**, en el campo **Texto de encabezado**, escriba el texto del encabezado que desea mostrar para la sección de finalización de la compra exprés del sitio (por ejemplo, **Finalización de compra exprés**).
1. Debajo de **Nivel de título**, seleccione el nivel de título (por ejemplo, **H2**).
1. Seleccione **Aceptar**.
1. En el panel de propiedades, en el campo **Altura del iFrame**, especifique o ajuste la altura del elemento iFrame (por ejemplo, **60**).
1. En el campo **Tipos de licitación admitidos**, introduzca **PayPal**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Agregar el fragmento de pago exprés a la página de finalización de pago

Para agregar el fragmento de pago exprés a la página de finalización del pago en el generador de sitios, siga estos pasos.

1. Ir a su sitio.
1. En el panel de navegación izquierdo, seleccione **Páginas** y luego seleccione la página de finalización de pago de su sitio.
1. Seleccione **Editar** para editar la página.
1. En la franja **Principal**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.

    > [!NOTE]
    > Si ya existe un módulo de contenedor que contiene un fragmento de finalización de pago, mueva la sección de pago exprés para que aparezca encima del contenedor de finalización de pago existente en la franja **Principal**. La sección de pago exprés se representará a continuación encima del contenedor de finalización de pago normal. Para subir o bajar un módulo de contenedor, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Subir** o **Bajar**.

1. En el panel de propiedades **Contenedor**, le recomendamos que configure los ajustes de propiedad de la siguiente manera:

    - **Diseño de contenedor**: seleccione **Apilado**.
    - **Ancho**: seleccione **Rellenar contenedor**.
    - **Elementos secundarios mostrados**: seleccione **Tres**.

1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar un fragmento**, busque y seleccione el fragmento de pago exprés que ha creado y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Agregar el fragmento de pago exprés a la página de carro

Para agregar el fragmento de pago exprés a la página de carro en el generador de sitios, siga estos pasos.

1. Ir a su sitio.
1. En el panel de navegación izquierdo, seleccione **Páginas** y luego seleccione la página de carro de su sitio.
1. Seleccione **Editar** para editar la página.
1. En la franja **Principal**, busque el contenedor que contiene el módulo **Carro**. El módulo **Carro** contendrá una franja **Pago exprés**.
1. Seleccione la franja **Pago exprés**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Pago exprés** y, a continuación, **Aceptar**.
1. En el panel de propiedades, en el campo **Tipos de licitación admitidos**, introduzca **Paypal**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

### <a name="modes-of-delivery"></a>Modos de entrega

Cuando el módulo de pago exprés está configurado para usar PayPal, la primera opción de entrega que se devuelve para la dirección de envío que se seleccionó para la cuenta de PayPal se completará previamente. Los usuarios podrán cambiar la dirección de envío si así lo desean.

El orden del modo de entrega se configura en la sección **Modos de entrega** para el canal en Commerce headquarters. Para obtener más información, consulte [Configurar los modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

El módulo de finalización de pago también utilizará el módulo de opciones de entrega cuando los modos de entrega se representen durante la finalización del pago. Para obtener más información, consulte [Módulo de opciones de entrega](../delivery-options-module.md).

Los modos de entrega se agregan a la lista de la tienda en línea en Commerce headquarters. Vaya a **Venta minorista y comercio \> Canales \> Tiendas en línea** y seleccione el id. de canal para su tienda. Luego seleccione **Configuración \> Modos de entrega**. Los modos de entrega del módulo que se muestran en la configuración aparecerán de manera similar en el sitio. Para agregar o quitar modos de entrega para un producto o canal minorista, seleccione **Administrar modos de entrega** en el Panel de acciones.

## <a name="additional-resources"></a>Recursos adicionales

[Preguntas frecuentes sobre pagos](payments-retail.md)

[Módulo de finalización de compra](../add-checkout-module.md)

[Módulo de pago](../payment-module.md)

[Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Módulo de opciones de entrega](../delivery-options-module.md)
