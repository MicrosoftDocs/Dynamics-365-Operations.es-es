---
title: Módulo de pago
description: En este artículo se trata el modulo de pago y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: fa1482cb73a40df5f9bc9d3037196def71accf18
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279485"
---
# <a name="payment-module"></a>Módulo de pago

[!include [banner](includes/banner.md)]

En este artículo se trata el modulo de pago y se explica la forma de configurarlo en Microsoft Dynamics 365 Commerce.

El módulo de pago permite a los clientes pagar pedidos con tarjetas de crédito o débito. La integración de pagos para este módulo la proporciona el connector de pagos de Dynamics 365 para Adyen. Para obtener más información sobre cómo instalar y configurar el conector de pagos, consulte [Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md).  

A partir de la versión 10.0.14 de Commerce, el módulo de pago también se ha integrado con Dynamics 365 Payment Connector para PayPal para permitir que los clientes paguen sus pedidos mediante PayPal. Para obtener más información sobre cómo instalar y configurar el Dynamics 365 Payment Connector para PayPal, consulte [Dynamics 365 Payment Connector para PayPal](paypal.md). 

## <a name="dynamics-365-payment-connector-for-adyen"></a>Conector de pago de Dynamics 365 para Adyen 

El módulo de pago aloja la información de pagos que se proporciona a través de Adyen en un marco en línea HTML (iframe). El módulo de pago interactúa con la Commerce Scale Unit para obtener la información de pagos de Adyen. Como parte de la interacción de la Commerce Scale Unit, el módulo de pago puede permitir que la información de la dirección de facturación se proporcione en el iFrame a través de Adyen o como un módulo independiente. En el tema Fabrikam, la dirección de facturación habilita como un módulo independiente. Este enfoque permite una mayor flexibilidad de formato, ya que las líneas de dirección se pueden representar para que se parezcan a las líneas de la dirección de envío.

El módulo de pago también permite a los clientes registrados guardar su información de pago. La información de pago y la dirección de facturación se guardan y gestionan a través del conector de pago de Adyen.

El módulo de pago cubre cualquier gasto de pedido que aún no esté cubierto por puntos de fidelidad o una tarjeta regalo. Si el total de un pedido está totalmente cubierto por puntos de fidelidad o créditos de tarjetas regalo, el módulo de pago se ocultará y el cliente podrá realizar el pedido sin él.

El conector de pago de Adyen también admite la autenticación segura de clientes (SCA). Parte de la Directiva de servicios de pago (PSD2) revisado de la Unión Europea (UE) requiere que los compradores en línea estén autenticados fuera de su experiencia de compra en línea cuando utilicen un método de pago electrónico. Durante el proceso de finalización de la compra, los clientes son redirigidos a su sitio bancario y luego, después de la autenticación, son redirigidos de nuevo al proceso de finalización de la compra de Commerce. Durante esta redirección, la información introducida por un cliente durante la finalización de compra (por ejemplo, la dirección de envío, las opciones de entrega, la información de la tarjeta regalo y la información de puntos de fidelidad) persistirá. Para poder activar esta característica en el conector de pagos de Adyen, el conector de pago debe configurarse para SCA en la sede de Commerce. Para obtener más información, consulte [Autenticación segura de clientes mediante Adyen](adyen_redirect.md). Esta característica se habilitó en la versión 10.0.12 de Commerce.

> [!NOTE]
> Para el conector de pago de Adyen, el módulo iframe del módulo de pago solo se puede procesar si agrega la URL de Adyen a la lista de permitidos del sitio. Para completar este paso, agregue **\*.adyen.com** a las directivas **child-src**, **connect-src**, **img-src**, **script-src** y **style-src** de la directiva de seguridad del contenido del sitio. Para obtener más información, consulte [Administrar la directiva de seguridad de contenido](manage-csp.md). 

La siguiente ilustración muestra un ejemplo de módulos de tarjeta regalo, puntos de fidelidad y pago de Adyen en una página de finalización de compra.

![Ejemplo de módulos de tarjeta regalo, puntos de fidelidad y pago de Adyen en una página de finalización de compra.](./media/ecommerce-payments.PNG)

## <a name="dynamics-365-payment-connector-for-paypal"></a>Dynamics 365 Payment Connector para PayPal

A partir de la versión 10.0.14 de Commerce, el módulo de pago también está integrado con Dynamics 365 Payment Connector para PayPal. Para obtener más información sobre cómo instalar y configurar este conector de pagos, consulte [Dynamics 365 Payment Connector para PayPal](paypal.md).
 
En la página de pago, puede tener configurados los conectores de Adyen y PayPal. El módulo de pago se ha mejorado con propiedades adicionales para ayudar a identificar con qué conector debería funcionar. Para obtener detalles, consulte las propiedades del módulo **Tipos de formas de pago admitidos** y **Es un pago primario** en la siguiente tabla.
  
Cuando el módulo de pago está configurado para utilizar el conector de pago de PayPal, aparece un botón de PayPal en la página de pago. Cuando el cliente lo invoca, el módulo de pago genera un iFrame que contiene información de PayPal. El cliente puede iniciar sesión y proporcionar su información de PayPal dentro de este iFrame para completar su transacción. Cuando un cliente elige pagar con PayPal, el saldo restante del pedido se cargará a través de PayPal.

El conector de pago de PayPal no requiere un módulo de dirección de facturación porque PayPal gestiona toda la información relacionada con la facturación dentro de su iFrame. Sin embargo, se requieren los módulos de dirección de envío y opciones de entrega.

La siguiente ilustración muestra un ejemplo de dos módulos de pago en una página de pago, uno configurado con el conector de pago de Adyen y el otro con el conector de pago de PayPal.
![Ejemplo de módulos de pago de Adyen y PayPal en una página de finalización de compra.](./media/ecommerce-paypal.png)

La siguiente ilustración muestra un ejemplo del iFrame de PayPal invocado mediante el botón de PayPal. 
![Ejemplo del iFrame de Paypal en una página de pago.](./media/ecommerce-paypal-iframe.png)

## <a name="payment-module-properties"></a>Propiedades del módulo de pago

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera | Texto del encabezado | Un encabezado opcional para el módulo de pago. |
| Altura del iframe | Píxeles | La altura del iframe, en píxeles. La altura se puede ajustar según sea necesario. |
| Mostrar dirección de facturación | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, Adyen proporcionará la dirección de facturación dentro del iframe del módulo de pago. Si se configura en **Falso**, Adyen no proporcionará la dirección de facturación y un usuario de Commerce tendrá que configurar un módulo para mostrar la dirección de facturación en la página de finalización de compra. Para el conector de pago de PayPal, este campo no tiene ningún impacto, ya que la dirección de facturación se gestiona por completo dentro de PayPal. |
| Anulación de estilo de pago | Código de hojas de estilo en cascada (CSS) | Como el módulo de pago está alojado en un iframe, la capacidad de estilos es limitada. Puede lograr aplicar estilos con esta propiedad. Para reemplazar los estilos del sitio, debe pegar el código CSS como valor de esta propiedad. Los estilos y reemplazos de CSS del generador de sitios no se aplican a este módulo. |
|Tipos de forma de pago admitidos| Cadena| Si se configuran varios conectores de pago, debe proporcionar la cadena de tipo de pago admitido como se define en la configuración del conector de pago de la sede de Commerce (consulte la siguiente imagen). Si está en blanco, se establece de forma predeterminada en el conector de pago de Adyen. Agregado en la versión 10.0.14 de Commerce.|
|Es pago primario|  **Verdadero** o **Falso** | Si se establece en **True**, cualquier mensaje de error se generará desde el conector de pago principal en la página de pago. Si los conectores de pago de Adyen y PayPal están configurados, configure Adyen en **True**, el cual se agregó en la versión 10.0.14 de Commerce.|
|Usar id. de conector| **Verdadero** o **Falso** | Utilice esta propiedad si se configuran varios conectores de pago para el sitio. Si es **True**, los conectores deberán usar la id. del conector para la correlación de pagos.|
|Utilice el código de idioma establecido por el navegador para iFrame|  **Verdadero** o **Falso** | (Solo Adyen) Si es **True**, el Adyen iFrame representará el idioma en función del contexto del navegador del usuario del sitio, en lugar de usar el código de idioma del canal de Commerce configurado para el sitio. Agregado en la versión 10.0.27 de Commerce.|

La siguiente ilustración muestra un ejemplo de valor **Tipos de formas de pago admitidos** establecido en "PayPal" en la configuración del conector de pago en la sede central de Commerce.
![Ejemplo de tipos de formas de pago admitidos en la sede central de Commerce.](./media/ecommerce-paymenttendertypes.png)

## <a name="billing-address"></a>Dirección de facturación

Se puede usar un módulo de dirección de facturación en la página de finalización de la compra si las líneas de dirección de facturación del conector de pago de Adyen no coinciden lo suficiente con la apariencia del resto del sitio. 

Para usar un módulo de dirección de facturación en la página de finalización de la compra cuando el módulo de pago está integrado con el conector de pago de Adyen, configure la propiedad **Mostrar dirección de facturación** en **False** para que se pueda utilizar un módulo de dirección de facturación dedicado en lugar de la dirección de facturación predeterminada de Adyen. En este caso, el autor del sitio debe incluir un módulo de dirección de facturación en la página de pago. El conector de pago de Adyen también permite la capacidad de utilizar la dirección de envío como dirección de facturación para minimizar el número de pasos para el usuario del sitio.

Similar a los módulos de pago, una propiedad **Tipos de formas de pago admitidos** se ha agregado al módulo de dirección de facturación en la versión 10.0.14 de Commerce. El valor de esta propiedad debe ser idéntico al valor proporcionado en el módulo de pago para garantizar que funcionen juntos. Para el conector de pago de Adyen, tanto el módulo de pago como el módulo de dirección de facturación deben dejar este valor en blanco (el estado predeterminado). Para el conector de PayPal, no se requiere un módulo de dirección de facturación dedicado. Para otros tipos de conectores de pago, la cadena debe proporcionarse como se configuró en la sede central de Commerce.

## <a name="add-a-payment-module-to-a-checkout-page-and-set-the-required-properties"></a>Agregar un módulo de pago a una página de finalización de compra y establecer las propiedades necesarias

Un módulo de pago solo se puede agregar a un módulo de finalización de compra. Para obtener más información acerca de cómo configurar un módulo de pago para una página de finalización de compra, consulte [Módulo de finalización de compra](add-checkout-module.md).

## <a name="configure-the-adyen-and-paypal-payment-connectors-when-both-are-used"></a>Configurar los conectores de pago de Adyen y PayPal cuando se utilizan ambos

Si se utilizarán los conectores de pago de Adyen y PayPal para su sitio, siga estos pasos en el creador de sitios de Commerce para agregar módulos de pago para cada conector al módulo de pago y luego configure las propiedades para cada módulo.

1. En el panel de propiedades del módulo de pago de PayPal, siga estos pasos:

    1. En el campo para la propiedad **Tipos de licitación admitidos**, introduzca **Paypal**.
    1. Desactive la casilla de verificación de la propiedad **Es pago primario**.
    1. Seleccione la casilla de verificación para la propiedad **Usar ID de conector**.

1. En el panel de propiedades del módulo de pago de Adyen, siga estos pasos:

    1. Deje en blanco el campo para la propiedad **Tipos de licitación admitidos**.
    1. Seleccione la casilla de verificación de la propiedad **Es pago primario**.
    1. Seleccione la casilla de verificación para la propiedad **Usar ID de conector**.

> [!NOTE]
> Cuando configura los conectores de Adyen y PayPal para que se utilicen juntos, la configuración del **Conector de pago de Dynamics 365 para Adyen** debe estar en la primera posición en la configuración del conector del canal en línea **Cuentas de pago** en la sede de Commerce. Para confirmar o cambiar el orden de los conectores, vaya a **Tiendas en línea** y seleccione el canal para su sitio. Entonces, en la pestaña **Configurar**, en la ficha desplegable **Cuentas de pago**, en **Conector**, asegúrese de que la configuración del **Conector de pago de Dynamics 365 para Adyen** está en la primera posición (es decir, en la línea superior), y que la configuración del **Conector de pago de Dynamics 365 para PayPal** está en la segunda línea. Agregue o elimine conectores según sea necesario para reordenarlos.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)

[Conector de pago de Dynamics 365 para Adyen](dev-itpro/adyen-connector.md)

[Dynamics 365 Payment Connector para PayPal](paypal.md)

[Autenticación segura de clientes mediante Adyen](adyen_redirect.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
