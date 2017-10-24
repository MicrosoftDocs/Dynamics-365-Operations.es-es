---
title: "Definición de descuentos específicos de un canal"
description: "Los minoristas establecen a menudo distintos descuentos en diferentes canales. Este tema revisa los conceptos que necesita conocer para crear un descuento para un canal específico."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailAffiliationPriceGroup, RetailCatalogPriceGroup, RetailChannelPriceGroup, RetailDiscountPriceGroup, RetailDiscountPricingWorkspace, RetailPeriodicDiscount, RetailStoreItemPriceList, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 16401
ms.assetid: d807fd51-86aa-47a0-8e00-6c5ddd21ff6b
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a0286ab72d7fa6b40228dfdcabde00bee9995d74
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="define-channel-specific-discounts"></a><span data-ttu-id="e04ae-104">Definición de descuentos específicos de un canal</span><span class="sxs-lookup"><span data-stu-id="e04ae-104">Define channel-specific discounts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="e04ae-105">Los minoristas establecen a menudo distintos descuentos en diferentes canales.</span><span class="sxs-lookup"><span data-stu-id="e04ae-105">Retailers often set different discounts in different channels.</span></span> <span data-ttu-id="e04ae-106">Este tema revisa los conceptos que necesita conocer para crear un descuento para un canal específico.</span><span class="sxs-lookup"><span data-stu-id="e04ae-106">This topic reviews the concepts you need to know to create a discount for a specific channel.</span></span> 

<a name="channel-specific-discounts"></a><span data-ttu-id="e04ae-107">Descuentos específicos de un canal</span><span class="sxs-lookup"><span data-stu-id="e04ae-107">Channel-specific discounts</span></span>
--------------------------

<span data-ttu-id="e04ae-108">Los minoristas ofrecen a menudo distintos descuentos en diferentes canales.</span><span class="sxs-lookup"><span data-stu-id="e04ae-108">Retailers often offer different discounts in different channels.</span></span> <span data-ttu-id="e04ae-109">Esto se puede realizar para responder a condiciones empresariales locales o para afrontar a la competencia.</span><span class="sxs-lookup"><span data-stu-id="e04ae-109">This is may be done to address local market conditions or to deal with competing retailers.</span></span>

<span data-ttu-id="e04ae-110">Microsoft Dynamics 365 for Retail usa grupos de precios para definir descuentos específicos según canal.</span><span class="sxs-lookup"><span data-stu-id="e04ae-110">Microsoft Dynamics 365 for Retail uses price groups to define channel-specific discounts.</span></span> <span data-ttu-id="e04ae-111">Los grupos de precios se pueden asignar a una o más de las entidades siguientes: canales, catálogos, afiliaciones y programas de fidelidad.</span><span class="sxs-lookup"><span data-stu-id="e04ae-111">Price groups can be assigned to one or more of the following entities: channels, catalogs, affiliations, and loyalty programs.</span></span> <span data-ttu-id="e04ae-112">Este artículo describe los canales, pero los mismos conceptos se aplican a los descuentos de catálogo, descuentos de afiliaciones y los descuentos por fidelidad.</span><span class="sxs-lookup"><span data-stu-id="e04ae-112">This article discusses channels, but the same concepts apply to catalog discounts, affiliations discounts, and loyalty discounts.</span></span>

## <a name="price-groups"></a><span data-ttu-id="e04ae-113">Grupos de precio</span><span class="sxs-lookup"><span data-stu-id="e04ae-113">Price groups</span></span>

<span data-ttu-id="e04ae-114">[![Grupos de precio](./media/price-groups-1024x608.png)](./media/price-groups.png)</span><span class="sxs-lookup"><span data-stu-id="e04ae-114">[![Price groups](./media/price-groups-1024x608.png)](./media/price-groups.png)</span></span>

<span data-ttu-id="e04ae-115">En el diagrama anterior se muestra la relación entre las entidades que pueden estar incluidas en una transacción (canal, catálogo, afiliación, cliente o tarjeta de fidelización) y los distintos tipos de descuento que pueden configurarse.</span><span class="sxs-lookup"><span data-stu-id="e04ae-115">The diagram above illustrates the relationship between entities that may be on a transaction (channel, catalog, affiliation, customer, loyalty card) and the various discount types that can be configured.</span></span> <span data-ttu-id="e04ae-116">Todas las transacciones se producen en un canal, por lo que se garantiza la presencia del canal en una transacción.</span><span class="sxs-lookup"><span data-stu-id="e04ae-116">All transactions occur in a channel, so the channel is guaranteed to be present on a transaction.</span></span> <span data-ttu-id="e04ae-117">Las entidades restantes son opcionales.</span><span class="sxs-lookup"><span data-stu-id="e04ae-117">The remaining entities are optional.</span></span> <span data-ttu-id="e04ae-118">En cada página de datos maestros hay un vínculo a una página de grupos de precios relacionada donde se pueden ver y agregar grupos de precios según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="e04ae-118">On each master data pages there is a link to a related price groups page where you can view and add price groups as needed.</span></span> <span data-ttu-id="e04ae-119">El grupo de precios se usa para relacionar cuatro tipos diferentes de entidades a los descuentos, los ajustes de precios y los acuerdos comerciales.</span><span class="sxs-lookup"><span data-stu-id="e04ae-119">A price group is used to relate four different types of entities to discounts, price adjustments, and trade agreements.</span></span> <span data-ttu-id="e04ae-120">Se recomienda planear una estrategia para nombrar a los grupos de precios con objeto de tenerlos organizados.</span><span class="sxs-lookup"><span data-stu-id="e04ae-120">We recommend that you plan a strategy for how you will name your price groups to keep them organized.</span></span> <span data-ttu-id="e04ae-121">Una opción sería usar una letra o un prefijo o un sufijo numérico para distinguir entre los diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="e04ae-121">One option would be to use a letter or number prefix or suffix to distinguish between the different types.</span></span> <span data-ttu-id="e04ae-122">Por ejemplo, 1-xxxxx para grupos de precios de canal y 2-xxxxx para grupos de precios de catálogo.</span><span class="sxs-lookup"><span data-stu-id="e04ae-122">For example, 1-xxxxx for channel price groups and 2-xxxxx for catalog price groups.</span></span> <span data-ttu-id="e04ae-123">Existen cuatro páginas de consulta que se centran en cada una de las entidades de venta al por menor que pueden tener descuentos asociados.</span><span class="sxs-lookup"><span data-stu-id="e04ae-123">There are four inquiry pages that focus on each of the retail entities that can have discounts associated to them.</span></span>

-   <span data-ttu-id="e04ae-124">**Grupos de precios de canal comercial**: esta página muestra una lista de canales y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="e04ae-124">**Retail channel price groups** - This page shows a list of channels and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="e04ae-125">**Grupos de precios de catálogo**: esta página muestra una lista de catálogos y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="e04ae-125">**Catalog price groups** - This page shows a list of catalogs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="e04ae-126">**Grupos de precios de fidelización**: esta página muestra una lista de programas de fidelización y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="e04ae-126">**Loyalty price groups** - This page shows a list of loyalty programs and discounts linked together for each price group.</span></span>
-   <span data-ttu-id="e04ae-127">**Grupos de precios de afiliación**: esta página muestra una lista de afiliaciones y descuentos vinculados conjuntamente para cada grupo de precios.</span><span class="sxs-lookup"><span data-stu-id="e04ae-127">**Affiliation price groups** - This page shows a list of affiliations and discounts linked together for each price group.</span></span>

## <a name="example-channel-discount-set-up"></a><span data-ttu-id="e04ae-128">Ejemplo de configuración de descuento por canal</span><span class="sxs-lookup"><span data-stu-id="e04ae-128">Example channel discount set up</span></span>
<span data-ttu-id="e04ae-129">En el ejemplo siguiente se muestran las tareas implicadas en la configuración de un descuento por canal.</span><span class="sxs-lookup"><span data-stu-id="e04ae-129">The following example illustrates the tasks involved in setting up a channel discount.</span></span>

1.  <span data-ttu-id="e04ae-130">Para este ejemplo puede tener un canal llamado **Houston** y va a crear un nuevo descuento llamado **Vuelta al cole**.</span><span class="sxs-lookup"><span data-stu-id="e04ae-130">For this example, you have a channel called **Houston**, and you're going to create a new discount called **Back-to-School.**</span></span>
2.  <span data-ttu-id="e04ae-131">Dado que la estrategia de precios y descuentos incluye la posibilidad de descuentos por canal, siempre creará un grupo de precios específico para un canal al crear un canal.</span><span class="sxs-lookup"><span data-stu-id="e04ae-131">Because the pricing and discount strategy includes the possibility of channel discounts, you always create a channel-specific price group when you create a channel.</span></span>
3.  <span data-ttu-id="e04ae-132">Tiene el grupo de precios **Houston-PG** asignado al canal **Houston**.</span><span class="sxs-lookup"><span data-stu-id="e04ae-132">You have the price group **Houston-PG** and it is assigned to the **Houston** channel.</span></span>
4.  <span data-ttu-id="e04ae-133">Después de crear el nuevo descuento **Vuelta al cole**, debe hacer clic en **Grupos de precios**, en la parte superior de la página **Descuento**.</span><span class="sxs-lookup"><span data-stu-id="e04ae-133">After you create the new **Back-to-School** discount, you need to click **Price groups** on the top of the **Discount** page.</span></span> <span data-ttu-id="e04ae-134">Se abre la página **Grupos de precios de descuento**.</span><span class="sxs-lookup"><span data-stu-id="e04ae-134">The **Discount price groups** page will open.</span></span> <span data-ttu-id="e04ae-135">A continuación, haga clic en **Nuevo** y seleccione el grupo de precios **Houston-PG**.</span><span class="sxs-lookup"><span data-stu-id="e04ae-135">Next, click **New** and select the **Houston-PG** price group.</span></span>
5.  <span data-ttu-id="e04ae-136">Ahora puede habilitar el descuento y transferirlo al canal.</span><span class="sxs-lookup"><span data-stu-id="e04ae-136">Now you can enable the discount and push it to the channel.</span></span>

 

<a name="see-also"></a><span data-ttu-id="e04ae-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e04ae-137">See also</span></span>
--------

[<span data-ttu-id="e04ae-138">Ajustes de precios y descuentos</span><span class="sxs-lookup"><span data-stu-id="e04ae-138">Price adjustments and discounts</span></span>](price-adjustments-discounts.md)




