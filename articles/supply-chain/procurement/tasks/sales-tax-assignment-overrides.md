---
title: Asignación de impuestos y anulaciones
description: Este procedimiento muestra cómo asignar grupos de impuestos a canales de Commerce.
author: mkirknel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 74a7eed04648c63c0b19d5de26d2bdbef59aec7d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207609"
---
# <a name="sales-tax-assignment-and-overrides"></a><span data-ttu-id="6f3ee-103">Asignación de impuestos y anulaciones</span><span class="sxs-lookup"><span data-stu-id="6f3ee-103">Sales tax assignment and overrides</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6f3ee-104">Este procedimiento muestra cómo asignar grupos de impuestos a canales de Commerce.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-104">This procedure demonstrates how to assign sales tax groups to commerce channels.</span></span> <span data-ttu-id="6f3ee-105">También recorre el proceso de crear una nueva anulación de impuestos y de asignarla a un grupo de anulaciones de impuestos de ventas existente.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-105">It also walks through the process of creating a new sales tax override and assigning it to an existing sales tax override group.</span></span> <span data-ttu-id="6f3ee-106">Este procedimiento usa la empresa USRT en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-106">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="6f3ee-107">Vaya a Retail y Commerce > Canales > Tiendas > Todas las tiendas.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-107">Go to Retail and Commerce > Channels > Stores > All stores.</span></span>
2. <span data-ttu-id="6f3ee-108">En la lista, haga clic en el vínculo Id. de canal para “Houston”.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-108">In the list, click the Channel ID link for "Houston."</span></span>
3. <span data-ttu-id="6f3ee-109">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-109">Click Edit.</span></span>
    * <span data-ttu-id="6f3ee-110">El campo "Grupo de impuestos sobre las ventas" contiene la lista de grupos de impuestos para la empresa actual.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-110">The "Sales tax group" field contains the list of sales tax groups for the current company.</span></span> <span data-ttu-id="6f3ee-111">El grupo actualmente asignado es un grupo de impuestos “Texas” genérico.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-111">The currently assigned group is a generic "Texas" sales tax group.</span></span> <span data-ttu-id="6f3ee-112">También hay grupos de impuestos para “Washington “y “, Washington King County.”</span><span class="sxs-lookup"><span data-stu-id="6f3ee-112">There are also sales tax groups for "Washington" and "Washington, King County."</span></span> <span data-ttu-id="6f3ee-113">Los grupos de impuestos pueden incluir los impuestos aplicables para múltiples municipios.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-113">Sales tax groups can include applicable taxes for multiple municipalities.</span></span>  
    * <span data-ttu-id="6f3ee-114">El campo "Anulación de impuestos" es donde los grupos de anulaciones de impuestos se pueden asignar al canal.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-114">The "Sales tax override" field is where sales tax override groups can be mapped to the channel.</span></span> <span data-ttu-id="6f3ee-115">Los grupos de anulaciones de impuestos se pueden utilizar para agrupar juntas las anulaciones de impuestos que funcionan para múltiples tiendas.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-115">Sales tax override groups can be used to group together sales tax overrides that work for multiple stores.</span></span> <span data-ttu-id="6f3ee-116">En lugar de asignar manualmente las anulaciones de impuestos una a una, el grupo se puede crear y asignar directamente a los canales para ahorrar tiempo.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-116">Rather than manually assigning sales tax overrides one by one, the group can be created and assigned directly to the channels to save time.</span></span>  
4. <span data-ttu-id="6f3ee-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-117">Click Save.</span></span>
5. <span data-ttu-id="6f3ee-118">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-118">Close the page.</span></span>
6. <span data-ttu-id="6f3ee-119">Vaya a Retail y Commerce > Configuración de canal > Impuestos > Anulaciones de impuestos de ventas.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-119">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax overrides.</span></span>
7. <span data-ttu-id="6f3ee-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-120">Click New.</span></span>
8. <span data-ttu-id="6f3ee-121">En el campo Anulación de impuestos, proporcione un nombre para su nueva anulación.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-121">In the Sales tax override field, provide a name for your new override.</span></span>
9. <span data-ttu-id="6f3ee-122">En el campo Descripción, proporcione una descripción de la anulación.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-122">In the Description field, provide a description of the override.</span></span>
10. <span data-ttu-id="6f3ee-123">Establezca el estado en “Habilitar”.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-123">Set the status to "Enable."</span></span>
11. <span data-ttu-id="6f3ee-124">Expanda o contraiga la sección Anular.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-124">Expand or collapse the Override section.</span></span>
12. <span data-ttu-id="6f3ee-125">En el campo Tipo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-125">In the Type field, select an option.</span></span>
    * <span data-ttu-id="6f3ee-126">Los grupos de impuestos de artículos se pueden utilizar para anular impuestos para elementos específicos que pertenecen al grupo.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-126">Item sales tax groups can be used to override taxes for specific items that belong to the group.</span></span> <span data-ttu-id="6f3ee-127">Por ejemplo, los artículos de alimentos se gravan normalmente de manera diferente que los bienes durables y probablemente tendrían su propio grupo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-127">For example, food items are typically taxed differently from hard goods, and would likely have their own sales tax group.</span></span> <span data-ttu-id="6f3ee-128">Los grupos de impuestos son grupos de impuestos que son aplicables a un canal concreto.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-128">Sales tax groups are groups of taxes that are applicable to a particular channel.</span></span> <span data-ttu-id="6f3ee-129">Por ejemplo, si un canal vende tanto al por menor como de negocio a negocio, se pueden usar diferentes grupos de impuestos de artículos.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-129">For example, if a channel sells both retail and business-to-business, different items sales tax groups may be used.</span></span> <span data-ttu-id="6f3ee-130">Se asignarían todos los impuestos aplicables al grupo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-130">All the applicable taxes would be mapped to the sales tax group.</span></span>  
    * <span data-ttu-id="6f3ee-131">Ahora puede seleccionar los impuestos "De" y "A" o "Grupo de impuestos de origen" y "Grupo de impuestos de destino" para crear su anulación de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-131">Now you can select the "From" and "To" taxes or "From tax group" and "To tax group" to create your sales tax override.</span></span> <span data-ttu-id="6f3ee-132">El campo “De” indica el impuesto o el grupo de impuestos que se anulará.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-132">The "From" field indicates the tax or tax group to be overridden.</span></span> <span data-ttu-id="6f3ee-133">La anulación por Grupo de impuestos de artículos proporciona diferentes opciones a la anulación por grupo de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-133">Overriding by Item sales tax group provides different options than overriding by sales tax group.</span></span> <span data-ttu-id="6f3ee-134">Las anulaciones de impuestos de ventas se pueden configurar para anular impuestos en transacciones completas o en líneas concretas en la transacción.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-134">Sales tax overrides can be set up to override taxes on entire transactions or on particular lines in the transaction.</span></span>  
13. <span data-ttu-id="6f3ee-135">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-135">Click Save.</span></span>
14. <span data-ttu-id="6f3ee-136">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-136">Close the page.</span></span>
15. <span data-ttu-id="6f3ee-137">Vaya a Retail y Commerce > Configuración de canal > Impuestos > Grupos de anulaciones de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-137">Go to Retail and Commerce > Channel setup > Sales taxes > Sales tax override groups.</span></span>
    * <span data-ttu-id="6f3ee-138">En este paso asignará la anulación de impuestos recién creada al grupo de anulaciones de impuestos de ventas asignado al canal Houston.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-138">In this step you will assigned the newly created sales tax override to the sales tax override group assigned to the Houston channel.</span></span>  
16. <span data-ttu-id="6f3ee-139">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-139">Click Edit.</span></span>
17. <span data-ttu-id="6f3ee-140">Expanda o contraiga la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-140">Expand or collapse the Setup section.</span></span>
18. <span data-ttu-id="6f3ee-141">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-141">Click Add.</span></span>
19. <span data-ttu-id="6f3ee-142">En el campo Anulación de impuestos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-142">In the Sales tax override field, click the drop-down button to open the lookup.</span></span>
20. <span data-ttu-id="6f3ee-143">Seleccione la anulación de impuestos previamente creada del impuesto sobre venta en la lista.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-143">Select the previously created sales tax override from the list.</span></span>
21. <span data-ttu-id="6f3ee-144">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-144">In the list, click the link in the selected row.</span></span>
22. <span data-ttu-id="6f3ee-145">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6f3ee-145">Click Save.</span></span>

