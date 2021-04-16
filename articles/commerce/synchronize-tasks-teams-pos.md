---
title: Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV
description: Este tema describe cómo sincronizar la administración de tareas entre Microsoft Teams y Dynamics 365 Commerce punto de venta (PDV).
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ca0cb32ac3ee508ddcd5346a895fb9904fa92517
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842741"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a><span data-ttu-id="791fa-103">Sincronizar la gestión de tareas entre Microsoft Teams y Dynamics 365 Commerce PDV</span><span class="sxs-lookup"><span data-stu-id="791fa-103">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="791fa-104">Este tema describe cómo sincronizar la administración de tareas entre Microsoft Teams y Dynamics 365 Commerce punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="791fa-104">This topic describes how to synchronize task management between Microsoft Teams and Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="791fa-105">Uno de los propósitos principales de la integración de Teams es permitir la sincronización de la administración de tareas entre la aplicación PDV y Teams.</span><span class="sxs-lookup"><span data-stu-id="791fa-105">One of the main purposes of Teams integration is to enable the synchronization of task management between the POS application and Teams.</span></span> <span data-ttu-id="791fa-106">De esta manera, los empleados de la tienda pueden usar la aplicación PDV o Teams para administrar tareas y no tienen que cambiar de aplicación.</span><span class="sxs-lookup"><span data-stu-id="791fa-106">In this way, store employees can use either the POS application or Teams to manage tasks, and don't have to switch applications.</span></span>

<span data-ttu-id="791fa-107">Debido a que Planner se usa como repositorio de tareas en Teams, debe haber un vínculo entre Teams y Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="791fa-107">Because Planner is used as a repository for tasks in Teams, there must be a link between Teams and Dynamics 365 Commerce.</span></span> <span data-ttu-id="791fa-108">Este vínculo se establece mediante el uso de un ID de plan específico para un equipo de tienda determinado.</span><span class="sxs-lookup"><span data-stu-id="791fa-108">This link is established by using a specific plan ID for a given store team.</span></span>

<span data-ttu-id="791fa-109">Los siguientes procedimientos muestran cómo configurar la sincronización de la administración de tareas entre las aplicaciones PDV y Teams.</span><span class="sxs-lookup"><span data-stu-id="791fa-109">The following procedures show how to set up task management synchronization between the POS and Teams applications.</span></span>

## <a name="publish-a-test-task-list-in-teams"></a><span data-ttu-id="791fa-110">Publica una lista de tareas de prueba en Teams</span><span class="sxs-lookup"><span data-stu-id="791fa-110">Publish a test task list in Teams</span></span>

<span data-ttu-id="791fa-111">El siguiente procedimiento asume que los equipos de su tienda están usando la integración de la gestión de tareas de Microsoft Teams con Commerce por primera vez.</span><span class="sxs-lookup"><span data-stu-id="791fa-111">The following procedure assumes that your store teams are using Microsoft Teams task management integration with Commerce for the first time.</span></span>

<span data-ttu-id="791fa-112">Para publicar una lista de tareas de prueba en Teams, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="791fa-112">To publish a test task list in Teams, follow these steps.</span></span>

1. <span data-ttu-id="791fa-113">Inicie sesión en el Teams como director de comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="791fa-113">Sign in to Teams as a communications manager.</span></span> <span data-ttu-id="791fa-114">Por lo general, los administradores de comunicaciones son usuarios que tienen el rol **Administrador regional** en Commerce.</span><span class="sxs-lookup"><span data-stu-id="791fa-114">Typically, communications managers are users who have the **Regional manager** role in Commerce.</span></span>
1. <span data-ttu-id="791fa-115">En el panel de navegación izquierdo, seleccione **Tareas por planificador**.</span><span class="sxs-lookup"><span data-stu-id="791fa-115">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="791fa-116">En la pestaña **Listas publicadas**, seleccione **Lista nueva** en la parte inferior izquierda y nombre a la nueva lista **Lista de tareas de prueba**.</span><span class="sxs-lookup"><span data-stu-id="791fa-116">On the **Published lists** tab, select **New list** in the lower left, and name the new list **Test task list**.</span></span>
1. <span data-ttu-id="791fa-117">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="791fa-117">Select **Create**.</span></span> <span data-ttu-id="791fa-118">La nueva lista aparece en **Borradores**.</span><span class="sxs-lookup"><span data-stu-id="791fa-118">The new list appears under **Drafts**.</span></span>
1. <span data-ttu-id="791fa-119">Bajo **Título de la tarea**, dele a la primera tarea el título **Integración de Teams de prueba**.</span><span class="sxs-lookup"><span data-stu-id="791fa-119">Under **Task title**, give the first task the title **Testing Teams integration**.</span></span> <span data-ttu-id="791fa-120">Luego seleccione **Introducir**.</span><span class="sxs-lookup"><span data-stu-id="791fa-120">Then select **Enter**.</span></span>
1. <span data-ttu-id="791fa-121">En la lista **Borradores**, seleccione la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="791fa-121">In the **Drafts** list, select the task list.</span></span> <span data-ttu-id="791fa-122">Luego seleccione **Publicar** en la esquina superior derecha.</span><span class="sxs-lookup"><span data-stu-id="791fa-122">Then select **Publish** in the upper-right corner.</span></span>
1. <span data-ttu-id="791fa-123">En el cuadro de diálogo **Seleccione a quién publicar**, seleccione los equipos que deben recibir la lista de tareas de prueba.</span><span class="sxs-lookup"><span data-stu-id="791fa-123">In the **Select who to publish to** dialog box, select the teams that should receive the test task list.</span></span>
1. <span data-ttu-id="791fa-124">Seleccione **Siguiente** para revisar su plan de publicación.</span><span class="sxs-lookup"><span data-stu-id="791fa-124">Select **Next** to review your publication plan.</span></span> <span data-ttu-id="791fa-125">Si debe realizar cambios, seleccione  **Atrás**.</span><span class="sxs-lookup"><span data-stu-id="791fa-125">If you must make changes, select **Back**.</span></span> 
1. <span data-ttu-id="791fa-126">Seleccione **Confirmar para continuar** y luego seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="791fa-126">Select **Confirm to proceed**, and then select **Publish**.</span></span>
1. <span data-ttu-id="791fa-127">Una vez finalizada la publicación, aparecerá un mensaje en la parte superior de la pestaña **Listas publicadas** indica si su lista de tareas se entregó correctamente.</span><span class="sxs-lookup"><span data-stu-id="791fa-127">After publishing is completed, a message at the top of the **Published lists** tab indicates whether your task list was successfully delivered.</span></span>

<span data-ttu-id="791fa-128">Para más información, consulte [Publique listas de tareas para crear y realizar un seguimiento del trabajo en su organización](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span><span class="sxs-lookup"><span data-stu-id="791fa-128">For more information, see [Publish task lists to create and track work in your organization](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span></span>

## <a name="link-pos-and-teams-for-task-management"></a><span data-ttu-id="791fa-129">Vincular PDV y Teams para la gestión de tareas</span><span class="sxs-lookup"><span data-stu-id="791fa-129">Link POS and Teams for task management</span></span>

<span data-ttu-id="791fa-130">Para vincular las aplicaciones PDV y Microsoft Teams para la gestión de tareas en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="791fa-130">To link the POS and Microsoft Teams applications for task management in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="791fa-131">Vaya a **Retail y Commerce \> Administración de tareas \> Integración de tareas con Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="791fa-131">Go to **Retail and Commerce \> Task management \> Tasks integration with Microsoft Teams**.</span></span>
1. <span data-ttu-id="791fa-132">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="791fa-132">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="791fa-133">Establezca la opción **Habilitar la integración de integración de tareas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="791fa-133">Set the **Enable Task Management Integration** option to **Yes**.</span></span>
1. <span data-ttu-id="791fa-134">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="791fa-134">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="791fa-135">En el panel de acciones, seleccione **Configurar administración de tarea**.</span><span class="sxs-lookup"><span data-stu-id="791fa-135">On the Action Pane, select **Setup task management**.</span></span> <span data-ttu-id="791fa-136">Debería recibir una notificación que indique que un trabajo por lotes que se denomina **Provisión de equipos** se está creando.</span><span class="sxs-lookup"><span data-stu-id="791fa-136">You should receive a notification that indicates that a batch job that is named **Teams provision** is being created.</span></span>
1. <span data-ttu-id="791fa-137">Vaya a **Administración del sistema \> Consultas \> Trabajos por lotes** y busque el trabajo más reciente que tenga la descripción **Provisión de equipos**.</span><span class="sxs-lookup"><span data-stu-id="791fa-137">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="791fa-138">Espere hasta que este trabajo termine de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="791fa-138">Wait until this job has finished running.</span></span>
1. <span data-ttu-id="791fa-139">Ejecute el **trabajo CDX 1070** para publicar el identificador del plan y almacenar referencias en Retail Server.</span><span class="sxs-lookup"><span data-stu-id="791fa-139">Run the **CDX job 1070** to publish the plan ID and store references to Retail Server.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="791fa-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="791fa-140">Additional resources</span></span>

[<span data-ttu-id="791fa-141">Información general sobre integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="791fa-141">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="791fa-142">Habilitar la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="791fa-142">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="791fa-143">Aprovisionar Microsoft Teams desde Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="791fa-143">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="791fa-144">Administrar roles de usuario en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="791fa-144">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="791fa-145">Asignar tiendas y equipos si estos últimos ya existen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="791fa-145">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="791fa-146">Preguntas frecuentes de la integración de Dynamics 365 Commerce y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="791fa-146">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
