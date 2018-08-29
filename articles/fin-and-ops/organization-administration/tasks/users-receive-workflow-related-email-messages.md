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
# <a name="configure-the-system-to-send-workflow-related-email-to-users"></a><span data-ttu-id="1f62b-103">Configurar el sistema para enviar correo electrónico relacionado con el flujo de trabajo a los usuarios</span><span class="sxs-lookup"><span data-stu-id="1f62b-103">Configure the system to send workflow-related email to users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1f62b-104">Usted puede configurar el sistema para enviar mensajes de correo electrónico a los usuarios cuando se produzcan eventos relacionados con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1f62b-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="1f62b-105">Por ejemplo, los mensajes de correo electrónico se pueden enviar a los usuarios cuando se les asignan documentos para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="1f62b-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="1f62b-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="1f62b-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="1f62b-107">Vaya a Administración del sistema > Usuarios > Usuarios.</span><span class="sxs-lookup"><span data-stu-id="1f62b-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="1f62b-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1f62b-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1f62b-109">Haga clic en Opciones de usuario.</span><span class="sxs-lookup"><span data-stu-id="1f62b-109">Click User options.</span></span>
4. <span data-ttu-id="1f62b-110">Haga clic en la pestaña Flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1f62b-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="1f62b-111">Asegúrese de que la sección Notificaciones está expandida.</span><span class="sxs-lookup"><span data-stu-id="1f62b-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="1f62b-112">En la sección Notificaciones, puede especificar la manera en que desea que se notifique al usuario acerca de los eventos relacionados con el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1f62b-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="1f62b-113">En la línea-artículo del campo tipo de notificación del flujo de trabajo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="1f62b-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="1f62b-114">Agrupado: las notificaciones de elementos de línea se agrupan en una solo mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1f62b-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="1f62b-115">Individual: se envía un mensaje de correo electrónico para cada artículo de línea.</span><span class="sxs-lookup"><span data-stu-id="1f62b-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="1f62b-116">Si desea que el usuario reciba notificaciones en el cliente, active la casilla de verificación Enviar notificaciones por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="1f62b-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="1f62b-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1f62b-117">Click Save.</span></span>
7. <span data-ttu-id="1f62b-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1f62b-118">Close the page.</span></span>


