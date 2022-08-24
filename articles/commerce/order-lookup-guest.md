---
title: Habilitar la búsqueda de pedidos para los pagos de invitados
description: Este artículo describe cómo habilitar la búsqueda de pedidos para los pagos de invitados en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 4f381f1ec0ea08f18db3cac474e8990906364504
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286901"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Habilitar la búsqueda de pedidos para los pagos de invitados

[!include [banner](includes/banner.md)]

Este artículo describe cómo habilitar la búsqueda de pedidos para los pagos de invitados en Microsoft Dynamics 365 Commerce.

La función de búsqueda de pedidos para pagos de invitados permite a los clientes que realizan compras como usuarios invitados buscar sus pedidos. La capacidad de búsqueda de pedidos es útil cuando los clientes desean realizar acciones como verificar el estado de cumplimiento de los productos en un pedido, verificar la dirección a la que se envió un pedido, reordenar un producto o confirmar en la tienda que se recogerá un pedido.

Los clientes que realizan pedidos como usuarios registrados pueden ver los detalles de sus pedidos cuando inician sesión, pero los clientes que utilizan el pago como invitado para realizar pedidos no pueden. Sin embargo, cuando la función de búsqueda de pedidos para pagos de invitados está habilitada, proporciona un formulario que los clientes pueden usar para buscar pedidos que realizaron como invitados. En este formulario, los clientes ingresan el ID de confirmación del pedido y (opcionalmente) la dirección de correo electrónico que especificaron al finalizar la compra.

Además, se puede incluir un enlace o botón que lleva al cliente directamente a la página de detalles del pedido para su pedido en cualquier correo electrónico transaccional relacionado con el pedido. Este enlace o botón funcionará para pedidos realizados tanto por usuarios registrados como por usuarios invitados.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>Active las funciones necesarias en la sede de Comercio

Para habilitar la búsqueda de pedidos para los pagos de invitados, debe activar las siguientes funciones en **Espacios de trabajo \> Gestión de funciones** en la sede de Commerce.

| Característica | Propósito |
|---------|---------|
| Característica de inclusión de detalles del pedido en la búsqueda de usuario anónimo de Retail | Esta función expone la interfaz de usuario en los parámetros de Commerce que le permite habilitar la API de búsqueda de pedidos para usuarios no autenticados y configurar cómo se muestran los datos personales. |
| Habilitar la generación de un id. de referencia del canal más seguro | Esta función genera un ID de referencia de canal de 12 caracteres más seguro (ID de confirmación de pedido) que se puede pasar en la cadena de consulta cuando se busca un pedido. |
| Generar un formato coherente de id. de referencia de canal entre canales | Esta función genera un ID de referencia de canal seguro para los pedidos que se realizan a través de un sitio de comercio electrónico, el punto de venta minorista (POS) o un centro de llamadas. Antes de poder activar esta función, la función **Habilitar la generación de un ID de referencia de canal más fuerte** debe estar activada. |

Después de activar la función **Característica de opción de detalles de pedidos de búsqueda de usuarios anónimos minoristas**, debe habilitar la API que admite la búsqueda de pedidos no autenticados en la sede de Comercio. Vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Pedidos de cliente**. Sobre la página **Pedidos de los clientes**, en la ficha desplegable **Búsqueda de pedidos**, establezca la opción **Habilitar la búsqueda de pedidos no autenticados** en **Sí**, como se muestra en la siguiente ilustración.

## <a name="manage-the-display-of-personal-data"></a>Gestionar la visualización de datos personales

La ficha desplegable **Búsqueda de pedidos** en la página **Pedidos de los clientes** en la sede de Commerce incluye un campo **Incluir datos personales en la búsqueda de pedidos de invitados** que le permite controlar si se muestra información personal a los clientes. Esta información personal incluye la dirección de envío del cliente y los últimos cuatro dígitos del número de tarjeta de crédito del cliente. De forma predeterminada, la información personal no se muestra a los clientes cuando la búsqueda de pedidos no autenticados está habilitada. En la tabla siguiente se describen las opciones disponibles.

| Opción | Resultado |
|--------|--------|
| Nunca | El valor predeterminado. No se muestra información personal en las búsquedas de pedidos. Cuando los usuarios registrados que han iniciado sesión buscan un pedido que crearon mientras estaban conectados, podrán ver su información personal. |
| Solo pedidos de invitado | La información personal se muestra en las búsquedas de pedidos para los pedidos que los clientes crearon como invitados. Si un pedido fue creado por un usuario registrado, ese usuario debe iniciar sesión para ver su información personal. |
| Todos los pedidos | Se muestra la información personal en todas las búsquedas de pedidos. |

> [!NOTE]
> Estas opciones determinan cuándo se muestran a los usuarios invitados anónimos datos personales como la dirección del cliente y los últimos cuatro dígitos del número de la tarjeta de crédito del cliente. Para ayudar a proteger la privacidad de los clientes registrados, le recomendamos que seleccione la opción **Solo pedidos de invitados**. Sin embargo, la opción más segura es **Nunca**.

Después de cambiar el valor del campo **Incluir datos personales en la búsqueda de pedidos de invitados**, debe ejecutar el trabajo 1070 (**Configuración de canal**) en la sede de Commerce yendo a **Retail y Commerce \> TI de Retail y Commerce \> Programación de distribución**.

## <a name="configure-the-order-lookup-module"></a>Configurar el módulo de búsqueda de pedidos

El módulo de búsqueda de pedidos en la biblioteca del módulo de Comercio se usa para representar el formulario que los usuarios invitados usan para buscar pedidos. El módulo de búsqueda de pedidos se puede incluir en la ranura del cuerpo de cualquier página que no requiera el inicio de sesión del cliente. Para obtener información sobre cómo configurar el módulo, consulte [Módulo de búsqueda de pedidos](order-lookup-module.md).

## <a name="configure-the-order-details-page"></a>Configurar la página de detalles del pedido

Antes de que los usuarios invitados puedan ver los detalles de su pedido, la página de detalles del pedido en su sitio de comercio electrónico debe estar configurada para que no requiera iniciar sesión. Para desactivar el requisito de inicio de sesión para la página de detalles de su pedido, abra la página en el creador de sitios de Commerce, seleccione la ranura **Página predeterminada (requerida)** en la vista de árbol y desmarque la casilla **¿Requiere iniciar sesión?** en la parte inferior del panel de propiedades a la derecha.

## <a name="add-a-link-to-order-details-in-transactional-emails"></a>Agregar un vínculo para los detalles del pedido en los correos electrónicos transaccionales

En los correos electrónicos relacionados con pedidos, puede proporcionar un vínculo o botón que lleve a los clientes a la página de detalles de su pedido. Para agregar este vínculo o botón, cree un hipervínculo HTML que dirija a la página de detalles del pedido en su sitio de comercio electrónico y pase el id. de confirmación del pedido y la dirección de correo electrónico del cliente como parámetros de URL, como se muestra en el siguiente ejemplo.

`<a href="https://[domain]/[orderdetailspage]?confirmationId=%orderconfirmationid%&propertyName=email&propertyValue=%customeremailaddress%" target="_blank">View my order status</a>`

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de búsqueda de pedidos](order-lookup-module.md)

[Configurar perfil de notificación por correo electrónico](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
