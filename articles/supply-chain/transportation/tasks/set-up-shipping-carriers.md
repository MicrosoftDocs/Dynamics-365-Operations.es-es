---
title: Configuración de transportistas de envío
description: En este tema se muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío.
author: ShylaThompson
manager: tfehr
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSShippingCarrierCustomerAccount,TMSCarrier
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7a71ea3983018b136d4fe3b22eadc0c332d2a698
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437223"
---
# <a name="set-up-shipping-carriers"></a><span data-ttu-id="3449f-103">Configuración de transportistas de envío</span><span class="sxs-lookup"><span data-stu-id="3449f-103">Set up shipping carriers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3449f-104">En este tema se muestra cómo configurar un transportista y definir detalles como el servicio, el modo de envío, la forma de pago de transporte, las restricciones de transporte y las tarifas de envío.</span><span class="sxs-lookup"><span data-stu-id="3449f-104">This topic shows how to set up a shipping carrier and define details such as service, shipment mode, transportation tender, transportation constraints, and shipping rate.</span></span> <span data-ttu-id="3449f-105">El coordinador de transporte puede asignar a continuación un transportista a una carga de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="3449f-105">A transportation coordinator can then assign a shipping carrier to an inbound or outbound load.</span></span>


## <a name="create-a-new-shipping-carrier"></a><span data-ttu-id="3449f-106">Creación de un nuevo transportista de envío</span><span class="sxs-lookup"><span data-stu-id="3449f-106">Create a new shipping carrier</span></span>
1. <span data-ttu-id="3449f-107">Vaya a **Panel de navegación > Módulos > Administración de transporte > Configuración > Transportistas > Transportistas de envío**.</span><span class="sxs-lookup"><span data-stu-id="3449f-107">Go to **Navigation pane > Modules > Transportation management > Setup > Carriers > Shipping carriers**.</span></span>
2. <span data-ttu-id="3449f-108">En el panel Acciones, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3449f-108">Select **New** on the Action Pane.</span></span>
3. <span data-ttu-id="3449f-109">En el campo **Transportista de envío**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-109">In the **Shipping carrier** field, type a value.</span></span>
4. <span data-ttu-id="3449f-110">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-110">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3449f-111">En el campo **Modo**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-111">In the **Mode** field, select an option from the drop-down menu.</span></span>

## <a name="fill-in-the-general-information-for-the-shipping-carrier"></a><span data-ttu-id="3449f-112">Cumplimentación de la información general del transportista de envío</span><span class="sxs-lookup"><span data-stu-id="3449f-112">Fill in the general information for the shipping carrier</span></span>
1. <span data-ttu-id="3449f-113">Alterne la expansión de la sección **Visión general**.</span><span class="sxs-lookup"><span data-stu-id="3449f-113">Toggle the expansion of the **Overview** section.</span></span>
2. <span data-ttu-id="3449f-114">Marque o quite la marca de la casilla **Activar transportista de envío**.</span><span class="sxs-lookup"><span data-stu-id="3449f-114">Check or uncheck the **Activate shipping carrier** checkbox.</span></span>
3. <span data-ttu-id="3449f-115">En el campo **Cuenta del proveedor**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-115">In the **Vendor account** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="3449f-116">Seleccione la cuenta de proveedor a la que asignar el transportista.</span><span class="sxs-lookup"><span data-stu-id="3449f-116">Select the vendor account to assign the shipping carrier to.</span></span>  
4. <span data-ttu-id="3449f-117">En el campo **Tipo de forma de pago de transporte**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="3449f-117">In the **Transportation tender type** field, select an option.</span></span> <span data-ttu-id="3449f-118">Seleccione **Manual** para usar la página Forma de pago del transporte, o seleccione **EDI** para actualizar la forma de pago mediante EDI (Electronic Data Interchange).</span><span class="sxs-lookup"><span data-stu-id="3449f-118">Select **Manual** to use the Transportation Tender page, or select **EDI** to update the tender by using Electronic Data Interchange (EDI).</span></span>  
5. <span data-ttu-id="3449f-119">Marque o quite la marca de la casilla **Activar calificación de transportistas**.</span><span class="sxs-lookup"><span data-stu-id="3449f-119">Check or uncheck the **Activate carrier rating** checkbox.</span></span>

## <a name="create-the-necessary-services-for-the-shipping-carrier"></a><span data-ttu-id="3449f-120">Creación de los servicios necesarios para el transportista de envío</span><span class="sxs-lookup"><span data-stu-id="3449f-120">Create the necessary services for the shipping carrier</span></span>
1. <span data-ttu-id="3449f-121">Alterne la expansión de la sección **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="3449f-121">Toggle the expansion of the **Services** section.</span></span>
2. <span data-ttu-id="3449f-122">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3449f-122">Select **New**.</span></span>
3. <span data-ttu-id="3449f-123">En el campo **Servicio de transportista**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-123">In the **Carrier service** field, type a value.</span></span>
4. <span data-ttu-id="3449f-124">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-124">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3449f-125">En el campo **Método de transporte**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-125">In the **Transportation method** field, select an option from the drop-down menu.</span></span>

## <a name="set-up-the-address-for-the-carrier-optional"></a><span data-ttu-id="3449f-126">Configuración de la dirección del transportista (opcional)</span><span class="sxs-lookup"><span data-stu-id="3449f-126">Set up the address for the carrier (optional)</span></span>
1. <span data-ttu-id="3449f-127">Alterne la expansión de la sección **Direcciones**.</span><span class="sxs-lookup"><span data-stu-id="3449f-127">Toggle the expansion of the **Addresses** section.</span></span>
2. <span data-ttu-id="3449f-128">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3449f-128">Select **New**.</span></span>
3. <span data-ttu-id="3449f-129">En el campo **Nombre o descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-129">In the **Name or description** field, type a value.</span></span>
4. <span data-ttu-id="3449f-130">En el campo **País/región**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-130">In the **Country/region** field, select an option from the drop-down menu.</span></span>
5. <span data-ttu-id="3449f-131">En el campo **Código postal**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-131">In the **ZIP/postal code** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="3449f-132">En el campo **Calle**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-132">In the **Street** field, type a value.</span></span>
7. <span data-ttu-id="3449f-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3449f-133">Select **OK**.</span></span>

## <a name="set-up-the-rating-profile-for-the-shipping-carrier"></a><span data-ttu-id="3449f-134">Configuración del perfil de clasificación del transportista de envío</span><span class="sxs-lookup"><span data-stu-id="3449f-134">Set up the rating profile for the shipping carrier</span></span>
1. <span data-ttu-id="3449f-135">Alterne la expansión de la sección **Perfiles de clasificación**.</span><span class="sxs-lookup"><span data-stu-id="3449f-135">Toggle the expansion of the **Rating profiles** section.</span></span>
2. <span data-ttu-id="3449f-136">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="3449f-136">Select **New**.</span></span>
3. <span data-ttu-id="3449f-137">En el campo **Perfil de clasificación**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-137">In the **Rating profile** field, type a value.</span></span>
4. <span data-ttu-id="3449f-138">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3449f-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="3449f-139">En el campo **Sitio**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-139">In the **Site** field, select an option from the drop-down menu.</span></span>
6. <span data-ttu-id="3449f-140">En el campo **Almacén**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-140">In the **Warehouse** field, select an option from the drop-down menu.</span></span>
7. <span data-ttu-id="3449f-141">En el campo **Motor de tarifas**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-141">In the **Rate engine** field, select an option from the drop-down menu.</span></span> <span data-ttu-id="3449f-142">Seleccione el motor de tasas según el contrato que tenga con el transportista.</span><span class="sxs-lookup"><span data-stu-id="3449f-142">Select the Rate engine that is in accordance with the contract that you have with the carrier.</span></span>  
8. <span data-ttu-id="3449f-143">En el campo **Tasa maestra**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-143">In the **Rate master** field, select an option from the drop-down menu.</span></span>
9. <span data-ttu-id="3449f-144">En el campo **Motor de tiempo de tránsito**, seleccione una opción en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="3449f-144">In the **Transit time engine** field, select an option from the drop-down menu.</span></span>
10. <span data-ttu-id="3449f-145">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="3449f-145">Select **Save**.</span></span>

