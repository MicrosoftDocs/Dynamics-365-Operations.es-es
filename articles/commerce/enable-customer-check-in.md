---
title: Habilitar las notificaciones de registro del cliente en el punto de venta (PDV)
description: Este artículo describe cómo habilitar las notificaciones de registro de clientes en punto de venta (PDV) de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.custom: ''
ms.assetid: ''
ROBOTS: ''
ms.openlocfilehash: 5627f529f72fe06103fa64548a7d182fc008bd83
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287660"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Habilitar las notificaciones de registro del cliente en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

Este artículo describe cómo habilitar las notificaciones de registro de clientes en punto de venta (PDV) de Microsoft Dynamics 365 Commerce.

En sus correos electrónicos de "pedido listo para recoger", las organizaciones pueden proporcionar un enlace o botón que permita a los clientes notificar a la tienda que están en las instalaciones y esperando que les traigan su paquete. Luego, los clientes reciben una confirmación de registro y la tienda recibe una notificación como una tarea en su aplicación de PDV. Esta tarea sirve como aviso para que un asociado de ventas entregue el pedido en el vehículo del cliente. Por tanto, el cliente no tiene que entrar en la tienda.

El flujo de trabajo de registro del cliente también se puede configurar para recopilar información adicional de los clientes, como su número de plaza de estacionamiento, la marca, el modelo y el color de su vehículo, e instrucciones de entrega. El encargado de la tienda minorista puede utilizar esta información para facilitar la cumplimentación de los pedidos.

## <a name="enable-customer-check-in"></a>Habilitar el registro de los clientes

Cuando la función de registro de cliente está activada, Commerce genera un id. de confirmación de pedido (también conocido como id. de referencia del canal). También genera los id. de confirmación de pedido para pedidos que se crean a través de canales de punto de venta (PDV) o de centro de llamadas. 

Para activar la característica de registro de cliente en la sede de Commerce, siga estos pasos.

1. Vaya a **Espacios de trabajo \> Administración de características**.
2. Busque la característica **Generar un formato de id. de referencia de canal coherente en todos los canales**. 
3. Seleccione la característica y, a continuación, **Habilitar ahora** en el panel de propiedades. 

## <a name="create-a-check-in-confirmation-page"></a>Crear una página de confirmación de registro

En su sitio de comercio electrónico, debe crear una nueva página que servirá como experiencia de confirmación del registro. Mediante configuración adicional, la página también puede incluir un formulario que recopila información adicional de los clientes para facilitar el cumplimiento de los pedidos. Para obtener información sobre cómo configurar la página y el módulo, consulte [Módulo de facturación de clientes](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Configurar la plantilla de correo electrónico transaccional

Debe agregar un enlace o botón **Estoy aquí** a la plantilla para el correo electrónico transaccional que los clientes reciben cuando su pedido está listo para ser recogido. Los clientes utilizarán este enlace o botón para notificar a la tienda que han llegado a recoger su pedido. 

Agregue el enlace o botón a la plantilla que está asignada al tipo de notificación **Embalaje completado** y el modo de entrega que está utilizando para a cumplimentación de pedidos en la acera. En la plantilla, cree un enlace HTML o un botón que señale a la URL de la página de confirmación de registro que creó y que incluya los nombres y valores de los parámetros, como se muestra en el siguiente ejemplo.

`<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%confirmationid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>`

Para obtener más información sobre cómo configurar plantillas de correo electrónico, consulte [Personalizar los correos electrónicos transaccionales por modo de entrega](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Se crea una tarea de confirmación de registro en PDV

Después de que un cliente notifique a la tienda que está presente para la recogida, la página de registro muestra un mensaje de confirmación y un código QR opcional que contiene el id. de confirmación del pedido del cliente. Al mismo tiempo, se crea una tarea en la lista de tareas en el PDV para la tienda donde el cliente recoge el pedido. Esta tarea contiene toda la información del cliente y del pedido que se requiere para cumplimentar el pedido. El campo de instrucciones de la tarea muestra cualquier información que se recopiló del cliente a través del formulario de información adicional.

## <a name="end-to-end-testing"></a>Pruebas de un extremo a otro

El registro del cliente requiere que se pasen parámetros y valores específicos a la página de registro y luego a la API de registro del cliente. Por lo tanto, el enfoque más sencillo es probar la característica en un entorno en el que se pueda crear y empaquetar un pedido de prueba. De esa manera, se puede generar un correo electrónico de "pedido listo para recoger" que tiene una URL con los nombres y valores de los parámetros requeridos.

Para probar la característica de registro de clientes, siga estos pasos.

1. Cree la página de registro del cliente y luego agregue y configure el módulo de registro del cliente. Para obtener más información, consulte [Módulo de registro para recogida](check-in-pickup-module.md). 
1. Registre la página, pero no la publique.
1. Agregue el siguiente enlace a una plantilla de correo electrónico que invoca el tipo de notificación de embalaje completo para un modo de entrega de recogida. Para obtener más información, consulte [Crear plantillas de correo electrónico para eventos transaccionales](email-templates-transactions.md).

    - **Para entornos de preproducción (UAT):** agregue el fragmento de código de la sección [Configurar la plantilla de correo electrónico transaccional](#configure-the-transactional-email-template) anterior en este artículo.
    - **Para entornos de producción:** agregue el siguiente código comentado para que los clientes existentes no se vean afectados.

        `<!-- https://[DOMAIN]/[CHECK_IN_PAGE]?channelReferenceId=%confirmationid%&channelId=%pickupchannelid%&packingSlipId=%packingslipid%&preview=inprogress -->`

1. Cree un pedido en el que se especifique el modo de entrega de recogida.
1. Cuando reciba el correo electrónico que se activa por el tipo de notificación de embalaje completo, pruebe el flujo de registro abriendo la página de registro que tiene la URL que agregó anteriormente. Como la URL incluye la marca `&preview=inprogress`, se le pedirá que se autentique antes de poder ver la página.
1. Introduzca cualquier información adicional que se necesita para configurar el módulo.
1. Verifique que la vista de confirmación del registro se muestre correctamente.
1. Abra un terminal del PDV para la tienda donde se recogerá el pedido.
1. Seleccione el icono **Pedidos a recoger** y verifique que aparezca el pedido.
1. Verifique que cualquier información adicional que se configuró en el módulo de registro aparece en el panel de detalles.

Una vez que haya verificado que la característica de registro del cliente funciona de un extremo a otro, siga estos pasos.

1. Publique la página de registro.
1. Si está probando en un entorno de producción, elimine el comentario de la URL en la plantilla de correo electrónico "pedido listo para recoger", de modo que se muestre el vínculo o botón **Estoy aquí**. Luego, vuelva a cargar la plantilla.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de registro para recogida](check-in-pickup-module.md)

[Personalizar correos electrónicos transaccionales por modo de entrega](customize-email-delivery-mode.md)

[Crear plantillas de correo electrónico para eventos transaccionales](email-templates-transactions.md)
