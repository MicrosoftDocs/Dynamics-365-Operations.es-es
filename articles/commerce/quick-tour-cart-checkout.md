---
title: Visión general de las páginas del carro y de la finalización de la compra
description: Este tema proporciona una visión general de las páginas de carro y finalización de pago en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4f7c708aa7f1a858e78cdbda809b90b944606022
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244801"
---
# <a name="cart-and-checkout-pages-overview"></a>Visión general de las páginas del carro y de la finalización de la compra

[!include [banner](includes/banner.md)]

Este tema proporciona una visión general de las páginas de carro y finalización de pago en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La página del carro de una sitio web de comercio electrónico muestra todos los artículos que un cliente ha agregado al carro. La página del carro se crea con el módulo del carro. El módulo del carro es un contenedor que hospeda todos los módulos que se necesitan para mostrar artículos en el carro. El módulo del carro puede usar otros módulos para mostrar el resumen de pedidos y los códigos promocionales que se han aplicado al pedido de cliente.

La página de finalización de compra de sitio web de comercio electrónico presenta un flujo detalles que los clientes pueden seguir para introducir toda la información necesaria para realizar un pedido. Un módulo de finalización de pago puede incluir módulos que administren la dirección de envío, los métodos de envío, la información de facturación, el resumen de pedidos y otra información relacionada con los pedidos de cliente.

## <a name="cart-page"></a>Página del carro

La página del carro sirve como el carro de la compara e incluye todos los artículos que se han agregado al carro.

En la siguiente ilustración se muestra un ejemplo de una página de carro que se creó mediante la biblioteca de módulos y el tema de “Fabrikam”.

![Ejemplo de una página de carro](./media/cart2.PNG)

El cuerpo principal de la página del carro muestra todos los artículos que el cliente ha agregado al carro. Se muestran todos los descuentos aplicables. Estos descuentos incluyen descuentos complejos. Entre los ejemplos se incluyen “Comprar 3 artículos y obtener el 10% de descuento“ o “Comprar una botella y una mochila para obtener el 10% de descuento”. El módulo de resumen de pedidos muestra el importe que se debe después de que se hayan aplicado los descuentos, el envío, los impuestos, etc. También un módulo de código de promoción que permite al cliente aplicar o quitar códigos promocionales.

Un cliente puede comprar de manera anónima o como un usuario que ha iniciado sesión. Si un cliente ha iniciado sesión, los artículos del carro se conservan entre sesiones. De esta manera, el cliente puede continuar haciendo compras desde varios dispositivos.

Desde el carro, el cliente puede continuar con la finalización de la compra. Un cliente puede iniciar la finalización de la compra como usuario invitado o como usuario que ha iniciado sesión.

Para obtener información acerca de cómo crear una página del carro, consulte [Agregar un módulo de carro a una página](add-cart-module.md).

## <a name="checkout-page"></a>Página Finalizar compra

La página de finalización de compra es donde los clientes especifican la información necesaria para realizar un pedido.

En la siguiente ilustración se muestra un ejemplo de una página de finalización de pago que se creó con la biblioteca de módulos.

![Ejemplo de una página de finalización de compra](./media/Checkout.PNG)

El cuerpo principal de página de finalización de compra es donde se recoge toda la información del pedido. Esta información incluye la dirección de envío, las opciones de entrega y la información de pago. La finalización de pago tiene un flujo detallado porque la información se debe especificar en un orden determinado de ser procesada. Por ejemplo, la dirección de envío se debe especificar antes de que se puedan calcular los costes de envío y se pueda autorizar el pago.

### <a name="shipping-address"></a>Dirección de envío

Se requiere una dirección de envío si se deben enviar los artículos. El formato de direcciones de envío para cada configuración regional se puede configurar en Dynamics 365 Commerce. Por ejemplo, si los artículos se envían a Estados Unidos, la dirección de envío debe incluir una dirección con el nombre de la calle, un estado y un código postal. Alguna validación de entrada básica se realiza para campos de dirección de envío, como una validación para caracteres alfanuméricos, longitud máxima y números. Aunque la validez de la propia dirección no está verificada, esta comprobación se puede realizar mediante servicios de terceros personalizados.

La dirección de envío se aplica a todos los artículos del carro para los que la opción “enviar” está seleccionada. Si utiliza el flujo de finalización de pago que se proporciona en la biblioteca de módulos, los elementos individuales del carro no se pueden enviar a direcciones diferentes. Si requiere esta capacidad, se puede implementar a través de la personalización de los módulos de finalización de compra.

Una vez que se proporciona la dirección de envío, se muestran los métodos de envío disponibles de la tienda en línea de Dynamics 365 Commerce. Los métodos de envío y las direcciones que admiten se pueden configurar en Commerce.

### <a name="payment"></a>Pago

El siguiente paso del flujo de finalización del pago es el pago. En comercio electrónico, se pueden usar varios métodos de pago para realizar pedidos, como tarjetas de crédito, tarjetas regalo y puntos de fidelización. También se puede usar una combinación de estas formas de pago. En función de las formas de pago que se usen, es posible que sea necesaria información adicional. Por ejemplo, un pago de tarjeta de crédito requiere una dirección de factura. Los pagos de tarjeta de crédito se procesan mediante el Adyen Payment Connector.

#### <a name="loyalty-points"></a>Puntos de fidelidad

Durante el flujo de finalización del pago, un cliente que es miembro de un programa de fidelización, y que ha acumulado puntos de fidelización, puede canjear esos puntos de fidelización por un pedido. El módulo de puntos de fidelización solo se muestra si el cliente tiene una suscripción existente de fidelización. Para usuarios invitados y no miembros, este módulo está oculto.

#### <a name="gift-cards"></a>Tarjetas regalo

La biblioteca de módulos permite que se canjeen las tarjetas regalo internas por un pedido. Para aplicar una tarjeta regalo interna, el cliente debe haber iniciado sesión. Para mayor seguridad, se recomienda que personalice el flujo mediante un número de identificación personal (PIN) para las tarjetas regalo internas.

### <a name="signed-in-and-guest-users"></a>Usuarios invitados y que han iniciado sesión

El cliente puede completar el proceso de finalización de compra como usuario invitado o como usuario que ha iniciado sesión. Si el cliente inicia sesión, se recupera automáticamente la información de la cuenta como direcciones de envío guardadas y detalles guardados de tarjetas de crédito.

### <a name="order-summary"></a>Resumen del pedido

La desprotección muestra un resumen de los artículos de línea del carro, de modo que el cliente pueda verificar el pedido antes de realizarlo. Los artículos de línea no se pueden editar durante el flujo de desprotección. Sin embargo, se proporciona un vínculo al carro en el caso de que el usuario desee volver y editar los artículos de línea.

Una vez que el cliente proporciona la información de envío y facturación, el resumen de pedidos refleja el importe debido una vez se han aplicado puntos de fidelización, tarjetas regalo y otros pagos.

### <a name="order-confirmation-and-email"></a>Correo electrónico y confirmación de pedido

Cuando el cliente realiza un pedido, se proporciona un número de confirmación. En este momento, el pago se ha autorizado pero no se ha cobrado. El pago solo se cobrará si se completa el pedido (es decir, cuando se envía o se recoge).

Una vez creado un pedido, se envía al cliente un correo electrónico de confirmación del pedido.

Para obtener más información acerca de cómo crear una página de finalización de compra, consulte [Agregar un módulo de finalización de compra a una página](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la página principal](quick-tour-home-page.md)

[Visión general de las páginas de detalles de producto](quick-tour-pdp.md)

[Visión general de las páginas de la gestión de cuentas](quick-tour-account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]