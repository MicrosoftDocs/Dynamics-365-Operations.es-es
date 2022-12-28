---
title: Configurar Google Pay con Adyen
description: Este artículo describe cómo configurar Google Pay con Adyen en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 07/05/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: cdf950fc7b3720543d93e108d4e3c3c2ab254e09
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838401"
---
# <a name="configure-google-pay-with-adyen"></a>Configurar Google Pay con Adyen

[!include [banner](../includes/banner.md)]

Este artículo describe cómo configurar Google Pay con Adyen en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce ofrece una integración lista para usar para Google Pay cuando se utiliza el servicio de pasarela de pago Adyen. Google Pay es un método de pago de cartera digital que utiliza una cuenta de Google Pay Merchant en coordinación con el servicio de pago Adyen. Cuando está configurado, el botón Google Pay está disponible como un método de pago seleccionable durante el pago de pedidos en línea. Cuando los usuarios seleccionan **Google Pa** en un navegador o dispositivo compatible, se les indica que completen su pago directamente con el servicio Google Pay. Luego vuelven a la tienda en línea para completar el pedido.

Cuando Google Pay se usa con el módulo de pago rápido en Commerce, la información de la cuenta de pago del usuario se completa automáticamente en el formulario de pago para ayudar al usuario a completar el proceso de pago más rápido. Commerce incluye un módulo de pago exprés que permite el comportamiento de pago exprés. El módulo de pago exprés se puede usar en un fragmento que se incluye en la página de pago o carro. La referencia de conector de Dynamics 365 Payment Connector para Google Pay se utiliza junto con el Dynamics 365 Payment Connector para Adyen para habilitar las opciones de pago exprés y de pago regular cuando se configura PayPal. Google Pay también se puede configurar con terminales de pago Adyen y el punto de venta (PDV) de Commerce para uso en la tienda.

## <a name="key-terms"></a>Términos clave

| Condición | Description |
|---|---|
| Google Pay | También conocido como "botón" de Google Pay, se trata de una oferta de pago de cartera compatible a través del conector Adyen. Permite una experiencia de cliente y una integración compatibles con Dynamics Google Pay Connector. |
| Cartera | Un tipo de pago que no incluye características de pago tradicionales, como el rango del número de identificación bancaria (BIN) y la fecha de vencimiento, que se utilizan para diferenciar los tipos de tarjetas de crédito y débito. |
| Módulo de pago exprés | Un módulo de Dynamics 365 Commerce que admite un comportamiento de pago más rápido con métodos de pago admitidos. |

## <a name="prerequisites"></a>Requisitos previos

El uso de Google Pay con Adyen en Commerce requiere una cuenta de Google Merchant. Para obtener información sobre cómo configurar su cuenta de Google Merchant, consulte la [documentación de Adyen sobre Google Pay](https://docs.adyen.com/payment-methods/google-pay/) y la [Lista de verificación de integración](https://developers.google.com/pay/api/web/guides/test-and-deploy/integration-checklist) de Google.

El método de pago Google Pay también debe estar integrado con su cuenta de Adyen. Para obtener instrucciones sobre el vínculo de integración, consulte [Adyen Google Pay](https://www.adyen.com/payment-methods/google-pay).

También debe habilitar la función de cartear mejorada en Dynamics 365 Commerce headquarters. Vaya a **Espacios de trabajo \> Administración de características**, busque la característica **Mejoras en los pagos y en la compatibilidad de la cartera**, seleccione la característica y, a continuación, seleccione **Habilitar**. Una vez habilitada la característica, ejecute la programación de distribución **1110** para que el cambio esté disponible en todos los canales.

## <a name="map-the-google-pay-payment-method"></a>Asignar el método de pago Google Pay

Google Pay es un método de pago de cartera digital. Para obtener información sobre cómo configurar la asignación de pagos para Google Pay, consulte [Soporte de pago con Cartera](../wallets.md).

Para asignar el método de pago Google Pay a los tipos de forma de pago con tarjeta para PDV y canales en línea, siga estos pasos.

1. En la sede central de Commerce, vaya a **Retail y Commerce \> Configuración de sede central \> Métodos de pago \> Tipos de tarjetas**.
1. Seleccione **Nuevo** para agregar una línea para Google Pay.
1. En el campo **ID**, escriba **GooglePay**.
1. En el campo **Nombre de pago electrónico**, escriba **Google Pay**.
1. En el campo **Tipo** , especifique **Cartera**.
1. En el campo **Emisor**, escriba **Google**.
1. En el Panel de acciones, seleccione **Asignación de procesador** para abrir el cuadro de diálogo **Métodos de asignación de pagos de procesador**.
1. En **Métodos de pago del procesador no asignados** verá una lista de métodos de pago de procesador no asignados, cada uno de los cuales está emparejado con el conector adecuado. Para asignar métodos de pago del procesador Google Pay no asignados a tipos de formas de pago con tarjeta, siga estos pasos para cada tipo de pago con tarjeta:

    1. En **Tipos de forma de pago con tarjeta**, seleccione un tipo de forma de pago con tarjeta.
    1. En la columna **Métodos de pago del procesador no asignados**, seleccione el conector **Dynamics 365 Payment Connector for Adyen** (para uso en el PDV) y el conector **Dynamics 365 Payment Connector for Google Pay** (para uso en canales en línea).
    1. Seleccione **Agregar**. Las selecciones se añaden a la columna **Métodos de pago del procesador asignados**.

1. Cuando haya terminado de asignar métodos de pago, seleccione **Guardar**.
1. En la página **Tipos de tarjetas**, seleccione **Guardar**.

## <a name="configure-a-commerce-online-store-for-google-pay"></a>Configurar una tienda en línea de Commerce para Google Pay

Para configurar una tienda en línea de Commerce para usar Google Pay, siga estos pasos.

1. En Commerce headquarters, vaya a **Venta minorista y comercio \> Canales \> Tiendas en línea**.
1. Seleccione el canal de la tienda en línea del sitio seleccionando su valor de **ID de canal minorista** del canal.
1. En la ficha rápida **Cuentas de pago**, en **Conector**, confirme que figura el conector **Dynamics 365 Payment Connector para Adyen**. Si no está en la lista, siga las instrucciones de [Configurar Dynamics 365 Payment Connector para Adyen](adyen-connector-setup.md) para agregarlo

    > [!NOTE]
    > En la mayoría de los casos, el conector **Dynamics 365 Payment Connector para Adyen** debe aparecer como primer conector de su canal (el primer conector también se conoce como conector principal). Luego debe ser seguido por otros conectores que se utilizarán, como los conectores **Dynamics 365 Payment Connector para PayPal** y **Dynamics 365 Payment Connector para GooglePay**.

1. Después de agregar el conector **Dynamics 365 Payment Connector para Adyen**, seleccione **Agregar** para agregar el conector **Dynamics 365 Payment Connector para GooglePay**. Luego establezca las siguientes propiedades para el conector.

    | Campo                  | Description | Requerido | Definir automáticamente | Valor de muestra |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nombre de ensamblado          | El nombre del ensamblado para Dynamics 365 Payment Connector para GooglePay. | Sí | Sí | *Nombre binario* |
    | Id. de cuenta de servicio     | El identificador único para la configuración de las propiedades del comerciante. Este identificador se estampa en las transacciones de pago e identifica las propiedades del comerciante que deben usar los procesos posteriores (como la facturación). | Sí | Sí | *GUID* |
    | Id. de Google merchant     | Ingrese el ID de Google Merchant que está asignado a su cuenta de Google Merchant. Esta propiedad es necesaria para entornos de producción, pero es opcional para entornos de prueba. Para obtener más información, visite <https://pay.google.com/>. | Sí | No | *Identificador numérico* |
    | ID de cuenta de comerciante    | Escriba el identificador único de comerciante de Adyen. Este valor se proporciona cuando se suscribe a Adyen como se describe en [Suscribirse a Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Sí | No | *Identificador de comerciante* |
    | Clave de la API de la nube          | Ingrese la clave de la API de la nube de Adyen. Para obtener esta clave, siga las instrucciones en [Cómo obtener la clave de la API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Sí | No | "abcdefg" |
    | Entorno de la puerta de enlace    | El entorno de la puerta de enlace de Adyen al que asignar. Los valores posibles son **Prueba** y **Activo**. Debe establecer este campo en **Activo** solo para dispositivos y transacciones de producción. | Sí | Sí | "Activo" |
    | Divisas admitidas   | Las divisas que debe procesar el conector. En escenarios de tarjeta presente, Adyen puede admitir divisas adicionales a través de [Conversión dinámica de divisas](https://www.adyen.com/pos-payments/dynamic-currency-conversion) después de que la solicitud de transacción se envíe al terminal de pago. Póngase en contacto con el soporte de Adyen para obtener una lista de las divisas admitidas. | Sí | Sí | "USD;EUR" |
    | Tipos de forma de pago admitidos | Los tipos de forma de pago que debe procesar el conector. | Sí | Sí | "GooglePay" |

1. Una vez que haya terminado de configurar las propiedades del conector, ejecute el trabajo de programación de la distribución **1070 (Configuración del canal)**.


### <a name="use-the-payment-express-module-with-google-pay"></a>Utilizar el módulo de pago express con Google Pay

El módulo de pago exprés de Commerce funciona con métodos de pago compatibles para ofrecer a los clientes del sitio la opción de finalizar el pago más rápidamente utilizando la información de su cuenta de servicio de pago durante el proceso de finalización de la compra. El módulo de pago exprés hace referencia al botón del conector configurado y devuelve los detalles del pedido seleccionado por el usuario (dirección, información de contacto y método de pago) para completar previamente el formulario de pago.

Cuando el módulo de pago exprés se usa con Google Pay, si los clientes seleccionan el botón Google Pay en la sección **Pago exprés**, se abrirá la ventana iframe de Google Pay. A continuación los usuarios pueden iniciar sesión en su cuenta de Google para usar la dirección de envío, la dirección de facturación, la dirección de correo electrónico y el método de pago de PayPal de su cuenta que elija para pagar la transacción.

Cuando los usuarios completan la acción en la ventana de Google Pay, se le dirige a la página de finalización de compra del sitio de Commerce, donde el formulario de finalización de la compra se completa automáticamente con los detalles de su cuenta de Google Pay. Cuando los usuarios regresen a la página de finalización de compra desde la ventana de Google Pay, verán los siguientes detalles:

- En el flujo exprés de pago, la primera opción de entrega que esté disponible para la dirección de envío que devolvió aparecerá seleccionada previamente para el usuario.
- Cuando se utiliza Google Pay no se devuelve ninguna dirección de correo electrónico de contacto. Los usuarios de finalización de compra de invitado deberán ingresar una dirección de correo electrónico en la sección de contacto de la página de finalización de compra. Los datos de contacto de los usuarios que han iniciado sesión se completarán automáticamente desde su cuenta de cliente de Dynamics (la dirección de correo electrónico principal que usaron para la autenticación).

Los clientes tienen la opción de revisar pedidos y cambiar los detalles del pedido antes de seleccionar **Realizar pedido** para finalizar el pedido.

### <a name="configure-google-pay-in-site-builder"></a>Configurar Google Pay en el generador de sitios 

Antes de configurar sus fragmentos o páginas con Google Pay, debe asegurarse de que sus directivas de seguridad de contenido para su sitio estén configuradas en el generador de sitios de Commerce.

Para asegurarse de que sus directivas de seguridad de contenido estén configuradas en el generador de sitios, siga estos pasos.

1. En su sitio, vaya a **Configuración del sitio \> Extensiones**.
1. En la pestaña **Directiva de seguridad de contenido**, agregue una línea para `*.google.com` a las directivas **child-src**, **connect-src**, **frame-ancestors**, **frame-src**, **img-src**, **script-src** y **style-src**.
1. Cuando haya terminado, seleccione **Guardar y publicar**.

### <a name="configure-the-payment-express-fragment-with-google-pay-in-site-builder"></a>Configure el fragmento de pago exprés con Google Pay en el generador de sitios

Para configurar el fragmento de pago exprés con Google Pay para la tienda en línea, siga estos pasos.

1. En el generador de sitios, vaya a **Fragmentos**.
1. Seleccione **Nuevo**.
1. En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Contenedor**, especifique un nombre de fragmento (por ejemplo, **Pago exprés**) y, a continuación, seleccione **Aceptar**. 
1. Seleccione la franja **Contenedor predeterminado** del nuevo fragmento.
1. En el panel de propiedades de la derecha, establezca las propiedades del módulo de contenedor:

    - **Encabezado** – Ingrese un encabezado para mostrar en la sección de pago exprés de su sitio (por ejemplo, **Pago exprés**).
    - **Diseño de contenedor**: seleccione **Flujo**.
    - **Ancho**: seleccione **Rellenar contenedor**.
    - **Elementos secundarios mostrados** - Seleccione **Tres** para especificar el número de elementos secundarios que cabrán en una fila de la sección de pago exprés de la página de finalización de pago (por ejemplo, un cuadro de texto, pago exprés para PayPal y pago exprés para Google Pay).
    - **Nombre de clase CSS** - escriba **msc-express-payment-container** (requerido).

    > [!IMPORTANT]
    > - El valor de **Nombre de clase CSS** debe establecerse en **msc-express-payment-container** para controlar el comportamiento del contenedor durante el pago. Este comportamiento incluye ocultar, contraer y otras acciones que se aplican a la sección de pago exprés durante el proceso de pago. La clase **msc-express-payment-container** funciona con las operaciones predeterminadas que se lanzan con el módulo de finalización de compra de la biblioteca de módulos.
    > - Se pueden incluir estilos adicionales con el **Nombre de clase CSS**. Si personaliza el comportamiento del módulo, verifique los controles de estilo si está utilizando el mismo comportamiento codificado de la biblioteca de módulos en el módulo de finalización de compra para el comportamiento de pago exprés.

1. En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Pago exprés** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo **Pago exprés**, especifique o ajuste el valor **Alto del iFrame** en píxeles (por ejemplo, **60**).
1. En el campo **Tipos de licitación admitidos**, introduzca **GooglePay**. El valor debe coincidir con la cadena **Tipos de forma de pago admitidos** en el conector que está configurado para el canal (como se describe en la sección [Configurar una tienda en línea de Commerce para Google Pay](#configure-a-commerce-online-store-for-google-pay) anterior de este artículo).

    > [!NOTE]
    > Puede repetir los pasos 6 a 9 para agregar módulos **Pago exprés** para otros métodos de pago. Alinee el valor de **Tipos de forma de pago admitidos** con los tipos de pago configurados adicionales (por ejemplo, **Paypal**).

1. Opcional: puede agregar un módulo de bloque de texto al módulo de contenedor predeterminado para incluir instrucciones o información. Después de agregar el módulo, en el panel de propiedades, ingrese el texto deseado en el campo **Texto enriquecido**. Puede colocar el texto encima o debajo de los módulos de pago exprés seleccionando los puntos suspensivos (**...**) en la franja **Bloque de texto** y luego seleccionando **Subir** o **Bajar**.
1. Seleccione **Guardar** para guardar los cambios y luego seleccione **Finalizar la edición**.
1. Para publicar la el fragmento, seleccione **Publicar**.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Agregar el fragmento de pago exprés a la página de finalización de pago

Para agregar el fragmento de pago exprés a la página de finalización de compra, siga estos pasos.

1. En el generador de sitios, vaya a **Páginas** y luego seleccione la página de finalización de pago de su sitio.
1. Seleccione **Editar**.
1. En la **Franja principal**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el panel de propiedades de la derecha, establezca las propiedades del módulo de contenedor:

    - **Diseño de contenedor**: seleccione **Apilado**.
    - **Ancho**: seleccione **Rellenar contenedor**.
    - **Elementos secundarios mostrados** - Seleccione **Tres** para especificar el número de elementos secundarios que cabrán en una fila de la sección de pago exprés de la página de finalización de pago (por ejemplo, un cuadro de texto, pago exprés para PayPal y pago exprés para Google Pay).

1. En la franja del módulo **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar un fragmento**, seleccione el fragmento de pago exprés que ha creado y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** para guardar los cambios y luego seleccione **Finalizar la edición**.
1. Seleccione **Publicar** para publicar la página.

> [!NOTE]
> Si la página de pago ya incluye un contenedor que tiene el fragmento de pago y desea que el módulo de pago exprés se represente sobre el contenedor de pago normal, puede colocarlo encima o debajo del pago existente seleccionando los puntos suspensivos (**...**) en la **Franja principal** y luego seleccionando **Subir** o **Bajar**.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Agregar el fragmento de pago exprés a la página de carro

Para agregar el fragmento de pago exprés a la página de carro, siga estos pasos.

1. En el generador de sitios, vaya a **Páginas** y luego seleccione la página de carro de su sitio.
2. Seleccione **Editar**.
3. En la vista de esquema, expanda la **Franja principal** en la vista de árbol y busque el contenedor que contiene el módulo de **Carro**.
4. En el módulo **Carro**, seleccione la franja **Pago exprés**, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
5. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Pago exprés** y, a continuación, **Aceptar**.
6. Seleccione la franja del módulo **Pago exprés**. Luego, en el panel de propiedades de la derecha, en **Tipos de forma de pago admitidos**, ingrese **GooglePay**. El valor debe coincidir con la cadena **Tipos de forma de pago admitidos** en el conector que se configuró para el canal (como se describe en la sección [Configurar una tienda en línea de Commerce para Google Pay](#configure-a-commerce-online-store-for-google-pay) anterior de este artículo).
1. Seleccione **Guardar** para guardar los cambios y luego seleccione **Finalizar la edición**.
1. Seleccione **Publicar** para publicar la página.

Los usuarios pueden incluir hasta tres módulos **Pago exprés** compatibles (en otras palabras, tres opciones de pago admitidas disponibles) en la franja **Pago exprés** del carro.

### <a name="set-up-google-pay-as-an-option-in-the-checkout-payment-section"></a>Configurar Google Pay como opción en la sección de pago

Puede configurar Google Pay como opción en la sección de pago para la función de solo pago, no exprés. El usuario completará el formulario de pago y la página de pago de Google Pay solo preparará el pago para Google Pay. No se utilizará información de la cuenta de Google para sobrescribir los detalles de pago completados.

> [!NOTE]
> El siguiente procedimiento asume que su sitio utiliza un fragmento de pago que está configurado con información de recogida, una dirección de envío, opciones de entrega, información de contacto, términos y condiciones opcionales y una sección para elementos de pago. El módulo de finalización de compra predeterminado de la biblioteca de módulos se lanza con un contenedor de sección de pago que tiene un bloque de texto, puntos de fidelidad, tarjeta regalo y módulos de pago. Para más información, ver [Módulo de pago](../payment-module.md).

Para configurar Google Pay como opción de pago regular en la sección **Método de pago** de la página de finalización de compra, siga estos pasos.

1. En el generador de sitios, vaya a **Fragmentos** y luego seleccione el fragmento de finalización de compra de su sitio.
1. Seleccione **Editar**.
1. En el espacio **Información de finalización de compra**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Pago** y, a continuación, **Aceptar**.
1. En el panel de propiedades de la derecha del módulo **Pago**, establezca las propiedades del módulo de contenedor:

    - **Encabezado** – Ingrese un encabezado para mostrar en la sección de pago exprés de su sitio (por ejemplo, **Google Pay**).
    - **Alto del iFrame** – Cambie el valor a su altura de diseño preferida en píxeles (por ejemplo, **75**). 
    - **Tipos de forma de pago admitidos** - Ingrese **GooglePay** para que coincida con la configuración del conector de Google Pay en Commerce headquarters.
    - **Es pago primario** – Deje la casilla sin marcar. (Esta propiedad normalmente está habilitada para el módulo de finalización de compra de Adyen).
    - **Anulación de estilo de pago** – Esta propiedad no es compatible con la configuración de Google Pay.
    - **Usar id. de conector** – Esta propiedad debe seleccionarse si se utilizan varios conectores de pago en la página.

1. Coloque el módulo por encima o por debajo de otros módulos de pago seleccionando los puntos suspensivos (**...**) en la franja **Pago** y luego seleccionando **Subir** o **Bajar**.
1. Seleccione **Guardar** para guardar los cambios y luego seleccione **Finalizar la edición**.
1. Seleccione **Publicar**.

### <a name="modes-of-delivery"></a>Modos de entrega

Con el módulo de pago exprés que utiliza Google Pay, se seleccionará previamente la primera opción de entrega que se devuelve para la dirección de envío seleccionada de la cuenta de PayPal. Los usuarios tienen la oportunidad de ajustar la dirección de envío a una opción diferente si así lo desean.

El orden en que se muestran los métodos de entrega en el módulo de pago exprés se configura en la página **Modos de entrega** del canal en Commerce headquarters. En Commerce headquarters, vaya a **Retail and Commerce \> Canales \> Tiendas en línea** y seleccione el valor **Id. de canal comercial** para su tienda. En el panel de acciones, en la pestaña **Configuración**, seleccione **Modos de entrega**. Los modos de envío que se enumeran se mostrarán en el mismo pedido en el módulo de pago exprés. Seleccione **Administrar modos de entrega** en el Panel de acciones para agregar o quitar modos de entrega para un producto o canal minorista. Para obtener más información sobre cómo configurar modos de entrega, consulte [Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

El módulo de finalización de pago también utiliza el módulo de opciones de entrega cuando los modos de entrega se representen durante la finalización del pago. Para obtener más información, consulte [Módulo de opciones de entrega](../delivery-options-module.md).

Los modos de entrega se muestran a medida que se agregan a la lista **Modos de entrega** en la tienda en línea.

## <a name="configure-commerce-pos-for-google-pay"></a>Configurar PDV de Commerce para Google Pay

La configuración de PDV utiliza la configuración del campo **Servicio EFT** del perfil de hardware para Dynamics 365 Payment Connector para Adyen. Para obtener información sobre cómo configurar el servicio de transferencia electrónica de fondos (EFT) para Dynamics 365 Payment Connector para Adyen en Commerce headquarters, consulte [Configurar un perfil de hardware de Dynamics 365 POS](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

La asignación de procesador para el conector Adyen captura los tipos de tarjetas de cartera que usa Google Pay en el terminal del PDV.

## <a name="additional-resources"></a>Recursos adicionales

[Preguntas frecuentes sobre pagos](payments-retail.md)

[Módulo de finalización de compra](../add-checkout-module.md)

[Módulo de pago](../payment-module.md)
