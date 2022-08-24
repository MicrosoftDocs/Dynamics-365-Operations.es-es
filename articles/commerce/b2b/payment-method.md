---
title: Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B
description: Este artículo describe cómo configurar el método de pago de la cuenta del cliente en Microsoft Dynamics 365 Commerce. También describe cómo los límites de crédito afectan la captura de pagos a cuenta en sitios de comercio electrónico de empresa a empresa (B2B).
author: josaw1
ms.date: 04/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: b8424920c3a177e01b71fc1c288b7acdd97ef191
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272027"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B

[!include [banner](../../includes/banner.md)]

Este artículo describe cómo configurar el método de pago de la cuenta del cliente en Microsoft Dynamics 365 Commerce. También describe cómo los límites de crédito afectan la captura de pagos a cuenta en sitios de comercio electrónico de empresa a empresa (B2B).

Los minoristas pueden aceptar distintos tipos de pago a cambio de los productos y los servicios que venden en un canal de comercio electrónico. Al configurar el sistema, se deben configurar en Dynamics 365 Commerce todos los tipos de pago que acepte un minorista. El método de pago de la cuenta del cliente (o "a cuenta") debe ser compatible con los sitios de comercio electrónico B2B. 

## <a name="prerequisites"></a>Requisitos previos

1. Agregue el método de pago de la cuenta del cliente en la sede central de Commerce.
2. Asocie el método de pago de la cuenta del cliente al canal de comercio electrónico.
3. Asegúrese de que la propiedad **Permitir a cuenta** está habilitada para el cliente en **Retail y Commerce \> Clientes \> Todos los clientes \> Valores predeterminados de pago** en la sede de Commerce.

    > [!NOTE]
    > Si se debe permitir que todos los clientes tengan habilitado el método de pago a cuenta, puede configurar la propiedad **Permitir a cuenta** a **Sí** para el cliente predeterminado del canal que está asociado con el sitio B2B. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Habilitar el método de pago de la cuenta del cliente en el generador de sitios de Commerce 

Para habilitar el método de pago de la cuenta del cliente en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Configuración del sitio \> Extensiones**.
1. Establezca la propiedad **Habilitar pagos de cuenta de cliente** en **Habilitado para clientes de B2B**. 
1. Seleccione **Guardar y publicar**.

> [!NOTE]
> La nueva configuración de sitio solo surtirá efecto cuando se haya actualizado el archivo app.settings.json. Para obtener más información, consulte [Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Habilite el método de pago de la cuenta del cliente en la página de finalización de compra del sitio de comercio electrónico B2B

Para habilitar el método de pago de la cuenta del cliente en la página de finalización de compra del sitio de comercio electrónico B2B, siga estos pasos.

1. En el generador de sitios de Commerce, busque y edite la página de pago o el fragmento que contiene el módulo de pago para el sitio de comercio electrónico B2B.
1. En la entrada **Contenedor de la sección de finalización de compra**, seleccione **Agregar módulo** y, a continuación, agregue un módulo **Pago de cuenta de cliente**.
1. Coloque el módulo **Pago de cuenta de cliente** seleccionando los puntos suspensivos (**...**) y seleccionando a continuación **Subir** o **Bajar** según sea necesario.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Confirmar que el método de pago de la cuenta del cliente se haya habilitado y publicado

Para confirmar que el método de pago de la cuenta del cliente se ha habilitado y publicado, siga estos pasos.

1. Inicie sesión en el sitio de comercio electrónico.
1. Agregue un producto al carro.
1. Vaya a la página de finalización de compra. Verá el nuevo método de pago de **Cuenta de cliente**.

## <a name="work-with-credit-limits"></a>Trabajar con límites de crédito

Cuando las capacidades para los pagos de cuentas de clientes están habilitadas en el sitio B2B, las organizaciones generalmente desean mostrar información sobre los límites de crédito y los saldos de los límites de crédito durante el proceso de captura de pedidos. El límite de crédito para un cliente está definido por la propiedad **Límite de crédito** en la ficha desplegable **Crédito y cobros** del registro de clientes en la sede de Commerce. Sin embargo, en escenarios B2B, un pedido que realiza un cliente a menudo debe facturarse a la cuenta de la organización a la que pertenece el cliente. Por lo tanto, debe configurar la propiedad **Cuenta de facturación** en la ficha desplegable **Factura y entrega** del registro de cliente al id. de cuenta de cliente de la organización. Luego, cuando el cliente realiza un pedido en el sitio B2B, el pedido se facturará a la organización. El sitio B2B también utilizará el límite de crédito de la organización en lugar del límite de crédito definido en el registro del cliente.

El cálculo del límite de crédito y el saldo que se muestran en el sitio web B2B dependen de la configuración de la propiedad **Tipo de límite de crédito** en la sede de Commerce. La ubicación de esta propiedad varía dependiendo de si la característica **Gestión de créditos** está habilitada en el espacio de trabajo **Administración de características**.

- Si la característica **Gestión de créditos** está habilitada, la propiedad se ubica en la ficha desplegable **Límites de crédito** en **Crédito y cobros \> Configuración \> Parámetros de crédito y cobros \> Créditos**. 
- Si la característica **Gestión de créditos** está deshabilitada, la propiedad se encuentra en **Calificación crediticia** en **Clientes \> Configuración \> Parámetros de clientes \> Calificación crediticia**.

Los valores que la propiedad **Tipo de límite de crédito** admite son **Ninguno**, **Saldo**, **Saldo + albarán o recibo del producto** y **Saldo + Todo**. Para obtener más información acerca de estos valores, consulte [Valores de tipo de límite de crédito](/dynamics365/supply-chain/sales-marketing/credit-limits-customers).

> [!NOTE]
> Le recomendamos que establezca la propiedad **Tipo de límite de crédito** a **Saldo + albarán o recibo del producto** para que los pedidos de venta abiertos no contribuyan al cálculo del saldo. Entonces, si sus clientes hacen pedidos en el futuro, no tienen que preocuparse de que esos pedidos afecten a su saldo actual.

Otra propiedad que afecta los pedidos a cuenta es **Límite de crédito obligatorio**, que se encuentra en la ficha desplegable **Crédito y cobros** del registro del cliente. Al establecer esta propiedad en **Sí** para clientes específicos, puede obligar al sistema a verificar su límite de crédito, incluso si la propiedad **Tipo de límite de crédito** se ha establecido en **Ninguno** para especificar que el límite de crédito no debe comprobarse para ningún cliente.

Actualmente, un cliente que utiliza el método de pago a cuenta no puede pagar más que el saldo de crédito restante de un pedido. Por ejemplo, si el saldo de crédito restante de un cliente es de 1000 $, pero el pedido vale 1200 $, el cliente puede pagar solo 1000 $ mediante el método a cuenta. Entonces, el cliente debe usar algún otro método de pago para pagar el saldo. En una versión futura, una configuración de Commerce permitirá a los usuarios gastar más allá de su límite de crédito al realizar pedidos.

El módulo **Crédito y cobros** tiene nuevas capacidades de gestión de crédito. Para activar estas funciones, habilite la característica **Gestión de créditos** en el espacio de trabajo **Administración de características**. Una de las nuevas funciones permite poner en espera los pedidos de venta según las reglas de bloqueo. La persona del administrador de crédito puede liberar o rechazar los pedidos después de un análisis más detallado. Sin embargo, la capacidad de poner pedidos de venta en espera no se aplica a los pedidos de Commerce, porque los pedidos de venta a menudo tienen un prepago y la característica **Gestión de créditos** no es totalmente compatible con los escenarios de prepago. 

Independientemente de si la característica **Gestión de créditos** está habilitada, si el saldo de un cliente supera el límite de crédito durante el proceso de entrega del pedido, los pedidos de venta no quedarán en espera. En su lugar, Commerce generará un mensaje de advertencia o un mensaje de error, según el valor del campo **Mensaje que aparece al exceder el límite de crédito** en la ficha rápida **Límites de crédito**.

La propiedad **Excluir de administración de crédito** que evita que los pedidos de venta de Commerce queden en espera se encuentra en el encabezado del pedido de venta (**Retail y Commerce \> Clientes \> Todos los pedidos de venta**). Si esta propiedad se establece en **Sí** (el valor predeterminado) para los pedidos de venta de Commerce, los pedidos se excluirán del flujo de trabajo en espera de la gestión de créditos. Aunque la propiedad se llame **Excluir de administración de crédito**, el límite de crédito definido seguirá utilizándose durante el proceso de entrega del pedido. Los pedidos simplemente no quedarán en espera.

La capacidad de poner en espera los pedidos de venta de Commerce en función de las reglas de bloqueo está planificada para futuras versiones de Commerce. Hasta que sea compatible, si debe obligar a los pedidos de venta de Commerce a pasar por los nuevos flujos de administración de crédito, puede personalizar los siguientes archivos XML en su solución de Visual Studio. En los archivos, modifique la lógica para que el indicador **CredManExcludeSalesOrder** se establezca en **No**. De esta manera, la propiedad **Excluir de la administración de crédito** se establecerá en **No** por defecto para los pedidos de venta de Commerce.

- RetailCreateCustomerOrderExtensions_CredMan_Extension.xml
- RetailCallCenterOrderExtensions_CredMan_Extension.xml

Sii el indicador **CredManExcludeSalesOrder** se establece en **No** y un cliente B2B puede comprar en las tiendas mediante la aplicación de punto de venta (PDV), es posible que falle el registro de las transacciones de efectivo y transporte. Por ejemplo, hay una regla de bloqueo en el tipo de pago en efectivo y el cliente B2B compró algunos artículos en la tienda usando efectivo. En este caso, el pedido de venta resultante no se facturará correctamente porque quedará en espera. Por lo tanto, el registro fallará. Por este motivo, le recomendamos que realice pruebas de un extremo a otro después de implementar esta personalización.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un sitio de comercio electrónico B2B](set-up-b2b-site.md)

[Administrar socios comerciales B2B utilizando jerarquías de clientes](partners-customer-hierarchies.md)

[Gestionar usuarios de partner comerciales en sitios de comercio electrónico B2B](manage-b2b-users.md)

[Establecer límites de cantidad de productos para sitios de comercio electrónico B2B](quantity-limits.md)

[Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
