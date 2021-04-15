---
title: Personalizar correos electrónicos transaccionales por modo de entrega
description: Este tema describe cómo configurar plantillas de correo electrónico personalizadas para tipos de notificación y modos de entrega específicos en Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 411e694b33e0443a336f6a8cdad78714630e4bf3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799382"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a>Personalizar correos electrónicos transaccionales por modo de entrega

[!include [banner](includes/banner.md)]

Este tema describe cómo configurar plantillas de correo electrónico personalizadas para tipos de notificación y modos de entrega específicos en Microsoft Dynamics 365 Commerce.

Los correos electrónicos transaccionales ahora se pueden personalizar para una combinación de un tipo de notificación (por ejemplo, **Pedido creado**, **Pedido empaquetado** o **Pedido facturado**) y un modo de entrega (por ejemplo, durante la noche, recogida en la tienda o recogida en puntos de entrega). Los correos electrónicos transaccionales personalizados permiten a los minoristas proporcionar a sus clientes experiencias de cumplimiento que se adaptan al modo de entrega del pedido. Por ejemplo, el evento "pedido empaquetado" se puede personalizar para que proporcione instrucciones de recolección en un punto de entrega para los clientes que eligen esa opción. Alternativamente, puede proporcionar el transportista de envío y la información de entrega para los clientes que eligen que se envíe su pedido.

> [!NOTE]
> Para utilizar la funcionalidad de correos electrónicos transaccionales personalizados, primero debe activar la característica **Personalizar correos electrónicos transaccionales por modo de entrega** yendo a **Espacios de trabajo \> Administración de características** en la sede central de Commerce.

Los correos electrónicos se pueden personalizar por modo de entrega para los siguientes tipos de notificación:

- **Cancelación de pedido**: este tipo de notificación por correo electrónico es nueva.
- **Pedido creado**
- **Pedido confirmado**
- **Pedido facturado**: este tipo de notificación por correo electrónico es nueva. Se puede utilizar en lugar del tipo de notificación **Pedido enviado** que enviará una notificación para cualquier evento de factura que tenga un modo de entrega enviado (no un modo de recogida, envío o envío electrónico).
- **Pedido recogido**
- **Pedido empaquetado**
- **Pedido listo para recoger**: este tipo de notificación se puede personalizar por modo de entrega solo si la característica **Compatibilidad para múltiples modos de entrega de recogida** está activada. En ese caso, este tipo de notificación es funcionalmente equivalente al tipo de notificación **Pedido empaquetado**.
- **Pago fallido**
- **Pedido de sustitución creado**

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a>Configurar plantillas de correo electrónico para modos de entrega específicos

Para este procedimiento, se supone que ya ha creado sus nuevas plantillas de correo electrónico personalizadas y las ha agregado a la página **Plantillas de correo electrónico de organización**. Para obtener información sobre cómo crear y cargar plantillas de correo electrónico, consulte [Crear plantillas de correo electrónico para eventos transaccionales](email-templates-transactions.md).

Para configurar plantillas de correo electrónico para modos específicos de entrega en la sede central de Commerce, siga estos pasos.

1. Vaya a **Perfil de notificación por correo electrónico de Commerce**.
1. En **Configuración de notificación de evento comercial**, seleccione un tipo de notificación existente.
1. Mientras el tipo de notificación aún está seleccionado, seleccione **Configurar modos de entrega**.
1. En el cuadro de diálogo **Modos de entrega**, seleccione **Nuevo**.
1. En la nueva fila, en el campo **Modo de entrega**, seleccione un modo de entrega.
1. En el campo **Identificación de correo**, seleccione la plantilla de correo electrónico para asignar al modo de entrega.
1. Active la casilla **Activo**.
1. Repita los pasos 4 a 7 para agregar más modos de entrega.
1. Cuando haya terminado, haga clic en **Aceptar**.

> [!NOTE]
> - Cuando hay más de un modo de entrega en las líneas de un pedido de cliente, se utilizará la plantilla predeterminada. La plantilla predeterminada es la plantilla que se asigna al tipo de notificación en la página **Perfil de notificación por correo electrónico de Commerce** página.
> - Si un pedido de venta tiene un modo de entrega que no se ha configurado para una plantilla de correo electrónico personalizada, se utilizará la plantilla de correo electrónico predeterminada.

## <a name="additional-resources"></a>Recursos adicionales

[Crear pedidos de centro de llamadas](tasks/create-call-center-orders.md)

[Cambiar el modo de entrega en PDV](pos-change-delivery-mode.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]