---
title: Administración de tareas en PDV
description: Este tema describe la gestión de tareas en la aplicación de punto de venta (PDV) de Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 18ba781795058de6228c712c6a22e59038e96368
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478371"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="fe8ae-103">Administración de tareas en PDV</span><span class="sxs-lookup"><span data-stu-id="fe8ae-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe8ae-104">Este tema describe la gestión de tareas en la aplicación de punto de venta (PDV) de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="fe8ae-105">La aplicación Dynamics 365 Commerce PDV tiene funciones de administración de tareas que permiten a los gerentes de tienda y trabajadores administrar tareas y actualizar el estado de la tarea.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-105">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="fe8ae-106">Los trabajadores de la tienda pueden acceder a las tareas seleccionando el mosaico **Tareas** mosaico en la página de inicio de PDV o seleccionando notificaciones de tareas.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-106">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="fe8ae-107">Por defecto, los trabajadores de la tienda son llevados a la pestaña **Mis tareas**, donde pueden ver las tareas que se les asignan.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-107">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="fe8ae-108">Sin embargo, pueden cambiar fácilmente a las pestañas **Tareas atrasadas**, **Tareas abiertas** y **Listas de tareas**.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-108">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="fe8ae-109">Operaciones de tareas para gerentes de tienda</span><span class="sxs-lookup"><span data-stu-id="fe8ae-109">Task operations for store managers</span></span>

<span data-ttu-id="fe8ae-110">Los gerentes de tienda pueden realizar las siguientes operaciones de tareas en la aplicación PDV utilizando los botones de la barra de comandos:</span><span class="sxs-lookup"><span data-stu-id="fe8ae-110">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="fe8ae-111">**Asignar** - Asignar tareas seleccionadas a un trabajador de la tienda.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-111">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="fe8ae-112">**Estado de la tarea** - Cambia el estado de las tareas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-112">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="fe8ae-113">**Filtrar** - Por defecto, solo se muestran las tareas activas.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-113">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="fe8ae-114">Sin embargo, al aplicar filtros, los gerentes pueden ver todas las tareas, incluso las tareas que se han completado o cancelado.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-114">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="fe8ae-115">**Nueva tarea** - Crea una tarea en una lista de tareas existente o una tarea de un solo propósito.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-115">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="fe8ae-116">Los trabajadores de la tienda pueden realizar las siguientes operaciones de tareas en la aplicación PDV utilizando los botones de la barra de comandos:</span><span class="sxs-lookup"><span data-stu-id="fe8ae-116">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="fe8ae-117">**Estado de la tarea** - Cambia el estado de las tareas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-117">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="fe8ae-118">**Filtrar** - Por defecto, solo se muestran las tareas activas.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-118">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="fe8ae-119">Sin embargo, al aplicar filtros, los trabajadores pueden ver todas las tareas, incluso las tareas que se han completado o cancelado.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-119">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="fe8ae-120">La siguiente ilustración muestra la pestaña **Mis tareas** en la aplicación PDV de Commerce.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-120">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Pestaña Mis tareas en la aplicación PDV de Commerce](media/POS-task-management.png)

<span data-ttu-id="fe8ae-122">La ilustración siguiente muestra la pestaña **Lista de tareas**.</span><span class="sxs-lookup"><span data-stu-id="fe8ae-122">The following illustration shows the **Task lists** tab.</span></span>

![Pestaña lista de tareas en la aplicación PDV de Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="fe8ae-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fe8ae-124">Additional resources</span></span>

[<span data-ttu-id="fe8ae-125">Visión general de la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="fe8ae-125">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="fe8ae-126">Configurar la administración de tareas</span><span class="sxs-lookup"><span data-stu-id="fe8ae-126">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="fe8ae-127">Crear listas de tareas y agregar tareas</span><span class="sxs-lookup"><span data-stu-id="fe8ae-127">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="fe8ae-128">Asignar listas de tareas a tiendas o empleados</span><span class="sxs-lookup"><span data-stu-id="fe8ae-128">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
