---
title: Contenedores de envío
description: Este tema describe cómo configurar contenedores de envío para el módulo de costo de entrega.
author: sherry-zheng
manager: tfehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainerTypeTable, ITMContainerTable, ITMContainerUnitTypeTable, ITMRefrigerationTypeTable, ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: ca712aa7f07792861d5ba36afd8d7b63cc9ce8fb
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500967"
---
# <a name="shipping-container-setup"></a><span data-ttu-id="892a9-103">Configuración del contenedor de envío</span><span class="sxs-lookup"><span data-stu-id="892a9-103">Shipping container setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="892a9-104">Este tema describe cómo configurar contenedores de envío para el módulo **Costo descargado**.</span><span class="sxs-lookup"><span data-stu-id="892a9-104">This topic describes how to set up shipping containers for the **Landed cost** module.</span></span>

## <a name="set-up-shipping-container-types"></a><a id="shipping-container-types"></a><span data-ttu-id="892a9-105">configurar tipos de contenedor de envío</span><span class="sxs-lookup"><span data-stu-id="892a9-105">Set up shipping container types</span></span>

<span data-ttu-id="892a9-106">Los tipos de contenedores de envío definen los tipos de contenedores de envío que están disponibles para su uso durante el envío y los viajes.</span><span class="sxs-lookup"><span data-stu-id="892a9-106">Shipping container types define the types of shipping containers that are available for use during shipping and voyages.</span></span>

<span data-ttu-id="892a9-107">Para trabajar con los tipos de contenedores de envío, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Tipos de contenedores de envío**.</span><span class="sxs-lookup"><span data-stu-id="892a9-107">To work with the shipping container types, go to **Landed cost \> Containers setup \> Shipping container types**.</span></span> <span data-ttu-id="892a9-108">Allí, puede ver, agregar y eliminar registros para sus tipos de contenedor.</span><span class="sxs-lookup"><span data-stu-id="892a9-108">There, you can view, add, and remove records for your container types.</span></span> <span data-ttu-id="892a9-109">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="892a9-109">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="892a9-110">Campo</span><span class="sxs-lookup"><span data-stu-id="892a9-110">Field</span></span> | <span data-ttu-id="892a9-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="892a9-111">Description</span></span> |
|---|---|
| <span data-ttu-id="892a9-112">Tipo de contenedor de envío</span><span class="sxs-lookup"><span data-stu-id="892a9-112">Shipping container type</span></span> | <span data-ttu-id="892a9-113">Escriba un nombre/número de identificador único para el tipo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="892a9-113">Enter a unique identification name/number for the shipping container type.</span></span> |
| <span data-ttu-id="892a9-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="892a9-114">Description</span></span> | <span data-ttu-id="892a9-115">Especifique una descripción del grupo de tipo de contenedor de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-115">Enter a description of the shipping container type.</span></span> |
| <span data-ttu-id="892a9-116">Volumen</span><span class="sxs-lookup"><span data-stu-id="892a9-116">Volume</span></span> | <span data-ttu-id="892a9-117">Ingrese el volumen máximo permitido en contenedores de envío de este tipo.</span><span class="sxs-lookup"><span data-stu-id="892a9-117">Enter the maximum volume that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="892a9-118">Importancia</span><span class="sxs-lookup"><span data-stu-id="892a9-118">Weight</span></span> | <span data-ttu-id="892a9-119">Ingrese el peso máximo permitido en contenedores de envío de este tipo.</span><span class="sxs-lookup"><span data-stu-id="892a9-119">Enter the maximum weight that is allowed in shipping containers of this type.</span></span> |
| <span data-ttu-id="892a9-120">Retornable</span><span class="sxs-lookup"><span data-stu-id="892a9-120">Returnable</span></span> | <span data-ttu-id="892a9-121">Especifique si los contenedores de envío de este tipo se pueden devolver al proveedor después de que se utilicen durante un viaje.</span><span class="sxs-lookup"><span data-stu-id="892a9-121">Specify whether shipping containers of this type can be returned to the vendor after they are used during a voyage.</span></span> <span data-ttu-id="892a9-122">Si esta opción se establece en *Sí*, pueden aplicarse costos adicionales por la devolución de contenedores de envío de este tipo al puerto de origen.</span><span class="sxs-lookup"><span data-stu-id="892a9-122">If this option is set to *Yes*, additional costs might apply for the return of shipping containers of this type to the port of origin.</span></span> |

## <a name="set-up-shipping-containers"></a><span data-ttu-id="892a9-123">Configuración de contenedores de envío</span><span class="sxs-lookup"><span data-stu-id="892a9-123">Set up shipping containers</span></span>

<span data-ttu-id="892a9-124">Utiliza los registros de contenedores de envío para identificar cada contenedor que usa durante los viajes.</span><span class="sxs-lookup"><span data-stu-id="892a9-124">You use shipping container records to identify each container that you use during voyages.</span></span> <span data-ttu-id="892a9-125">Cuando crea un viaje, puede seleccionar un contenedor específico para él en la lista de todos los registros de contenedores de envío que ha definido aquí.</span><span class="sxs-lookup"><span data-stu-id="892a9-125">When you create a voyage, you can select a specific container for it in the list of all the shipping container records that you've defined here.</span></span> <span data-ttu-id="892a9-126">Esta función es especialmente útil si su empresa posee sus propios contenedores de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-126">This feature is especially useful if your company owns its own shipping containers.</span></span>

<span data-ttu-id="892a9-127">No es necesario que ingrese los números de contenedor de envío para los contenedores de envío que se usarán solo una vez.</span><span class="sxs-lookup"><span data-stu-id="892a9-127">You don't have to enter shipping container numbers for shipping containers that will be used only one time.</span></span> <span data-ttu-id="892a9-128">En su lugar, puede agregar el número de contenedor de envío cuando cree un viaje.</span><span class="sxs-lookup"><span data-stu-id="892a9-128">Instead, you can add the shipping container number when you create a voyage.</span></span>

<span data-ttu-id="892a9-129">Los registros de contenedores de envío se utilizan solo en el costo de entrega.</span><span class="sxs-lookup"><span data-stu-id="892a9-129">Shipping container records are used only in Landed cost.</span></span> <span data-ttu-id="892a9-130">No están disponibles en el módulo estándar **Gestión de transporte** (TMS).</span><span class="sxs-lookup"><span data-stu-id="892a9-130">They aren't available in the standard **Transportation management** module (TMS).</span></span>

<span data-ttu-id="892a9-131">Para trabajar con contenedores de envío, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Contenedores de envío**.</span><span class="sxs-lookup"><span data-stu-id="892a9-131">To work with shipping containers, go to **Landed cost \> Containers setup \> Shipping containers**.</span></span> <span data-ttu-id="892a9-132">Allí, puede ver, agregar y eliminar registros para sus contenedores de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-132">There, you can view, add, and remove records your shipping containers.</span></span> <span data-ttu-id="892a9-133">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="892a9-133">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="892a9-134">Campo</span><span class="sxs-lookup"><span data-stu-id="892a9-134">Field</span></span> | <span data-ttu-id="892a9-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="892a9-135">Description</span></span> |
|---|---|
| <span data-ttu-id="892a9-136">Contenedor de envío</span><span class="sxs-lookup"><span data-stu-id="892a9-136">Shipping container</span></span> | <span data-ttu-id="892a9-137">Escriba un nombre/número de identificador único para el contenedor de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-137">Enter a unique identification name/number for the shipping container.</span></span> |
| <span data-ttu-id="892a9-138">Tipo de contenedor de envío</span><span class="sxs-lookup"><span data-stu-id="892a9-138">Shipping container type</span></span> | <span data-ttu-id="892a9-139">Seleccione el tipo de contenedor de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-139">Select the type of shipping container.</span></span> <span data-ttu-id="892a9-140">Para obtener más información, consulte la sección [Configurar tipos de contenedor de envío](#shipping-container-types) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="892a9-140">For more information, see the [Set up shipping container types](#shipping-container-types) section earlier in this topic.</span></span> |

> [!NOTE]
> - <span data-ttu-id="892a9-141">La configuración del contenedor de envío es opcional.</span><span class="sxs-lookup"><span data-stu-id="892a9-141">The shipping container setup is optional.</span></span> <span data-ttu-id="892a9-142">Por lo general, lo usará solo si su empresa posee sus propios contenedores de envío o, a menudo, reutiliza los mismos contenedores de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-142">Typically, you will use it only if your company owns its own shipping containers or often reuses the same shipping containers.</span></span>
> - <span data-ttu-id="892a9-143">No se calculan dígitos de control para los números de contenedores de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-143">No check digits are calculated for shipping container numbers.</span></span>

## <a name="set-up-unit-types"></a><a name="unit-types"></a><span data-ttu-id="892a9-144">Configurar tipos de unidad</span><span class="sxs-lookup"><span data-stu-id="892a9-144">Set up unit types</span></span>

<span data-ttu-id="892a9-145">Los tipos de unidades establecen agrupaciones y métodos de identificación adicionales para los contenedores de envío.</span><span class="sxs-lookup"><span data-stu-id="892a9-145">Unit types establish additional groupings and identification methods for shipping containers.</span></span> <span data-ttu-id="892a9-146">El tipo de unidad se usa típicamente para identificar el tipo de contenedor en el que se empaquetan las mercancías, como paletas o tambores.</span><span class="sxs-lookup"><span data-stu-id="892a9-146">The unit type is typically used to identify the type of container that goods are packaged in, such as pallets or drums.</span></span> <span data-ttu-id="892a9-147">Puede seleccionar un tipo de unidad cuando configura un contenedor en la página **Todos los contenedores de envío**.</span><span class="sxs-lookup"><span data-stu-id="892a9-147">You can select a unit type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="892a9-148">Los tipos de unidad se utilizan solo en el costo de aterrizaje.</span><span class="sxs-lookup"><span data-stu-id="892a9-148">Unit types are used only in Landed cost.</span></span> <span data-ttu-id="892a9-149">No están disponibles en TMS.</span><span class="sxs-lookup"><span data-stu-id="892a9-149">They aren't available in TMS.</span></span>

<span data-ttu-id="892a9-150">Para trabajar con tipos de unidades, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Tipos de unidades**.</span><span class="sxs-lookup"><span data-stu-id="892a9-150">To work with unit types, go to **Landed cost \> Containers setup \> Unit types**.</span></span> <span data-ttu-id="892a9-151">Allí, puede ver, agregar y eliminar registros para sus tipos de unidades.</span><span class="sxs-lookup"><span data-stu-id="892a9-151">There, you can view, add, and remove records for your unit types.</span></span> <span data-ttu-id="892a9-152">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="892a9-152">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="892a9-153">Campo</span><span class="sxs-lookup"><span data-stu-id="892a9-153">Field</span></span> | <span data-ttu-id="892a9-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="892a9-154">Description</span></span> |
|---|---|
| <span data-ttu-id="892a9-155">Tipo de unidad</span><span class="sxs-lookup"><span data-stu-id="892a9-155">Unit type</span></span> | <span data-ttu-id="892a9-156">Escriba un nombre/número de identificador único para el tipo de unidad.</span><span class="sxs-lookup"><span data-stu-id="892a9-156">Enter a unique identification name/number for the unit type.</span></span> |
| <span data-ttu-id="892a9-157">Descripción</span><span class="sxs-lookup"><span data-stu-id="892a9-157">Description</span></span> | <span data-ttu-id="892a9-158">Especifique una descripción del tipo de unidad.</span><span class="sxs-lookup"><span data-stu-id="892a9-158">Enter a description of the unit type.</span></span> |

## <a name="set-up-refrigeration-types"></a><a name="refrigeration-types"></a><span data-ttu-id="892a9-159">Configuración de los tipos de refrigeración</span><span class="sxs-lookup"><span data-stu-id="892a9-159">Set up refrigeration types</span></span>

<span data-ttu-id="892a9-160">Los tipos de refrigeración establecen grupos y métodos de identificación adicionales para contenedores de envío (normalmente contenedores refrigerados).</span><span class="sxs-lookup"><span data-stu-id="892a9-160">Refrigeration types establish additional groupings and identification methods for shipping containers (usually refrigerated containers).</span></span> <span data-ttu-id="892a9-161">Puede seleccionar un tipo de refrigeración cuando configura un contenedor en la página **Todos los contenedores de envío**.</span><span class="sxs-lookup"><span data-stu-id="892a9-161">You can select a refrigeration type when you set up a container on the **All shipping containers** page.</span></span>

<span data-ttu-id="892a9-162">Para trabajar con tipos de refrigeración, vaya a **Coste de aterrizaje \> Configuración de contenedores \> Tipos de refrigeración**.</span><span class="sxs-lookup"><span data-stu-id="892a9-162">To work with refrigeration types, go to **Landed cost \> Containers setup \> Refrigeration types**.</span></span> <span data-ttu-id="892a9-163">Allí, puede ver, agregar y eliminar registros para sus tipos de refrigeración.</span><span class="sxs-lookup"><span data-stu-id="892a9-163">There, you can view, add, and remove records for your refrigeration types.</span></span> <span data-ttu-id="892a9-164">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="892a9-164">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="892a9-165">Campo</span><span class="sxs-lookup"><span data-stu-id="892a9-165">Field</span></span> | <span data-ttu-id="892a9-166">Descripción</span><span class="sxs-lookup"><span data-stu-id="892a9-166">Description</span></span> |
|---|---|
| <span data-ttu-id="892a9-167">Tipo de refrigeración</span><span class="sxs-lookup"><span data-stu-id="892a9-167">Refrigeration type</span></span> | <span data-ttu-id="892a9-168">Escriba un nombre/número de identificador único para el tipo de refrigeración.</span><span class="sxs-lookup"><span data-stu-id="892a9-168">Enter a unique identification name/number for the refrigeration type.</span></span> |
| <span data-ttu-id="892a9-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="892a9-169">Description</span></span> | <span data-ttu-id="892a9-170">Especifique una descripción del tipo de refrigeración.</span><span class="sxs-lookup"><span data-stu-id="892a9-170">Enter a description of the refrigeration type.</span></span> |
