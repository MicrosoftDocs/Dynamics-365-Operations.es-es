---
title: Configurar un perfil de visión general de recepción de artículos
description: Este tema se centra en la configuración de un perfil general de llegadas.
author: ShylaThompson
manager: tfehr
ms.date: 07/30/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 49670e4287faf3e50a824a5cbedd83ea7dbb8152
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244360"
---
# <a name="set-up-an-item-arrival-overview-profile"></a><span data-ttu-id="0aa8f-103">Configurar un perfil de visión general de recepción de artículos</span><span class="sxs-lookup"><span data-stu-id="0aa8f-103">Set up an item arrival overview profile</span></span>

<span data-ttu-id="0aa8f-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="0aa8f-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="0aa8f-105">Este tema se centra en la configuración de un perfil general de llegadas.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-105">This topic focuses on the setup of an arrival overview profile.</span></span> <span data-ttu-id="0aa8f-106">El perfil general de llegadas es una recopilación de reglas que se aplicarán cuando un usuario abra la página Visión general de llegadas.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-106">The arrival overview profile is a collection of rules that will be applied when the Arrival overview page is opened by a user.</span></span> <span data-ttu-id="0aa8f-107">Puede utilizar este procedimiento en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-107">You can use this procedure in demo data company USMF.</span></span> <span data-ttu-id="0aa8f-108">Este procedimiento normalmente se llevaría a cabo por un empleado de recepción.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-108">This procedure would typically be carried out by a receiving clerk.</span></span>

1. <span data-ttu-id="0aa8f-109">En el panel de navegación, vaya a **Módulos > Gestión de inventarios > Configuración > Distribución > Perfiles de visión general de llegadas**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-109">In the navigation pane, go to **Modules > Inventory management > Setup > Distribution > Arrival overview profiles**.</span></span>
2. <span data-ttu-id="0aa8f-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-110">Select **New**.</span></span> <span data-ttu-id="0aa8f-111">Dado que casi siempre trabajará en el mismo almacén para descargar cargas completas de camión, debe crear un perfil general de llegadas para simplificar el proceso de registrar los artículos recibidos.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-111">Because you will almost always work in the same warehouse offloading full truck loads, you should create an arrival overview profile to simplify the process of registering received items.</span></span>  
3. <span data-ttu-id="0aa8f-112">En el campo **Nombre de perfil de visión general de llegadas**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-112">In the **Arrival overview profile name** field, type a value.</span></span>
4. <span data-ttu-id="0aa8f-113">En el campo **Mostrar líneas**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-113">In the **Show lines** field, select an option.</span></span> <span data-ttu-id="0aa8f-114">Seleccione las líneas que desee mostrar para las recepciones:</span><span class="sxs-lookup"><span data-stu-id="0aa8f-114">Select which lines to show for the receipts:</span></span>  

    - <span data-ttu-id="0aa8f-115">**Todo**: permite mostrar todas las líneas, independientemente de su estado.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-115">**All** – Show all lines, regardless of status.</span></span>   
    - <span data-ttu-id="0aa8f-116">**En curso**: permite mostrar líneas para recepciones en las que el progreso sea Completo o Parcialmente.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-116">**In progress** – Show lines for receipts in which the progress is Complete or Partly.</span></span> <span data-ttu-id="0aa8f-117">Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-117">This means that for each line, either the full quantity or part of the quantity has been registered in an arrival journal.</span></span>   
    - <span data-ttu-id="0aa8f-118">**Incompleto**: permite mostrar líneas para recepciones en las que el progreso sea Ninguno o Parcialmente.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-118">**Not complete** – Show lines for receipts in which the progress is None or Partly.</span></span> <span data-ttu-id="0aa8f-119">Esto significa que, para cada línea, se ha registrado toda la cantidad o una parte en un diario de recepción.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-119">This means that for each line, nothing or only part of the quantity has been registered in an arrival journal.</span></span>  

5. <span data-ttu-id="0aa8f-120">Expanda o contraiga la sección **Opciones de llegada**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-120">Expand or collapse the **Arrival options** section.</span></span>
6. <span data-ttu-id="0aa8f-121">En el campo **Días hacia adelante**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-121">In the **Days forward** field, type a value.</span></span> <span data-ttu-id="0aa8f-122">Esto establece un filtro para mostrar líneas de recepción previstas dentro de los próximos días (según el número que se establezca).</span><span class="sxs-lookup"><span data-stu-id="0aa8f-122">This sets a filter to show the receipt lines expected to be received within the next few days (depending on the number you set).</span></span>  
7. <span data-ttu-id="0aa8f-123">En el campo **Días hacia atrás**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-123">In the **Days back** field, type a value.</span></span> <span data-ttu-id="0aa8f-124">Esto establece un filtro para mostrar líneas de recepción previstas para varios días antes de hoy.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-124">This sets a filter to show the receipt lines expected to be received a number of days before today.</span></span>  
8. <span data-ttu-id="0aa8f-125">En el campo **Almacenes**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-125">In the **Warehouses** field, type a value.</span></span> <span data-ttu-id="0aa8f-126">Aplique un filtro por uno o varios almacenes.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-126">Filter on one or more warehouses.</span></span>  
9. <span data-ttu-id="0aa8f-127">En el campo **Modo de entrega**, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-127">In the **Mode of delivery** field, select a value.</span></span> <span data-ttu-id="0aa8f-128">Esto establece un filtro para mostrar solo las líneas de recepción con este modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-128">This sets a filter to show only the receipt lines with this Mode of delivery.</span></span>  
10. <span data-ttu-id="0aa8f-129">En el campo **Nombre**, seleccione WHS.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-129">In the **Name** field, select WHS.</span></span>
11. <span data-ttu-id="0aa8f-130">En el campo **Almacén**, seleccione el almacén 24.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-130">In the **Warehouse** field, select warehouse 24.</span></span> <span data-ttu-id="0aa8f-131">Este es el almacén predeterminado que se usará para las líneas de recepción registradas que usen este perfil.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-131">This is the default warehouse that will be used for registered receipt lines that use this profile.</span></span>  
12. <span data-ttu-id="0aa8f-132">En el campo **Ubicación**, seleccione **Baydoor**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-132">In the **Location** field, select **Baydoor**.</span></span> <span data-ttu-id="0aa8f-133">Esta es la ubicación predeterminada que se usará para las líneas de recepción registradas que usen este perfil.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-133">This is the default location that will be used for registered receipt lines that use this profile.</span></span>  
13. <span data-ttu-id="0aa8f-134">Expanda o contraiga la sección **Detalles de consulta de llegada**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-134">Expand or collapse the **Arrival query details** section.</span></span>
14. <span data-ttu-id="0aa8f-135">En el campo **Restringir a sitio**, seleccione el sitio 2.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-135">In the **Restrict to site** field, select site 2.</span></span> <span data-ttu-id="0aa8f-136">Esto establece un filtro para mostrar solo las líneas de recepción con este sitio.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-136">This sets a filter to show only the receipt lines with this site.</span></span>  
15. <span data-ttu-id="0aa8f-137">Establezca la opción **Pedidos de compra** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-137">Set the **Purchase orders** option to **Yes**.</span></span> <span data-ttu-id="0aa8f-138">Seleccione líneas de recepción de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-138">Select receipt lines from purchase orders.</span></span>  
16. <span data-ttu-id="0aa8f-139">Establezca la opción Pedidos de **transferencia** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-139">Set the **Transfer** orders option to **Yes**.</span></span> <span data-ttu-id="0aa8f-140">Seleccione líneas de recepción de pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-140">Select receipt lines from transfer orders.</span></span>  
17. <span data-ttu-id="0aa8f-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-141">Select **Save**.</span></span>
18. <span data-ttu-id="0aa8f-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0aa8f-142">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]