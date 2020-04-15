---
title: Configurar listas maestras de tasas
description: Este procedimiento muestra cómo configurar una tasa maestra.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2aaceb78029408dcea67d0382fd1fc05e550d02a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146201"
---
# <a name="set-up-rate-masters"></a><span data-ttu-id="4e028-103">Configurar listas maestras de tasas</span><span class="sxs-lookup"><span data-stu-id="4e028-103">Set up rate masters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4e028-104">Este procedimiento muestra cómo configurar una tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="4e028-104">This procedure shows you how to set up a rate master.</span></span> <span data-ttu-id="4e028-105">El administrador de logística configura normalmente tasas maestras, en función de los contratos firmados con los transportistas.</span><span class="sxs-lookup"><span data-stu-id="4e028-105">The logistic manager usually sets up rate masters, depending on the contracts signed with the carriers.</span></span> <span data-ttu-id="4e028-106">En este caso, configurará una tasa maestra para una compañía aérea.</span><span class="sxs-lookup"><span data-stu-id="4e028-106">In this scenario you will set up a rate master for an air carrier.</span></span> <span data-ttu-id="4e028-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="4e028-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-rate-master"></a><span data-ttu-id="4e028-108">Configuración de tasas maestras</span><span class="sxs-lookup"><span data-stu-id="4e028-108">Set up rate master</span></span>
1. <span data-ttu-id="4e028-109">Vaya a Administración de transporte > Configuración > Clasificación > Tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="4e028-109">Go to Transportation management > Setup > Rating > Rate master.</span></span>
2. <span data-ttu-id="4e028-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e028-110">Click New.</span></span>
3. <span data-ttu-id="4e028-111">En el campo Tasa maestra, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e028-111">In the Rate master field, type a value.</span></span>
4. <span data-ttu-id="4e028-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e028-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4e028-113">En el campo Id. de metadatos de clasificación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e028-113">In the Rating metadata ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="4e028-114">El identificador de metadatos de clasificación determinará los datos necesarios para la tasa maestra, ya que define los metadatos previstos por el motor de TMS que usa esta tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="4e028-114">The rating metadata ID will determine the data needed for the rate master, as it defines the metadata expected by the TMS engine using this rate master.</span></span>  
6. <span data-ttu-id="4e028-115">Para este ejemplo, seleccione la opción P2P.</span><span class="sxs-lookup"><span data-stu-id="4e028-115">For this example, select the P2P option</span></span>
7. <span data-ttu-id="4e028-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e028-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="4e028-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e028-117">Click Save.</span></span>

## <a name="set-up-rate-base"></a><span data-ttu-id="4e028-118">Configuración de la base de tasa</span><span class="sxs-lookup"><span data-stu-id="4e028-118">Set up rate base</span></span>
1. <span data-ttu-id="4e028-119">Haga clic en Base de tasa.</span><span class="sxs-lookup"><span data-stu-id="4e028-119">Click Rate base.</span></span>
    * <span data-ttu-id="4e028-120">La base de tasa determina la tasa del transportista, y se puede usar para configurar una estructura de tarifa al estructurar las tasas en los puntos de interrupción definidos en el maestro de interrupción.</span><span class="sxs-lookup"><span data-stu-id="4e028-120">The rate base determines the rate of the carrier, and can be used to set up a tariff structure as it structures the rates in the breakpoints defined in the break master.</span></span>  
2. <span data-ttu-id="4e028-121">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e028-121">Click New.</span></span>
3. <span data-ttu-id="4e028-122">En el campo Base de tasa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e028-122">In the Rate base field, type a value.</span></span>
4. <span data-ttu-id="4e028-123">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e028-123">In the Name field, type a value.</span></span>
5. <span data-ttu-id="4e028-124">En el campo Maestro de interrupción, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e028-124">In the Break master field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="4e028-125">Los maestros de interrupción se usan para definir la estructura de precios y sus puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="4e028-125">Break masters are used to define the pricing structure and its breakpoints.</span></span> <span data-ttu-id="4e028-126">La estructura de precios usa precios con niveles basados en dimensiones físicas.</span><span class="sxs-lookup"><span data-stu-id="4e028-126">The pricing structure uses tiered pricing that is based on physical dimensions.</span></span>  
6. <span data-ttu-id="4e028-127">Para este ejemplo, use el peso.</span><span class="sxs-lookup"><span data-stu-id="4e028-127">For this example, use weight</span></span>
7. <span data-ttu-id="4e028-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e028-128">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="4e028-129">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="4e028-129">Toggle the expansion of the Details section.</span></span>
9. <span data-ttu-id="4e028-130">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e028-130">Click New.</span></span>
10. <span data-ttu-id="4e028-131">En el campo Código postal de la ubicación de devolución de, especifique "30301".</span><span class="sxs-lookup"><span data-stu-id="4e028-131">In the Drop-off Postal Code From field, type '30301'.</span></span>
11. <span data-ttu-id="4e028-132">En el campo Código postal de la ubicación de devolución a, especifique "30318".</span><span class="sxs-lookup"><span data-stu-id="4e028-132">In the Drop-off Postal Code To field, type '30318'.</span></span>
12. <span data-ttu-id="4e028-133">En el campo País o región de la ubicación de devolución, escriba "EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="4e028-133">In the Drop-off Country Region field, type 'USA'.</span></span>
13. <span data-ttu-id="4e028-134">En el campo <1.00 Lbs, escriba "100".</span><span class="sxs-lookup"><span data-stu-id="4e028-134">In the <1.00 Lbs field, type '100'.</span></span>
    * <span data-ttu-id="4e028-135">Inserte la tasa por libras si el peso total de la carga es inferior a 1 libra.</span><span class="sxs-lookup"><span data-stu-id="4e028-135">Insert the rate per lbs if the total weight of the load is less than 1 pound.</span></span>  
14. <span data-ttu-id="4e028-136">En el campo <5,00 Lbs, escriba "300".</span><span class="sxs-lookup"><span data-stu-id="4e028-136">In the <5.00 Lbs field, type '300'.</span></span>
    * <span data-ttu-id="4e028-137">Inserte la tasa por libras si el peso total de la carga es inferior a 5 libras.</span><span class="sxs-lookup"><span data-stu-id="4e028-137">Insert the rate per lbs if the total weight of the load is less than 5 pounds.</span></span>  
15. <span data-ttu-id="4e028-138">En el campo <20,00 Lbs, escriba "500".</span><span class="sxs-lookup"><span data-stu-id="4e028-138">In the <20.00 Lbs field, type '500'.</span></span>
    * <span data-ttu-id="4e028-139">Inserte la tasa por libra si el peso total de la carga es inferior a 20 libras.</span><span class="sxs-lookup"><span data-stu-id="4e028-139">Insert the rate per lbs if the total weight of the load is less than 20 pounds.</span></span>  
16. <span data-ttu-id="4e028-140">En el campo <100,00 Lbs, escriba "1000".</span><span class="sxs-lookup"><span data-stu-id="4e028-140">In the <100.00 Lbs field, type '1000'.</span></span>
    * <span data-ttu-id="4e028-141">Inserte la tasa por libra si el peso total de la carga es inferior a 100 libras.</span><span class="sxs-lookup"><span data-stu-id="4e028-141">Insert the rate per lbs if the total weight of the load is less than 100 pounds.</span></span>  
17. <span data-ttu-id="4e028-142">En el campo <1000,00 Lbs, escriba "3000".</span><span class="sxs-lookup"><span data-stu-id="4e028-142">In the <1,000.00 Lbs field, type '3000'.</span></span>
    * <span data-ttu-id="4e028-143">Inserte la tasa por libra si el peso total de la carga es inferior a 1000 libras.</span><span class="sxs-lookup"><span data-stu-id="4e028-143">Insert the rate per lbs if the total weight of the load is less than 1000 pounds.</span></span>  
18. <span data-ttu-id="4e028-144">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e028-144">Click Save.</span></span>
19. <span data-ttu-id="4e028-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e028-145">Close the page.</span></span>

## <a name="assign-rate-base"></a><span data-ttu-id="4e028-146">Asignación de la base de tasa</span><span class="sxs-lookup"><span data-stu-id="4e028-146">Assign rate base</span></span>
1. <span data-ttu-id="4e028-147">Expanda la sección Asignaciones de base de tasa.</span><span class="sxs-lookup"><span data-stu-id="4e028-147">Toggle the expansion of the Rate base assignments section.</span></span>
2. <span data-ttu-id="4e028-148">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e028-148">Click New.</span></span>
    * <span data-ttu-id="4e028-149">Puede tener varias asignaciones de base de tasa para cada tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="4e028-149">You can have several rate base assignments for each rate master.</span></span> <span data-ttu-id="4e028-150">Esto permite crear varios puntos de precios distintos para cada transportista, en función de los destinos, los servicios o distintas bases de tasa.</span><span class="sxs-lookup"><span data-stu-id="4e028-150">This makes it possible to create several different price points for each carrier depending on destinations, services, or different rate bases.</span></span> <span data-ttu-id="4e028-151">En este procedimiento creará solo una asignación de base de tasa.</span><span class="sxs-lookup"><span data-stu-id="4e028-151">In this procedure you will only create one rate base assignment.</span></span>  
3. <span data-ttu-id="4e028-152">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e028-152">In the Name field, type a value.</span></span>
4. <span data-ttu-id="4e028-153">En el campo Base de tasa, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e028-153">In the Rate base field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="4e028-154">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e028-154">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4e028-155">En el campo Servicio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e028-155">In the Service field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="4e028-156">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4e028-156">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="4e028-157">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e028-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="4e028-158">En el campo Código postal de recogida, escriba "98052".</span><span class="sxs-lookup"><span data-stu-id="4e028-158">In the Pick-up Postal Code field, type '98052'.</span></span>
    * <span data-ttu-id="4e028-159">Especifique desde qué código postal será válida esta asignación de base de tasa.</span><span class="sxs-lookup"><span data-stu-id="4e028-159">Specify which postal code this rate base assignment should be valid from.</span></span>    
10. <span data-ttu-id="4e028-160">En el campo País o región de recogida, escriba "EE. UU.".</span><span class="sxs-lookup"><span data-stu-id="4e028-160">In the Pick-up Country Region field, type 'USA'.</span></span>
11. <span data-ttu-id="4e028-161">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e028-161">Click Save.</span></span>

