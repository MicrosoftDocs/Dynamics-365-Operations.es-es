---
title: El correo electrónico de bienvenida no se envía cuando se crean nuevos clientes
description: Este artículo proporciona una guía para la solución de problemas que puede ayudar si no se envía una notificación de correo electrónico de bienvenida cuando se crea un nuevo cliente en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/01/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 5aa7d864555f96194500989e2d7ad200d8892121
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219414"
---
# <a name="welcome-email-isnt-sent-when-new-customers-are-created"></a>El correo electrónico de bienvenida no se envía cuando se crean nuevos clientes

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía para la solución de problemas que puede ayudar si no se envía una notificación de correo electrónico de bienvenida cuando se crea un nuevo cliente en Microsoft Dynamics 365 Commerce.

## <a name="description"></a>Description

Cuando se crea un nuevo cliente en la sede de Commerce, no se envía un correo electrónico de bienvenida al cliente, aunque se configura una notificación por correo electrónico para el tipo de notificación **Cliente creado** por correo electrónico.

## <a name="resolution"></a>Resolución

### <a name="associate-an-email-notification-profile-under-commerce-parameters"></a>Asociar un perfil de notificación por correo electrónico en los parámetros de Commerce

1. En la sede central, vaya a **Retail y Commerce \> Configuración de sede central \> Parámetros \> Parámetros de Commerce \> General**.
2. En la lista desplegable **Perfil de notificación por correo electrónico**, seleccione el perfil de notificación de correo electrónico que contiene una asignación entre el tipo de notificación creada por el cliente y una plantilla de correo electrónico creada por el cliente.  

> [!NOTE] 
> Cuando habilita las notificaciones creadas por el cliente, los clientes que se crean en todos los canales dentro de la entidad legal recibirán un correo electrónico creado por el cliente. Actualmente, las notificaciones creadas por los clientes no se pueden limitar a un solo canal.

Para obtener más información, consulte [Crear plantillas de correo electrónico para eventos transaccionales](../email-templates-transactions.md). 

## <a name="additional-resources"></a>Recursos adicionales

[Configurar perfil de notificación por correo electrónico](../email-notification-profiles.md)
