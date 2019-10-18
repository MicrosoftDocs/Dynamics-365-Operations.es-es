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
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="1c000-103">Permitir a los usuarios que reciban mensajes de correo electrónico relacionados con el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1c000-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1c000-104">Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1c000-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="1c000-105">Por ejemplo, los mensajes de correo electrónico se pueden enviar a los usuarios cuando se les asignan documentos para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="1c000-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="1c000-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="1c000-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="1c000-107">Vaya a **Panel de navegación > Módulos > Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="1c000-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="1c000-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1c000-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1c000-109">En el **Panel de acciones**, haga clic en **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="1c000-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="1c000-110">Haga clic en la pestaña **Flujo de trabajo**. Asegúrese de que está expandida la sección **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="1c000-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="1c000-111">En la sección **Notificaciones**, puede especificar la manera en que desea que se notifique al usuario acerca de los eventos relacionados con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1c000-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="1c000-112">En el campo **Tipo de notificación de flujo de trabajo de línea-artículo**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="1c000-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="1c000-113">Agrupado: las notificaciones de elementos de línea se agrupan en una solo mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1c000-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="1c000-114">Individual: se envía un mensaje de correo electrónico para cada artículo de línea.</span><span class="sxs-lookup"><span data-stu-id="1c000-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="1c000-115">Si desea que el usuario reciba notificaciones en el cliente, active la casilla de verificación **Enviar notificaciones por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="1c000-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="1c000-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1c000-116">Click **Save**.</span></span>
7. <span data-ttu-id="1c000-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1c000-117">Close the page.</span></span>

