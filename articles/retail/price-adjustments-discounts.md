---
title: Ajustes de precios y descuentos
description: "Este artículo proporciona información acerca de los ajustes de precios y descuentos en Microsoft Dynamics 365 for Retail."
author: scott-tucker
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters, RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15891
ms.assetid: bab5adf3-ddf0-4c22-a2eb-b4d25b88de99
ms.search.region: global
ms.search.industry: Retail
ms.author: scotttuc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 04fd3b3df2637f897d4c25681d00d3700517b070
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="7df1b-103">Ajustes de precios y descuentos</span><span class="sxs-lookup"><span data-stu-id="7df1b-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7df1b-104">Este artículo proporciona información acerca de los ajustes de precios y descuentos en Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="7df1b-104">This article provides information about price adjustments and discounts in Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="7df1b-105">En Dynamics 365 for Retail, puede realizar ajustes de precios a los productos y también puede configurar los descuentos que se aplican a un artículo de línea o una transacción en el punto de venta (PDV), en un pedido de ventas del centro de llamadas o en un pedido en línea.</span><span class="sxs-lookup"><span data-stu-id="7df1b-105">In Dynamics 365 for Retail, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="7df1b-106">Tanto los ajustes de precios como los descuentos se pueden vincular a grupos de precios.</span><span class="sxs-lookup"><span data-stu-id="7df1b-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="7df1b-107">Para los ajustes de precios y descuentos, puede especificar una sola fecha inicial y la fecha final o un período que se repite, un código de descuento y algunos atributos adicionales.</span><span class="sxs-lookup"><span data-stu-id="7df1b-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> <span data-ttu-id="7df1b-108">Los ajustes de precios y los descuentos se pueden aplicar a productos, variantes o categorías.</span><span class="sxs-lookup"><span data-stu-id="7df1b-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="7df1b-109">Si se aplica más de un descuento a un producto, un cliente puede recibir uno de los descuentos o un descuento combinado, en función de la configuración del descuento.</span><span class="sxs-lookup"><span data-stu-id="7df1b-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="7df1b-110">Dynamics 365 for Retail aplica automáticamente el descuento o la combinación de descuentos que proporcionan el mejor precio al cliente.</span><span class="sxs-lookup"><span data-stu-id="7df1b-110">Dynamics 365 for Retail automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="7df1b-111">Cuando configure un ajuste de precio o un descuento, asegúrese de confirmar que los grupos de precios se asignan a los canales, catálogos, afiliaciones o programas de fidelidad correctos a los que desea que el descuento se aplique.</span><span class="sxs-lookup"><span data-stu-id="7df1b-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="7df1b-112">Además, si desea generar automáticamente el id. de descuento, puede configurar secuencias numéricas en la página **Parámetros de ventas al por menor** antes de definir un nuevo descuento o ajuste de precios.</span><span class="sxs-lookup"><span data-stu-id="7df1b-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Retail parameters** page before you define a new price adjustment or discount.</span></span> <span data-ttu-id="7df1b-113">**Nota**: puede eliminar un ajuste de precios o un descuento.</span><span class="sxs-lookup"><span data-stu-id="7df1b-113">**Note:** You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="7df1b-114">Sin embargo, se perderá la información estadística.</span><span class="sxs-lookup"><span data-stu-id="7df1b-114">However, statistical information will be lost.</span></span>

### <a name="types-of-discounts"></a><span data-ttu-id="7df1b-115">Tipos de descuentos</span><span class="sxs-lookup"><span data-stu-id="7df1b-115">Types of discounts</span></span>

<span data-ttu-id="7df1b-116">Hay cuatro tipos de descuentos comerciales:</span><span class="sxs-lookup"><span data-stu-id="7df1b-116">There are four types of retail discounts:</span></span>

-   <span data-ttu-id="7df1b-117">**Descuento simple**: un único porcentaje o importe.</span><span class="sxs-lookup"><span data-stu-id="7df1b-117">**Simple discount** – A single percentage or amount.</span></span>
-   <span data-ttu-id="7df1b-118">**Descuento por cantidades**: un descuento que se aplica cuando se compran dos o más productos.</span><span class="sxs-lookup"><span data-stu-id="7df1b-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
-   <span data-ttu-id="7df1b-119">**Descuento combinado**: un descuento que se aplica cuando se compra una combinación concreta de productos.</span><span class="sxs-lookup"><span data-stu-id="7df1b-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
-   <span data-ttu-id="7df1b-120">**Descuento por umbral**: un descuento que se aplica cuando el total de la transacción es superior al importe especificado.</span><span class="sxs-lookup"><span data-stu-id="7df1b-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>

<span data-ttu-id="7df1b-121">Tanto los ajustes de precios como los descuentos se pueden asociar con los grupos de precios.</span><span class="sxs-lookup"><span data-stu-id="7df1b-121">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="7df1b-122">A continuación, los grupos de precios pueden asociarse con canales, catálogos, afiliaciones y programas de fidelidad.</span><span class="sxs-lookup"><span data-stu-id="7df1b-122">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>




