---
title: "Creación de un nuevo diseño de almacén"
description: "Este procedimiento le muestra cómo configurar la información sobre las ubicaciones de un almacén."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 253440d81edd6f71b52ae349398e3c6a895bf05c
ms.contentlocale: es-es
ms.lasthandoff: 09/12/2017

---
# <a name="create-a-new-warehouse-layout"></a><span data-ttu-id="87f51-103">Creación de un nuevo diseño de almacén</span><span class="sxs-lookup"><span data-stu-id="87f51-103">Create a new warehouse layout</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="87f51-104">Este procedimiento le muestra cómo configurar la información sobre las ubicaciones de un almacén.</span><span class="sxs-lookup"><span data-stu-id="87f51-104">This procedure shows you how to set up information about the locations in a warehouse.</span></span> <span data-ttu-id="87f51-105">Esto solo se aplica a los almacenes creados con el “almacenamiento básico” en el módulo Gestión del inventario, no en los almacenes creados en el módulo Gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="87f51-105">This applies only to warehouses created using "basic warehousing" in the Inventory management module, not to warehouses created in the Warehouse management module.</span></span> <span data-ttu-id="87f51-106">Puede utilizar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="87f51-106">You can use this procedure in demo data company USMF, or on your own data.</span></span>


## <a name="set-the-default-location-capacity"></a><span data-ttu-id="87f51-107">Definir la capacidad de la ubicación predeterminada</span><span class="sxs-lookup"><span data-stu-id="87f51-107">Set the default location capacity</span></span>
1. <span data-ttu-id="87f51-108">Vaya a Gestión del inventario > Configurar > Parámetros de la gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="87f51-108">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="87f51-109">Haga clic en la ficha Ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="87f51-109">Click the Locations tab.</span></span>
3. <span data-ttu-id="87f51-110">En el campo Ancho estándar, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="87f51-110">In the Standard width field, enter a number.</span></span>
4. <span data-ttu-id="87f51-111">En el campo Profundidad estándar, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="87f51-111">In the Standard depth field, enter a number.</span></span>
5. <span data-ttu-id="87f51-112">En el campo Alto estándar, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="87f51-112">In the Standard height field, enter a number.</span></span>
6. <span data-ttu-id="87f51-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="87f51-113">Click Save.</span></span>
7. <span data-ttu-id="87f51-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="87f51-114">Close the page.</span></span>

## <a name="define-the-location-name-format"></a><span data-ttu-id="87f51-115">Definir el formato del nombre de ubicación</span><span class="sxs-lookup"><span data-stu-id="87f51-115">Define the location name format</span></span>
1. <span data-ttu-id="87f51-116">Vaya a Gestión del inventario> Configuración > Desglose del inventario > Almacenes</span><span class="sxs-lookup"><span data-stu-id="87f51-116">Go to Inventory management > Setup > Inventory breakdown > Warehouses.</span></span>
2. <span data-ttu-id="87f51-117">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="87f51-117">Click New.</span></span>
3. <span data-ttu-id="87f51-118">En el campo Almacén, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="87f51-118">In the Warehouse field, type a value.</span></span>
4. <span data-ttu-id="87f51-119">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="87f51-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="87f51-120">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="87f51-120">In the Site field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="87f51-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="87f51-121">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="87f51-122">Alterne la expansión de la sección Nombres de ubicación.</span><span class="sxs-lookup"><span data-stu-id="87f51-122">Toggle the expansion of the Location names section.</span></span>
    * <span data-ttu-id="87f51-123">Las opciones de esta sección definen el formato predeterminado para los nombres de ubicación.</span><span class="sxs-lookup"><span data-stu-id="87f51-123">The options in this section define the default format for location names.</span></span> <span data-ttu-id="87f51-124">En nuestro ejemplo, incluiremos el número de pasillo, el número de la estantería y el número de balda.</span><span class="sxs-lookup"><span data-stu-id="87f51-124">In our example, we'll include the aisle number, rack number and shelf number.</span></span>  
8. <span data-ttu-id="87f51-125">Establezca la opción Incluir pasillo en Sí.</span><span class="sxs-lookup"><span data-stu-id="87f51-125">Set the Include aisle option to Yes.</span></span>
9. <span data-ttu-id="87f51-126">Establezca la opción Incluir estantería en Sí.</span><span class="sxs-lookup"><span data-stu-id="87f51-126">Set the Include rack option to Yes.</span></span>
10. <span data-ttu-id="87f51-127">En el campo Formato, escriba una valor para la estantería.</span><span class="sxs-lookup"><span data-stu-id="87f51-127">In the Format field, for the rack, type a value.</span></span>
    * <span data-ttu-id="87f51-128">Por ejemplo: -##</span><span class="sxs-lookup"><span data-stu-id="87f51-128">For example: -##</span></span>  
11. <span data-ttu-id="87f51-129">Establezca la opción Incluir balda en Sí.</span><span class="sxs-lookup"><span data-stu-id="87f51-129">Set the Include shelf option to Yes.</span></span>
12. <span data-ttu-id="87f51-130">En el campo Formato, escriba una valor para la balda.</span><span class="sxs-lookup"><span data-stu-id="87f51-130">In the Format field, for the shelf, type a value.</span></span>
    * <span data-ttu-id="87f51-131">Por ejemplo: -##</span><span class="sxs-lookup"><span data-stu-id="87f51-131">For example: -##</span></span>  

## <a name="define-warehouse-locations"></a><span data-ttu-id="87f51-132">Definir las ubicaciones del almacén</span><span class="sxs-lookup"><span data-stu-id="87f51-132">Define warehouse locations</span></span>
1. <span data-ttu-id="87f51-133">En el panel de acciones, haga clic en Almacén.</span><span class="sxs-lookup"><span data-stu-id="87f51-133">On the Action Pane, click Warehouse.</span></span>
2. <span data-ttu-id="87f51-134">Haga clic en Asistente para ubicación.</span><span class="sxs-lookup"><span data-stu-id="87f51-134">Click Location Wizard.</span></span>
3. <span data-ttu-id="87f51-135">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-135">Click Next.</span></span>
4. <span data-ttu-id="87f51-136">Anular la selección de la opción Muelle de salida</span><span class="sxs-lookup"><span data-stu-id="87f51-136">De-select the Outbound docks option</span></span>
5. <span data-ttu-id="87f51-137">Anular la selección de la opción Ubicaciones de almacenaje</span><span class="sxs-lookup"><span data-stu-id="87f51-137">De-select the Bulk locations option</span></span>
6. <span data-ttu-id="87f51-138">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-138">Click Next.</span></span>
7. <span data-ttu-id="87f51-139">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-139">Click Next.</span></span>
8. <span data-ttu-id="87f51-140">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-140">Click Next.</span></span>
9. <span data-ttu-id="87f51-141">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-141">Click Next.</span></span>
10. <span data-ttu-id="87f51-142">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-142">Click Next.</span></span>
11. <span data-ttu-id="87f51-143">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-143">Click Next.</span></span>
12. <span data-ttu-id="87f51-144">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-144">Click Next.</span></span>
    * <span data-ttu-id="87f51-145">Tenga en cuenta que las dimensiones físicas que se muestran en esta página son las que establece al inicio de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="87f51-145">Note that the physical dimensions shown on this page are the ones that you set at the start of this procedure.</span></span>  
13. <span data-ttu-id="87f51-146">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="87f51-146">Click Next.</span></span>
14. <span data-ttu-id="87f51-147">Haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="87f51-147">Click Finish.</span></span>
15. <span data-ttu-id="87f51-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="87f51-148">Close the page.</span></span>
16. <span data-ttu-id="87f51-149">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="87f51-149">Refresh the page.</span></span>

