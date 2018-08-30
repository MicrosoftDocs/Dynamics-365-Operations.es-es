--- 
title: "Configurar el sistema para enviar correo electrónico relacionado con el flujo de trabajo a los usuarios"
description: "Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo."
author: jasongre
manager: AnnBe
ms.date: 02/21/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 04d90c9ded1ba7fb1ceac4ff1d54f54f6c43f9e9
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="configure-the-system-to-send-workflow-related-email-to-users"></a>Configurar el sistema para enviar correo electrónico relacionado con el flujo de trabajo a los usuarios

[!include [task guide banner](../../includes/task-guide-banner.md)]

Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo. Por ejemplo, los mensajes de correo electrónico se pueden enviar a los usuarios cuando se les asignan documentos para su aprobación. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a Administración del sistema > Usuarios > Usuarios.
2. En la lista, busque y seleccione el registro deseado.
3. Haga clic en Opciones de usuario.
4. Haga clic en la pestaña Flujo de trabajo.
    * Asegúrese de que la sección Notificaciones está expandida.     En la sección Notificaciones, puede especificar la manera en que desea que se notifique al usuario acerca de los eventos relacionados con el flujo de trabajo.  
5. En la línea-artículo del campo tipo de notificación del flujo de trabajo, seleccione una opción.
    * Agrupado: las notificaciones de elementos de línea se agrupan en una solo mensaje de correo electrónico.    Individual: se envía un mensaje de correo electrónico para cada artículo de línea.  
    * Si desea que el usuario reciba notificaciones en el cliente, active la casilla de verificación Enviar notificaciones por correo electrónico.  
6. Haga clic en Guardar.
7. Cierre la página.


