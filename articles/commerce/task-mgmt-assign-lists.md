---
title: Asignar listas de tareas a tiendas o empleados
description: Este tema describe cómo asignar listas de tareas a tiendas o empleados en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 82cec9861b759037f40315fb2e6f36002a0ac059
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036818"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="30790-103">Asignar listas de tareas a tiendas o empleados</span><span class="sxs-lookup"><span data-stu-id="30790-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="30790-104">Este tema describe cómo asignar listas de tareas a tiendas o empleados en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="30790-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="30790-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="30790-105">Overview</span></span>

<span data-ttu-id="30790-106">La gestión de tareas en Dynamics 365 Commerce le permite asignar una lista de tareas a múltiples tiendas o empleados, o a una combinación de tiendas y empleados.</span><span class="sxs-lookup"><span data-stu-id="30790-106">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="30790-107">Por ejemplo, un gerente regional de 20 tiendas podría querer asignar la lista de tareas **Preparación de la temporada de vacaciones** a las 20 tiendas.</span><span class="sxs-lookup"><span data-stu-id="30790-107">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="30790-108">Comience el proceso de asignación de la lista de tareas</span><span class="sxs-lookup"><span data-stu-id="30790-108">Start the task list assignment process</span></span>

<span data-ttu-id="30790-109">Para comenzar el proceso de asignación de una lista de tareas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30790-109">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="30790-110">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.</span><span class="sxs-lookup"><span data-stu-id="30790-110">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="30790-111">Seleccione la lista de tareas para asignar.</span><span class="sxs-lookup"><span data-stu-id="30790-111">Select the task list to assign.</span></span>
1. <span data-ttu-id="30790-112">Seleccione **Iniciar proceso**.</span><span class="sxs-lookup"><span data-stu-id="30790-112">Select **Start process**.</span></span>
1. <span data-ttu-id="30790-113">En el cuadro de diálogo **Iniciar proceso**, en la pestaña **General**, en el campo **Nombre del proceso**, introduzca un nombre (por ejemplo, **Tiendas de la región este**).</span><span class="sxs-lookup"><span data-stu-id="30790-113">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="30790-114">En el campo **Fecha objetivo**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="30790-114">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="30790-115">Para asignar la lista de tareas a las tiendas, en la pestaña **Tiendas**, use el filtro **Jerarquía organizativa** para buscar y seleccionar las tiendas.</span><span class="sxs-lookup"><span data-stu-id="30790-115">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="30790-116">Para asignar la lista de tareas a los empleados, en la pestaña **Trabajadores**, busque y seleccione a los empleados.</span><span class="sxs-lookup"><span data-stu-id="30790-116">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="30790-117">Seleccione **Aceptar** para iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="30790-117">Select **OK** to start the process.</span></span> <span data-ttu-id="30790-118">La lista de tareas se asigna a las tiendas o empleados seleccionados.</span><span class="sxs-lookup"><span data-stu-id="30790-118">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="30790-119">La siguiente ilustración muestra un ejemplo de cómo encontrar y seleccionar tiendas en el cuadro de diálogo **Iniciar proceso**.</span><span class="sxs-lookup"><span data-stu-id="30790-119">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Encontrar y seleccionar tiendas en el cuadro de diálogo Iniciar proceso](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="30790-121">Asigna listas de tareas de forma periódica</span><span class="sxs-lookup"><span data-stu-id="30790-121">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="30790-122">El minorista a veces tiene tareas recurrentes, como "Lista de verificación de cierre del jueves" o "Lista de verificación del primer día del mes".</span><span class="sxs-lookup"><span data-stu-id="30790-122">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="30790-123">Por lo tanto, es posible que desee asignar la lista de tareas de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="30790-123">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="30790-124">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.</span><span class="sxs-lookup"><span data-stu-id="30790-124">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="30790-125">Seleccione la lista de tareas para asignar.</span><span class="sxs-lookup"><span data-stu-id="30790-125">Select the task list to assign.</span></span>
1. <span data-ttu-id="30790-126">Seleccione **Iniciar proceso**.</span><span class="sxs-lookup"><span data-stu-id="30790-126">Select **Start process**.</span></span>
1. <span data-ttu-id="30790-127">En el cuadro de diálogo **Iniciar proceso**, en la pestaña **General**, en el campo **Nombre del proceso**, introduzca un nombre.</span><span class="sxs-lookup"><span data-stu-id="30790-127">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="30790-128">Establezca la opción **Periodicidad** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="30790-128">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="30790-129">En el campo **Fecha objetivo de periodicidad compensada en días**, introduzca una cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="30790-129">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="30790-130">Por ejemplo, si introduce **4**, la fecha objetivo es la fecha de periodicidad más cuatro días.</span><span class="sxs-lookup"><span data-stu-id="30790-130">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="30790-131">En la pestaña **Ejecutar en segundo plano** seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="30790-131">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="30790-132">En el cuadro de diálogo **Definir periodicidad**, introduzca los criterios de frecuencia y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="30790-132">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="30790-133">La siguiente ilustración muestra un ejemplo de cómo ingresar criterios de frecuencia en el cuadro de diálogo **Definir periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="30790-133">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Introducir el criterio de frecuencia en el cuadro de diálogo Definir periodicidad](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="30790-135">Seguimiento del estado de la lista de tareas</span><span class="sxs-lookup"><span data-stu-id="30790-135">Track task list status</span></span>

<span data-ttu-id="30790-136">Si es un gerente regional o gerente de tienda, es posible que desee realizar un seguimiento del estado de las listas de tareas que se han asignado a varias tiendas o empleados.</span><span class="sxs-lookup"><span data-stu-id="30790-136">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="30790-137">Luego puede hacer un seguimiento de las tiendas o los trabajadores que no completaron sus tareas asignadas a tiempo.</span><span class="sxs-lookup"><span data-stu-id="30790-137">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="30790-138">El back office de Commerce le permite ver el estado de las listas de tareas, reasignar tareas o cambiar el estado de una tarea.</span><span class="sxs-lookup"><span data-stu-id="30790-138">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="30790-139">Para realizar un seguimiento del estado de la lista de tareas para todas las tareas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30790-139">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="30790-140">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de procesos de tareas**.</span><span class="sxs-lookup"><span data-stu-id="30790-140">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="30790-141">Seleccione la pestaña **Todas las listas de tareas** para ver el estado de todas las listas de tareas asignadas a varias tiendas.</span><span class="sxs-lookup"><span data-stu-id="30790-141">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="30790-142">Para realizar un seguimiento de la lista de estado de tareas de todas las tareas que tiene asignadas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="30790-142">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="30790-143">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de procesos de tareas**.</span><span class="sxs-lookup"><span data-stu-id="30790-143">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="30790-144">Seleccione la pestaña **Mis tareas** o **Todas las tareas** para ver o actualizar el estado de las tareas que se le asignan.</span><span class="sxs-lookup"><span data-stu-id="30790-144">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30790-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="30790-145">Additional resources</span></span>

[<span data-ttu-id="30790-146">Visión general de la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="30790-146">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="30790-147">Configurar la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="30790-147">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="30790-148">Crear listas de tareas y agregar tareas</span><span class="sxs-lookup"><span data-stu-id="30790-148">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="30790-149">Administración de tareas en PDV</span><span class="sxs-lookup"><span data-stu-id="30790-149">Task management in POS</span></span>](task-mgmt-POS.md)
