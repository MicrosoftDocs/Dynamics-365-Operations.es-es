---
title: El correo electrónico de bienvenida no se envía cuando se crean nuevos clientes
description: Este tema proporciona una guía para la solución de problemas que puede ayudar si no se envía una notificación de correo electrónico de bienvenida cuando se crea un nuevo cliente en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 1a4faf6cd189f69232e7f9ab8d0e79b320cfe2d9
ms.sourcegitcommit: d2e5d38ed1550287b12c90331fc4136ed546b14c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/25/2022
ms.locfileid: "8349957"
---
# <a name="welcome-email-is-not-sent-when-new-customers-are-created"></a>El correo electrónico de bienvenida no se envía cuando se crean nuevos clientes

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la solución de problemas que puede ayudar si no se envía una notificación de correo electrónico de bienvenida cuando se crea un nuevo cliente en Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Cuando se crea un nuevo cliente en la sede de Commerce, no se envía un correo electrónico de bienvenida al cliente, aunque se configura una notificación por correo electrónico para el tipo de notificación **Cliente creado** por correo electrónico.

## <a name="resolution"></a>Resolución

### <a name="set-the-correct-email-id-value-for-the-customer-created-email-notification-type"></a>Establezca el valor de identificador de correo electrónico correcto para el tipo de notificación de correo electrónico creado por el cliente

Para establecer el valor correcto de **Id. de correo** para el tipo de notificación **Cliente creado** por correo electrónico en la sede, sigue estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede central \> Perfil de notificación de correo de Commerce**.
1. En el panel de navegación de la izquierda, seleccione el perfil de notificación de correo.
1. En **Configuración de notificaciones de eventos de Retail**, para el tipo **Cliente creado** de notificación por correo electrónico, configure el campo **Identificación de correo** campo a **NewCust**.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar perfil de notificación por correo electrónico](../email-notification-profiles.md)