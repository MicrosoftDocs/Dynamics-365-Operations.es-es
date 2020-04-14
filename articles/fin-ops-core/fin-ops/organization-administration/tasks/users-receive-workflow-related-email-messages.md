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
ms.openlocfilehash: f4c9f2f22bc4b5ca5b4351f7956ad2eb6d3b903d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140430"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permitir a los usuarios que reciban mensajes de correo electrónico relacionados con el flujo de trabajo

[!include [banner](../../includes/banner.md)]

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

