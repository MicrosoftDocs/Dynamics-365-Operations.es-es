---
title: Generar un plan con restricciones
description: Este tema explica cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad.
author: ShylaThompson
manager: tfehr
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d8b9d5712dd1b4f9958de775e1a2224b64485d05
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987223"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="df074-103">Generar un plan con restricciones</span><span class="sxs-lookup"><span data-stu-id="df074-103">Generate a constrained plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="df074-104">Este tema explica cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad.</span><span class="sxs-lookup"><span data-stu-id="df074-104">This topic explains how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="df074-105">El plan garantiza que la fabricación no comience antes de que los materiales estén disponibles y que no se reserven recursos en exceso.</span><span class="sxs-lookup"><span data-stu-id="df074-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="df074-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="df074-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="df074-107">Este procedimiento se va a utilizar para el planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="df074-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="df074-108">Configurar un plan restringido</span><span class="sxs-lookup"><span data-stu-id="df074-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="df074-109">En la página principal, seleccione el espacio trabajo **Planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="df074-109">In the home page, select the **Master planning** workspace.</span></span>
2. <span data-ttu-id="df074-110">Seleccione **Planes maestros** en la lista de vínculos en el extremo derecho del área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="df074-110">Select **Master plans** in the list of links on the far right side of the workspace.</span></span>
3. <span data-ttu-id="df074-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="df074-111">In the list, find and select the desired record.</span></span> <span data-ttu-id="df074-112">Ejemplo: **StaticPlan**</span><span class="sxs-lookup"><span data-stu-id="df074-112">Example: **StaticPlan**</span></span>  
4. <span data-ttu-id="df074-113">Seleccione **Sí** en el campo **Capacidad limitada**.</span><span class="sxs-lookup"><span data-stu-id="df074-113">Select **Yes** in the **Finite capacity** field.</span></span>
5. <span data-ttu-id="df074-114">En el campo **Límite de tiempo de capacidad finita**, indique `30`.</span><span class="sxs-lookup"><span data-stu-id="df074-114">In the **Finite capacity time fence** field, enter `30`.</span></span>
6. <span data-ttu-id="df074-115">Expanda la sección **Límites de tiempo en días**.</span><span class="sxs-lookup"><span data-stu-id="df074-115">Expand the **Time fences in days** section.</span></span>
7. <span data-ttu-id="df074-116">Seleccione **Sí** en el campo **Capacidad**.</span><span class="sxs-lookup"><span data-stu-id="df074-116">Select **Yes** in the **Capacity** field.</span></span>
8. <span data-ttu-id="df074-117">En el campo **Límite de tiempo de programación de capacidad (días)**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="df074-117">In the **Capacity scheduling time fence (days)** field, enter a number.</span></span> <span data-ttu-id="df074-118">Ejemplo: `60`</span><span class="sxs-lookup"><span data-stu-id="df074-118">Example: `60`</span></span>  
9. <span data-ttu-id="df074-119">Seleccione **Sí** en el campo **Retrasos calculados**.</span><span class="sxs-lookup"><span data-stu-id="df074-119">Select **Yes** in the **Calculated delays** field.</span></span>
10. <span data-ttu-id="df074-120">En el campo **Calcular límite de tiempo de retrasos (días)**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="df074-120">In the **Calculate delays time fence (days)** field, enter a number.</span></span> <span data-ttu-id="df074-121">Ejemplo: `60`</span><span class="sxs-lookup"><span data-stu-id="df074-121">Example: `60`</span></span> 
11. <span data-ttu-id="df074-122">Expanda la sección **Retrasos calculados**.</span><span class="sxs-lookup"><span data-stu-id="df074-122">Expand the **Calculated delays** section.</span></span>
12. <span data-ttu-id="df074-123">Seleccione **Sí** en todos los campos **Agregar el retraso calculado a la fecha de requisito**.</span><span class="sxs-lookup"><span data-stu-id="df074-123">Select **Yes** in all **Add the calculated delay to the requirement date** fields.</span></span>
13. <span data-ttu-id="df074-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="df074-124">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="df074-125">Crear un plan restringido</span><span class="sxs-lookup"><span data-stu-id="df074-125">Create a constrained plan</span></span>
1. <span data-ttu-id="df074-126">Seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="df074-126">Select **Run**.</span></span>
2. <span data-ttu-id="df074-127">En el campo **Plan maestro**, especifique o seleccione el plan para el que ha configurado restricciones.</span><span class="sxs-lookup"><span data-stu-id="df074-127">In the **Master plan** field, enter or select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="df074-128">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="df074-128">Select **OK**.</span></span>
4. <span data-ttu-id="df074-129">Seleccione **Pedidos planificados**.</span><span class="sxs-lookup"><span data-stu-id="df074-129">Select **Planned orders**.</span></span>

