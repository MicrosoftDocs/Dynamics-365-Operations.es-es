---
title: Definición de descuentos específicos de un canal
description: Los minoristas establecen a menudo distintos descuentos en diferentes canales. Este tema revisa los conceptos que necesita conocer para crear un descuento para un canal específico.
author: scott-tucker
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: c4003bd78e400994f3c164d2f7e8e3aa5ce93146
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802078"
---
# <a name="define-channel-specific-discounts"></a><span data-ttu-id="f988f-104">Definir descuentos específicos de un canal</span><span class="sxs-lookup"><span data-stu-id="f988f-104">Define channel-specific discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f988f-105">Este tema revisa los conceptos que necesita conocer para crear un descuento para un canal específico.</span><span class="sxs-lookup"><span data-stu-id="f988f-105">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span>

## <a name="channel-specific-discounts"></a><span data-ttu-id="f988f-106">Descuentos específicos de un canal</span><span class="sxs-lookup"><span data-stu-id="f988f-106">Channel-specific discounts</span></span>

<span data-ttu-id="f988f-107">Los minoristas ofrecen a menudo distintos descuentos en diferentes canales.</span><span class="sxs-lookup"><span data-stu-id="f988f-107">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="f988f-108">Esto se puede realizar para responder a condiciones empresariales locales o para afrontar a la competencia.</span><span class="sxs-lookup"><span data-stu-id="f988f-108">This may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="f988f-109">Commerce usa grupos de precios para definir descuentos específicos de canal.</span><span class="sxs-lookup"><span data-stu-id="f988f-109">Commerce uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="f988f-110">Los grupos de precios se pueden asignar a una o más de las entidades siguientes: canales, catálogos, afiliaciones y programas de fidelidad.</span><span class="sxs-lookup"><span data-stu-id="f988f-110">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="f988f-111">Este artículo describe los canales, pero los mismos conceptos se aplican a los descuentos de catálogo, descuentos de afiliaciones y los descuentos por fidelidad.</span><span class="sxs-lookup"><span data-stu-id="f988f-111">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="f988f-112">Grupos de precio</span><span class="sxs-lookup"><span data-stu-id="f988f-112">Price groups</span></span>

<span data-ttu-id="f988f-113">[![Grupos de precio](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="f988f-113">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="f988f-114">En el diagrama anterior se muestra la relación entre las entidades que pueden estar incluidas en una transacción (canal, catálogo, afiliación, cliente o tarjeta de fidelización) y los distintos tipos de descuento que pueden configurarse.</span><span class="sxs-lookup"><span data-stu-id="f988f-114">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="f988f-115">Todas las transacciones se producen en un canal, por lo que se garantiza la presencia del canal en una transacción.</span><span class="sxs-lookup"><span data-stu-id="f988f-115">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="f988f-116">Las entidades restantes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="f988f-116">The remaining entities are optional.</span></span> <span data-ttu-id="f988f-117">En cada página de datos maestros hay un vínculo a una página de grupos de precios relacionada donde se pueden ver y agregar grupos de precios según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f988f-117">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="f988f-118">El grupo de precios se usa para relacionar cuatro tipos diferentes de entidades a los descuentos, los ajustes de precios y los acuerdos comerciales.</span><span class="sxs-lookup"><span data-stu-id="f988f-118">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="f988f-119">Se recomienda planear una estrategia para nombrar a los grupos de precios con objeto de tenerlos organizados.</span><span class="sxs-lookup"><span data-stu-id="f988f-119">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="f988f-120">Una opción sería usar una letra o un prefijo o un sufijo numérico para distinguir entre los diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="f988f-120">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="f988f-121">Por ejemplo, 1-xxxxx para grupos de precios de canal y 2-xxxxx para grupos de precios de catálogo.</span><span class="sxs-lookup"><span data-stu-id="f988f-121">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="f988f-122">Existen cuatro páginas de consulta que se centran en cada una de las entidades de Commerce que pueden tener descuentos asociados.</span><span class="sxs-lookup"><span data-stu-id="f988f-122">There are four inquiry pages that focus on each of the commerce entities that can have discounts associated to them.</span></span>

- <span data-ttu-id="f988f-123">**Grupos de precios de canal**: esta página muestra una lista de canales y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="f988f-123">**Channel channel price groups** – This page shows a list of channels and discounts linked together for each price group.</span></span>
- <span data-ttu-id="f988f-124">**Grupos de precios de catálogo**: esta página muestra una lista de catálogos y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="f988f-124">**Catalog price groups** – This page shows a list of catalogs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="f988f-125">**Grupos de precios de fidelización**: esta página muestra una lista de programas de fidelización y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="f988f-125">**Loyalty price groups** – This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
- <span data-ttu-id="f988f-126">**Grupos de precios de afiliación**: esta página muestra una lista de afiliaciones y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="f988f-126">**Affiliation price groups** – This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="f988f-127">Ejemplo de configuración de descuento por canal</span><span class="sxs-lookup"><span data-stu-id="f988f-127">Example channel discount set up</span></span>

<span data-ttu-id="f988f-128">En el ejemplo siguiente se muestran las tareas implicadas en la configuración de un descuento por canal.</span><span class="sxs-lookup"><span data-stu-id="f988f-128">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1. <span data-ttu-id="f988f-129">Para este ejemplo puede tener un canal llamado **Houston** y va a crear un nuevo descuento llamado **Vuelta al cole**.</span><span class="sxs-lookup"><span data-stu-id="f988f-129">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School**.</span></span>
2. <span data-ttu-id="f988f-130">Dado que la estrategia de precios y descuentos incluye la posibilidad de descuentos por canal, siempre creará un grupo de precios específico para un canal al crear un canal.</span><span class="sxs-lookup"><span data-stu-id="f988f-130">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3. <span data-ttu-id="f988f-131">Tiene el grupo de precios **Houston-PG** asignado al canal **Houston**.</span><span class="sxs-lookup"><span data-stu-id="f988f-131">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4. <span data-ttu-id="f988f-132">Después de crear el nuevo descuento **Vuelta al cole**, debe hacer clic en **Grupos de precios**, en la parte superior de la página **Descuento**.</span><span class="sxs-lookup"><span data-stu-id="f988f-132">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="f988f-133">Se abre la página **Grupos de precios de descuento**.</span><span class="sxs-lookup"><span data-stu-id="f988f-133">The **Discount price groups** page will open.</span></span> <span data-ttu-id="f988f-134">A continuación, haga clic en **Nuevo** y seleccione el grupo de precios **Houston-PG**.</span><span class="sxs-lookup"><span data-stu-id="f988f-134">Next, click **New** and select the **Houston-PG** price group.</span></span>
5. <span data-ttu-id="f988f-135">Ahora puede habilitar el descuento y transferirlo al canal.</span><span class="sxs-lookup"><span data-stu-id="f988f-135">Now you can enable the discount and push it to the channel.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f988f-136">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f988f-136">Additional resources</span></span>

[<span data-ttu-id="f988f-137">Ajustes de precios y descuentos</span><span class="sxs-lookup"><span data-stu-id="f988f-137">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]