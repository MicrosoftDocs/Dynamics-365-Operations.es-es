---
title: Ajustes de precios y descuentos
description: Este artículo proporciona información sobre ajustes de precios y descuentos en Dynamics 365 Commerce.
author: scott-tucker
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 0c2adaa5cd935d5b593bfbb3215d3466fcafab7b
ms.sourcegitcommit: 1d74636bf9db5fb33e998322899504b709b4f89f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/19/2020
ms.locfileid: "4584324"
---
# <a name="price-adjustments-and-discounts"></a><span data-ttu-id="285e0-103">Ajustes de precios y descuentos</span><span class="sxs-lookup"><span data-stu-id="285e0-103">Price adjustments and discounts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="285e0-104">Este artículo proporciona información sobre ajustes de precios y descuentos en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="285e0-104">This article provides information about price adjustments and discounts in Dynamics 365 Commerce.</span></span>

<span data-ttu-id="285e0-105">En Commerce, puede realizar ajustes de precios en los productos y configurar los descuentos que se aplican a un artículo de línea o a una transacción en el punto de venta (PDV), en un pedido de ventas del centro de llamadas o en un pedido en línea.</span><span class="sxs-lookup"><span data-stu-id="285e0-105">In Commerce, you can make price adjustments to products, and can also set up discounts that are applied to a line item or a transaction at the point of sale (POS), in a call center sales order, or in an online order.</span></span> <span data-ttu-id="285e0-106">Tanto los ajustes de precios como los descuentos se pueden vincular a grupos de precios.</span><span class="sxs-lookup"><span data-stu-id="285e0-106">Both price adjustments and discounts can be linked to price groups.</span></span> <span data-ttu-id="285e0-107">Para los ajustes de precios y descuentos, puede especificar una sola fecha inicial y la fecha final o un período que se repite, un código de descuento y algunos atributos adicionales.</span><span class="sxs-lookup"><span data-stu-id="285e0-107">For both price adjustments and discounts, you can specify a single start date and end date or a reoccurring period, a discount code, and a few additional attributes.</span></span> 

<span data-ttu-id="285e0-108">Los ajustes de precios y los descuentos se pueden aplicar a productos, variantes o categorías.</span><span class="sxs-lookup"><span data-stu-id="285e0-108">Price adjustments and discounts can be applied to products, variants, or categories.</span></span> <span data-ttu-id="285e0-109">Si se aplica más de un descuento a un producto, un cliente puede recibir uno de los descuentos o un descuento combinado, en función de la configuración del descuento.</span><span class="sxs-lookup"><span data-stu-id="285e0-109">If more than one discount applies to a product, a customer might receive either one of the discounts or a combined discount, depending on the configuration of the discount.</span></span> <span data-ttu-id="285e0-110">Commerce aplica automáticamente el descuento o la combinación de descuentos que proporcionan el mejor precio al cliente.</span><span class="sxs-lookup"><span data-stu-id="285e0-110">Commerce automatically applies the discount or combination of discounts that gives the best price to the customer.</span></span> <span data-ttu-id="285e0-111">Cuando configure un ajuste de precio o un descuento, asegúrese de confirmar que los grupos de precios se asignan a los canales, catálogos, afiliaciones o programas de fidelidad correctos a los que desea que el descuento se aplique.</span><span class="sxs-lookup"><span data-stu-id="285e0-111">When you set up a price adjustment or a discount, be sure to confirm that price groups are assigned to the correct channels, catalogs, affiliations, or loyalty programs that you want the discount to apply to.</span></span> <span data-ttu-id="285e0-112">Además, si desea generar automáticamente el id. de descuento, puede configurar secuencias numéricas en la página **Parámetros de Commerce** antes de definir un nuevo descuento o ajuste de precios.</span><span class="sxs-lookup"><span data-stu-id="285e0-112">Additionally, if you want to automatically generate the discount ID, set up number sequences on the **Commerce parameters** page before you define a new price adjustment or discount.</span></span>

> [!NOTE]
> <span data-ttu-id="285e0-113">Puede eliminar un ajuste de precios o un descuento.</span><span class="sxs-lookup"><span data-stu-id="285e0-113">You can delete a price adjustment or a discount.</span></span> <span data-ttu-id="285e0-114">Sin embargo, se perderá la información estadística.</span><span class="sxs-lookup"><span data-stu-id="285e0-114">However, statistical information will be lost.</span></span>

## <a name="types-of-discounts"></a><span data-ttu-id="285e0-115">Tipos de descuentos</span><span class="sxs-lookup"><span data-stu-id="285e0-115">Types of discounts</span></span>

<span data-ttu-id="285e0-116">Hay muchos tipos de descuentos:</span><span class="sxs-lookup"><span data-stu-id="285e0-116">There are many types of discounts:</span></span>

- <span data-ttu-id="285e0-117">**Descuento simple**: un único porcentaje o importe.</span><span class="sxs-lookup"><span data-stu-id="285e0-117">**Simple discount** – A single percentage or amount.</span></span>
- <span data-ttu-id="285e0-118">**Descuento por cantidades**: un descuento que se aplica cuando se compran dos o más productos.</span><span class="sxs-lookup"><span data-stu-id="285e0-118">**Quantity discount** – A discount that is applied when two or more products are purchased.</span></span>
- <span data-ttu-id="285e0-119">**Descuento combinado**: un descuento que se aplica cuando se compra una combinación concreta de productos.</span><span class="sxs-lookup"><span data-stu-id="285e0-119">**Mix and match discount** – A discount that is applied when a specific combination of products is purchased.</span></span>
- <span data-ttu-id="285e0-120">**Descuento por umbral**: un descuento que se aplica cuando el total de la transacción es superior al importe especificado.</span><span class="sxs-lookup"><span data-stu-id="285e0-120">**Threshold discount** – A discount that is applied when the transaction total is more than a specified amount.</span></span>
- <span data-ttu-id="285e0-121">**Descuento basados en la forma de pago**: un descuento que se aplica cuando el total de la transacción es superior a un monto específico y se utiliza un tipo de pago específico (por ejemplo, efectivo, tarjeta de crédito o débito) para el pago.</span><span class="sxs-lookup"><span data-stu-id="285e0-121">**Tender-based discount** – A discount that is applied when the transaction total is more than a specified amount and a specific payment type (for example, cash, credit, or debit card) is used for payment.</span></span>
- <span data-ttu-id="285e0-122">**Descuento de envío**: un descuento que se aplica cuando el total de la transacción es superior a una cantidad especificada y se utiliza un modo de entrega específico (por ejemplo, envío en dos días o envío al día siguiente) en el pedido.</span><span class="sxs-lookup"><span data-stu-id="285e0-122">**Shipping discount** – A discount that is applied when the transaction total is more than a specified amount and a specific mode of delivery (for example, two day shipping or overnight shipping) is used on the order.</span></span>

<span data-ttu-id="285e0-123">Tanto los ajustes de precios como los descuentos se pueden asociar con los grupos de precios.</span><span class="sxs-lookup"><span data-stu-id="285e0-123">Both price adjustments and discounts can be associated with price groups.</span></span> <span data-ttu-id="285e0-124">A continuación, los grupos de precios pueden asociarse con canales, catálogos, afiliaciones y programas de fidelidad.</span><span class="sxs-lookup"><span data-stu-id="285e0-124">Price groups can then be associated with channels, catalogs, affiliations, and loyalty programs.</span></span>
