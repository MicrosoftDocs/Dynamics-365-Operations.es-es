---
title: Configuración del embalaje manual (febrero de 2016 y mayo de 2016)
description: El proceso de embalaje le permite validar y empaquetar productos en contenedores.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile, WHSParameters, WHSContainerType, WHSPackProfile, WHSCloseContainerProfile, InventLocationIdLookup, UnitOfMeasureLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b90b4a71e2447e942dbb4a9645ef93064da630d3
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "347730"
---
# <a name="set-up-manual-packing-february-2016--may-2016"></a><span data-ttu-id="63979-103">Configuración del embalaje manual (febrero de 2016 y mayo de 2016)</span><span class="sxs-lookup"><span data-stu-id="63979-103">Set up manual packing (February 2016 & May 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="63979-104">El proceso de embalaje le permite validar y empaquetar productos en contenedores.</span><span class="sxs-lookup"><span data-stu-id="63979-104">The packing process allows you to validate and pack products into containers.</span></span> <span data-ttu-id="63979-105">En este proceso, los trabajadores de almacén seleccionan productos de las ubicaciones de almacenamiento y las mueven a una estación de embalaje donde comprueban los tipos y las cantidades de artículos, y los asignan a los contenedores adecuados.</span><span class="sxs-lookup"><span data-stu-id="63979-105">In this process, warehouse workers pick products from the storage locations and move them to a packing station where they check the item quantities and types, and assign them to appropriate containers.</span></span> <span data-ttu-id="63979-106">Cuando un contenedor se empaqueta por completo, pueden cerrarlo y moverlo a los muelles de salida, y los productos estarán listos para enviarse.</span><span class="sxs-lookup"><span data-stu-id="63979-106">When a container is fully packed, they can close it and move it to the outbound docks, and the products are ready to ship.</span></span> <span data-ttu-id="63979-107">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="63979-107">This procedure uses the USMF demo company.</span></span> <span data-ttu-id="63979-108">Este procedimiento es únicamente para las versiones de febrero de 2016 y mayo de 2016 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="63979-108">This procedure is for the February 2016 & May 2016 versions of Dynamics 365 for Operations only.</span></span>


## <a name="set-up-location-profiles"></a><span data-ttu-id="63979-109">Configurar perfiles de ubicación</span><span class="sxs-lookup"><span data-stu-id="63979-109">Set up location profiles</span></span>
1. <span data-ttu-id="63979-110">Vaya a Gestión de almacenes > Configurar > Almacén > Perfiles de ubicación.</span><span class="sxs-lookup"><span data-stu-id="63979-110">Go to Warehouse management > Setup > Warehouse > Location profiles.</span></span>
2. <span data-ttu-id="63979-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="63979-111">Click New.</span></span>
    * <span data-ttu-id="63979-112">El perfil de la ubicación se usa para las instalaciones de embalaje y contiene información y reglas para una ubicación.</span><span class="sxs-lookup"><span data-stu-id="63979-112">The location profile is used for packing stations and contains information and rules for a location.</span></span>  
3. <span data-ttu-id="63979-113">En el campo Id. de perfil de ubicación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-113">In the Location profile ID field, type a value.</span></span>
4. <span data-ttu-id="63979-114">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-114">In the Name field, type a value.</span></span>
5. <span data-ttu-id="63979-115">En el campo Formato de ubicación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-115">In the Location format field, enter or select a value.</span></span>
6. <span data-ttu-id="63979-116">En el campo Tipo de ubicación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-116">In the Location type field, enter or select a value.</span></span>
7. <span data-ttu-id="63979-117">Seleccione Sí en el campo Permitir artículos combinados.</span><span class="sxs-lookup"><span data-stu-id="63979-117">Select Yes in the Allow mixed items field.</span></span>
8. <span data-ttu-id="63979-118">Seleccione Sí en el campo Permitir estados de inventario combinados.</span><span class="sxs-lookup"><span data-stu-id="63979-118">Select Yes in the Allow mixed  inventory statuses field.</span></span>
9. <span data-ttu-id="63979-119">Seleccione Sí en el campo Anular reglas para días de lote.</span><span class="sxs-lookup"><span data-stu-id="63979-119">Select Yes in the Override rules for batch days field.</span></span>
10. <span data-ttu-id="63979-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="63979-120">Close the page.</span></span>

## <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="63979-121">Configurar parámetros de gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="63979-121">Set up warehouse management parameters</span></span> 
1. <span data-ttu-id="63979-122">Vaya a Gestión de almacenes > Configurar > Parámetros de gestión de inventario y almacenes.</span><span class="sxs-lookup"><span data-stu-id="63979-122">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="63979-123">Haga clic en la ficha Embalaje.</span><span class="sxs-lookup"><span data-stu-id="63979-123">Click the Packing tab.</span></span>
3. <span data-ttu-id="63979-124">En el campo Id. de perfil para la ubicación de embalaje, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-124">In the Profile ID for packing location field, enter or select a value.</span></span>
    * <span data-ttu-id="63979-125">Seleccione el perfil de ubicación que desea usar para embalaje.</span><span class="sxs-lookup"><span data-stu-id="63979-125">Select the location profile that you want to use for packing.</span></span>  
4. <span data-ttu-id="63979-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="63979-126">Close the page.</span></span>

## <a name="set-up-container-types"></a><span data-ttu-id="63979-127">Configurar tipos de contenedor</span><span class="sxs-lookup"><span data-stu-id="63979-127">Set up container types</span></span>
1. <span data-ttu-id="63979-128">Vaya a Administración de almacenes > Configurar > Contenedores > Tipos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="63979-128">Go to Warehouse management > Setup > Containers > Container types.</span></span>
2. <span data-ttu-id="63979-129">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="63979-129">Click New.</span></span>
    * <span data-ttu-id="63979-130">Se pueden definir los tipos de contenedores que se usarán.</span><span class="sxs-lookup"><span data-stu-id="63979-130">You can define the types of containers to use.</span></span> <span data-ttu-id="63979-131">Puede especificar las dimensiones físicas del contenedor, incluida la tara, el peso máximo, el volumen máximo, la longitud máxima, el ancho y el peso.</span><span class="sxs-lookup"><span data-stu-id="63979-131">You can specify the physical dimensions of the container, including tare weight, maximum weight, maximum volume, length, width, and weight.</span></span>  <span data-ttu-id="63979-132">Los atributos son campos personalizados que le permiten agregar dimensiones adicionales en el tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="63979-132">The Attributes are customized fields that allow you to add extra dimensions on the container type.</span></span>     
3. <span data-ttu-id="63979-133">En el campo Código de tipo de contenedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-133">In the Container type code field, type a value.</span></span>
4. <span data-ttu-id="63979-134">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-134">In the Description field, type a value.</span></span>
5. <span data-ttu-id="63979-135">En el campo Tara, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="63979-135">In the Tare weight field, enter a number.</span></span>
6. <span data-ttu-id="63979-136">Escriba un número en el campo Peso máximo.</span><span class="sxs-lookup"><span data-stu-id="63979-136">In the Maximum weight field, enter a number.</span></span>
7. <span data-ttu-id="63979-137">En el campo Volumen, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="63979-137">In the Volume field, enter a number.</span></span>
8. <span data-ttu-id="63979-138">En el campo Longitud, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="63979-138">In the Length field, enter a number.</span></span>
9. <span data-ttu-id="63979-139">En el campo Ancho, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="63979-139">In the Width field, enter a number.</span></span>
10. <span data-ttu-id="63979-140">En el campo Alto, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="63979-140">In the Height field, enter a number.</span></span>
11. <span data-ttu-id="63979-141">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="63979-141">Click Save.</span></span>
12. <span data-ttu-id="63979-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="63979-142">Close the page.</span></span>

## <a name="set-up-packing-profiles"></a><span data-ttu-id="63979-143">Configurar perfiles de embalaje</span><span class="sxs-lookup"><span data-stu-id="63979-143">Set up packing profiles</span></span>
1. <span data-ttu-id="63979-144">Vaya a Gestión de almacenes > Configurar > Embalaje > Perfiles de embalaje.</span><span class="sxs-lookup"><span data-stu-id="63979-144">Go to Warehouse management > Setup > Packing > Packing profiles.</span></span>
2. <span data-ttu-id="63979-145">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="63979-145">Click New.</span></span>
3. <span data-ttu-id="63979-146">En el campo Id. del perfil de empaquetado, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-146">In the Packing profile ID field, type a value.</span></span>
4. <span data-ttu-id="63979-147">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-147">In the Description field, type a value.</span></span>
5. <span data-ttu-id="63979-148">En el campo Id. de perfil de cierre de contenedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-148">In the Container closing profile ID field, enter or select a value.</span></span>
    * <span data-ttu-id="63979-149">Un id. de perfil de cierre de contenedor es opcional y es el perfil del contenedor de cierre predeterminado para este perfil de embalaje.</span><span class="sxs-lookup"><span data-stu-id="63979-149">A container closing profile ID is optional and is the default close container profile for this packing profile.</span></span>  
6. <span data-ttu-id="63979-150">En el campo Modo del id. de contenedor, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="63979-150">In the Container ID mode field, select an option.</span></span>
    * <span data-ttu-id="63979-151">Esta opción determina si se generará automáticamente un id. de contenedor cuando se cree un o contenedor o si se creará un id. de contenedor manualmente.</span><span class="sxs-lookup"><span data-stu-id="63979-151">This option determines whether a container ID will be automatically generated when a container is created or if a container ID will be created manually.</span></span>  
7. <span data-ttu-id="63979-152">En el campo Tipo de contenedor, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-152">In the Container type field, enter or select a value.</span></span>
    * <span data-ttu-id="63979-153">El tipo de contenedor se usará de forma predeterminada cuando se cree un nuevo contenedor.</span><span class="sxs-lookup"><span data-stu-id="63979-153">The container type will be used by default when a new container is created.</span></span>  
8. <span data-ttu-id="63979-154">Active la casilla Crear contenedor automáticamente al cerrar el contenedor.</span><span class="sxs-lookup"><span data-stu-id="63979-154">Select the Autocreate container at container close check box.</span></span>
9. <span data-ttu-id="63979-155">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="63979-155">Click Save.</span></span>
10. <span data-ttu-id="63979-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="63979-156">Close the page.</span></span>

## <a name="set-up-container-closing-profiles"></a><span data-ttu-id="63979-157">Configurar perfiles de cierre de contenedor</span><span class="sxs-lookup"><span data-stu-id="63979-157">Set up container closing profiles</span></span>
1. <span data-ttu-id="63979-158">Vaya a Administración de almacenes > Configurar > Contenedores > Perfiles de cierre de contenedor.</span><span class="sxs-lookup"><span data-stu-id="63979-158">Go to Warehouse management > Setup > Containers > Container closing profiles.</span></span>
    * <span data-ttu-id="63979-159">Los perfiles de cierre del contenedor definen qué sucede cuando se cierra un contenedor.</span><span class="sxs-lookup"><span data-stu-id="63979-159">Container closing profiles define what happens when a container is closed.</span></span> <span data-ttu-id="63979-160">Puede configurar varios perfiles de contenedor de cierre.</span><span class="sxs-lookup"><span data-stu-id="63979-160">You can set up multiple close container profiles.</span></span>       
2. <span data-ttu-id="63979-161">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="63979-161">Click New.</span></span>
3. <span data-ttu-id="63979-162">En el campo Id. de perfil de cierre de contenedor, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-162">In the Container closing profile ID field, type a value.</span></span>
4. <span data-ttu-id="63979-163">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-163">In the Description field, type a value.</span></span>
5. <span data-ttu-id="63979-164">En el campo Manifiesto en, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="63979-164">In the Manifest at field, select an option.</span></span>
    * <span data-ttu-id="63979-165">Especifique si se producirán manifiestos al cerrar contenedores de cierre o al confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="63979-165">Specify whether manifesting will occur when closing containers or when confirming the shipment.</span></span> <span data-ttu-id="63979-166">Tenga en cuenta que los manifiestos requieren Administración de transporte.</span><span class="sxs-lookup"><span data-stu-id="63979-166">Note that manifesting requires Transportation management.</span></span> <span data-ttu-id="63979-167">Los manifiestos se deben implementar en los motores de transporte para que funcionen.</span><span class="sxs-lookup"><span data-stu-id="63979-167">Manifesting must be implemented in the transportation engines in order for it work.</span></span>  
6. <span data-ttu-id="63979-168">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-168">In the Warehouse field, enter or select a value.</span></span>
7. <span data-ttu-id="63979-169">En el campo Ubicación predeterminada del envío final, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-169">In the Default location for final shipment field, enter or select a value.</span></span>
    * <span data-ttu-id="63979-170">Esta será la ubicación a la que se moverán los productos después de que se cierren los contenedores.</span><span class="sxs-lookup"><span data-stu-id="63979-170">This will be location to which products will be moved after the containers are closed.</span></span> <span data-ttu-id="63979-171">Esta ubicación debe tener un perfil de ubicación definido en Parámetros de almacén.</span><span class="sxs-lookup"><span data-stu-id="63979-171">This location must have a location profile defined on Warehouse parameters.</span></span>  
8. <span data-ttu-id="63979-172">En el campo Unidad de peso, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="63979-172">In the Weight unit field, enter or select a value.</span></span>
9. <span data-ttu-id="63979-173">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="63979-173">Click Save.</span></span>

