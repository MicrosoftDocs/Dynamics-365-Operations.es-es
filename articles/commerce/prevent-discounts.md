---
title: Opciones para evitar descuentos de productos comerciales
description: Existen varios motivos por los que los minoristas pueden querer evitar que algunos de sus productos tengan descuentos, tanto por una promoción o durante la venta PDV.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailPeriodicDiscount
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 85183
ms.assetid: e8c5a24f-7edd-4fd6-af80-5e0ac9f03127
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 6a683ffce487dc4388711ad160c2e8dc55a690dd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415465"
---
# <a name="options-for-preventing-discounts-for-retail-products"></a><span data-ttu-id="201cb-103">Opciones para evitar descuentos de productos comerciales</span><span class="sxs-lookup"><span data-stu-id="201cb-103">Options for preventing discounts for retail products</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="201cb-104">Existen varios motivos por los que los minoristas pueden querer evitar que algunos de sus productos tengan descuentos, tanto por una promoción o durante la venta PDV.</span><span class="sxs-lookup"><span data-stu-id="201cb-104">There are various reasons why retailers may want to prevent some products from being discounted, either from a promotion or during the sale at the POS.</span></span>

<span data-ttu-id="201cb-105">Las opciones siguientes, que se pueden encontrar en la pestaña **Commerce** de productos emitidos, permitirán que el producto se configure para evitar todos o descuentos manuales.</span><span class="sxs-lookup"><span data-stu-id="201cb-105">The following options, which can be found on the **Commerce** tab of released products, will allow the product to be configured to prevent all or manual discounts.</span></span> <span data-ttu-id="201cb-106">Los valores también se pueden especificar al nivel de categoría de la jerarquía de categoría.</span><span class="sxs-lookup"><span data-stu-id="201cb-106">The settings can also be specified at the category level from the category hierarchy.</span></span>

- <span data-ttu-id="201cb-107">**Evite todos los descuentos**: Seleccione esta opción para impedir que se apliquen todos los tipos de descuentos a este producto.</span><span class="sxs-lookup"><span data-stu-id="201cb-107">**Prevent all discounts** – Select this option to prevent all types of discounts from being applied to this product.</span></span> <span data-ttu-id="201cb-108">Esto incluye promociones como Descuentos combinados, los descuentos de cantidad y de umbral, así como los descuentos manuales de línea y transacción que se aplican durante una venta por un PDV.</span><span class="sxs-lookup"><span data-stu-id="201cb-108">This includes promotions such as mix and match, quantity and threshold discounts, as well as manual line and transaction discounts that are applied during a sale by a POS user.</span></span>
- <span data-ttu-id="201cb-109">**Evitar los descuentos manuales**: Seleccione esta opción para evitar sólo los descuentos manuales de la línea o transacción que se aplican durante una venta por un usuario PDV.</span><span class="sxs-lookup"><span data-stu-id="201cb-109">**Prevent manual discounts** – Select this option to only prevent the manual line or transaction discounts that are applied during a sale by a POS user.</span></span> <span data-ttu-id="201cb-110">Los productos con esta opción seleccionada todavía están aptos para promociones, como descuentos de combinados y de cantidad y de umbral.</span><span class="sxs-lookup"><span data-stu-id="201cb-110">Products with this option selected are still eligible for promotions, such as mix and match and quantity and threshold discounts.</span></span>

> [!NOTE]
> <span data-ttu-id="201cb-111">Estos ajustes no limitan la operación de la anulación de precio, ya que esto establece el precio base y no se trata como un descuento.</span><span class="sxs-lookup"><span data-stu-id="201cb-111">These settings do not restrict the price override operation, because that sets the base price and is not treated as a discount.</span></span>

<span data-ttu-id="201cb-112">[![Evite el campo de descuentos](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span><span class="sxs-lookup"><span data-stu-id="201cb-112">[![Prevent discounts field](./media/prevent-discounts.png)](./media/prevent-discounts.png)</span></span>
