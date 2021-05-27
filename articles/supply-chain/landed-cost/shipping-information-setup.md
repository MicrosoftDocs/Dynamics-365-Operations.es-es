---
title: Configurar información de envío
description: Este tema describe cómo configurar la información de envío para el módulo de costo de entrega.
author: sherry-zheng
ms.date: 12/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMGoodsDescriptionTable, ITMVesselTable, ITMExporterTable, ITMCommodityCodeTable, ITMCustomsDescription
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-04
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 5093e42b0b5247c24c271ad50c80889516586d58
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020896"
---
# <a name="shipping-information-setup"></a><span data-ttu-id="29ca6-103">Configurar información de envío</span><span class="sxs-lookup"><span data-stu-id="29ca6-103">Shipping information setup</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="29ca6-104">Este tema describe cómo configurar la información de envío para el módulo de **costo de entrega**.</span><span class="sxs-lookup"><span data-stu-id="29ca6-104">This topic describes how to set up shipping information for the **Landed cost** module.</span></span>

## <a name="description-of-goods"></a><a name="description-of-goods"></a><span data-ttu-id="29ca6-105">Descripción de los bienes</span><span class="sxs-lookup"><span data-stu-id="29ca6-105">Description of goods</span></span>

<span data-ttu-id="29ca6-106">Las descripciones de bienes ayudan a identificar un viaje, contenedor de envío o folio de bienes y los bienes que contiene.</span><span class="sxs-lookup"><span data-stu-id="29ca6-106">Descriptions of goods help identify a voyage, shipping container, or folio of goods, and the goods in it.</span></span> <span data-ttu-id="29ca6-107">Puede seleccionar una descripción de las mercancías en el encabezado del contenedor de envío o en el encabezado del folio.</span><span class="sxs-lookup"><span data-stu-id="29ca6-107">You can select a description of goods on the shipping container header or the folio header.</span></span>

<span data-ttu-id="29ca6-108">Para trabajar con descripciones de productos, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Descripción de bienes**.</span><span class="sxs-lookup"><span data-stu-id="29ca6-108">To work with descriptions of goods, go to **Landed cost \> Shipping information setup \> Description of goods**.</span></span> <span data-ttu-id="29ca6-109">Allí, puede ver, abrir, crear y eliminar registros para las descripciones de los productos.</span><span class="sxs-lookup"><span data-stu-id="29ca6-109">There, you can view, open, create, and delete records for descriptions of goods.</span></span> <span data-ttu-id="29ca6-110">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="29ca6-110">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="29ca6-111">Campo</span><span class="sxs-lookup"><span data-stu-id="29ca6-111">Field</span></span> | <span data-ttu-id="29ca6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-112">Description</span></span> |
|---|---|
| <span data-ttu-id="29ca6-113">Descripción de los bienes</span><span class="sxs-lookup"><span data-stu-id="29ca6-113">Description of goods</span></span> | <span data-ttu-id="29ca6-114">Ingrese un nombre / número de identificación único para el tipo de bienes que utilizarán esta descripción.</span><span class="sxs-lookup"><span data-stu-id="29ca6-114">Enter a unique identification name/number for the type of goods that will use this description.</span></span> |
| <span data-ttu-id="29ca6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-115">Description</span></span> | <span data-ttu-id="29ca6-116">Ingrese una descripción del tipo de bienes en esta categoría.</span><span class="sxs-lookup"><span data-stu-id="29ca6-116">Enter a description of the type of goods in this category.</span></span> |

## <a name="vessels"></a><a name="vessels"></a><span data-ttu-id="29ca6-117">Embarcaciones</span><span class="sxs-lookup"><span data-stu-id="29ca6-117">Vessels</span></span>

<span data-ttu-id="29ca6-118">Un barco es el nombre único de un barco o nave que utiliza una empresa o agencia de transporte.</span><span class="sxs-lookup"><span data-stu-id="29ca6-118">A vessel is the unique name of a ship or vessel that a shipping company or agency uses.</span></span> <span data-ttu-id="29ca6-119">Cuando crea un viaje, siempre debe seleccionar o ingresar un barco para él.</span><span class="sxs-lookup"><span data-stu-id="29ca6-119">When you create a voyage, you must always either select or enter a vessel for it.</span></span> <span data-ttu-id="29ca6-120">Si utiliza con frecuencia las mismas naves, puede agilizar y facilitar la creación de un nuevo viaje creando un registro de nave para cada una de ellas, lo que permite a los usuarios seleccionar la nave de una lista en lugar de ingresar el nombre o el número manualmente cada vez.</span><span class="sxs-lookup"><span data-stu-id="29ca6-120">If you often use the same vessels, then you can make it faster and easier to create a new voyage by creating a vessel record for each of them, thereby allowing users to select the vessel from a list rather then enter the name or number manually each time.</span></span>

<span data-ttu-id="29ca6-121">Para trabajar con naves, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Naves**.</span><span class="sxs-lookup"><span data-stu-id="29ca6-121">To work with vessels, go to **Landed cost \> Shipping information setup \> Vessels**.</span></span> <span data-ttu-id="29ca6-122">Allí, puede ver, abrir, crear y eliminar registros para naves.</span><span class="sxs-lookup"><span data-stu-id="29ca6-122">There, you can view, open, create, and delete records for vessels.</span></span> <span data-ttu-id="29ca6-123">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="29ca6-123">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="29ca6-124">Campo</span><span class="sxs-lookup"><span data-stu-id="29ca6-124">Field</span></span> | <span data-ttu-id="29ca6-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-125">Description</span></span> |
|---|---|
| <span data-ttu-id="29ca6-126">Embarcación</span><span class="sxs-lookup"><span data-stu-id="29ca6-126">Vessel</span></span> | <span data-ttu-id="29ca6-127">Ingrese un nombre / número de identificación único para el barco que se utilizará para transportar mercancías en un viaje.</span><span class="sxs-lookup"><span data-stu-id="29ca6-127">Enter a unique identification name/number for the ship that will be used to transport goods on a voyage.</span></span> |
| <span data-ttu-id="29ca6-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-128">Description</span></span> | <span data-ttu-id="29ca6-129">Especifique una descripción de la nave.</span><span class="sxs-lookup"><span data-stu-id="29ca6-129">Enter a description of the vessel.</span></span> <span data-ttu-id="29ca6-130">Por lo general, esta descripción identifica el nombre del barco y la compañía / agente de envío.</span><span class="sxs-lookup"><span data-stu-id="29ca6-130">Typically, this description identifies the name of the ship and the shipping company/agent.</span></span> |
| <span data-ttu-id="29ca6-131">Modo de entrega</span><span class="sxs-lookup"><span data-stu-id="29ca6-131">Mode of delivery</span></span> | <span data-ttu-id="29ca6-132">Seleccione el modo de entrega que utiliza la nave (como _Aéreo_, _Marítimo_ o _Ferroviario_).</span><span class="sxs-lookup"><span data-stu-id="29ca6-132">Select the mode of delivery that the vessel uses (such as _Air_, _Ocean_, or _Train_).</span></span> |

## <a name="exporters"></a><span data-ttu-id="29ca6-133">Exportadores</span><span class="sxs-lookup"><span data-stu-id="29ca6-133">Exporters</span></span>

<span data-ttu-id="29ca6-134">Cada registro de exportador identifica un proveedor o exportador que puede definirse como el proveedor de un viaje.</span><span class="sxs-lookup"><span data-stu-id="29ca6-134">Each exporter record identifies a vendor or exporter that can be defined as the vendor for a voyage.</span></span> <span data-ttu-id="29ca6-135">El exportador puede asociarse con un viaje y utilizarse para informar.</span><span class="sxs-lookup"><span data-stu-id="29ca6-135">The exporter can be associated with a voyage and used for reporting.</span></span>

<span data-ttu-id="29ca6-136">Para trabajar con exportadores, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Exportadores**.</span><span class="sxs-lookup"><span data-stu-id="29ca6-136">To work with exporters, go to **Landed cost \> Shipping information setup \> Exporters**.</span></span> <span data-ttu-id="29ca6-137">Allí, puede ver, abrir, crear y eliminar registros para exportadores.</span><span class="sxs-lookup"><span data-stu-id="29ca6-137">There, you can view, open, create, and delete records for exporters.</span></span> <span data-ttu-id="29ca6-138">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="29ca6-138">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="29ca6-139">Campo</span><span class="sxs-lookup"><span data-stu-id="29ca6-139">Field</span></span> | <span data-ttu-id="29ca6-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-140">Description</span></span> |
|---|---|
| <span data-ttu-id="29ca6-141">Exportador</span><span class="sxs-lookup"><span data-stu-id="29ca6-141">Exporter</span></span> | <span data-ttu-id="29ca6-142">Ingrese un nombre / número de identificación único para el exportador de bienes que se transportan en un viaje.</span><span class="sxs-lookup"><span data-stu-id="29ca6-142">Enter a unique identification name/number for the exporter of goods that are transported on a voyage.</span></span> |
| <span data-ttu-id="29ca6-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-143">Description</span></span> | <span data-ttu-id="29ca6-144">Especifique una descripción del exportador.</span><span class="sxs-lookup"><span data-stu-id="29ca6-144">Enter a description of the exporter.</span></span> <span data-ttu-id="29ca6-145">Por lo general, esta descripción identifica el nombre completo de la compañía/agente de envío.</span><span class="sxs-lookup"><span data-stu-id="29ca6-145">Typically, this description identifies the full name of the shipping company/agent.</span></span> |

## <a name="commodity-codes"></a><span data-ttu-id="29ca6-146">Códigos de mercancías</span><span class="sxs-lookup"><span data-stu-id="29ca6-146">Commodity codes</span></span>

<span data-ttu-id="29ca6-147">Utiliza códigos de productos básicos para ayudar con la identificación de aduanas y el cálculo de las tasas arancelarias para las mercancías en un viaje.</span><span class="sxs-lookup"><span data-stu-id="29ca6-147">You use commodity codes to help with customs identification and the calculation of duty rates for goods on a voyage.</span></span> <span data-ttu-id="29ca6-148">Puede seleccionar códigos de productos en la página **Productos lanzados**.</span><span class="sxs-lookup"><span data-stu-id="29ca6-148">You can select commodity codes on the **Released products** page.</span></span>

<span data-ttu-id="29ca6-149">Para trabajar con códigos de mercacnía, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Códigos de mercancía**.</span><span class="sxs-lookup"><span data-stu-id="29ca6-149">To work with commodity codes, go to **Landed cost \> Shipping information setup \> Commodity codes**.</span></span> <span data-ttu-id="29ca6-150">Allí, puede ver, abrir, crear y eliminar registros para códigos de mercacnía.</span><span class="sxs-lookup"><span data-stu-id="29ca6-150">There, you can view, open, create, and delete records for commodity codes.</span></span> <span data-ttu-id="29ca6-151">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="29ca6-151">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="29ca6-152">Campo</span><span class="sxs-lookup"><span data-stu-id="29ca6-152">Field</span></span> | <span data-ttu-id="29ca6-153">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-153">Description</span></span> |
|---|---|
| <span data-ttu-id="29ca6-154">Código de mercancía</span><span class="sxs-lookup"><span data-stu-id="29ca6-154">Commodity code</span></span> | <span data-ttu-id="29ca6-155">Ingrese un código único para este tipo de producto.</span><span class="sxs-lookup"><span data-stu-id="29ca6-155">Enter a unique code for this type of commodity.</span></span> |
| <span data-ttu-id="29ca6-156">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-156">Description</span></span> | <span data-ttu-id="29ca6-157">Especifique una descripción del código de tipo de mercancía.</span><span class="sxs-lookup"><span data-stu-id="29ca6-157">Enter a description of the commodity type.</span></span> |

## <a name="customs-description"></a><span data-ttu-id="29ca6-158">Descripción de aduanas</span><span class="sxs-lookup"><span data-stu-id="29ca6-158">Customs description</span></span>

<span data-ttu-id="29ca6-159">Las descripciones aduaneras ayudan a identificar las mercancías con fines aduaneros.</span><span class="sxs-lookup"><span data-stu-id="29ca6-159">Customs descriptions help identify goods for customs purposes.</span></span> <span data-ttu-id="29ca6-160">Puede seleccionar una descripción de aduana en la página **Productos lanzados** o en las líneas de la orden de compra.</span><span class="sxs-lookup"><span data-stu-id="29ca6-160">You can select a customs description on the **Released products** page or on purchase order lines.</span></span>

<span data-ttu-id="29ca6-161">Para trabajar con descripciones de aduanas, vaya a **Coste de aterrizaje \> Configuración de la información de envío \> Descripción de aduanas**.</span><span class="sxs-lookup"><span data-stu-id="29ca6-161">To work with customs descriptions, go to **Landed cost \> Shipping information setup \> Customs description**.</span></span> <span data-ttu-id="29ca6-162">Allí, puede ver, abrir, crear y eliminar registros para las descripciones de aduanas.</span><span class="sxs-lookup"><span data-stu-id="29ca6-162">There, you can view, open, create, and delete records for custom descriptions.</span></span> <span data-ttu-id="29ca6-163">En la tabla siguiente se describen los campos disponibles para cada registro.</span><span class="sxs-lookup"><span data-stu-id="29ca6-163">The following table describes the fields that are available for each record.</span></span>

| <span data-ttu-id="29ca6-164">Campo</span><span class="sxs-lookup"><span data-stu-id="29ca6-164">Field</span></span> | <span data-ttu-id="29ca6-165">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-165">Description</span></span> |
|---|---|
| <span data-ttu-id="29ca6-166">Descripción de aduanas</span><span class="sxs-lookup"><span data-stu-id="29ca6-166">Customs description</span></span> | <span data-ttu-id="29ca6-167">Ingrese un código único para este tipo de clasificación de aduanas.</span><span class="sxs-lookup"><span data-stu-id="29ca6-167">Enter a unique code for this type of customs classification.</span></span> <span data-ttu-id="29ca6-168">A menudo, este código será la descripción oficial proporcionada por una autoridad aduanera para la descripción y el valor cualitativo de las mercancías.</span><span class="sxs-lookup"><span data-stu-id="29ca6-168">Often, this code will be the official description that is provided by a customs authority for the description and qualitative value of the goods.</span></span> |
| <span data-ttu-id="29ca6-169">Descripción</span><span class="sxs-lookup"><span data-stu-id="29ca6-169">Description</span></span> | <span data-ttu-id="29ca6-170">Especifique una descripción del grupo de clasificación de aduanas.</span><span class="sxs-lookup"><span data-stu-id="29ca6-170">Enter a description of the customs classification.</span></span> |
