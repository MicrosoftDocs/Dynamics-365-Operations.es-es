---
title: Habilitar las notificaciones de registro del cliente en el punto de venta (PDV)
description: Este tema describe cómo habilitar las notificaciones de registro de clientes en punto de venta (PDV) de Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: cf9331e1da54520787686a3f190e2ef6d150c0c10bd521919407f5e6c74551d1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6774592"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Habilitar las notificaciones de registro del cliente en el punto de venta (PDV)

[!include [banner](includes/banner.md)]

Este tema describe cómo habilitar las notificaciones de registro de clientes en punto de venta (PDV) de Microsoft Dynamics 365 Commerce.

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

Agregue el enlace o botón a la plantilla que está asignada al tipo de notificación **Embalaje completado** y el modo de entrega que está utilizando para a cumplimentación de pedidos en la acera. En la plantilla, cree un enlace HTML o un botón que apunte a la URL de la página de confirmación de registro que creó. He aquí un ejemplo.

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
Para obtener más información sobre cómo configurar plantillas de correo electrónico, consulte [Personalizar los correos electrónicos transaccionales por modo de entrega](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>Se crea una tarea de confirmación de registro en PDV

Después de que un cliente notifica a la tienda que está presente para la recogida, recibe una notificación de confirmación de registro y se crea una tarea en la lista de tareas en el PDV donde el cliente está recogiendo el pedido. La tarea contiene toda la información del cliente y del pedido que se requiere para cumplimentar el pedido. En la tarea, el campo de instrucciones muestra cualquier información que se recopiló del cliente a través del formulario de información adicional. 

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de registro para recogida](check-in-pickup-module.md)
