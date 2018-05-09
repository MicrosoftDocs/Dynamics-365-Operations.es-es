--- 
title: "Configuración de transportistas de envío"
description: "Este procedimiento muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: af23cc5e7018e5ea5aef2ad7cb70b4f4994488cc
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="d2e43-103">Configuración de transportistas de envío</span><span class="sxs-lookup"><span data-stu-id="d2e43-103">Set up shipping carriers</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2e43-104">Este procedimiento muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío.</span><span class="sxs-lookup"><span data-stu-id="d2e43-104">This procedure shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="d2e43-105">El coordinador de transporte puede asignar a continuación un transportista a una carga de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="d2e43-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="d2e43-106">Creación de un nuevo transportista de envío</span><span class="sxs-lookup"><span data-stu-id="d2e43-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="d2e43-107">Vaya a Administración de transporte > Configuración > Transportistas > Transportistas de envío.</span><span class="sxs-lookup"><span data-stu-id="d2e43-107">Go to Transportation management > Setup > Carriers > Shipping carriers.</span></span>
2. <span data-ttu-id="d2e43-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d2e43-108">Click New.</span></span>
3. <span data-ttu-id="d2e43-109">En el campo Transportista de envío, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-109">In the Shipping carrier field, type a value.</span></span>
4. <span data-ttu-id="d2e43-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="d2e43-111">En el campo Modo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-111">In the Mode field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="d2e43-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d2e43-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-113">In the list, click the link in the selected row.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="d2e43-114">Cumplimentación de la información general del transportista de envío</span><span class="sxs-lookup"><span data-stu-id="d2e43-114">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="d2e43-115">Expanda la sección Visión general.</span><span class="sxs-lookup"><span data-stu-id="d2e43-115">Toggle the expansion of the Overview section.</span></span>
2. <span data-ttu-id="d2e43-116">Marque o quite la marca de la casilla Activar transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="d2e43-116">Check or uncheck the Activate shipping carrier checkbox.</span></span>
3. <span data-ttu-id="d2e43-117">En el campo Proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-117">In the Vendor field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d2e43-118">Seleccione la cuenta de proveedor a la que asignar el transportista.</span><span class="sxs-lookup"><span data-stu-id="d2e43-118">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="d2e43-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-119">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="d2e43-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-120">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d2e43-121">En el campo Tipo de forma de pago de transporte, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d2e43-121">In the Transportation tender type field, select an option.</span></span>
    * <span data-ttu-id="d2e43-122">Seleccione Manual para usar la página del formulario Forma de pago del transporte, o seleccione EDI para actualizar la forma de pago mediante EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="d2e43-122">Select Manual to use the Transportation Tender page, or select EDI to update the tender by using Electronic Data Interchange (EDI).</span></span>  
7. <span data-ttu-id="d2e43-123">Marque o quite la marca de la casilla Activar calificación de transportistas.</span><span class="sxs-lookup"><span data-stu-id="d2e43-123">Check or uncheck the Activate carrier rating checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="d2e43-124">Creación de los servicios necesarios para el transportista de envío</span><span class="sxs-lookup"><span data-stu-id="d2e43-124">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="d2e43-125">Expanda la sección Servicios.</span><span class="sxs-lookup"><span data-stu-id="d2e43-125">Toggle the expansion of the Services section.</span></span>
2. <span data-ttu-id="d2e43-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d2e43-126">Click New.</span></span>
3. <span data-ttu-id="d2e43-127">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-127">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d2e43-128">En el campo Servicio de transportista, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-128">In the Carrier service field, type a value.</span></span>
5. <span data-ttu-id="d2e43-129">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-129">In the Name field, type a value.</span></span>
6. <span data-ttu-id="d2e43-130">En el campo Método de transporte, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-130">In the Transportation method field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d2e43-131">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-131">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="d2e43-132">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-132">In the list, click the link in the selected row.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="d2e43-133">Configuración de la dirección del transportista (opcional)</span><span class="sxs-lookup"><span data-stu-id="d2e43-133">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="d2e43-134">Alterne la expansión de la sección Direcciones.</span><span class="sxs-lookup"><span data-stu-id="d2e43-134">Toggle the expansion of the Addresses section.</span></span>
2. <span data-ttu-id="d2e43-135">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d2e43-135">Click New.</span></span>
3. <span data-ttu-id="d2e43-136">En el campo Nombre o descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-136">In the Name or description field, type a value.</span></span>
4. <span data-ttu-id="d2e43-137">En el campo País o región, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-137">In the Country/region field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="d2e43-138">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-138">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d2e43-139">En el campo Código postal, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-139">In the ZIP/postal code field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d2e43-140">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-140">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="d2e43-141">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-141">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d2e43-142">En el campo Calle, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-142">In the Street field, type a value.</span></span>
10. <span data-ttu-id="d2e43-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d2e43-143">Click OK.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="d2e43-144">Configuración del perfil de clasificación del transportista de envío</span><span class="sxs-lookup"><span data-stu-id="d2e43-144">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="d2e43-145">Expanda la sección Perfiles de clasificación.</span><span class="sxs-lookup"><span data-stu-id="d2e43-145">Toggle the expansion of the Rating profiles section.</span></span>
2. <span data-ttu-id="d2e43-146">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d2e43-146">Click New.</span></span>
3. <span data-ttu-id="d2e43-147">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-147">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d2e43-148">En el campo Perfil de clasificación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-148">In the Rating profile field, type a value.</span></span>
5. <span data-ttu-id="d2e43-149">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d2e43-149">In the Name field, type a value.</span></span>
6. <span data-ttu-id="d2e43-150">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-150">In the Site field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d2e43-151">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-151">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="d2e43-152">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-152">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="d2e43-153">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-153">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="d2e43-154">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-154">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="d2e43-155">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-155">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="d2e43-156">En el campo Motor de tasas, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-156">In the Rate engine field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="d2e43-157">Seleccione el motor de tasas según el contrato que tenga con el transportista.</span><span class="sxs-lookup"><span data-stu-id="d2e43-157">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
13. <span data-ttu-id="d2e43-158">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-158">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="d2e43-159">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-159">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="d2e43-160">En el campo Tasa maestra, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-160">In the Rate master field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="d2e43-161">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d2e43-161">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="d2e43-162">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-162">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="d2e43-163">En el campo Motor de tiempo de tránsito, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d2e43-163">In the Transit time engine field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="d2e43-164">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d2e43-164">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="d2e43-165">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d2e43-165">Click Save.</span></span>


