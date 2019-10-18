---
title: Permitir a los usuarios que reciban mensajes de correo electrónico relacionados con el flujo de trabajo
description: Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo.
author: jasongre
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e08f95ef6d263ee0f8c0a94b258c8a2795786bc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189853"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permitir a los usuarios que reciban mensajes de correo electrónico relacionados con el flujo de trabajo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo. Por ejemplo, los mensajes de correo electrónico se pueden enviar a los usuarios cuando se les asignan documentos para su aprobación. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Usuarios > Usuarios**.
2. En la lista, busque y seleccione el registro deseado.
3. En el **Panel de acciones**, haga clic en **Opciones de usuario**.
4. Haga clic en la pestaña **Flujo de trabajo**. Asegúrese de que está expandida la sección **Notificaciones**. En la sección **Notificaciones**, puede especificar la manera en que desea que se notifique al usuario acerca de los eventos relacionados con el flujo de trabajo.  
5. En el campo **Tipo de notificación de flujo de trabajo de línea-artículo**, seleccione una opción.
    - Agrupado: las notificaciones de elementos de línea se agrupan en una solo mensaje de correo electrónico.
    - Individual: se envía un mensaje de correo electrónico para cada artículo de línea.  
    - Si desea que el usuario reciba notificaciones en el cliente, active la casilla de verificación **Enviar notificaciones por correo electrónico**.  
6. Haga clic en **Guardar**.
7. Cierre la página.

