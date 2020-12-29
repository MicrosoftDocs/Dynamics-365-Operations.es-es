---
title: Crear plantillas de correo electrónico para eventos transaccionales
description: Este tema describe cómo crear, cargar y configurar plantillas de correo electrónico para eventos transaccionales en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ea484bfc1e9b293c53d7293c50630c4955000131
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415447"
---
# <a name="create-email-templates-for-transactional-events"></a>Crear plantillas de correo electrónico para eventos transaccionales

[!include [banner](includes/banner.md)]

Este tema describe cómo crear, cargar y configurar plantillas de correo electrónico para eventos transaccionales en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Dynamics 365 Commerce proporciona una solución inmediata para enviar correos electrónicos que alertan a los clientes sobre eventos transaccionales (por ejemplo, cuando se realiza un pedido, un pedido está listo para ser recogido o se ha enviado un pedido). Este tema describe los pasos para crear, cargar y configurar las plantillas de correo electrónico que se utilizan para enviar correos electrónicos transaccionales.

## <a name="create-an-email-template"></a>Crear una plantilla de correo electrónico

Antes de poder asignar un evento transaccional específico a una plantilla de correo electrónico, debe crear la plantilla.

Para crear una plantilla de correo electrónico, siga estos pasos:

1. En la central de Commerce, vaya a **Plantillas de correo electrónico de organización**, que está en **Retail y Commerce \> Configuración de central \> Plantillas de correo electrónico de organización** o **Administración de la organización \> Configuración \> Plantillas de correo electrónico de organización**.
1. Seleccione **Nuevo**.
1. En **General**, configure los siguientes campos:

    - **Id. de correo**: el id. de correo electrónico es el identificador único para una plantilla y es el valor que se muestra cuando selecciona una plantilla para asignarla a un evento.
    - **Descripción del correo electrónico**: puede usar este campo opcional para proporcionar una descripción de la plantilla. El valor que introduzca aparece solo en la Central de Commerce.
    - **Nombre del remitente** el nombre que introduzca aparece en el campo "de" de la mayoría de los clientes de correo electrónico.
    - **Correo electrónico del remitente**: introduzca la dirección de correo electrónico que se debe usar para los correos electrónicos que se envían utilizando esta plantilla.
    - **Código de idioma predeterminado**: este campo especifica la versión localizada del correo electrónico que se envía por defecto, si el canal que invoca esta plantilla no proporciona ningún idioma.

1. En **Contenido del mensaje de correo electrónico**, seleccione **Nuevo**.
1. En el campo **Idioma**, introduzca el idioma para la plantilla de correo electrónico. Puede agregar más idiomas y plantillas localizadas más adelante.
1. En el campo **Tema**, introduzca el asunto del correo electrónico que debe aparecer en el campo del asunto del correo electrónico.
1. Seleccione **Editar** para cargar su plantilla de correo electrónico.

## <a name="create-an-email-message-body-by-using-html"></a>Crear un cuerpo de mensaje de correo electrónico utilizando HTML

El cuerpo del mensaje de su correo electrónico está compuesto en HTML. Puede usar cualquier diseño, estilo y marca que permitan el HTML y las hojas de estilo en cascada en línea (CSS). También puede usar imágenes, si las aloja en un punto final web disponible públicamente. Para agregar una imagen, introduzca la dirección URL de la imagen en el atributo **src** de la etiqueta HTML **&lt;img&gt;**.

> [!NOTE]
> Los clientes de correo electrónico imponen limitaciones de diseño y estilo que pueden requerir ajustes en el HTML y el CSS que utiliza para el cuerpo del mensaje. Le recomendamos que se familiarice con las prácticas recomendadas para crear HTML que sea compatible con los clientes de correo electrónico más populares.

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

| Nombre de marcador de posición    | Valor de marcador de posición                                                |
|---------------------|------------------------------------------------------------------|
| customername        | El nombre del cliente que hizo el pedido.                   |
| salesid             | El id. de ventas del pedido.                                       |
| deliveryaddress     | Dirección de entrega de los pedidos enviados.                         |
| customeraddress     | Dirección del cliente.                                     |
| deliverydate        | Fecha de entrega.                                               |
| shipdate            | Fecha de envío.                                                   |
| modeofdelivery      | Modo de entrega del pedido.                                  |
| gastos             | Cargos totales del pedido.                                 |
| impuesto                 | Impuestos totales del pedido.                                     |
| total               | Importe total del pedido.                                  |
| ordernetamount      | Importe total del pedido, menos los impuestos totales.             |
| descuento            | Descuento total del pedido.                                |
| storename           | Nombre de la tienda en que se hizo el pedido.                |
| storeaddress        | Dirección de la tienda que hizo el pedido.                  |
| storeopenfrom       | Hora de apertura de la tienda que hizo el pedido.             |
| storeopento         | Hora de cierre de la tienda que hizo el pedido.             |
| pickupstorename     | Nombre de la tienda en la que se recogerá el pedido.         |
| pickupstoreaddress  | Dirección de la tienda en la que se recogerá el pedido.      |
| pickupopenstorefrom | Hora de apertura de la tienda en la que se recogerá el pedido. |
| pickupopenstoreto   | Hora de cierre de la tienda en la que se recogerá el pedido. |

### <a name="order-line-placeholders-sales-line-level"></a>Marcadores de posición de línea (nivel de línea de ventas)

Los siguientes marcadores de posición recuperan y muestran datos de productos individuales (líneas) en el pedido de ventas.

| Nombre de marcador de posición               | Valor de marcador de posición |
|--------------------------------|-------------------|
| productid                      | Id. del producto para la línea. |
| lineproductname                | El nombre del producto. |
| lineproductdescription         | Descripción del producto. |
| linequantity                   | Número de unidades que se pidieron para la línea, más la unidad de medida (por ejemplo, **ea** o **par**). |
| lineunit                       | Unidad de medida para la línea. |
| linequantity_withoutunit       | Número de unidades que se pidieron para la línea, sin unidad de medida. |
| linequantitypicked             | Cuando se usa el evento **PickOrder**, el número de unidades que se recogieron. En caso contrario, **0** (cero). |
| linequantitypicked_withoutunit | Cuando se usa el evento **PickOrder**, el número de unidades que se recogieron, sin unidad de medida. En caso contrario, **0** (cero). |
| linequantitypacked             | Cuando se usan los eventos **PackOrder** y **Pedido listo para recoger**, el número de unidades que se empaquetaron. En caso contrario, **0** (cero). |
| linequantitypacked_withoutuom  | Cuando se usan los eventos **PackOrder** y **Pedido listo para recoger**, el número de unidades que se empaquetaron, sin unidad de medida. En caso contrario, **0** (cero). |
| linequantityshipped            | Siempre **0**, excepto cuando se utilizan eventos específicos, como se describe en la siguiente fila. |
| linequantityshipped_withoutuom | Cuando se usa el evento **ShipOrder**, el número de unidades que se recogieron, sin unidad de medida. En caso contrario, **0** (cero). |
| lineprice                      | El precio de una sola unidad. |
| linenetamount                  | Se aplica el precio de la línea, según el número de unidades y el descuento. |
| linediscount                   | Descuento para una unidad individual. |
| lineshipdate                   | Fecha de envío de la línea. |
| linedeliverydate               | Fecha de entrega para la línea. |
| linedeliverymode               | Modo de entrega para la línea. |
| linedeliveryaddress            | Dirección de entrega para la línea. |
| giftcardnumber                 | Número de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| giftcardbalance                | Saldo de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| giftcardmessage                | Mensaje de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| giftcardpin                    | Número de identificación personal (PIN) de la tarjeta regalo, para productos del tipo de tarjeta regalo. (Este marcador de posición es específico para tarjetas de regalo externas). |
| giftcardexpiration             | Fecha de vencimiento de la tarjeta regalo, para productos del tipo de tarjeta regalo. (Este marcador de posición es específico para tarjetas de regalo externas). |
| giftcardrecipientname          | Nombre del destinatario de la tarjeta regalo, para productos del tipo de tarjeta regalo. |
| giftcardbuyername              | Nombre del comprador de la tarjeta regalo, para productos del tipo de tarjeta regalo. |

### <a name="format-of-order-line-placeholders-in-the-email-message-body"></a>Formato de marcadores de posición de línea de pedido en el cuerpo del mensaje de correo electrónico

Cuando cree el HTML para las líneas de pedido individuales en el cuerpo del mensaje de correo electrónico, rodee el bloque repetitivo de HTML y los marcadores de posición para las líneas con los siguientes marcadores de posición que se colocan dentro de las etiquetas de comentarios HTML.

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

- El id. de correo electrónico de la plantilla de correo electrónico debe ser **emailRecpt**.
- El texto del recibo se inserta en el correo electrónico utilizando el marcador de posición **%message%**. Para asegurarse de que el cuerpo del recibo se representa correctamente, rodee el marcador de posición **%message%** con etiquetas HTML **&lt;pre&gt;** y **&lt;/pre&gt;**.
- Los saltos de línea en el HTML para el encabezado y pie de página del correo electrónico se convierten a etiquetas HTML **&lt;br /&gt;**, para que el cuerpo del recibo se represente correctamente. Para eliminar el espacio vertical no deseado en sus correos electrónicos de recibo, elimine los saltos de línea de cualquier lugar del HTML donde no se requiera espacio vertical.

Para obtener más información sobre cómo configurar recibos de correo electrónico, consulte [Configurar recibos de correo electrónico](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts).

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

[Configurar recepciones por correo electrónico](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-email-receipts)

[Enviar recibos por correo electrónico desde PDV modernos ](email-receipts.md)
