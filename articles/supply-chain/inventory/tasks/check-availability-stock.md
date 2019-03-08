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
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26a8f51eda1f4249862a23fa0103b7a144d974a1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "338001"
---
# <a name="check-the-availability-of-stock"></a><span data-ttu-id="5e34f-103">Comprobar la disponibilidad de existencias</span><span class="sxs-lookup"><span data-stu-id="5e34f-103">Check the availability of stock</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5e34f-104">Este procedimiento le muestra cómo comprobar el inventario disponible y el inventario físico disponible para un número de artículo concreto.</span><span class="sxs-lookup"><span data-stu-id="5e34f-104">This procedure shows you how to check on-hand and physical on-hand inventory for a specific item number.</span></span> <span data-ttu-id="5e34f-105">También se muestra cómo obtener la información de suministro relacionada con un artículo.</span><span class="sxs-lookup"><span data-stu-id="5e34f-105">It also shows you how to get supply information related to an item.</span></span> <span data-ttu-id="5e34f-106">El inventario físico disponible es el inventario disponible que se tiene a mano, es decir, se ha comprado, recibido y registrado.</span><span class="sxs-lookup"><span data-stu-id="5e34f-106">Physical on-hand inventory is the on-hand inventory that’s available – that is, it’s purchased, received and registered.</span></span> <span data-ttu-id="5e34f-107">El inventario disponible incluye el inventario disponible que se tiene a mano, pero también el inventario pedido y que se espera pero aún no se ha recibido o registrado.</span><span class="sxs-lookup"><span data-stu-id="5e34f-107">On-hand inventory includes the available on-hand inventory, but also the inventory that’s been ordered and is expected, but not yet received or registered.</span></span> <span data-ttu-id="5e34f-108">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="5e34f-108">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="5e34f-109">Si está usando USMF, puede utilizar los valores del ejemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="5e34f-109">If you are using USMF you can use the example values that are shown.</span></span> <span data-ttu-id="5e34f-110">Estas tareas las realizará normalmente un trabajador del almacén.</span><span class="sxs-lookup"><span data-stu-id="5e34f-110">These tasks would typically be carried out by a warehouse worker.</span></span>


## <a name="check-on-hand-inventory-for-an-item"></a><span data-ttu-id="5e34f-111">Comprobar el inventario disponible de un artículo</span><span class="sxs-lookup"><span data-stu-id="5e34f-111">Check on-hand inventory for an item</span></span>
1. <span data-ttu-id="5e34f-112">Vaya a Gestión de inventario > Consultas e informes > Inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="5e34f-112">Go to Inventory management > Inquiries and reports > On-hand inventory.</span></span>
2. <span data-ttu-id="5e34f-113">Seleccione la fila Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="5e34f-113">Select the Item number row.</span></span>
    * <span data-ttu-id="5e34f-114">Para consultar el inventario disponible por número de artículo, seleccione la fila donde Tabla está establecido en Inventario disponible y Campo está establecido en Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="5e34f-114">To query the on-hand inventory by item number, select the row where the Table is set to On-hand inventory and Field is set to Item number.</span></span>  
3. <span data-ttu-id="5e34f-115">En el campo Criterios, seleccione el artículo que desea consultar.</span><span class="sxs-lookup"><span data-stu-id="5e34f-115">In the Criteria field, select the item you want to query.</span></span>
    * <span data-ttu-id="5e34f-116">Si utiliza a la empresa de datos de prueba USMF, puede seleccionar "M9201".</span><span class="sxs-lookup"><span data-stu-id="5e34f-116">If you're using the USMF demo data company, you can select 'M9201'.</span></span>  
4. <span data-ttu-id="5e34f-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e34f-117">Click OK.</span></span>
5. <span data-ttu-id="5e34f-118">Haga clic en Dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5e34f-118">Click Dimensions.</span></span>
    * <span data-ttu-id="5e34f-119">La ficha Dimensiones permite seleccionar cuánto detalle desea ver sobre su inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="5e34f-119">The Dimensions tab allows you select how much detail you want to see about your on-hand inventory.</span></span> <span data-ttu-id="5e34f-120">Si necesita los datos relacionados con la reserva, debe mostrar todas las dimensiones de inventario para los artículos que usan los procesos avanzados de almacén (WHS).</span><span class="sxs-lookup"><span data-stu-id="5e34f-120">If you need data related to reservation, you must display all inventory dimensions for the items that use advanced warehouse (WHS) processes.</span></span>  
6. <span data-ttu-id="5e34f-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e34f-121">Click OK.</span></span>
7. <span data-ttu-id="5e34f-122">En el panel de acciones, haga clic en Información relacionada.</span><span class="sxs-lookup"><span data-stu-id="5e34f-122">On the Action Pane, click Related information.</span></span>
    * <span data-ttu-id="5e34f-123">Si no ve esto, es posible que tenga que hacer clic en los puntos suspensivos (…) para ver opciones adicionales del panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="5e34f-123">If you don’t see this, you may need to click on the Ellipsis button (…) to see additional action pane options.</span></span>  
8. <span data-ttu-id="5e34f-124">Haga clic en Visión general de suministros.</span><span class="sxs-lookup"><span data-stu-id="5e34f-124">Click Supply overview.</span></span>
    * <span data-ttu-id="5e34f-125">La ficha Visión general de suministros proporciona la información para un artículo específico, como la cantidad disponible, el plazo y la información del proveedor.</span><span class="sxs-lookup"><span data-stu-id="5e34f-125">The Supply overview tab provides supply information for a specific item, such as the quantity on-hand, the lead time, and vendor information.</span></span>  
9. <span data-ttu-id="5e34f-126">Expanda la sección Disponible.</span><span class="sxs-lookup"><span data-stu-id="5e34f-126">Expand the On-hand section.</span></span>
10. <span data-ttu-id="5e34f-127">Expanda la sección Proveedores.</span><span class="sxs-lookup"><span data-stu-id="5e34f-127">Expand the Vendors section.</span></span>
11. <span data-ttu-id="5e34f-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e34f-128">Close the page.</span></span>
12. <span data-ttu-id="5e34f-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e34f-129">Close the page.</span></span>

## <a name="check-physical-on-hand-inventory"></a><span data-ttu-id="5e34f-130">Comprobar el inventario físico disponible</span><span class="sxs-lookup"><span data-stu-id="5e34f-130">Check physical on-hand inventory</span></span>
1. <span data-ttu-id="5e34f-131">Vaya a Gestión de almacén > Consultas e informes > Inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="5e34f-131">Go to Warehouse management > Inquiries and reports > Physical on-hand inventory.</span></span>
2. <span data-ttu-id="5e34f-132">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5e34f-132">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="5e34f-133">Puede utilizar los campos Sitio y Almacén para filtrar la lista de artículos.</span><span class="sxs-lookup"><span data-stu-id="5e34f-133">You can use the Site and Warehouse fields to filter the list of items.</span></span>  
3. <span data-ttu-id="5e34f-134">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="5e34f-134">Refresh the page.</span></span>
4. <span data-ttu-id="5e34f-135">Haga clic en Mostrar dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5e34f-135">Click Display Dimensions.</span></span>
    * <span data-ttu-id="5e34f-136">La ficha Mostrar dimensiones permite seleccionar cuánto detalle desea ver sobre su inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="5e34f-136">The Dimensions Display tab allows you select how much detail you want to see about your on-hand inventory.</span></span>  
5. <span data-ttu-id="5e34f-137">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e34f-137">Click OK.</span></span>
6. <span data-ttu-id="5e34f-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e34f-138">Close the page.</span></span>

## <a name="check-on-hand-inventory-by-location"></a><span data-ttu-id="5e34f-139">Comprobar el inventario disponible por ubicación</span><span class="sxs-lookup"><span data-stu-id="5e34f-139">Check on-hand inventory by location</span></span>
1. <span data-ttu-id="5e34f-140">Vaya a Gestión de almacén > Consultas e informes > Inventario disponible por ubicación.</span><span class="sxs-lookup"><span data-stu-id="5e34f-140">Go to Warehouse management > Inquiries and reports > On hand by location.</span></span>
2. <span data-ttu-id="5e34f-141">En el campo Almacén, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="5e34f-141">In the Warehouse field, type a value.</span></span>
    * <span data-ttu-id="5e34f-142">Si utiliza a la empresa de datos de prueba USMF, puede usar “51".</span><span class="sxs-lookup"><span data-stu-id="5e34f-142">If you're using the USMF demo data company, you can use '51'.</span></span>  
3. <span data-ttu-id="5e34f-143">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="5e34f-143">Refresh the page.</span></span>
4. <span data-ttu-id="5e34f-144">Haga clic en Mostrar dimensiones.</span><span class="sxs-lookup"><span data-stu-id="5e34f-144">Click Display Dimensions.</span></span>
5. <span data-ttu-id="5e34f-145">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="5e34f-145">Click OK.</span></span>
6. <span data-ttu-id="5e34f-146">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5e34f-146">Close the page.</span></span>

