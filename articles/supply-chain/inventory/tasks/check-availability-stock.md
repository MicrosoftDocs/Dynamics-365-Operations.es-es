---
title: Comprobar la disponibilidad de existencias
description: Este procedimiento le muestra cómo comprobar el inventario disponible y el inventario físico disponible para un número de artículo concreto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnHandItemListPage, SysQueryForm, InventDimParmFixed, InventSupply, DefaultDashboard, WHSInventPhysicalOnhand, WHSOnHand
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b78b2e4ec3179450d635857353846c9bcb23eed
ms.sourcegitcommit: ef08bf1258aefb525d56bf85ef19311be26ab94c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "1795181"
---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="05ca7-103">Comprobar la disponibilidad de existencias</span><span class="sxs-lookup"><span data-stu-id="05ca7-103">Check the availability of stock</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="05ca7-104">Este procedimiento le muestra cómo comprobar el inventario disponible y el inventario físico disponible para un número de artículo concreto.</span><span class="sxs-lookup"><span data-stu-id="05ca7-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="05ca7-105">También se muestra cómo obtener la información de suministro relacionada con un artículo.</span><span class="sxs-lookup"><span data-stu-id="05ca7-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="05ca7-106">El inventario físico disponible es el inventario disponible que se tiene a mano, es decir, se ha comprado, recibido y registrado.</span><span class="sxs-lookup"><span data-stu-id="05ca7-106">Physical on-hand inventory is the on-hand inventory that’s available – that is, it’s purchased, received and registered.</span></span> <span data-ttu-id="05ca7-107">El inventario disponible incluye el inventario disponible que se tiene a mano, pero también el inventario pedido y que se espera pero aún no se ha recibido o registrado.</span><span class="sxs-lookup"><span data-stu-id="05ca7-107">On-hand inventory includes the available on-hand inventory, but also the inventory that’s been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="05ca7-108">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="05ca7-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="05ca7-109">Si está usando USMF, puede utilizar los valores del ejemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="05ca7-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="05ca7-110">Estas tareas las realizará normalmente un trabajador del almacén.</span><span class="sxs-lookup"><span data-stu-id="05ca7-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="05ca7-111">Comprobar el inventario disponible de un artículo</span><span class="sxs-lookup"><span data-stu-id="05ca7-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="05ca7-112">Vaya a Gestión de inventario > Consultas e informes > Inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="05ca7-112">Go to Inventory management > Inquiries and reports > On-hand inventory.</span></span>
2. <span data-ttu-id="05ca7-113">Seleccione la fila Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="05ca7-113">Select the Item number row.</span></span>
    * <span data-ttu-id="05ca7-114">Para consultar el inventario disponible por número de artículo, seleccione la fila donde Tabla está establecido en Inventario disponible y Campo está establecido en Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="05ca7-114">To query the on-hand inventory by item number, select the row where the Table is set to On-hand inventory and Field is set to Item number.</span></span>  
3. <span data-ttu-id="05ca7-115">En el campo Criterios, seleccione el artículo que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="05ca7-115">In the Criteria field, select the item you want to query.</span></span>
    * <span data-ttu-id="05ca7-116">Si utiliza a la empresa de datos de prueba USMF, puede seleccionar "M9201".</span><span class="sxs-lookup"><span data-stu-id="05ca7-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="05ca7-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="05ca7-117">Click OK.</span></span>
5. <span data-ttu-id="05ca7-118">Haga clic en Dimensiones.</span><span class="sxs-lookup"><span data-stu-id="05ca7-118">Click Dimensions.</span></span>
    * <span data-ttu-id="05ca7-119">La ficha Dimensiones permite seleccionar cuánto detalle desea ver sobre su inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="05ca7-119">The Dimensions tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="05ca7-120">Si necesita los datos relacionados con la reserva, debe mostrar todas las dimensiones de inventario para los artículos que usan los procesos avanzados de almacén (WHS).</span><span class="sxs-lookup"><span data-stu-id="05ca7-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>  
6. <span data-ttu-id="05ca7-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="05ca7-121">Click OK.</span></span>
7. <span data-ttu-id="05ca7-122">En el panel de acciones, haga clic en Información relacionada.</span><span class="sxs-lookup"><span data-stu-id="05ca7-122">On the Action Pane, click Related information.</span></span>
    * <span data-ttu-id="05ca7-123">Si no ve esto, es posible que tenga que hacer clic en los puntos suspensivos (…) para ver opciones adicionales del panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="05ca7-123">If you don’t see this, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>  
8. <span data-ttu-id="05ca7-124">Haga clic en Visión general de suministros.</span><span class="sxs-lookup"><span data-stu-id="05ca7-124">Click Supply overview.</span></span>
    * <span data-ttu-id="05ca7-125">La ficha Visión general de suministros proporciona la información para un artículo específico, como la cantidad disponible, el plazo y la información del proveedor.</span><span class="sxs-lookup"><span data-stu-id="05ca7-125">The Supply overview tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="05ca7-126">Expanda la sección Disponible.</span><span class="sxs-lookup"><span data-stu-id="05ca7-126">Expand the On-hand section.</span></span>
10. <span data-ttu-id="05ca7-127">Expanda la sección Proveedores.</span><span class="sxs-lookup"><span data-stu-id="05ca7-127">Expand the Vendors section.</span></span>
11. <span data-ttu-id="05ca7-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="05ca7-128">Close the page.</span></span>
12. <span data-ttu-id="05ca7-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="05ca7-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="05ca7-130">Comprobar el inventario físico disponible</span><span class="sxs-lookup"><span data-stu-id="05ca7-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="05ca7-131">Vaya a Gestión de almacén > Consultas e informes > Inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="05ca7-131">Go to Warehouse management > Inquiries and reports > Physical on-hand inventory.</span></span>
2. <span data-ttu-id="05ca7-132">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="05ca7-132">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="05ca7-133">Puede utilizar los campos Sitio y Almacén para filtrar la lista de artículos.</span><span class="sxs-lookup"><span data-stu-id="05ca7-133">You can use the Site and Warehouse fields to filter the list of items.</span></span>  
3. <span data-ttu-id="05ca7-134">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="05ca7-134">Refresh the page.</span></span>
4. <span data-ttu-id="05ca7-135">Haga clic en Mostrar dimensiones.</span><span class="sxs-lookup"><span data-stu-id="05ca7-135">Click Display Dimensions.</span></span>
    * <span data-ttu-id="05ca7-136">La ficha Mostrar dimensiones permite seleccionar cuánto detalle desea ver sobre su inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="05ca7-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>  
5. <span data-ttu-id="05ca7-137">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="05ca7-137">Click OK.</span></span>
6. <span data-ttu-id="05ca7-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="05ca7-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="05ca7-139">Comprobar el inventario disponible por ubicación</span><span class="sxs-lookup"><span data-stu-id="05ca7-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="05ca7-140">Vaya a Gestión de almacén > Consultas e informes > Inventario disponible por ubicación.</span><span class="sxs-lookup"><span data-stu-id="05ca7-140">Go to Warehouse management > Inquiries and reports > On hand by location.</span></span>
2. <span data-ttu-id="05ca7-141">En el campo Almacén, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="05ca7-141">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="05ca7-142">Si utiliza a la empresa de datos de prueba USMF, puede usar “51".</span><span class="sxs-lookup"><span data-stu-id="05ca7-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="05ca7-143">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="05ca7-143">Refresh the page.</span></span>
4. <span data-ttu-id="05ca7-144">Haga clic en Mostrar dimensiones.</span><span class="sxs-lookup"><span data-stu-id="05ca7-144">Click Display Dimensions.</span></span>
5. <span data-ttu-id="05ca7-145">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="05ca7-145">Click OK.</span></span>
6. <span data-ttu-id="05ca7-146">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="05ca7-146">Close the page.</span></span>

