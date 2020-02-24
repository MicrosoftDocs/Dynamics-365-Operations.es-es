---
title: Configurar el autoservicio para empleados
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e44a35071b8d0987e6c949fb11312204317b44a1
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010477"
---
# <a name="configure-employee-self-service"></a><span data-ttu-id="821c6-102">Configurar el autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="821c6-102">Configure employee self service</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="821c6-103">En Microsoft Dynamics 365 Human Resources, puede configurar iconos para la navegación de nivel superior en autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="821c6-103">In Microsoft Dynamics 365 Human Resources, you can configure tiles for top-level navigation in Employee self service.</span></span> <span data-ttu-id="821c6-104">El icono del plan de prestaciones dirige a los usuarios a los planes de prestaciones en los que son idóneos para inscribirse.</span><span class="sxs-lookup"><span data-stu-id="821c6-104">Benefit plan tiles direct users to benefit plans that they are eligible to enroll in.</span></span>

## <a name="set-up-a-role-center-tile"></a><span data-ttu-id="821c6-105">Configurar un icono de centro de roles</span><span class="sxs-lookup"><span data-stu-id="821c6-105">Set up a role center tile</span></span>

1. <span data-ttu-id="821c6-106">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de autoservicio para empleados**.</span><span class="sxs-lookup"><span data-stu-id="821c6-106">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="821c6-107">Seleccione la pestaña **Configuración del icono del centro de roles** y luego seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="821c6-107">Select the **Role center tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="821c6-108">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="821c6-108">Specify values for the following fields:</span></span>

   | <span data-ttu-id="821c6-109">Campo</span><span class="sxs-lookup"><span data-stu-id="821c6-109">Field</span></span> | <span data-ttu-id="821c6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="821c6-110">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="821c6-111">Id. de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-111">Tile ID</span></span> | <span data-ttu-id="821c6-112">El identificador único del icono.</span><span class="sxs-lookup"><span data-stu-id="821c6-112">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="821c6-113">Texto de etiqueta de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-113">Tile label text</span></span> | <span data-ttu-id="821c6-114">El texto que aparecerá para el icono en el autoservicio.</span><span class="sxs-lookup"><span data-stu-id="821c6-114">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="821c6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="821c6-115">Description</span></span> | <span data-ttu-id="821c6-116">Una descripción del icono.</span><span class="sxs-lookup"><span data-stu-id="821c6-116">A description of the tile.</span></span> |
   | <span data-ttu-id="821c6-117">Dirección de Internet</span><span class="sxs-lookup"><span data-stu-id="821c6-117">Internet address</span></span> | <span data-ttu-id="821c6-118">Introduzca la URL de la página de autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="821c6-118">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="821c6-119">Tamaño de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-119">Tile size</span></span> | <span data-ttu-id="821c6-120">El tamaño del icono: pequeño, mediano o grande.</span><span class="sxs-lookup"><span data-stu-id="821c6-120">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="821c6-121">Destino</span><span class="sxs-lookup"><span data-stu-id="821c6-121">Target</span></span> | <span data-ttu-id="821c6-122">Especifica si la página debe abrirse en una nueva ventana o en la ventana actual.</span><span class="sxs-lookup"><span data-stu-id="821c6-122">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="821c6-123">Imagen de fondo de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-123">Tile background image</span></span> | <span data-ttu-id="821c6-124">La URL de la imagen a usar para el icono (opcional).</span><span class="sxs-lookup"><span data-stu-id="821c6-124">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="821c6-125">Inicio</span><span class="sxs-lookup"><span data-stu-id="821c6-125">Start</span></span> | <span data-ttu-id="821c6-126">La fecha y hora de inicio del icono en las que debe estar disponible.</span><span class="sxs-lookup"><span data-stu-id="821c6-126">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="821c6-127">Fin</span><span class="sxs-lookup"><span data-stu-id="821c6-127">End</span></span> | <span data-ttu-id="821c6-128">La fecha y hora de finalización del icono en las que debe estar disponible.</span><span class="sxs-lookup"><span data-stu-id="821c6-128">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="821c6-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="821c6-129">Select **Save**.</span></span>

## <a name="set-up-a-benefit-plans-tile"></a><span data-ttu-id="821c6-130">Configurar un icono de planes de prestaciones</span><span class="sxs-lookup"><span data-stu-id="821c6-130">Set up a benefit plans tile</span></span>

1. <span data-ttu-id="821c6-131">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de autoservicio para empleados**.</span><span class="sxs-lookup"><span data-stu-id="821c6-131">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="821c6-132">Seleccione la pestaña **Configuración del icono de planes de prestaciones** y luego seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="821c6-132">Select the **Benefit plans tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="821c6-133">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="821c6-133">Specify values for the following fields:</span></span>

   | <span data-ttu-id="821c6-134">Campo</span><span class="sxs-lookup"><span data-stu-id="821c6-134">Field</span></span> | <span data-ttu-id="821c6-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="821c6-135">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="821c6-136">Id. de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-136">Tile ID</span></span> | <span data-ttu-id="821c6-137">El identificador único del icono.</span><span class="sxs-lookup"><span data-stu-id="821c6-137">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="821c6-138">Texto de etiqueta de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-138">Tile label text</span></span> | <span data-ttu-id="821c6-139">El texto que aparecerá para el icono en el autoservicio.</span><span class="sxs-lookup"><span data-stu-id="821c6-139">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="821c6-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="821c6-140">Description</span></span> | <span data-ttu-id="821c6-141">Una descripción del icono.</span><span class="sxs-lookup"><span data-stu-id="821c6-141">A description of the tile.</span></span> |
   | <span data-ttu-id="821c6-142">Dirección de Internet</span><span class="sxs-lookup"><span data-stu-id="821c6-142">Internet address</span></span> | <span data-ttu-id="821c6-143">Introduzca la URL de la página de autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="821c6-143">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="821c6-144">Tamaño de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-144">Tile size</span></span> | <span data-ttu-id="821c6-145">El tamaño del icono: pequeño, mediano o grande.</span><span class="sxs-lookup"><span data-stu-id="821c6-145">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="821c6-146">Destino</span><span class="sxs-lookup"><span data-stu-id="821c6-146">Target</span></span> | <span data-ttu-id="821c6-147">Especifica si la página debe abrirse en una nueva ventana o en la ventana actual.</span><span class="sxs-lookup"><span data-stu-id="821c6-147">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="821c6-148">Imagen de fondo de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-148">Tile background image</span></span> | <span data-ttu-id="821c6-149">La URL de la imagen a usar para el icono (opcional).</span><span class="sxs-lookup"><span data-stu-id="821c6-149">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="821c6-150">Inicio</span><span class="sxs-lookup"><span data-stu-id="821c6-150">Start</span></span> | <span data-ttu-id="821c6-151">La fecha y hora de inicio del icono en las que debe estar disponible.</span><span class="sxs-lookup"><span data-stu-id="821c6-151">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="821c6-152">Fin</span><span class="sxs-lookup"><span data-stu-id="821c6-152">End</span></span> | <span data-ttu-id="821c6-153">La fecha y hora de finalización del icono en las que debe estar disponible.</span><span class="sxs-lookup"><span data-stu-id="821c6-153">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="821c6-154">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="821c6-154">Select **Save**.</span></span>

## <a name="set-up-a-flex-credit-plan-tile"></a><span data-ttu-id="821c6-155">Configurar un icono de plan de crédito flexible</span><span class="sxs-lookup"><span data-stu-id="821c6-155">Set up a flex credit plan tile</span></span>

1. <span data-ttu-id="821c6-156">En el espacio de trabajo **Administración de prestaciones**, en **Configuración**, seleccione **Parámetros de autoservicio para empleados**.</span><span class="sxs-lookup"><span data-stu-id="821c6-156">In the **Benefits management** workspace, under **Setup**, select **Employee self service parameters**.</span></span>

2. <span data-ttu-id="821c6-157">Seleccione la pestaña **Configuración del icono de plan de crédito flexible** y luego seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="821c6-157">Select the **Flex credit plan tile setup** tab, and then select **New**.</span></span>

3. <span data-ttu-id="821c6-158">Especifique los valores para los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="821c6-158">Specify values for the following fields:</span></span>

   | <span data-ttu-id="821c6-159">Campo</span><span class="sxs-lookup"><span data-stu-id="821c6-159">Field</span></span> | <span data-ttu-id="821c6-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="821c6-160">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="821c6-161">Id. de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-161">Tile ID</span></span> | <span data-ttu-id="821c6-162">El identificador único del icono.</span><span class="sxs-lookup"><span data-stu-id="821c6-162">The unique identifier for the tile.</span></span> |
   | <span data-ttu-id="821c6-163">Texto de etiqueta de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-163">Tile label text</span></span> | <span data-ttu-id="821c6-164">El texto que aparecerá para el icono en el autoservicio.</span><span class="sxs-lookup"><span data-stu-id="821c6-164">The text that will appear for the tile on Self-service.</span></span> |
   | <span data-ttu-id="821c6-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="821c6-165">Description</span></span> | <span data-ttu-id="821c6-166">Una descripción del icono.</span><span class="sxs-lookup"><span data-stu-id="821c6-166">A description of the tile.</span></span> |
   | <span data-ttu-id="821c6-167">Dirección de Internet</span><span class="sxs-lookup"><span data-stu-id="821c6-167">Internet address</span></span> | <span data-ttu-id="821c6-168">Introduzca la URL de la página de autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="821c6-168">Enter the URL to the employee self service page.</span></span> |
   | <span data-ttu-id="821c6-169">Tamaño de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-169">Tile size</span></span> | <span data-ttu-id="821c6-170">El tamaño del icono: pequeño, mediano o grande.</span><span class="sxs-lookup"><span data-stu-id="821c6-170">The size of the tile: Small, Medium, or Large.</span></span> |
   | <span data-ttu-id="821c6-171">Destino</span><span class="sxs-lookup"><span data-stu-id="821c6-171">Target</span></span> | <span data-ttu-id="821c6-172">Especifica si la página debe abrirse en una nueva ventana o en la ventana actual.</span><span class="sxs-lookup"><span data-stu-id="821c6-172">Specifies whether the page should open in a new window or the current window.</span></span> |
   | <span data-ttu-id="821c6-173">Imagen de fondo de icono</span><span class="sxs-lookup"><span data-stu-id="821c6-173">Tile background image</span></span> | <span data-ttu-id="821c6-174">La URL de la imagen a usar para el icono (opcional).</span><span class="sxs-lookup"><span data-stu-id="821c6-174">The URL of the image to use for the tile (optional).</span></span> |
   | <span data-ttu-id="821c6-175">Inicio</span><span class="sxs-lookup"><span data-stu-id="821c6-175">Start</span></span> | <span data-ttu-id="821c6-176">La fecha y hora de inicio del icono en las que debe estar disponible.</span><span class="sxs-lookup"><span data-stu-id="821c6-176">The beginning date and time the tile should be available.</span></span> |
   | <span data-ttu-id="821c6-177">Fin</span><span class="sxs-lookup"><span data-stu-id="821c6-177">End</span></span> | <span data-ttu-id="821c6-178">La fecha y hora de finalización del icono en las que debe estar disponible.</span><span class="sxs-lookup"><span data-stu-id="821c6-178">The end date and time the tile should be available.</span></span> |

4. <span data-ttu-id="821c6-179">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="821c6-179">Select **Save**.</span></span>
