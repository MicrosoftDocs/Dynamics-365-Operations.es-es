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
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3d249809f15b50c59620d69a901a427dc3ecb2f0
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477593"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="5d09e-103">Asignar listas de tareas a tiendas o empleados</span><span class="sxs-lookup"><span data-stu-id="5d09e-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5d09e-104">Este tema describe cómo asignar listas de tareas a tiendas o empleados en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5d09e-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5d09e-105">La gestión de tareas en Dynamics 365 Commerce le permite asignar una lista de tareas a múltiples tiendas o empleados, o a una combinación de tiendas y empleados.</span><span class="sxs-lookup"><span data-stu-id="5d09e-105">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="5d09e-106">Por ejemplo, un gerente regional de 20 tiendas podría querer asignar la lista de tareas **Preparación de la temporada de vacaciones** a las 20 tiendas.</span><span class="sxs-lookup"><span data-stu-id="5d09e-106">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="5d09e-107">Comience el proceso de asignación de la lista de tareas</span><span class="sxs-lookup"><span data-stu-id="5d09e-107">Start the task list assignment process</span></span>

<span data-ttu-id="5d09e-108">Para comenzar el proceso de asignación de una lista de tareas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5d09e-108">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="5d09e-109">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-109">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="5d09e-110">Seleccione la lista de tareas para asignar.</span><span class="sxs-lookup"><span data-stu-id="5d09e-110">Select the task list to assign.</span></span>
1. <span data-ttu-id="5d09e-111">Seleccione **Iniciar proceso**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-111">Select **Start process**.</span></span>
1. <span data-ttu-id="5d09e-112">En el cuadro de diálogo **Iniciar proceso**, en la pestaña **General**, en el campo **Nombre del proceso**, introduzca un nombre (por ejemplo, **Tiendas de la región este**).</span><span class="sxs-lookup"><span data-stu-id="5d09e-112">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="5d09e-113">En el campo **Fecha objetivo**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="5d09e-113">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="5d09e-114">Para asignar la lista de tareas a las tiendas, en la pestaña **Tiendas**, use el filtro **Jerarquía organizativa** para buscar y seleccionar las tiendas.</span><span class="sxs-lookup"><span data-stu-id="5d09e-114">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="5d09e-115">Para asignar la lista de tareas a los empleados, en la pestaña **Trabajadores**, busque y seleccione a los empleados.</span><span class="sxs-lookup"><span data-stu-id="5d09e-115">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="5d09e-116">Seleccione **Aceptar** para iniciar el proceso.</span><span class="sxs-lookup"><span data-stu-id="5d09e-116">Select **OK** to start the process.</span></span> <span data-ttu-id="5d09e-117">La lista de tareas se asigna a las tiendas o empleados seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5d09e-117">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="5d09e-118">La siguiente ilustración muestra un ejemplo de cómo encontrar y seleccionar tiendas en el cuadro de diálogo **Iniciar proceso**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-118">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Encontrar y seleccionar tiendas en el cuadro de diálogo Iniciar proceso](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="5d09e-120">Asigna listas de tareas de forma periódica</span><span class="sxs-lookup"><span data-stu-id="5d09e-120">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="5d09e-121">El minorista a veces tiene tareas recurrentes, como "Lista de verificación de cierre del jueves" o "Lista de verificación del primer día del mes".</span><span class="sxs-lookup"><span data-stu-id="5d09e-121">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="5d09e-122">Por lo tanto, es posible que desee asignar la lista de tareas de forma periódica.</span><span class="sxs-lookup"><span data-stu-id="5d09e-122">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="5d09e-123">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de tareas**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-123">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="5d09e-124">Seleccione la lista de tareas para asignar.</span><span class="sxs-lookup"><span data-stu-id="5d09e-124">Select the task list to assign.</span></span>
1. <span data-ttu-id="5d09e-125">Seleccione **Iniciar proceso**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-125">Select **Start process**.</span></span>
1. <span data-ttu-id="5d09e-126">En el cuadro de diálogo **Iniciar proceso**, en la pestaña **General**, en el campo **Nombre del proceso**, introduzca un nombre.</span><span class="sxs-lookup"><span data-stu-id="5d09e-126">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="5d09e-127">Establezca la opción **Periodicidad** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-127">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="5d09e-128">En el campo **Fecha objetivo de periodicidad compensada en días**, introduzca una cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="5d09e-128">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="5d09e-129">Por ejemplo, si introduce **4**, la fecha objetivo es la fecha de periodicidad más cuatro días.</span><span class="sxs-lookup"><span data-stu-id="5d09e-129">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="5d09e-130">En la pestaña **Ejecutar en segundo plano** seleccione **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-130">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="5d09e-131">En el cuadro de diálogo **Definir periodicidad**, introduzca los criterios de frecuencia y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-131">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="5d09e-132">La siguiente ilustración muestra un ejemplo de cómo ingresar criterios de frecuencia en el cuadro de diálogo **Definir periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-132">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Introducir el criterio de frecuencia en el cuadro de diálogo Definir periodicidad](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="5d09e-134">Seguimiento del estado de la lista de tareas</span><span class="sxs-lookup"><span data-stu-id="5d09e-134">Track task list status</span></span>

<span data-ttu-id="5d09e-135">Si es un gerente regional o gerente de tienda, es posible que desee realizar un seguimiento del estado de las listas de tareas que se han asignado a varias tiendas o empleados.</span><span class="sxs-lookup"><span data-stu-id="5d09e-135">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="5d09e-136">Luego puede hacer un seguimiento de las tiendas o los trabajadores que no completaron sus tareas asignadas a tiempo.</span><span class="sxs-lookup"><span data-stu-id="5d09e-136">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="5d09e-137">El back office de Commerce le permite ver el estado de las listas de tareas, reasignar tareas o cambiar el estado de una tarea.</span><span class="sxs-lookup"><span data-stu-id="5d09e-137">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="5d09e-138">Para realizar un seguimiento del estado de la lista de tareas para todas las tareas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5d09e-138">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="5d09e-139">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de procesos de tareas**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-139">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="5d09e-140">Seleccione la pestaña **Todas las listas de tareas** para ver el estado de todas las listas de tareas asignadas a varias tiendas.</span><span class="sxs-lookup"><span data-stu-id="5d09e-140">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="5d09e-141">Para realizar un seguimiento de la lista de estado de tareas de todas las tareas que tiene asignadas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5d09e-141">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="5d09e-142">Vaya a **Retail y Commerce \> Administración de tareas \> Administración de procesos de tareas**.</span><span class="sxs-lookup"><span data-stu-id="5d09e-142">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="5d09e-143">Seleccione la pestaña **Mis tareas** o **Todas las tareas** para ver o actualizar el estado de las tareas que se le asignan.</span><span class="sxs-lookup"><span data-stu-id="5d09e-143">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5d09e-144">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5d09e-144">Additional resources</span></span>

[<span data-ttu-id="5d09e-145">Visión general de la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="5d09e-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="5d09e-146">Configurar la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="5d09e-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="5d09e-147">Crear listas de tareas y agregar tareas</span><span class="sxs-lookup"><span data-stu-id="5d09e-147">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="5d09e-148">Administración de tareas en PDV</span><span class="sxs-lookup"><span data-stu-id="5d09e-148">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
