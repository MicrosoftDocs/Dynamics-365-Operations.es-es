---
title: Configurar Apple Pay con Adyen en Dynamics 365 Commerce
description: Este artículo describe cómo configurar Apple Pay con Adyen en Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 11/15/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-06-20
ms.openlocfilehash: 0949b9d7a4b181605d43956932b4fc095940bd64
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9780382"
---
# <a name="set-up-apple-pay-with-adyen-in-dynamics-365-commerce"></a>Configurar Apple Pay con Adyen en Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Este artículo describe cómo configurar Apple Pay con Adyen en Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Términos clave

| Condición | Description |
|---|---|
| Apple Pay | También conocido como "botón" Apple Pay, Apple Pay se trata de una oferta de pago de cartera compatible a través del conector Adyen. Permite una experiencia de cliente y una integración compatibles con Microsoft Dynamics 365 Apple Pay Connector. |
| Cartera | Un tipo de pago que no incluye características de pago tradicionales, como el rango del número de identificación bancaria (BIN) y la fecha de vencimiento, que se utilizan para diferenciar los tipos de tarjetas de crédito y débito. |

Dynamics 365 Commerce ofrece una integración lista para usar para Apple Pay cuando se utiliza el servicio de pasarela de pago Adyen. Apple Pay es un método de pago de cartera digital que utiliza una cuenta de Apple Pay Merchant en coordinación con el servicio de pago Adyen. Cuando está configurado, el botón Apple Pay está disponible como un método de pago que es parte de una página de pago del pedido de la tienda en línea. El botón Apple Pay se presenta como una opción de pago solo para dispositivos Apple Pay compatibles. Cuando los usuarios seleccionan **Apple Pay** en un navegador o dispositivo compatible, se les lleva directamente al servicio Apple Pay para que completen su pago. Luego vuelven a la tienda en línea para completar el pedido.

La referencia de conector de Dynamics 365 Payment Connector for Apple Pay se utiliza junto con el Dynamics 365 Payment Connector para Adyen para habilitar las opciones de pago de Apple Pay y tarjeta de crécdito en un sitio. Apple Pay también se puede configurar para su uso en tiendas que tienen terminales de pago de Adyen que usan Dynamics 365 Payment Connector para Adyen con el punto de venta (POS) de Commerce. En este caso, Dynamics 365 Payment Connector para Adyen maneja el toque del dispositivo Apple Payment a través de la terminal.

## <a name="prerequisites"></a>Requisitos previos

Se requiere una cuenta de comerciante de Apple para usar Apple Pay con Adyen en Commerce. Para obtener información sobre cómo configurar Apple Pay en su área de cliente de prueba, consulte [Integración directa de Apple Pay](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#set-up-apple-pay). Para obtener información sobre qué hacer cuando esté listo para comenzar a funcionar en su entorno de producción, consulte [Puesta en marcha](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).

El método de pago de Apple Pay también debe estar integrado con su cuenta de Adyen. Adyen puede ayudarle a configurar el método de pago y también puede ayudarlo a garantizar que los dominios para los que usará el certificado estén asignados para usar con el certificado.

Para habilitar la característica de cartera mejorada en Commerce headquarters, vaya a **Espacios de trabajo \> Administración de características** y busque la característica **Mejoras en los pagos y en la compatibilidad de la cartera**. Seleccione la característica y, a continuación, seleccione **Habilitar**. Una vez habilitada la característica, ejecute la programación de distribución **1110** para que el cambio esté disponible en todos los canales.

## <a name="map-the-apple-pay-payment-method"></a>Asignar el método de pago Apple Pay

Apple Pay es un método de pago de cartera digital. Para obtener información sobre cómo configurar la asignación de pagos para Apple Pay, consulte [Soporte de pago con Cartera](../wallets.md).

Para asignar el método de pago de Apple Pay en Commerce headquarters, siga estos pasos.

1. Vaya a **Retail y Comercio \> Configuración de canales \> Métodos de pago \> Tipos de tarjetas**.
1. Seleccione **Nuevo** para agregar una línea para Apple Pay y establezca los siguientes valores en ella:

    - **ID:** ApplePay
    - **Nombre de pago electrónico:** Apple Pay
    - **Tipo:** Wallet
    - **Emisor:** Apple

1. Seleccione **Asignación de procesador** para abrir el cuadro de diálogo **Métodos de asignación de pagos de procesador**. La columna **Métodos de pago del procesador no asignado** enumera los métodos de pago admitidos para cada conector disponible (Adyen, PayPal y Apple).
1. Asigne los métodos de pago admitidos que desee para el conector **Dynamics 365 Payment Connector for Adyen** (para uso en el PDV) y el conector **Dynamics 365 Payment Connector for Google Pay** (para el canal en línea).
1. Para cada línea de mapeo, en la columna **Métodos de pago del procesador no asignado**, seleccione la línea para admitir y, a continuación, seleccione **Agregar** para mover las selecciones a la columna **Métodos de pago del procesador asignado**.
1. Seleccione **OK** y luego, en la página **Tipos de tarjetas**, seleccione **Guardar**.

## <a name="set-up-the-apple-pay-certificate-for-your-site"></a>Configurar el certificado de Apple Pay para su sitio

Para cada sitio, debe cargar el archivo de asociación de dominio (también conocido como el certificado de Apple Pay) como se describe en la [Documentación de Apple Pay de Adyen](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live). Puede utilizar el creador de sitios de Commerce para cargar el archivo de asociación de dominio en la biblioteca multimedia de su sitio.

Para instalar el certificado de Apple Pay en el generador de sitios, siga estos pasos.

1. Descargue el certificado (archivo de asociación de dominio) de [Adyen](https://docs.adyen.com/payment-methods/apple-pay/web-drop-in#going-live).
1. Agregue la extensión .txt al archivo de asociación de dominio.
1. En el creador de sitios, [suba](../upload-serve-static-files.md) el archivo de asociación de dominio a la biblioteca de medios de su sitio.
1. Vaya a **URL**.
1. Seleccione **Nuevo \> Nueva URL**.
1. En el cuadro de diálogo **Nueva URL**, seleccione **Activo de la biblioteca de medios**.
1. En el campo **Ruta URL**, ingrese la ruta URL (si aún no se ha ingresado). Después de la URL base del dominio, ingrese la siguiente cadena de Apple requerida: `<domain>/.well-known/apple-developer-merchantid-domain-association.txt`.
1. Seleccione **Siguiente**. La biblioteca de medios muestra todos los activos de medios del tipo de **documento** (.txt).
1. Seleccione el archivo de asociación de dominio que se debe servir para las solicitudes a la URL que definió antes.
1. Seleccione **Crear**.

En este punto, la dirección URL que ha creado se encuentra en un estado de borrador. Publique la URL para completar el proceso. El archivo al que apunta la URL no se devolverá hasta que publique la URL.

## <a name="configure-a-commerce-online-store-for-apple-pay"></a>Configurar una tienda en línea de Commerce para Apple Pay

Para configurar una tienda en línea de Commerce para Apple Pay, siga estos pasos.

1. En Commerce headquarters, vaya a **Venta minorista y comercio \> Canales \> Tiendas en línea**.
1. Seleccione el valor **Id. de canal comercial** del canal de la tienda en línea de su sitio.
1. En la ficha desplegable **Cuentas de pago**, agregue el conector **Dynamics 365 Payment Connector for Adyen** si aún no está configurado, siguiendo las instrucciones en [Configurar Dynamics 365 Payment Connector para Adyen](adyen-connector-setup.md).
1. Después de configurar el conector Adyen, seleccione **Agregar** para agregar el conector **Dynamics 365 Payment Connector for Apple Pay**.
1. Introduzca valores para las propiedades del comerciante del conector.

    | Propiedad               | Description | Requerido | Definir automáticamente | Valor de ejemplo |
    | ---------------------- | ----------- | -------- | ----------------- | ------------ |
    | Nombre de ensamblado          | El nombre del ensamblado para Dynamics 365 Payment Connector para Apple Pay. | Sí | Sí | Nombre binario |
    | Id. de cuenta de servicio     | El identificador único para la configuración de las propiedades del comerciante. Este identificador se estampa en las transacciones de pago e identifica las propiedades del comerciante que deben usar los procesos posteriores (como la facturación). | Sí | Sí | Guid |
    | ID de cuenta de comerciante    | Escriba el identificador único de comerciante de Adyen. Este valor se proporciona cuando se suscribe a Adyen como se describe en [Suscribirse a Adyen](adyen-connector-setup.md#sign-up-with-adyen). | Sí | No | MerchantIdentifier |
    | Clave de la API de la nube          | Ingrese la clave de la API de la nube de Adyen. Puede obtener esta clave siguiendo las instrucciones en [Cómo obtener la clave de la API](https://docs.adyen.com/developers/user-management/how-to-get-the-api-key). | Sí | N.º | abcdefg |
    | Entorno de la puerta de enlace    | Introduzca el entorno de la puerta de enlace al que asignar. Los valores posibles son **Prueba** y **Activo**. Debe establecer este campo en **Activo** solo para dispositivos y transacciones de producción. | Sí | Sí | Activo |
    | Divisas admitidas   | Introduzca las divisas que debe procesar el conector. En escenarios de tarjeta presente, Adyen puede admitir divisas adicionales a través de [Conversión dinámica de divisas](https://www.adyen.com/pos-payments/dynamic-currency-conversion) después de que la solicitud de transacción se envíe al terminal de pago. Póngase en contacto con el soporte de Adyen para obtener una lista de las divisas admitidas. | Sí | Sí | USD;EUR |
    | Tipos de forma de pago admitidos | Introduzca los tipos de forma de pago que debe procesar el conector. | Sí | Sí | ApplePay |

1. Una vez ingresada la información del comerciante, ejecute el trabajo de programación de distribución de configuración de canal **1070**.

## <a name="configure-commerce-pos-for-apple-pay"></a>Configurar PDV de Commerce para Apple Pay

La configuración de PDV utiliza la configuración del campo **Servicio EFT** del perfil de hardware para Dynamics 365 Payment Connector para Adyen. En Commerce headquarters, configure el servicio EFT para Dynamics 365 Payment Connector para Adyen como se describe en [Configurar una sección del perfil de hardware de Dynamics 365 POS](adyen-connector-setup.md#set-up-a-dynamics-365-pos-hardware-profile).

Asegúrese de agregar **ApplePay** a la lista de tipos de licitación en el campo **Tipos de licitación admitidos**. Utilice punto y coma (;) para separar los tipos de moneda de la lista.

La asignación de procesador para el conector Adyen capturará los tipos de tarjetas de cartera que usa Apple Pay en el terminal del PDV.

### <a name="configure-content-security-policies-in-site-builder"></a>Configurar políticas de seguridad de contenido en el creador de sitios

Antes de configurar sus fragmentos o páginas con Apple Pay, debe asegurarse de que sus directivas de seguridad de contenido (CSP) están configuradas en el generador de sitios de Commerce para su sitio.

Para configurar las directivas de seguridad de contenido en el generador de sitios, siga estos pasos.

1. Vaya a **Configuración del sitio \> Extensiones**.
1. En la pestaña **Directiva de seguridad de contenido**, seleccione **Agregar** para agregar una línea que tenga `https://applepay.cdn-apple.com/jsapi/v1/apple-pay-sdk.js` a las secciones **child-src**, **connect-src**, **frame-src**, **img-src**, **script-src** y **style-src**.
1. Cuando haya terminado, seleccione **Guardar y publicr** para confirmar los cambios.

### <a name="set-up-apple-pay-as-a-checkout-payment-option"></a>Configurar Apple Pay como una opción de pago

Para configurar Apple Pay como una opción de pago en la página de pago (no exprés) de su sitio, siga estos pasos.

1. En el generador de sitios, vaya a **Fragmentos** y seleccione el fragmento de finalización de compra de su sitio.
1. Seleccione **Editar**.
1. En la ranura **Contenedor de sección de finalización de compra**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Apple Pay** y, a continuación, **Aceptar**.
1. Seleccione **Guardar**.
1. Seleccione **Finalizar edición** para comprobar en el fragmento y luego seleccione **Publicar** para publicarlo.

Las configuraciones para el módulo **Apple Pay** están integradas en el módulo y se conectan con el conector de Dynamics 365 Payment Connector para Apple Pay configurado para el canal en línea en Commerce headquarters.

### <a name="apple-pay-payment-behavior"></a>Comportamiento de pago de Apple Pay

El botón de pago de **Apple Pay** solo se muestra en dispositivos compatibles con Apple Pay (iPhones, iPads y navegadores Safari compatibles con Apple Pay). Si un usuario no está usando uno de estos dispositivos, el botón de pago de **Apple Pay** está oculto a la vista.

Cuando un usuario selecciona el botón de pago de **Apple Pay**, aparece el cuadro de diálogo **Apple Pay**. Allí, el usuario puede autenticarse en su dispositivo o navegador Apple Pay. El cuadro de diálogo **Apple Pay** muestra un resumen del monto del pedido y el método de pago que el usuario ha configurado en su Apple Wallet. El usuario puede revisar estos detalles y luego seleccionar **Pagar** para completar el pago. Una vez que se completa el pago, el usuario es dirigido a la página del sitio **Pedido completado** que muestra un resumen detallado del pedido para la transacción completada.

## <a name="additional-resources"></a>Recursos adicionales

[Preguntas frecuentes sobre pagos](payments-retail.md)

[Módulo de finalización de compra](../add-checkout-module.md)

[Módulo de pago](../payment-module.md)
