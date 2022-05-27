---
title: Crear plantillas de correo electrónico para eventos transaccionales
description: Este tema describe cómo crear, cargar y configurar plantillas de correo electrónico para eventos transaccionales en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 08e247bac577dc0bb8a4635d61f0082793380da9
ms.sourcegitcommit: 602a319f4720b39a56b7660b530236912d484391
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "8722528"
---
# <a name="create-email-templates-for-transactional-events"></a>Crear plantillas de correo electrónico para eventos transaccionales

[!include [banner](includes/banner.md)]


Este tema describe cómo crear, cargar y configurar plantillas de correo electrónico para eventos transaccionales en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce proporciona una solución lista para usar para enviar correos electrónicos que alertan a los clientes sobre eventos transaccionales. Por ejemplo, se pueden enviar correos electrónicos cuando se realiza un pedido, cuando está listo para su recogida o cuando se ha enviado. Este tema describe los pasos para crear, cargar y configurar las plantillas de correo electrónico que se utilizan para enviar correos electrónicos transaccionales.

## <a name="notification-types"></a>Tipos de notificación

Las notificaciones se pueden configurar para informar a los clientes por correo electrónico cuando ocurren eventos específicos como parte del pedido y del ciclo de vida del cliente. Para configurar las notificaciones, debe asignar una plantilla de correo electrónico a un tipo de notificación creando un perfil de notificación de correo electrónico de Commerce. Para obtener información sobre cómo configurar perfiles de notificación de correo electrónico, consulte [Configurar un perfil de notificación de correo electrónico](email-notification-profiles.md).

Dynamics 365 Commerce admite los siguientes tipos de notificación.

### <a name="order-created"></a>Pedido creado

El tipo de notificación *Pedido creado* se activa cuando se crea un nuevo pedido de venta en la sede de Commerce.

> [!NOTE]
> El tipo de notificación de pedido creado no se activa para transacciones de pago al contado sin entrega a domicilio que se producen en un terminal de punto de venta (POS). En este caso, se genera un recibo enviado por correo electrónico o impreso. Para más información, consulte [Enviar recibos por correo electrónico desde Modern POS (MPOS)](email-receipts.md).

### <a name="order-confirmed"></a>Pedido confirmado

El tipo de notificación *Pedido confirmado* se activa cuando se genera un documento de confirmación de pedido para un pedido de ventas de la sede de Commerce.

### <a name="picking-completed"></a>Picking completado

El tipo de notificación *Recogida completada* se activa cuando una lista de selección de un pedido se marca como completada en la sede de Commerce.

> [!NOTE]
> El tipo de notificación de recogida completada no se activa cuando un artículo se marca como recogido en un terminal del PDV.

### <a name="packing-completed"></a>Embalaje completado

El tipo de notificación *Albarán completado* se activa cuando se genera un documento de albarán para un pedido en la sede de Commerce en un terminal del PDV.

El tipo de notificación de albarán completado admite los siguientes marcadores de posición de correo electrónico adicionales para facilitar la funcionalidad de "pedido listo para recoger" y la búsqueda de pedidos a partir de correos electrónicos transaccionales.

| Nombre de marcador de posición    | Propósito |
| ------------------- | ------- |
| `pickupstorename`     | El nombre de la tienda donde está disponible el pedido para recogerlo. |
| `pickupstoreaddress`  | La dirección de la tienda donde está disponible el pedido para recogerlo. |
| `pickupstoreopenfrom` | La hora de apertura de la tienda de recogida. |
| `pickupstoreopento` | La hora de cierre de la tienda de recogida. |
| `pickupchannelid`     | El ID del canal de la tienda de recogida. |
| `packingslipid`      | El ID del albarán del pedido que se recogerá. |
| `confirmationid`      | El ID de la confirmación del pedido que se recogerá. (Este ID a veces se denomina ID de referencia del canal). |

Para obtener más información sobre las funciones de registro de clientes y búsqueda de pedidos, consulte [Configurar la detección geográfica y la redirección](geo-detection-redirection.md) y [Habilitar la búsqueda de pedidos para los pagos de invitados](order-lookup-guest.md).

### <a name="order-ready-for-pickup"></a>Pedido listo para su recogida

El tipo de notificación *Pedido listo para recoger* se activa cuando un pedido se marca como embalado y el modo de entrega se establece en **El cliente lo recoge** en una o más líneas de pedido.

> [!NOTE]
> El tipo de notificación de pedido listo para recoger ha quedado obsoleto en favor del tipo de notificación de embalaje completado. Este tipo de notificación se personaliza según el modo de envío.

### <a name="order-shipped"></a>Pedido enviado

El tipo de notificación *Pedido enviado* se activa cuando se factura un pedido que tiene un modo de entrega sin recogida en tienda.

> [!NOTE]
> El tipo de notificación de pedido enviado ha quedado obsoleto en favor del tipo de notificación de pedido facturado. Este tipo de notificación se personaliza según el modo de envío.

### <a name="order-invoiced"></a>Pedido facturado

El tipo de notificación *Pedido facturado* se activa cuando un pedido se factura en el PDV o en la sede de Commerce.

### <a name="issue-gift-card"></a>Emitir tarjeta regalo

El tipo de notificación *Emisión de tarjeta de regalo* se activa cuando se factura un pedido de ventas que contiene un producto del tipo de tarjeta de regalo.

> [!NOTE]
> El correo electrónico de notificación de emisión de la tarjeta de regalo se envía al destinatario de la tarjeta de regalo. El destinatario de la tarjeta de regalo se especifica en la sede de Commerce, en una línea de pedido de ventas en la pestaña **Embalaje**, en **Detalles de línea**. Se puede especificar de forma manual o mediante programación.

El tipo de notificación de emisión de tarjeta de regalo admite los siguientes marcadores de posición adicionales.

| Nombre de marcador de posición      | Propósito |
| --------------------- | ------- |
| `giftcardnumber`        | Número de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| `availablebalance` | El saldo restante en la tarjeta regalo. |
| `giftcardmessage`       | Mensaje de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| `giftcardpin`         | Número de identificación personal (PIN) de la tarjeta regalo, para productos del tipo de tarjeta regalo. (Este marcador de posición es específico para tarjetas de regalo externas). |
| `giftcardexpiration`    | Fecha de vencimiento de la tarjeta regalo, para productos del tipo de tarjeta regalo. (Este marcador de posición es específico para tarjetas de regalo externas). |
| `giftcardrecipientname` | Nombre del destinatario de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| `giftcardbuyername`     | Nombre del comprador de la tarjeta regalo, para productos del tipo de tarjeta regalo. |

Para obtener más información acerca de las tarjetas de regalo, consulte [Tarjetas regalo digitales de comercio electrónico](digital-gift-cards.md) y [Asistencia para tarjetas de regalo externas](dev-itpro/gift-card.md).

### <a name="order-cancellation"></a>Cancelación del pedido

El tipo de notificación *Pedido cancelado* se activa cuando un pedido se cancela en la sede de Commerce.

### <a name="customer-created"></a>Cliente creado

El tipo de notificación *Cliente creado* se activa cuando se crea una nueva entidad de cliente en la sede de Commerce.

### <a name="b2b-prospect-approved"></a>Cliente potencial B2B aprobado

El tipo de notificación *Cliente potencial B2B aprobado* se activa cuando se aprueba la solicitud de incorporación de un cliente potencial en la sede de Commerce. Para obtener más información sobre cómo aprobar o rechazar clientes potenciales B2B, consulte [Configurar el usuario administrador para un nuevo socio comercial](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

El tipo de notificación de cliente potencial B2B aprobado admite los siguientes marcadores de posición adicionales.

| Nombre de marcador de posición | Propósito                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`       | El nombre del cliente potencial B2B tal como se introduce en la aplicación. |
| `lastname`         | El apellido del cliente potencial B2B tal como se introduce en la aplicación. |
| `company`          | El nombre de la empresa del candidato tal como se introduce en la aplicación. |
| `email`            | El correo electrónico del cliente potencial tal como se introduce en la aplicación.   |
| `zipcode`          | El código postal de la dirección principal del cliente potencial. |
| `comments`         | El comentario que el cliente potencial introdujo en la aplicación. |
| `storename`        | El nombre del canal en el que se creó el cliente potencial. |
| `storeurl`         | Vacío por defecto. Se debe crear una extensión personalizada para usar este marcador de posición. |

### <a name="b2b-prospect-rejected"></a>Cliente potencial B2B rechazado

El tipo de notificación *Cliente potencial B2B rechazado* se activa cuando se rechaza la solicitud de incorporación de un cliente potencial en la sede de Commerce. Para obtener más información sobre cómo aprobar o rechazar clientes potenciales B2B, consulte [Configurar el usuario administrador para un nuevo socio comercial](b2b/manage-b2b-users.md#set-up-the-administrator-user-for-a-new-business-partner). 

El tipo de notificación de cliente potencial B2B rechazado admite los siguientes marcadores de posición adicionales.

| Nombre de marcador de posición | Propósito                                                      |
| ---------------- | ------------------------------------------------------------ |
| `firstname`        | El nombre del cliente potencial B2B tal como se introduce en la aplicación. |
| `lastname`         | El apellido del cliente potencial B2B tal como se introduce en la aplicación. |
| `company`          | El nombre de la empresa del candidato tal como se introduce en la aplicación. |

## <a name="create-an-email-template"></a>Crear una plantilla de correo electrónico

Antes de poder asignar un evento transaccional específico a una plantilla de correo electrónico, debe crear la plantilla.

Para crear una plantilla de correo electrónico, siga estos pasos:

1. En la sede de Commerce, vaya a **Comercio minorista y Commerce \> Configuración de sede \> Plantillas de correo electrónico de organización** o **Administración de la organización \> Configuración \> Plantillas de correo electrónico de organización**.
1. Seleccione **Nuevo**.
1. En **General**, configure los siguientes campos:

    - **Id. de correo electrónico**: el id. de correo electrónico es el identificador único de una plantilla. Es el valor que se muestra cuando selecciona una plantilla para asignarla a un evento.
    - **Descripción del correo electrónico**: puede usar este campo opcional para proporcionar una descripción de la plantilla. El valor que introduzca aparece solo en la Central de Commerce.
    - **Nombre del remitente** el nombre que introduzca aparece en el campo "de" de la mayoría de los clientes de correo electrónico.
    - **Correo electrónico del remitente**: introduzca la dirección de correo electrónico que se debe usar para los correos electrónicos que se envían utilizando esta plantilla.
    - **Código de idioma predeterminado**: este campo especifica la versión localizada del correo electrónico que se envía por defecto, si el canal que invoca esta plantilla especifica ningún idioma.

1. En **Contenido del mensaje de correo electrónico**, seleccione **Nuevo**.
1. En el campo **Idioma**, introduzca el idioma para la plantilla de correo electrónico. Puede agregar más idiomas y plantillas localizadas más adelante.
1. En el campo **Tema**, introduzca el asunto del correo electrónico que debe aparecer en el campo del asunto del correo electrónico.
1. Seleccione **Editar** para cargar su plantilla de correo electrónico.

## <a name="create-an-email-message-body-by-using-html"></a>Crear un cuerpo de mensaje de correo electrónico utilizando HTML

El cuerpo del mensaje de su correo electrónico está compuesto en HTML. Puede usar cualquier diseño, estilo y marca que permitan el HTML y las hojas de estilo en cascada en línea (CSS). También puede usar imágenes, si las aloja en un punto final web disponible públicamente. Para agregar una imagen, introduzca la dirección URL de la imagen en el atributo **src** de la etiqueta HTML **&lt;img&gt;**.

> [!NOTE]
> Los clientes de correo electrónico imponen limitaciones de diseño y estilo que pueden requerir ajustes en el HTML y el CSS que utiliza para el cuerpo del mensaje. Le recomendamos que se familiarice con las prácticas recomendadas para crear HTML que los clientes de correo electrónico más populares admitan.

## <a name="add-placeholders-to-the-email-message-body"></a>Agregar marcadores de posición al cuerpo del mensaje de correo electrónico

Su correo electrónico puede contener marcadores de posición que se reemplazan con valores específicos del cliente y de la transacción cuando se genera el correo electrónico. Los marcadores de posición siempre están rodeados por signos de porcentaje (%) y se insertan directamente en el documento HTML.

He aquí un ejemplo.

```html
<p>
    Hello %customername%,<br />
    Order number %salesid%, can be picked up from the <b>%pickupstorename%</b> store.
</p>
```

### <a name="order-placeholders-sales-order-level"></a>Marcadores de posición de pedido (nivel de pedido de ventas)

Los siguientes marcadores de posición recuperan y muestran datos definidos en el nivel de pedido de ventas (en oposición al nivel de línea de ventas).

| Nombre de marcador de posición     | Propósito                                                      |
| -------------------- | ------------------------------------------------------------ |
| `customername`         | El nombre del cliente que hizo el pedido.               |
| `customeraddress`      | Dirección del cliente.                                 |
| `customeremailaddress` | La dirección de correo electrónico que el cliente introdujo al finalizar la compra.     |
| `salesid`              | El id. de ventas del pedido.                                   |
| `orderconfirmationid`  | Id. de canal cruzado que se generó en la creación del pedido.   |
| `channelid`            | Id. del canal minorista o en línea a través del cual se realizó el pedido. |
| `deliveryname`         | Nombre que se especifica para la dirección de entrega.         |
| `deliveryaddress`      | Dirección de entrega de los pedidos enviados.                     |
| `deliverydate`         | Fecha de entrega.                                           |
| `shipdate`             | Fecha de envío.                                               |
| `modeofdelivery`       | Modo de entrega del pedido.                              |
| `ordernetamount`       | Importe total del pedido, menos los impuestos totales.         |
| `discount`            | Descuento total del pedido.                            |
| `charges`              | Cargos totales del pedido.                             |
| `tax`                  | Impuestos totales del pedido.                                 |
| `total`                | Importe total del pedido.                              |
| `storename`            | Nombre de la tienda en que se hizo el pedido.            |
| `storeaddress`         | Dirección de la tienda que hizo el pedido.              |
| `storeopenfrom`        | Hora de apertura de la tienda que hizo el pedido.         |
| `storeopento`          | Hora de cierre de la tienda que hizo el pedido.         |
| `pickupstorename`      | Nombre de la tienda en la que se recogerá el pedido.\*   |
| `pickupstoreaddress`   | Dirección de la tienda en la que se recogerá el pedido.\* |
| `pickupopenstorefrom`  | Hora de apertura de la tienda en la que se recogerá el pedido.\* |
| `pickupopenstoreto`    | Hora de cierre de la tienda en la que se recogerá el pedido.\* |
| `pickupchannelid`     | Id. de canal de la tienda que se especifica para un modo de entrega de recogida.\* |
| `packingslipid`        | Id. del albarán que se generó cuando se empaquetaron las líneas de un pedido.\* |

\* Estos marcadores de posición devuelven datos solo cuando se utilizan para el tipo de notificaicón **Pedido listo para recoger**. 

### <a name="order-line-placeholders-sales-line-level"></a>Marcadores de posición de línea (nivel de línea de ventas)

Los siguientes marcadores de posición recuperan y muestran datos de productos individuales (líneas) en el pedido de ventas.

| Nombre de marcador de posición               | Propósito |
|--------------------------------|-------------------|
| `productid`                      | <p>El id. del producto. Este id. tiene en cuenta las variantes.</p><p><strong>Nota:</strong> este marcador de posición ha quedado en desuso en favor de `lineproductrecid`.</p> |
| `lineproductrecid`               | El id. del producto. Este id. tiene en cuenta las variantes. Identifica de forma única un artículo en el nivel de variante. |
| `lineitemid`                     | Id. de nivel de producto del producto. (Este id. tiene en cuenta las variantes.) |
| `lineproductvariantid`           | El id. de la variante del producto. |
| `lineproductname`                | El nombre del producto. |
| `lineproductdescription`         | Descripción del producto. |
| `linequantity`                   | Número de unidades que se pidieron para la línea, más la unidad de medida (por ejemplo, **ea** o **par**). |
| `lineunit`                       | Unidad de medida para la línea. |
| `linequantity_withoutunit`       | Número de unidades que se pidieron para la línea, sin unidad de medida. |
| `linequantitypicked`             | Cuando se usa el evento **PickOrder**, el número de unidades que se recogieron. En caso contrario, **0** (cero). |
| `linequantitypicked_withoutunit` | Cuando se usa el evento **PickOrder**, el número de unidades que se recogieron, sin unidad de medida. En caso contrario, **0** (cero). |
| `linequantitypacked`             | Cuando se usan los eventos **PackOrder** y **Pedido listo para recoger**, el número de unidades que se empaquetaron. En caso contrario, **0** (cero). |
| `linequantitypacked_withoutuom`  | Cuando se usan los eventos **PackOrder** y **Pedido listo para recoger**, el número de unidades que se empaquetaron, sin unidad de medida. En caso contrario, **0** (cero). |
| `linequantityshipped`            | Siempre **0**, excepto cuando se utilizan eventos específicos, como se describe en la siguiente fila. |
| `linequantityshipped_withoutuom` | Cuando se usa el evento **ShipOrder**, el número de unidades que se recogieron, sin unidad de medida. En caso contrario, **0** (cero). |
| `lineprice`                      | El precio de una sola unidad. |
| `linenetamount`                  | Se aplica el precio de la línea, según el número de unidades y el descuento. |
| `linediscount`                   | Descuento para una unidad individual. |
| `lineshipdate`                   | Fecha de envío de la línea. |
| `linedeliverydate`               | Fecha de entrega para la línea. |
| `linedeliverymode`               | Modo de entrega para la línea. |
| `linedeliveryaddress`            | Dirección de entrega para la línea. |
| `linepickupdate`                 | Fecha de recogida que especificó el cliente, para pedidos que utilizan un modo de recogida de entrega. |
| `linepickuptimeslot`             | Intervalo de tiempo de recogida que especificó el cliente, para pedidos que utilizan un modo de recogida de entrega. |
| `giftcardnumber`                 | Número de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| `giftcardbalance`                | Saldo de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| `giftcardmessage`                | Mensaje de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| `giftcardpin`                    | El PIN de la tarjeta regalo, para productos del tipo de tarjeta regalo. (Este marcador de posición es específico para tarjetas de regalo externas). |
| `giftcardexpiration`             | Fecha de vencimiento de la tarjeta regalo, para productos del tipo de tarjeta regalo. (Este marcador de posición es específico para tarjetas de regalo externas). |
| `giftcardrecipientname`          | Nombre del destinatario de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| `giftcardbuyername`              | Nombre del comprador de la tarjeta regalo, para productos del tipo de tarjeta regalo. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Formato de marcadores de posición de línea de pedido en el cuerpo del mensaje de correo electrónico

Cuando cree el HTML para las líneas de pedido individuales en el cuerpo del mensaje de correo electrónico, rodee el bloque repetitivo de HTML y los marcadores de posición para las líneas con los siguientes marcadores de posición. Observe que los marcadores de posición están dentro de las etiquetas de comentarios HTML.

```html
<!--%tablebegin.salesline%-->

(Insert the repeating block of HTML and placeholders for individual lines here.)

<!--%tableend.salesline%-->
```

He aquí un ejemplo.

```HTML
<table>
    <tr>
        <td>Product name</td>
        <td>Quantity</td>
        <td>Price</td>
    </tr>
    <!--%tablebegin.salesline%-->
    <tr>
        <td>%lineproductname%</td>
        <td>%linequantity_withoutunit%</td>
        <td>%lineprice%</td>
    </tr>
    <!--%tableend.salesline%-->
</table>
```

## <a name="create-a-template-for-emailed-receipts"></a>Crear una plantilla para recibos enviados por correo electrónico

Los recibos pueden enviarse por correo electrónico a los clientes que realizan compras en un punto de venta (POS) minorista. En general, los pasos para crear la plantilla de recibo enviado por correo electrónico son los mismos que los pasos para crear plantillas para otros eventos transaccionales. Sin embargo, se requieren los siguientes cambios:

- El texto del recibo se inserta en el correo electrónico utilizando el marcador de posición **%message%**. Para asegurarse de que el cuerpo del recibo se representa correctamente, rodee el marcador de posición **%message%** con las etiquetas HTML **&lt;pre&gt;** y **&lt;/pre&gt;**.
- El marcador de posició **%receiptid%** se puede utilizar para mostrar un código QR o un código de barras que representa el id. del recibo. (Los códigos QR y los códigos de barras son generados dinámicamente y servidos por un servicio de terceros). Para obtener más información sobre cómo mostrar un código QR o un código de barras en un recibo enviado por correo electrónico, consulte [Agregar un código QR o un código de barras a los correos electrónicos transaccionales y de recibos](add-qr-code-barcode-email.md).

## <a name="upload-the-email-html"></a>Cargar el HTML del correo electrónico

Una vez que haya creado y probado el HTML para el cuerpo del mensaje, debe cargarlo en la Central de Commerce. Actualmente, el HTML del correo electrónico no se puede exportar. Por lo tanto, debe mantener la copia maestra de su HTML fuera de la Central de Commerce.

Para cargar un HTML de plantilla de correo electrónico nuevo o editado, siga estos pasos.

1. En la central de Commerce, vaya a **Retail y Commerce \> Configuración de la central \> Plantillas de correo electrónico de la organización**.
1. Seleccione la fila del idioma para el que desea agregar o reemplazar HTML. Alternativamente, seleccione **Nuevo** para crear una fila para un nuevo idioma.
1. Seleccione **Editar**.
1. En el cuadro de diálogo que aparece, seleccione **Explorar**. Busque el documento HTML que desea cargar, selecciónelo y luego seleccione **Abierto**.
1. Seleccione **Cargar**.
1. Después de que el correo electrónico HTML aparezca en la ventana de vista previa, seleccione **Aceptar**.
1. Asegúrese de que esté seleccionada la casilla **Con cuerpo** para la fila.

Si ya configuró la Central de Commerce para enviar correos electrónicos, su correo electrónico nuevo o actualizado se enviará a todos los clientes que realicen una transacción que invoque el evento asignado a la plantilla.

Para obtener más información sobre cómo configurar correos electrónicos en Dynamics 365 Commerce, consulte [Configurar y enviar correos electrónicos](../fin-ops-core/fin-ops/organization-administration/configure-email.md).

## <a name="additional-resources"></a>Recursos adicionales 

[Configurar perfil de notificación por correo electrónico](email-notification-profiles.md)

[Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md)

[Configurar recepciones por correo electrónico](/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Enviar recibos por correo electrónico desde PDV modernos ](email-receipts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
