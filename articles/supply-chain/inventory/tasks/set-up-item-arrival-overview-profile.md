---
title: "Configurar un perfil de visión general de recepción de artículos"
description: "Esta tarea se centra en la configuración de un perfil general de llegadas."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 5ddc491d73bbb6ac02e37a9c9b9d93545f6f9556
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="7c2d6-103">Configurar un perfil de visión general de recepción de artículos</span><span class="sxs-lookup"><span data-stu-id="7c2d6-103">Set up an item arrival overview profile</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7c2d6-104">Esta tarea se centra en la configuración de un perfil general de llegadas.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-104">This task focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="7c2d6-105">El perfil general de llegadas es una recopilación de reglas que se aplicarán cuando un usuario abra la página Visión general de llegadas.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-105">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="7c2d6-106">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-106">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="7c2d6-107">Este procedimiento normalmente se llevaría a cabo por un empleado de recepción.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-107">This procedure would typically be carried out by a receiving clerk.</span></span>





1. <span data-ttu-id="7c2d6-108">Vaya a Gestión del inventario > Configuración > Distribución > Perfiles de visión general de llegadas.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-108">Go to Inventory management > Setup > Distribution > Arrival overview profiles.</span></span>
2. <span data-ttu-id="7c2d6-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-109">Click New.</span></span>
    * <span data-ttu-id="7c2d6-110">Dado que casi siempre trabajará en el mismo almacén para descargar cargas completas de camión, debe crear un perfil general de llegadas para simplificar el proceso de registrar los artículos recibidos.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-110">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="7c2d6-111">En el campo Nombre de perfil de visión general de llegadas, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-111">In the Arrival overview profile name field, type a value.</span></span>
4. <span data-ttu-id="7c2d6-112">En el campo Mostrar líneas, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-112">In the Show lines field, select an option.</span></span>
    * <span data-ttu-id="7c2d6-113">Seleccione las líneas que mostrar en las recepciones: Todo: mostrar todas las líneas, independientemente del estado.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-113">Select which lines to show for the receipts:   All – Show all lines, regardless of status.</span></span>   <span data-ttu-id="7c2d6-114">En curso: mostrar líneas para recepciones en las que el progreso sea Completo o Parcialmente.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-114">In progress – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="7c2d6-115">Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-115">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   <span data-ttu-id="7c2d6-116">Incompleto: mostrar líneas para recepciones en las que el progreso sea Ninguno o Parcialmente.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-116">Not complete – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="7c2d6-117">Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-117">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  
5. <span data-ttu-id="7c2d6-118">Expanda o contraiga la sección Opciones de llegada.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-118">Expand or collapse the Arrival options section.</span></span>
6. <span data-ttu-id="7c2d6-119">En el campo Días hacia adelante, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-119">In the Days forward field, type a value.</span></span>
    * <span data-ttu-id="7c2d6-120">Esto establece un filtro para mostrar líneas de recepción previstas dentro de los próximos días (según el número que se establezca).</span><span class="sxs-lookup"><span data-stu-id="7c2d6-120">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="7c2d6-121">En el campo Días hacia atrás, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-121">In the Days back field, type a value.</span></span>
    * <span data-ttu-id="7c2d6-122">Esto establece un filtro para mostrar líneas de recepción previstas para varios días antes de hoy.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-122">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="7c2d6-123">En el campo Almacenes, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-123">In the Warehouses field, type a value.</span></span>
    * <span data-ttu-id="7c2d6-124">Aplique un filtro por uno o varios almacenes.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-124">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="7c2d6-125">En el campo Modo de entrega, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-125">In the Mode of delivery field, select a value.</span></span>
    * <span data-ttu-id="7c2d6-126">Esto establece un filtro para mostrar solo las líneas de recepción con este modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-126">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="7c2d6-127">En el campo Nombre, seleccione WHS.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-127">In the Name field, select WHS.</span></span>
11. <span data-ttu-id="7c2d6-128">En el campo Almacén, seleccione el almacén 24.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-128">In the Warehouse field, select warehouse 24.</span></span>
    * <span data-ttu-id="7c2d6-129">Este es el almacén predeterminado que se usará para las líneas de recepción registradas que usen este perfil.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-129">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="7c2d6-130">En el campo Ubicación, seleccione Baydoor.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-130">In the Location field, select Baydoor.</span></span>
    * <span data-ttu-id="7c2d6-131">Esta es la ubicación predeterminada que se usará para las líneas de recepción registradas que usen este perfil.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-131">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="7c2d6-132">Expanda o contraiga la sección Detalles de consulta de llegada.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-132">Expand or collapse the Arrival query details section.</span></span>
14. <span data-ttu-id="7c2d6-133">En el campo Restringir a sitio, seleccione el sitio 2.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-133">In the Restrict to site field, select site 2.</span></span>
    * <span data-ttu-id="7c2d6-134">Esto establece un filtro para mostrar solo las líneas de recepción con este sitio.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-134">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="7c2d6-135">Establezca la opción Pedidos de compra en Sí.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-135">Set the Purchase orders option to Yes.</span></span>
    * <span data-ttu-id="7c2d6-136">Seleccione líneas de recepción de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-136">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="7c2d6-137">Establezca la opción Pedidos de transferencia en Sí.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-137">Set the Transfer orders option to Yes.</span></span>
    * <span data-ttu-id="7c2d6-138">Seleccione líneas de recepción de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-138">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="7c2d6-139">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-139">Click Save.</span></span>
18. <span data-ttu-id="7c2d6-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="7c2d6-140">Close the page.</span></span>

