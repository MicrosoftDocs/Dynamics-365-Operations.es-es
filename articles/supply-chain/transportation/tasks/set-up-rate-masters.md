---
title: Configurar listas maestras de tasas
description: Este procedimiento muestra cómo configurar una tasa maestra.
author: ShylaThompson
manager: tfehr
ms.date: 10/16/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSBreakMaster,TMSRateMaster,TMSRateMasterBase,TMSRateBaseType, TMSRouteWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 47fa7edeba81d826a00668a2da74113f552437f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4974269"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="599dc-103">Configurar listas maestras de tasas</span><span class="sxs-lookup"><span data-stu-id="599dc-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="599dc-104">Este procedimiento muestra cómo configurar una tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="599dc-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="599dc-105">El administrador de logística configura normalmente tasas maestras, en función de los contratos firmados con los transportistas.</span><span class="sxs-lookup"><span data-stu-id="599dc-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="599dc-106">En este caso, configurará una tasa maestra para una compañía aérea.</span><span class="sxs-lookup"><span data-stu-id="599dc-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="599dc-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="599dc-107">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-break-master"></a><span data-ttu-id="599dc-108">Configurar un maestro de interrupción</span><span class="sxs-lookup"><span data-stu-id="599dc-108">Set up break master</span></span>

1. <span data-ttu-id="599dc-109">Vaya a **Administración de transporte > Configuración > Clasificación > Maestro de interrupción**.</span><span class="sxs-lookup"><span data-stu-id="599dc-109">Go to **Transportation management > Setup > Rating > Break master**.</span></span> <span data-ttu-id="599dc-110">Los maestros de interrupción se usan para definir la estructura de precios y sus puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="599dc-110">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="599dc-111">La estructura de precios usa precios con niveles basados en dimensiones físicas.</span><span class="sxs-lookup"><span data-stu-id="599dc-111">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
1. <span data-ttu-id="599dc-112">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="599dc-112">Select **New**.</span></span>
1. <span data-ttu-id="599dc-113">En el campo **Maestro de interrupción**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="599dc-113">In the **Break master** field, enter a value.</span></span>
1. <span data-ttu-id="599dc-114">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="599dc-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="599dc-115">En el campo **Tipo de datos**, seleccione el tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="599dc-115">In the **Data type** field, select the data type.</span></span>
1. <span data-ttu-id="599dc-116">En el campo **Comparación**, ingrese el tipo de comparación solicitada (usando operadores).</span><span class="sxs-lookup"><span data-stu-id="599dc-116">In the **Comparison** field, enter the kind of comparison requested (using operators).</span></span>
1. <span data-ttu-id="599dc-117">En el campo **Unidad de interrupción** especifique los valores de la unidad de interrupción.</span><span class="sxs-lookup"><span data-stu-id="599dc-117">In the **Break unit** field, enter the break unit.</span></span>
1. <span data-ttu-id="599dc-118">En la sección **Detalles**, cree tantas pausas como sea necesario para la estructura de precios.</span><span class="sxs-lookup"><span data-stu-id="599dc-118">In the **Details** section, create as many breaks as needed for the pricing structure.</span></span>
1. <span data-ttu-id="599dc-119">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="599dc-119">Select **Save**.</span></span>

## <a name="set-up-rate-master"></a><span data-ttu-id="599dc-120">Configuración de tasas maestras</span><span class="sxs-lookup"><span data-stu-id="599dc-120">Set up rate master</span></span>

1. <span data-ttu-id="599dc-121">Vaya a **Administración de transporte > Configuración > Clasificación > Tasa maestra**.</span><span class="sxs-lookup"><span data-stu-id="599dc-121">Go to **Transportation management > Setup > Rating > Rate master**.</span></span>
1. <span data-ttu-id="599dc-122">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="599dc-122">Select **New**.</span></span>
1. <span data-ttu-id="599dc-123">En el campo **Tasa maestra**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="599dc-123">In the **Rate master** field, type a value.</span></span>
1. <span data-ttu-id="599dc-124">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="599dc-124">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="599dc-125">En el campo **Id. de metadatos de clasificación**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="599dc-125">In the **Rating metadata ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="599dc-126">El identificador de metadatos de clasificación determinará los datos necesarios para la tasa maestra, ya que define los metadatos previstos por el motor de gestión de transporte que usa esta tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="599dc-126">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the transportation management engine using this rate master.</span></span>  
1. <span data-ttu-id="599dc-127">Para este ejemplo, seleccione la opción P2P.</span><span class="sxs-lookup"><span data-stu-id="599dc-127">For this example, select the P2P option.</span></span> <span data-ttu-id="599dc-128">Esto ya está definido en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="599dc-128">This is already defined in the demo data.</span></span>
1. <span data-ttu-id="599dc-129">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="599dc-129">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="599dc-130">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="599dc-130">Select **Save**.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="599dc-131">Configuración de la base de tasa</span><span class="sxs-lookup"><span data-stu-id="599dc-131">Set up rate base</span></span>

1. <span data-ttu-id="599dc-132">Seleccione **Base de tasa**.</span><span class="sxs-lookup"><span data-stu-id="599dc-132">Select **Rate base**.</span></span>
    * <span data-ttu-id="599dc-133">La base de tasa determina la tasa del transportista, y se puede usar para configurar una estructura de tarifa al estructurar las tasas en los puntos de interrupción definidos en el maestro de interrupción.</span><span class="sxs-lookup"><span data-stu-id="599dc-133">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="599dc-134">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="599dc-134">Select **New**.</span></span>
3. <span data-ttu-id="599dc-135">En el campo **Base de tasa**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="599dc-135">In the **Rate base** field, type a value.</span></span>
4. <span data-ttu-id="599dc-136">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="599dc-136">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="599dc-137">En el campo **Maestro de interrupción**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="599dc-137">In the **Break master** field, select the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="599dc-138">Los maestros de interrupción se usan para definir la estructura de precios y sus puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="599dc-138">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="599dc-139">La estructura de precios usa precios con niveles basados en dimensiones físicas.</span><span class="sxs-lookup"><span data-stu-id="599dc-139">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="599dc-140">Para este ejemplo, use el peso.</span><span class="sxs-lookup"><span data-stu-id="599dc-140">For this example, use weight.</span></span> <span data-ttu-id="599dc-141">Esto ya está definido en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="599dc-141">This is already defined in the demo data.</span></span>
7. <span data-ttu-id="599dc-142">En la lista, seleccione el vínculo de la fila resaltada.</span><span class="sxs-lookup"><span data-stu-id="599dc-142">In the list, select the link in the highlighted row.</span></span>
8. <span data-ttu-id="599dc-143">Expanda la sección **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="599dc-143">Expand the **Details** section.</span></span>
9. <span data-ttu-id="599dc-144">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="599dc-144">Select **New**.</span></span>
10. <span data-ttu-id="599dc-145">En el campo **Código postal de la ubicación de devolución de**, especifique "30301".</span><span class="sxs-lookup"><span data-stu-id="599dc-145">In the **Drop-off Postal Code From** field, type "30301".</span></span>
11. <span data-ttu-id="599dc-146">En el campo **Código postal de la ubicación de devolución a**, especifique "30318".</span><span class="sxs-lookup"><span data-stu-id="599dc-146">In the **Drop-off Postal Code To** field, type "30318".</span></span>
12. <span data-ttu-id="599dc-147">En el campo **País o región de la ubicación de devolución**, escriba "EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="599dc-147">In the **Drop-off Country Region** field, type "USA".</span></span>
13. <span data-ttu-id="599dc-148">En el campo **<1.00 Lbs**, escriba "100".</span><span class="sxs-lookup"><span data-stu-id="599dc-148">In the **<1.00 Lbs** field, type "100".</span></span>
    * <span data-ttu-id="599dc-149">Inserte la tasa por libras si el peso total de la carga es inferior a 1 libra.</span><span class="sxs-lookup"><span data-stu-id="599dc-149">Insert the rate per pounds if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="599dc-150">En el campo **<5.00 Lbs**, escriba "300".</span><span class="sxs-lookup"><span data-stu-id="599dc-150">In the **<5.00 Lbs** field, type "300".</span></span>
    * <span data-ttu-id="599dc-151">Inserte la tasa por libras si el peso total de la carga es inferior a 5 libras.</span><span class="sxs-lookup"><span data-stu-id="599dc-151">Insert the rate per pounds if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="599dc-152">En el campo **<20.00 Lbs**, escriba "500".</span><span class="sxs-lookup"><span data-stu-id="599dc-152">In the **<20.00 Lbs** field, type "500".</span></span>
    * <span data-ttu-id="599dc-153">Inserte la tasa por libras si el peso total de la carga es inferior a 20 libras.</span><span class="sxs-lookup"><span data-stu-id="599dc-153">Insert the rate per pounds if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="599dc-154">En el campo **<100.00 Lbs**, escriba "1000".</span><span class="sxs-lookup"><span data-stu-id="599dc-154">In the **<100.00 Lbs** field, type "1000".</span></span>
    * <span data-ttu-id="599dc-155">Inserte la tasa por libras si el peso total de la carga es inferior a 100 libras.</span><span class="sxs-lookup"><span data-stu-id="599dc-155">Insert the rate per pounds if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="599dc-156">En el campo **<1,000.00 Lbs**, escriba "3000".</span><span class="sxs-lookup"><span data-stu-id="599dc-156">In the **<1,000.00 Lbs** field, type "3000".</span></span>
    * <span data-ttu-id="599dc-157">Inserte la tasa por libras si el peso total de la carga es inferior a 1000 libras.</span><span class="sxs-lookup"><span data-stu-id="599dc-157">Insert the rate per pounds if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="599dc-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="599dc-158">Select **Save**.</span></span>
19. <span data-ttu-id="599dc-159">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="599dc-159">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="599dc-160">Asignación de la base de tasa</span><span class="sxs-lookup"><span data-stu-id="599dc-160">Assign rate base</span></span>

1. <span data-ttu-id="599dc-161">Expanda la sección **Asignaciones de base de tasa**.</span><span class="sxs-lookup"><span data-stu-id="599dc-161">Expand the **Rate base assignments** section.</span></span>
2. <span data-ttu-id="599dc-162">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="599dc-162">Select **New**.</span></span>
    * <span data-ttu-id="599dc-163">Puede tener varias asignaciones de base de tasa para cada tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="599dc-163">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="599dc-164">Esto permite crear varios puntos de precios distintos para cada transportista, en función de los destinos, los servicios o distintas bases de tasa.</span><span class="sxs-lookup"><span data-stu-id="599dc-164">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="599dc-165">En este procedimiento creará solo una asignación de base de tasa.</span><span class="sxs-lookup"><span data-stu-id="599dc-165">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="599dc-166">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="599dc-166">In the **Name** field, type a value.</span></span>
4. <span data-ttu-id="599dc-167">En el campo **Base de tasa**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="599dc-167">In the **Rate base** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="599dc-168">En la lista, seleccione el vínculo de la fila resaltada.</span><span class="sxs-lookup"><span data-stu-id="599dc-168">In the list, select the link in the highlighted row.</span></span>
6. <span data-ttu-id="599dc-169">En el campo **Servicio**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="599dc-169">In the **Service** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="599dc-170">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="599dc-170">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="599dc-171">En la lista, seleccione el vínculo de la fila resaltada.</span><span class="sxs-lookup"><span data-stu-id="599dc-171">In the list, select the link in the highlighted row.</span></span>
9. <span data-ttu-id="599dc-172">En el campo **Código postal de recogida**, escriba "98052".</span><span class="sxs-lookup"><span data-stu-id="599dc-172">In the **Pick-up Postal Code** field, type "98052".</span></span>
    * <span data-ttu-id="599dc-173">Especifique desde qué código postal será válida esta asignación de base de tasa.</span><span class="sxs-lookup"><span data-stu-id="599dc-173">Specify which postal code this rate base assignment should be valid from.</span></span>
10. <span data-ttu-id="599dc-174">En el campo **País o región de recogida**, escriba "EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="599dc-174">In the **Pick-up Country Region** field, type "USA".</span></span>
11. <span data-ttu-id="599dc-175">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="599dc-175">Select **Save**.</span></span>
