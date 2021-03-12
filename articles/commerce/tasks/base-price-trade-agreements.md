---
title: Precio base y acuerdos comerciales
description: Este procedimiento le muestra la creación de acuerdos comerciales de precios de venta específicos de canal.
author: josaw1
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PriceDiscGroup, RetailStoreTable, RetailChannelPriceGroup, EcoResProductDetailsExtended, PriceDiscAdmTable, PriceDiscAdm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: db3a91807c0cfb51426c03eeaf7785168e6ad0de
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006067"
---
# <a name="base-price-and-trade-agreements"></a><span data-ttu-id="11ff5-103">Precio base y acuerdos comerciales</span><span class="sxs-lookup"><span data-stu-id="11ff5-103">Base price and trade agreements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="11ff5-104">Este procedimiento le muestra la creación de acuerdos comerciales de precios de venta específicos de canal.</span><span class="sxs-lookup"><span data-stu-id="11ff5-104">This procedure walks through creating channel-specific sales price trade agreements.</span></span> <span data-ttu-id="11ff5-105">Este procedimiento usa la empresa de datos de demostración USRT.</span><span class="sxs-lookup"><span data-stu-id="11ff5-105">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="11ff5-106">En el **Panel de navegación**, vaya a **Módulos > Retail y Commerce > Administración de precios y descuentos > Grupos de precios > Todos los grupos de precios**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-106">In the **Navigation pane**, go to **Modules > Retail and Commerce > Pricing and discounts management > Price groups > All price groups**.</span></span> <span data-ttu-id="11ff5-107">Los grupos de precios son la manera en que los acuerdos comerciales se asignan a los canales específicos.</span><span class="sxs-lookup"><span data-stu-id="11ff5-107">Price groups are how trade agreements are assigned to specific channels.</span></span> <span data-ttu-id="11ff5-108">El uso de grupos de precios para asignar acuerdos comerciales a un canal permite precios específicos de canal.</span><span class="sxs-lookup"><span data-stu-id="11ff5-108">Using price groups to assign trade agreements to a channel enables channel-specific pricing.</span></span>  
2. <span data-ttu-id="11ff5-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-109">Click **New**.</span></span>
3. <span data-ttu-id="11ff5-110">En el campo **Grupos de precios**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="11ff5-110">In the **Price groups** field, type a value.</span></span>
4. <span data-ttu-id="11ff5-111">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="11ff5-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="11ff5-112">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-112">Click **Save**.</span></span>
6. <span data-ttu-id="11ff5-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="11ff5-113">Close the page.</span></span>
7. <span data-ttu-id="11ff5-114">En el **Panel de navegación**, vaya **Módulos > Retail y Commerce > Canales > Tiendas > Todas las tiendas**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-114">In the **Navigation pane**, go to **Modules > Retail and Commerce > Channels > Stores > All stores**.</span></span>
8. <span data-ttu-id="11ff5-115">En la lista, seleccione "Nueva York"</span><span class="sxs-lookup"><span data-stu-id="11ff5-115">In the list, select 'New York'</span></span>
9. <span data-ttu-id="11ff5-116">En el panel de acciones, haga clic en **Tienda**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-116">On the Action Pane, click **Store**.</span></span>
10. <span data-ttu-id="11ff5-117">Haga clic en **Grupos de precios**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-117">Click **Price groups**.</span></span>
11. <span data-ttu-id="11ff5-118">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-118">Click **New**.</span></span>
12. <span data-ttu-id="11ff5-119">En el campo **Grupos de precios**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="11ff5-119">In the **Price groups** field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="11ff5-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="11ff5-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="11ff5-121">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-121">Click **Save**.</span></span>
15. <span data-ttu-id="11ff5-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="11ff5-122">Close the page.</span></span>
16. <span data-ttu-id="11ff5-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="11ff5-123">Close the page.</span></span>
17. <span data-ttu-id="11ff5-124">En el **Panel de navegación**, vaya a **Módulos > Retail y Commerce > Productos y categorías > Productos liberados por categoría**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-124">In the **Navigation pane**, go to **Modules > Retail and Commerce > Products and categories > Released products by category**.</span></span>
18. <span data-ttu-id="11ff5-125">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="11ff5-125">In the list, click the link in the selected row.</span></span>
19. <span data-ttu-id="11ff5-126">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-126">Click **Edit**.</span></span>
20. <span data-ttu-id="11ff5-127">Expanda la ficha desplegable **Ventas**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-127">Expand the **Sell** fastTab.</span></span>
21. <span data-ttu-id="11ff5-128">En el campo **Precio**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="11ff5-128">In the **Price** field, enter a number.</span></span> <span data-ttu-id="11ff5-129">Este precio se usa si no se encuentra ningún acuerdo comercial aplicable.</span><span class="sxs-lookup"><span data-stu-id="11ff5-129">This price is used if no applicable trade agreements are found.</span></span>  
22. <span data-ttu-id="11ff5-130">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-130">Click **Save**.</span></span>
23. <span data-ttu-id="11ff5-131">En **Panel de acciones**, haga clic en **Vender**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-131">On the **Action Pane**, click **Sell**.</span></span>
24. <span data-ttu-id="11ff5-132">Haga clic en **Crear acuerdos comerciales**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-132">Click **Create trade agreements**.</span></span>
25. <span data-ttu-id="11ff5-133">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-133">Click **New**.</span></span>
26. <span data-ttu-id="11ff5-134">En el campo **Nombre**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="11ff5-134">In the **Name** field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="11ff5-135">En la lista, seleccione **Commerce**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-135">In the list, select **Commerce**.</span></span> <span data-ttu-id="11ff5-136">En los datos de demostración, el nombre de diario **Commerce** tiene la relación predeterminada de **Precio (ventas)**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-136">In the demo data, the **Commerce** journal name has the default relation of **Price (sales)**.</span></span> <span data-ttu-id="11ff5-137">Esto significa que todas las nuevas líneas creadas se asignarán de forma predeterminada a los acuerdos comerciales de precio de ventas.</span><span class="sxs-lookup"><span data-stu-id="11ff5-137">That means all new lines created will default to sales price trade agreements.</span></span>  
28. <span data-ttu-id="11ff5-138">En el **panel de acciones**, haga clic en **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-138">On the **Action pane**, click **Lines**.</span></span>
29. <span data-ttu-id="11ff5-139">En el campo **Tipo de código de parte** seleccione "Grupo".</span><span class="sxs-lookup"><span data-stu-id="11ff5-139">In the **Party code type** field, select 'Group'.</span></span>
30. <span data-ttu-id="11ff5-140">En el campo **Selección de cuentas**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="11ff5-140">In the **Account selection** field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="11ff5-141">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="11ff5-141">In the list, find and select the desired record.</span></span> <span data-ttu-id="11ff5-142">Esto completará Vincular el grupo de precios a un cana al Acuerdo comercial.</span><span class="sxs-lookup"><span data-stu-id="11ff5-142">This will complete the link from Channel to Price group to Trade agreement.</span></span>  
32. <span data-ttu-id="11ff5-143">En el campo **Relación de artículos**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="11ff5-143">In the **Item relation** field, type a value.</span></span>
33. <span data-ttu-id="11ff5-144">En el campo **Importe en divisa**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="11ff5-144">In the **Amount in currency** field, enter a number.</span></span>
34. <span data-ttu-id="11ff5-145">En la ficha desplegable **Detalles**, active o desactive la casilla de verificación **Buscar siguiente**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-145">In the **Details** fastTab, check or uncheck the **Find next** checkbox.</span></span> <span data-ttu-id="11ff5-146">Cuando **Buscar siguiente** se establezca en "Sí", el motor de precios continuará buscando acuerdos comerciales aplicables con un precio de venta menor.</span><span class="sxs-lookup"><span data-stu-id="11ff5-146">When **Find next** is set to 'Yes', the pricing engine will continue to search for applicable trade agreements with a lower sale price.</span></span> <span data-ttu-id="11ff5-147">Cuando **Buscar siguiente** se establezca en "No", el motor de precios detendrá la búsqueda y usará el acuerdo comercial.</span><span class="sxs-lookup"><span data-stu-id="11ff5-147">When **Find next** is set to 'No', the price engine stops searching and uses the trade agreement.</span></span>  
35. <span data-ttu-id="11ff5-148">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-148">Click **Post**.</span></span>
36. <span data-ttu-id="11ff5-149">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-149">Click **OK**.</span></span>
37. <span data-ttu-id="11ff5-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="11ff5-150">Close the page.</span></span>
38. <span data-ttu-id="11ff5-151">En el panel **Acciones**, haga clic en Vender.</span><span class="sxs-lookup"><span data-stu-id="11ff5-151">On the **Action Pane**, click Sell.</span></span>
39. <span data-ttu-id="11ff5-152">Haga clic en **Precio de ventas**.</span><span class="sxs-lookup"><span data-stu-id="11ff5-152">Click **Sales price**.</span></span>

