---
title: Permitir a los usuarios que reciban mensajes de correo electrónico relacionados con el flujo de trabajo
description: Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 221e38cbe31e2ad24a56cb2e71206a1ebcdd619e
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4799013"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Permitir a los usuarios que reciban mensajes de correo electrónico relacionados con el flujo de trabajo

[!include [banner](../../includes/banner.md)]

Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo. Por ejemplo, los mensajes de correo electrónico se pueden enviar a los usuarios cuando se les asignan documentos para su aprobación. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a **Panel de navegación > Módulos > Administración del sistema > Usuarios > Usuarios**.
2. En la lista, busque y seleccione el registro deseado.
3. En el **panel Acciones**, haga clic en **Opciones de usuario**.
4. Haga clic en la pestaña **Flujo de trabajo**. Asegúrese de que está expandida la sección **Notificaciones**. En la sección **Notificaciones**, puede especificar la manera en que desea que se notifique al usuario acerca de los eventos relacionados con el flujo de trabajo.  
5. En el campo **Tipo de notificación de flujo de trabajo de línea-artículo**, seleccione una opción.
    - Agrupado: las notificaciones de elementos de línea se agrupan en una solo mensaje de correo electrónico.
    - Individual: se envía un mensaje de correo electrónico para cada artículo de línea.  
    - Si desea que el usuario reciba notificaciones en el cliente, active la casilla de verificación **Enviar notificaciones por correo electrónico**.  
6. Haga clic en **Guardar**.
7. Cierre la página.

> [!NOTE]
> Las plantillas de correo electrónico del flujo de trabajo se obtendrán de las plantillas de correo electrónico del sistema o de las plantillas de correo electrónico de la organización, dependiendo de si el flujo de trabajo es un flujo de trabajo a nivel de sistema (no específico de la compañía) o de nivel de organización (específico de la compañía).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]