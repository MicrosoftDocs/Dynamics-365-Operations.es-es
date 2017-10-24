--- 
title: "Configurar el embalaje manual (febrero y mayo de 2016 únicamente)"
description: El proceso de embalaje le permite validar y empaquetar productos en contenedores.
author: BibiSp
manager: AnnBe
ms.date: 11/04/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7f992a6a1655cd868d79228c490d59b46bfae715
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-manual-packing-february--may-2016-only"></a><span data-ttu-id="663fa-103">Configurar el embalaje manual (febrero y mayo de 2016 únicamente)</span><span class="sxs-lookup"><span data-stu-id="663fa-103">Set up manual packing (February & May 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="663fa-104">El proceso de embalaje le permite validar y empaquetar productos en contenedores.</span><span class="sxs-lookup"><span data-stu-id="663fa-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="663fa-105">En este proceso, los trabajadores de almacén seleccionan productos de las ubicaciones de almacenamiento y las mueven a una estación de embalaje donde comprueban los tipos y las cantidades de artículos, y los asignan a los contenedores adecuados.</span><span class="sxs-lookup"><span data-stu-id="663fa-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="663fa-106">Cuando un contenedor se empaqueta por completo, pueden cerrarlo y moverlo a los muelles de salida, y los productos estarán listos para enviarse.</span><span class="sxs-lookup"><span data-stu-id="663fa-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="663fa-107">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="663fa-107">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="663fa-108">Configurar perfiles de ubicación</span><span class="sxs-lookup"><span data-stu-id="663fa-108">Set up location profiles</span></span>
1. <span data-ttu-id="663fa-109">Vaya a Gestión de almacenes > Configurar > Almacén > Perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="663fa-109">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="663fa-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="663fa-110">Click New.</span></span>
    * <span data-ttu-id="663fa-111">El perfil de la ubicación se usa para las instalaciones de embalaje y contiene información y reglas para una ubicación.</span><span class="sxs-lookup"><span data-stu-id="663fa-111">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="663fa-112">En el campo Id. de perfil de ubicación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-112">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="663fa-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="663fa-114">En el campo Formato de ubicación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-114">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="663fa-115">En el campo Tipo de ubicación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-115">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="663fa-116">Seleccione Sí en el campo Permitir artículos combinados.</span><span class="sxs-lookup"><span data-stu-id="663fa-116">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="663fa-117">Seleccione Sí en el campo Permitir estados de inventario combinados.</span><span class="sxs-lookup"><span data-stu-id="663fa-117">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="663fa-118">Seleccione Sí en el campo Anular reglas para días de lote.</span><span class="sxs-lookup"><span data-stu-id="663fa-118">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="663fa-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663fa-119">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="663fa-120">Configurar parámetros de gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="663fa-120">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="663fa-121">Vaya a Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="663fa-121">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="663fa-122">Haga clic en la ficha Embalaje.</span><span class="sxs-lookup"><span data-stu-id="663fa-122">Click the Packing tab.</span></span>
3. <span data-ttu-id="663fa-123">En el campo Id. de perfil para la ubicación de embalaje, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-123">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="663fa-124">Seleccione el perfil de ubicación que desea usar para embalaje.</span><span class="sxs-lookup"><span data-stu-id="663fa-124">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="663fa-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663fa-125">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="663fa-126">Configurar tipos de contenedor</span><span class="sxs-lookup"><span data-stu-id="663fa-126">Set up container types</span></span>
1. <span data-ttu-id="663fa-127">Vaya a Administración de almacenes > Configurar > Contenedores > Tipos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="663fa-127">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="663fa-128">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="663fa-128">Click New.</span></span>
    * <span data-ttu-id="663fa-129">Se pueden definir los tipos de contenedores que se usarán.</span><span class="sxs-lookup"><span data-stu-id="663fa-129">You can define the types of containers to use.</span></span> <span data-ttu-id="663fa-130">Puede especificar las dimensiones físicas del contenedor, incluida la tara, el peso máximo, el volumen máximo, la longitud máxima, el ancho y el peso.</span><span class="sxs-lookup"><span data-stu-id="663fa-130">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="663fa-131">Los atributos son campos personalizados que le permiten agregar dimensiones adicionales en el tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="663fa-131">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="663fa-132">En el campo Código de tipo de contenedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-132">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="663fa-133">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-133">In the Description field, type a value.</span></span>
5. <span data-ttu-id="663fa-134">En el campo Tara, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="663fa-134">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="663fa-135">Escriba un número en el campo Peso máximo.</span><span class="sxs-lookup"><span data-stu-id="663fa-135">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="663fa-136">En el campo Volumen, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="663fa-136">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="663fa-137">En el campo Longitud, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="663fa-137">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="663fa-138">En el campo Ancho, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="663fa-138">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="663fa-139">En el campo Alto, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="663fa-139">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="663fa-140">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="663fa-140">Click Save.</span></span>
12. <span data-ttu-id="663fa-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663fa-141">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="663fa-142">Configurar perfiles de embalaje</span><span class="sxs-lookup"><span data-stu-id="663fa-142">Set up packing profiles</span></span>
1. <span data-ttu-id="663fa-143">Vaya a Gestión de almacenes > Configurar > Embalaje > Perfiles de embalaje.</span><span class="sxs-lookup"><span data-stu-id="663fa-143">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="663fa-144">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="663fa-144">Click New.</span></span>
3. <span data-ttu-id="663fa-145">En el campo Id. del perfil de empaquetado, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-145">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="663fa-146">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-146">In the Description field, type a value.</span></span>
5. <span data-ttu-id="663fa-147">En el campo Id. de perfil de cierre de contenedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-147">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="663fa-148">Un id. de perfil de cierre de contenedor es opcional y es el perfil del contenedor de cierre predeterminado para este perfil de embalaje.</span><span class="sxs-lookup"><span data-stu-id="663fa-148">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="663fa-149">En el campo Modo del id. de contenedor, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="663fa-149">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="663fa-150">Esta opción determina si se generará automáticamente un id. de contenedor cuando se cree un o contenedor o si se creará un id. de contenedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="663fa-150">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="663fa-151">En el campo Tipo de contenedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-151">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="663fa-152">El tipo de contenedor se usará de forma predeterminada cuando se cree un nuevo contenedor.</span><span class="sxs-lookup"><span data-stu-id="663fa-152">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="663fa-153">Active la casilla Crear contenedor automáticamente al cerrar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="663fa-153">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="663fa-154">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="663fa-154">Click Save.</span></span>
10. <span data-ttu-id="663fa-155">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663fa-155">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="663fa-156">Configurar perfiles de cierre de contenedor</span><span class="sxs-lookup"><span data-stu-id="663fa-156">Set up container closing profiles</span></span>
1. <span data-ttu-id="663fa-157">Vaya a Administración de almacenes > Configurar > Contenedores > Perfiles de cierre de contenedor.</span><span class="sxs-lookup"><span data-stu-id="663fa-157">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="663fa-158">Los perfiles de cierre del contenedor definen qué sucede cuando se cierra un contenedor.</span><span class="sxs-lookup"><span data-stu-id="663fa-158">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="663fa-159">Puede configurar varios perfiles de contenedor de cierre.</span><span class="sxs-lookup"><span data-stu-id="663fa-159">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="663fa-160">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="663fa-160">Click New.</span></span>
3. <span data-ttu-id="663fa-161">En el campo Id. de perfil de cierre de contenedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-161">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="663fa-162">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-162">In the Description field, type a value.</span></span>
5. <span data-ttu-id="663fa-163">En el campo Manifiesto en, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="663fa-163">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="663fa-164">Especifique si se producirán manifiestos al cerrar contenedores de cierre o al confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="663fa-164">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="663fa-165">Tenga en cuenta que los manifiestos requieren Administración de transporte.</span><span class="sxs-lookup"><span data-stu-id="663fa-165">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="663fa-166">Los manifiestos se deben implementar en los motores de transporte para que funcionen.</span><span class="sxs-lookup"><span data-stu-id="663fa-166">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="663fa-167">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-167">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="663fa-168">En el campo Ubicación predeterminada del envío final, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-168">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="663fa-169">Esta será la ubicación a la que se moverán los productos después de que se cierren los contenedores.</span><span class="sxs-lookup"><span data-stu-id="663fa-169">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="663fa-170">Esta ubicación debe tener un perfil de ubicación definido en Parámetros de almacén.</span><span class="sxs-lookup"><span data-stu-id="663fa-170">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="663fa-171">En el campo Unidad de peso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663fa-171">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="663fa-172">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="663fa-172">Click Save.</span></span>


