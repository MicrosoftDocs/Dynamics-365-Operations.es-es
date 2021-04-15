---
title: La tienda minorista no aparece en la lista de tiendas desde donde recoger
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando una tienda minorista no aparece en la lista de tiendas donde se pueden recoger los artículos.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9974b3e10bbdcd2e8a8723a3be4b70401bb9e546
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801612"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a><span data-ttu-id="cb0b1-103">La tienda minorista no aparece en la lista de tiendas desde donde recoger</span><span class="sxs-lookup"><span data-stu-id="cb0b1-103">Retail store doesn't appear in the list of stores to pick up from</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cb0b1-104">Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando una tienda minorista no aparece en la lista de tiendas donde se pueden recoger los artículos.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-104">This topic provides troubleshooting guidance that can help when a retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="description"></a><span data-ttu-id="cb0b1-105">Descripción</span><span class="sxs-lookup"><span data-stu-id="cb0b1-105">Description</span></span>

<span data-ttu-id="cb0b1-106">Una tienda minorista no aparece en la lista de tiendas donde se pueden recoger artículos.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-106">A retail store doesn't appear in the list of stores where items can be picked up.</span></span>

## <a name="resolution"></a><span data-ttu-id="cb0b1-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="cb0b1-107">Resolution</span></span>

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a><span data-ttu-id="cb0b1-108">Configure la longitud y latitud de la dirección de la tienda en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="cb0b1-108">Configure the longitude and latitude for the store address in Commerce headquarters</span></span>

<span data-ttu-id="cb0b1-109">Para configurar la longitud y latitud de la dirección de la tienda en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-109">To configure the longitude and latitude for the store address in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="cb0b1-110">Vaya a **Retail y Commerce \> Canales \> Tiendas \> Todas las tiendas**.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-110">Go to **Retail and Commerce \> Channels \> Stores \> All stores**.</span></span>
1. <span data-ttu-id="cb0b1-111">Busque la tienda que desea que aparezca entre las opciones de recogida en el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-111">Find the store that you want to appear among the pickup options on the e-commerce site.</span></span> <span data-ttu-id="cb0b1-112">Tome nota de su valor de **Número de unidad operativa**.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-112">Make a note of its **Operating unit number** value.</span></span>
1. <span data-ttu-id="cb0b1-113">Vaya a **Administración de la organización \> Organizaciones \> Unidades operativas**.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-113">Go to **Organization administration \> Organizations \> Operating units**.</span></span>
1. <span data-ttu-id="cb0b1-114">Busque el número de unidad operativa que anotó anteriormente y luego seleccione la unidad operativa en los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-114">Search for the operating unit number that you noted earlier, and then select the operating unit in the search results.</span></span>
1. <span data-ttu-id="cb0b1-115">En la ficha desplegable **Direcciones**, seleccione **Más opciones** y luego seleccione **Avanzado**.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-115">On the **Addresses** FastTab, select **More options**, and then select **Advanced**.</span></span>
1. <span data-ttu-id="cb0b1-116">En la ficha desplegable **General**, asegúrese de que los campos **Longitud** y **Latitud** están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-116">On the **General** FastTab, make sure that the **Longitude** and **Latitude** fields are correctly set.</span></span> <span data-ttu-id="cb0b1-117">Como parte de este paso, asegúrese de que los valores estén especificados correctamente como números positivos o negativos.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-117">As part of this step, make sure that the values are correctly specified as positive or negative numbers.</span></span>

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a><span data-ttu-id="cb0b1-118">Configurar grupos de cumplimentación en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="cb0b1-118">Configure fulfillment groups in Commerce headquarters</span></span>

<span data-ttu-id="cb0b1-119">Para configurar grupos de cumplimentación en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-119">To configure fulfillment groups in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="cb0b1-120">Vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-120">Go to **Retail and Commerce \> Channels \> Online stores**.</span></span>
1. <span data-ttu-id="cb0b1-121">Seleccione la tienda en línea a configurar.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-121">Select the online store to configure.</span></span>
1. <span data-ttu-id="cb0b1-122">En el panel de acciones, seleccione **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimentación**.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-122">On the Action Pane, select **Set up**, and then select **Fulfillment group assignment**.</span></span>
1. <span data-ttu-id="cb0b1-123">En la página **Asignación de grupo de cumplimentación**, seleccione el grupo de cumplimentación para la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-123">On the **Fulfillment group assignment** page, select the fulfillment group for the online store.</span></span>
1. <span data-ttu-id="cb0b1-124">En **Configuración**, asegúrese de que la tienda minorista esté configurada correctamente para el grupo de cumplimentación.</span><span class="sxs-lookup"><span data-stu-id="cb0b1-124">Under **Setup**, make sure that the retail store is correctly configured for the fulfillment group.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb0b1-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="cb0b1-125">Additional resources</span></span> 

[<span data-ttu-id="cb0b1-126">Crear una unidad operativa</span><span class="sxs-lookup"><span data-stu-id="cb0b1-126">Create an operating unit</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[<span data-ttu-id="cb0b1-127">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="cb0b1-127">Set up an online channel</span></span>](../channel-setup-online.md)
