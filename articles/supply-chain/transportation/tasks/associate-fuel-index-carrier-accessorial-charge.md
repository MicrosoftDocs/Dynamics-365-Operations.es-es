---
title: Asociación de un índice de combustible con un transportista como cargo adicional
description: Este procedimiento muestra cómo crear una asignación de cargos adicionales, un cargo adicional de transportista y cargos adicionales maestros por recargo por combustible, y cómo asociar un índice de combustible de transportista con un transportista.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c91d49c2ccdc274632e3acf94b836e19dc6cdaa8
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017009"
---
# <a name="associate-a-fuel-index-with-a-carrier-as-an-accessorial-charge"></a><span data-ttu-id="7d05d-103">Asociación de un índice de combustible con un transportista como cargo adicional</span><span class="sxs-lookup"><span data-stu-id="7d05d-103">Associate a fuel index with a carrier as an accessorial charge</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7d05d-104">Este procedimiento muestra cómo crear una asignación de cargos adicionales, un cargo adicional de transportista y cargos adicionales maestros por recargo por combustible, y cómo asociar un índice de combustible de transportista con un transportista.</span><span class="sxs-lookup"><span data-stu-id="7d05d-104">This guide shows how to create an accessorial assignment, carrier accessorial charge, accessorial master for fuel surcharge, and associate a carrier fuel index with a carrier.</span></span> <span data-ttu-id="7d05d-105">Es necesario haber configurado un índice de combustible de transportista antes de ejecutar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7d05d-105">You need to have set up a carrier fuel index before you run this guide.</span></span> <span data-ttu-id="7d05d-106">Puede usar el procedimiento "Configuración de un índice de combustible de transportista".</span><span class="sxs-lookup"><span data-stu-id="7d05d-106">You can use the "Set up a carrier fuel index" guide to do this.</span></span> <span data-ttu-id="7d05d-107">Estas tareas de configuración las realiza normalmente el administrador de logística.</span><span class="sxs-lookup"><span data-stu-id="7d05d-107">These setup tasks are typically done by a Logistics manager.</span></span> <span data-ttu-id="7d05d-108">Los datos de demostración utilizados para crear este procedimiento son los de la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="7d05d-108">The demo data used to create this procedure is USMF.</span></span>


## <a name="create-an-accessorial-master"></a><span data-ttu-id="7d05d-109">Creación de un cargo maestro adicional</span><span class="sxs-lookup"><span data-stu-id="7d05d-109">Create an accessorial master</span></span>
1. <span data-ttu-id="7d05d-110">Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales maestros.</span><span class="sxs-lookup"><span data-stu-id="7d05d-110">Go to Transportation management > Setup > Rating > Accessorial masters.</span></span>
2. <span data-ttu-id="7d05d-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7d05d-111">Click New.</span></span>
3. <span data-ttu-id="7d05d-112">En el campo Cargos adicionales maestros, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7d05d-112">In the Accessorial master field, type a value.</span></span>
4. <span data-ttu-id="7d05d-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7d05d-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="7d05d-114">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7d05d-114">Click Save.</span></span>

## <a name="create-a-carrier-accessorial-charge"></a><span data-ttu-id="7d05d-115">Creación de un cargo adicional de transportista</span><span class="sxs-lookup"><span data-stu-id="7d05d-115">Create a carrier accessorial charge</span></span>
1. <span data-ttu-id="7d05d-116">Vaya a Administración de transporte > Configuración > Clasificación > Cargos adicionales del transportista.</span><span class="sxs-lookup"><span data-stu-id="7d05d-116">Go to Transportation management > Setup > Rating > Carrier accessorial charges.</span></span>
2. <span data-ttu-id="7d05d-117">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7d05d-117">Click New.</span></span>
3. <span data-ttu-id="7d05d-118">En el campo Id. de cargos adicionales del transportista, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7d05d-118">In the Carrier accessorial ID field, type a value.</span></span>
4. <span data-ttu-id="7d05d-119">En el campo Transportista de envío, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d05d-119">In the Shipping carrier field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="7d05d-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7d05d-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7d05d-121">En este ejemplo, elija el transportista por camión.</span><span class="sxs-lookup"><span data-stu-id="7d05d-121">In this example, choose Truck Carrier.</span></span>  
6. <span data-ttu-id="7d05d-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7d05d-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="7d05d-123">En el campo Servicio de transportista, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d05d-123">In the Carrier service field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="7d05d-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7d05d-124">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="7d05d-125">En el campo Cargos adicionales maestros, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d05d-125">In the Accessorial master field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="7d05d-126">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7d05d-126">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="7d05d-127">En este ejemplo, elija los cargos adicionales maestros recién creados.</span><span class="sxs-lookup"><span data-stu-id="7d05d-127">In this example, choose the newly created Accessorial master.</span></span>  
11. <span data-ttu-id="7d05d-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7d05d-128">Click Save.</span></span>

## <a name="create-an-accessorial-assignment"></a><span data-ttu-id="7d05d-129">Creación de una asignación de cargos adicionales</span><span class="sxs-lookup"><span data-stu-id="7d05d-129">Create an accessorial assignment</span></span>
1. <span data-ttu-id="7d05d-130">Haga clic en Asignaciones de cargos adicionales.</span><span class="sxs-lookup"><span data-stu-id="7d05d-130">Click Accessorial assignments.</span></span>
2. <span data-ttu-id="7d05d-131">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7d05d-131">Click New.</span></span>
3. <span data-ttu-id="7d05d-132">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7d05d-132">In the Name field, type a value.</span></span>
4. <span data-ttu-id="7d05d-133">Expanda la sección Criterios.</span><span class="sxs-lookup"><span data-stu-id="7d05d-133">Toggle the expansion of the Criteria section.</span></span>
    * <span data-ttu-id="7d05d-134">En los criterios puede elegir aplicar siempre un suplemento por combustible o, para este ejemplo, elija que se aplique solo dentro de determinada región.</span><span class="sxs-lookup"><span data-stu-id="7d05d-134">In the criteria, you can choose to always apply the fuel surcharge or for this example choose that it only applies within a certain region.</span></span>  
5. <span data-ttu-id="7d05d-135">En el campo Valor inicial de código postal, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7d05d-135">In the ZIP/postal code from field, type a value.</span></span>
6. <span data-ttu-id="7d05d-136">En el campo Valor final de código postal, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7d05d-136">In the ZIP/postal code to field, type a value.</span></span>
7. <span data-ttu-id="7d05d-137">Expanda la sección Cálculo.</span><span class="sxs-lookup"><span data-stu-id="7d05d-137">Toggle the expansion of the Calculation section.</span></span>
    * <span data-ttu-id="7d05d-138">En la sección de cálculo, puede especificar la manera de calcular el recargo por combustible.</span><span class="sxs-lookup"><span data-stu-id="7d05d-138">In the calculation section you can specify how to calculate the fuel surcharge.</span></span> <span data-ttu-id="7d05d-139">Este cálculo depende de la unidad adicional que haya elegido como base para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="7d05d-139">This calculation depends on the Accessorial unit that you chose as the base for your calculation.</span></span>  
8. <span data-ttu-id="7d05d-140">En el campo Tipo de tasas de cargos adicionales, seleccione Suplemento por combustible.</span><span class="sxs-lookup"><span data-stu-id="7d05d-140">In the Accessorial fee type field, select 'Fuel surcharge'.</span></span>
9. <span data-ttu-id="7d05d-141">En el campo Unidad adicional, seleccione Kilometraje.</span><span class="sxs-lookup"><span data-stu-id="7d05d-141">In the Accessorial unit field, select 'Mileage'.</span></span>
10. <span data-ttu-id="7d05d-142">En el campo Región, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d05d-142">In the Region field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="7d05d-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7d05d-143">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="7d05d-144">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7d05d-144">Click Save.</span></span>

## <a name="update-the-carrier-rating-profile"></a><span data-ttu-id="7d05d-145">Actualización del perfil de clasificación de transportista</span><span class="sxs-lookup"><span data-stu-id="7d05d-145">Update the carrier rating profile</span></span>
1. <span data-ttu-id="7d05d-146">Vaya a Administración de transporte > Configuración > Transportistas > Transportistas de envío.</span><span class="sxs-lookup"><span data-stu-id="7d05d-146">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="7d05d-147">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="7d05d-147">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="7d05d-148">Expanda la sección Perfiles de clasificación.</span><span class="sxs-lookup"><span data-stu-id="7d05d-148">Toggle the expansion of the Rating profiles section.</span></span>
4. <span data-ttu-id="7d05d-149">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="7d05d-149">Click Edit.</span></span>
5. <span data-ttu-id="7d05d-150">En el campo Índice de combustible del transportista, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="7d05d-150">In the Carrier fuel index field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="7d05d-151">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7d05d-151">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="7d05d-152">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7d05d-152">Click Save.</span></span>

