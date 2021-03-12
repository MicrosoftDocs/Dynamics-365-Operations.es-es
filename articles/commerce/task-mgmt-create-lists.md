---
title: Crear listas de tareas y agregar tareas
description: Este tema describe cómo crear listas de tareas y agregarlas tareas en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cca5e0efd6516d02c372e8a616b6bb0c39f3088c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006219"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="e3373-103">Crear listas de tareas y agregar tareas</span><span class="sxs-lookup"><span data-stu-id="e3373-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e3373-104">Este tema describe cómo crear listas de tareas y agregarlas tareas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e3373-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e3373-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="e3373-105">Overview</span></span>

<span data-ttu-id="e3373-106">Una *tarea* define un trabajo específico o una acción que alguien debe completar en o antes de una fecha de vencimiento especificada.</span><span class="sxs-lookup"><span data-stu-id="e3373-106">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="e3373-107">En Dynamics 365 Commerce, una tarea puede incluir instrucciones detalladas e información sobre una persona de contacto.</span><span class="sxs-lookup"><span data-stu-id="e3373-107">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="e3373-108">También puede incluir enlaces a operaciones de back-office, operaciones de punto de venta (PDV) o páginas del sitio, para ayudar a mejorar la productividad y proporcionar el contexto que el propietario de la tarea requiere para completar la tarea de manera eficiente.</span><span class="sxs-lookup"><span data-stu-id="e3373-108">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="e3373-109">Una *lista de tareas* es una colección de tareas que deben completarse como parte de un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="e3373-109">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="e3373-110">Por ejemplo, puede haber una lista de tareas que un nuevo trabajador debe completar durante la incorporación, una lista de tareas para los cajeros que trabajan en turnos nocturnos o una lista de tareas que debe completarse para preparar la tienda para una próxima temporada de vacaciones.</span><span class="sxs-lookup"><span data-stu-id="e3373-110">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="e3373-111">En Commerce, cada lista de tareas que tiene una fecha objetivo se puede asignar a cualquier número de tiendas o empleados y se puede configurar para que se repita.</span><span class="sxs-lookup"><span data-stu-id="e3373-111">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="e3373-112">Tanto los gerentes como los trabajadores pueden crear listas de tareas en la oficina administrativa de Commerce y luego asignarlas a un conjunto de tiendas.</span><span class="sxs-lookup"><span data-stu-id="e3373-112">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="e3373-113">Crear una lista de tareas</span><span class="sxs-lookup"><span data-stu-id="e3373-113">Create a task list</span></span>

<span data-ttu-id="e3373-114">Para crear una lista de tareas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e3373-114">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="e3373-115">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.</span><span class="sxs-lookup"><span data-stu-id="e3373-115">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="e3373-116">Seleccione **Nueva** y luego introduzca valores en los campos **Nombre**, **Descripción** y **Propietario**.</span><span class="sxs-lookup"><span data-stu-id="e3373-116">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="e3373-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e3373-117">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="e3373-118">Agregar tareas a una lista de tareas</span><span class="sxs-lookup"><span data-stu-id="e3373-118">Add tasks to a task list</span></span>

<span data-ttu-id="e3373-119">Para agregar tareas a una lista de tareas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e3373-119">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="e3373-120">En la ficha desplegable **Tareas** de una lista de tareas existente, seleccione **Nueva** para agregar una tarea.</span><span class="sxs-lookup"><span data-stu-id="e3373-120">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="e3373-121">En el cuadro de diálogo **Crear una tarea nueva**, en el campo **Nombre** introduzca un nombre para la tarea.</span><span class="sxs-lookup"><span data-stu-id="e3373-121">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="e3373-122">En el campo **Datos debidos compensados desde la fecha objetivo**, introduzca un valor entero positivo o negativo.</span><span class="sxs-lookup"><span data-stu-id="e3373-122">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="e3373-123">Por ejemplo, introduzca **-2** si la tarea debe completarse dos días antes de la fecha de vencimiento de la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="e3373-123">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="e3373-124">En el campo **Notas**, introduzca instrucciones detalladas.</span><span class="sxs-lookup"><span data-stu-id="e3373-124">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="e3373-125">En el campo **Persona de contacto** introduzca el nombre de un experto en la materia que el propietario de la tarea puede contactar si necesita ayuda.</span><span class="sxs-lookup"><span data-stu-id="e3373-125">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="e3373-126">En el campo **Enlace de tarea**, introduzca un enlace, basado en la naturaleza de la tarea.</span><span class="sxs-lookup"><span data-stu-id="e3373-126">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="e3373-127">Aunque puedes usar el campo **Asignado a** para asignar tareas a alguien mientras está creando una lista de tareas, le recomendamos que evite asignar tareas durante la creación de la lista de tareas.</span><span class="sxs-lookup"><span data-stu-id="e3373-127">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="e3373-128">En su lugar, asigne las tareas después de que la lista se instancie para tiendas individuales.</span><span class="sxs-lookup"><span data-stu-id="e3373-128">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="e3373-129">Use enlaces de tareas para ayudar a mejorar la productividad de los trabajadores</span><span class="sxs-lookup"><span data-stu-id="e3373-129">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="e3373-130">Commerce le permite vincular tareas a operaciones PDV específicas, como ejecutar un informe de ventas, ver un video de capacitación en línea para orientación de nuevos empleados o realizar una operación de back-office.</span><span class="sxs-lookup"><span data-stu-id="e3373-130">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="e3373-131">Esta característica ayuda a los propietarios de tareas a obtener la información que necesitan para completar una tarea de manera eficiente.</span><span class="sxs-lookup"><span data-stu-id="e3373-131">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="e3373-132">Para agregar enlaces de tareas mientras crea una tarea, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e3373-132">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="e3373-133">En la ficha desplegable **Tareas** de una lista de tareas existente, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e3373-133">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="e3373-134">En el cuadro de diálogo **Editar tarea**, en el campo **Enlace de tarea**, seleccione una o más de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e3373-134">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="e3373-135">Seleccione **Opción del menú** para configurar una operación de back-office, como "Kits de productos".</span><span class="sxs-lookup"><span data-stu-id="e3373-135">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="e3373-136">Seleccione **Operación PDV** para configurar una operación PDV, como "Informes de ventas".</span><span class="sxs-lookup"><span data-stu-id="e3373-136">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="e3373-137">Seleccione **URL** para configurar una URL absoluta.</span><span class="sxs-lookup"><span data-stu-id="e3373-137">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="e3373-138">La siguiente ilustración muestra la selección de enlaces de tareas en el cuadro de diálogo **Editar tarea**.</span><span class="sxs-lookup"><span data-stu-id="e3373-138">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Seleccionar enlaces de tareas en el cuadro de diálogo Editar tarea](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="e3373-140">Configure una operación PDV para que pueda vincularse a una tarea</span><span class="sxs-lookup"><span data-stu-id="e3373-140">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="e3373-141">Para configurar una operación PDV para que pueda vincularse a una tarea, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e3373-141">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="e3373-142">Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> PDV \> Operaciones PDV**.</span><span class="sxs-lookup"><span data-stu-id="e3373-142">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="e3373-143">Seleccione **Editar**, encuentre la operación PDV y después seleccione la casilla **Habilitar administración de tareas**.</span><span class="sxs-lookup"><span data-stu-id="e3373-143">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e3373-144">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e3373-144">Additional resources</span></span>

[<span data-ttu-id="e3373-145">Visión general de la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="e3373-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="e3373-146">Configurar la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="e3373-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="e3373-147">Asignar listas de tareas a tiendas o empleados</span><span class="sxs-lookup"><span data-stu-id="e3373-147">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="e3373-148">Administración de tareas en PDV</span><span class="sxs-lookup"><span data-stu-id="e3373-148">Task management in POS</span></span>](task-mgmt-POS.md)
