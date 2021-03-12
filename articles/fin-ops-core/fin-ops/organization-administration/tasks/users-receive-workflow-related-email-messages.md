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
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="91335-103">Permitir a los usuarios que reciban mensajes de correo electrónico relacionados con el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="91335-103">Enable users to receive workflow-related email messages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="91335-104">Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91335-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="91335-105">Por ejemplo, los mensajes de correo electrónico se pueden enviar a los usuarios cuando se les asignan documentos para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="91335-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="91335-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="91335-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="91335-107">Vaya a **Panel de navegación > Módulos > Administración del sistema > Usuarios > Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="91335-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="91335-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="91335-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="91335-109">En el **panel Acciones**, haga clic en **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="91335-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="91335-110">Haga clic en la pestaña **Flujo de trabajo**. Asegúrese de que está expandida la sección **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="91335-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="91335-111">En la sección **Notificaciones**, puede especificar la manera en que desea que se notifique al usuario acerca de los eventos relacionados con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91335-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="91335-112">En el campo **Tipo de notificación de flujo de trabajo de línea-artículo**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="91335-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="91335-113">Agrupado: las notificaciones de elementos de línea se agrupan en una solo mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="91335-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="91335-114">Individual: se envía un mensaje de correo electrónico para cada artículo de línea.</span><span class="sxs-lookup"><span data-stu-id="91335-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="91335-115">Si desea que el usuario reciba notificaciones en el cliente, active la casilla de verificación **Enviar notificaciones por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="91335-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="91335-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="91335-116">Click **Save**.</span></span>
7. <span data-ttu-id="91335-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="91335-117">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="91335-118">Las plantillas de correo electrónico del flujo de trabajo se obtendrán de las plantillas de correo electrónico del sistema o de las plantillas de correo electrónico de la organización, dependiendo de si el flujo de trabajo es un flujo de trabajo a nivel de sistema (no específico de la compañía) o de nivel de organización (específico de la compañía).</span><span class="sxs-lookup"><span data-stu-id="91335-118">The workflow email templates will be sourced from either system email templates or organization email templates depending on whether the workflow is a system-level (not company specific) or organization-level (company specific) workflow.</span></span>
