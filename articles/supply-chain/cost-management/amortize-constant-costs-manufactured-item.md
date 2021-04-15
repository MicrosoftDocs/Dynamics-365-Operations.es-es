---
title: Amortizar los costes constantes para un artículo fabricado
description: Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante.
author: AndersGirke
ms.date: 04/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 274503
ms.assetid: 535ab25d-a031-4e8c-84ec-478f2987a1ad
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: 5f44c0c7a50df55206ddd08ce71772f8caac9363
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808121"
---
# <a name="amortize-constant-costs-for-a-manufactured-item"></a><span data-ttu-id="500ed-103">Amortizar los costes constantes para un artículo fabricado</span><span class="sxs-lookup"><span data-stu-id="500ed-103">Amortize constant costs for a manufactured item</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="500ed-104">Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante.</span><span class="sxs-lookup"><span data-stu-id="500ed-104">A manufactured item’s constant costs reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span> 

<span data-ttu-id="500ed-105">El concepto de tamaño del lote de gestión de costes se usa para amortizar estos costes constantes en el coste calculado de un artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="500ed-105">The concept of a costing lot size is used to amortize these constant costs in the calculated cost of a manufactured item.</span></span> <span data-ttu-id="500ed-106">Este concepto tiene varios sinónimos, uno de los cuales es el tamaño del lote de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="500ed-106">This concept has several synonyms, one of which is accounting lot size.</span></span> <span data-ttu-id="500ed-107">El concepto de costes constantes de amortización también tiene varios sinónimos, uno de los cuales es el de costes constantes proporcionales.</span><span class="sxs-lookup"><span data-stu-id="500ed-107">The concept of amortizing constant costs also has several synonyms, one of which is proportional constant costs.</span></span>

<span data-ttu-id="500ed-108">La cantidad del tamaño del lote de gestión de costes para un artículo fabricado se usa en un cálculo de lista de materiales (L. MAT).</span><span class="sxs-lookup"><span data-stu-id="500ed-108">The quantity of a costing lot size for a manufactured item is used in a bill of material (BOM) calculation.</span></span> <span data-ttu-id="500ed-109">La cantidad depende de cómo se inicia y realiza el cálculo de L. MAT, tal como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="500ed-109">The quantity depends on how you initiate and perform the BOM calculation, as illustrated by the following:</span></span>

-   <span data-ttu-id="500ed-110">La cantidad de cálculo predeterminada en un cálculo de L. MAT de un producto: la cantidad de pedido estándar del artículo para inventario funciona como el tamaño de lote de gestión de costes, pero el valor predeterminado debe ser una cantidad superior para reflejar la cantidad del pedido múltiple del artículo.</span><span class="sxs-lookup"><span data-stu-id="500ed-110">Default calculation quantity in an item’s BOM calculation − The item’s standard order quantity for inventory acts as the costing lot size, but the default value might be a greater quantity to reflect the item’s order quantity multiple.</span></span> <span data-ttu-id="500ed-111">La cantidad y el múltiplo de pedido estándar del artículo se pueden definir en su configuración de pedido predeterminada o en la configuración específica del pedido.</span><span class="sxs-lookup"><span data-stu-id="500ed-111">The item’s standard order quantity and multiple can be defined within its default order settings or site-specific order settings.</span></span>
-   <span data-ttu-id="500ed-112">Cantidad de cálculo especificada en el cálculo de L. MAT de un artículo: la cantidad de cálculo especificada actúa como tamaño de lote de gestión de costes para el artículo.</span><span class="sxs-lookup"><span data-stu-id="500ed-112">Specified calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item.</span></span> <span data-ttu-id="500ed-113">La cantidad del cálculo usa inicialmente la cantidad del pedido estándar del artículo; sin embargo, puede reemplazar manualmente los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="500ed-113">The calculation quantity initially uses the item’s standard order quantity, but the default value can be manually overridden.</span></span> <span data-ttu-id="500ed-114">La cantidad de cálculo especificada representa el tamaño de lote de gestión de costes para el artículo especificado, y para componentes fabricados con un tipo de producción de línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="500ed-114">The specified calculation quantity represents the costing lot size for the specified item, and for manufactured components that have a BOM line type of production.</span></span> <span data-ttu-id="500ed-115">Esto se debe a que se supone que el componente va a producirse en la cantidad exacta.</span><span class="sxs-lookup"><span data-stu-id="500ed-115">This is because it is assumed that the component will be produced to the exact quantity.</span></span> <span data-ttu-id="500ed-116">El tamaño de lote de gestión de costes para otros componentes fabricados que tengan un tipo de línea de L. MAT de artículo reflejará su cantidad de pedido estándar.</span><span class="sxs-lookup"><span data-stu-id="500ed-116">The costing lot size for other manufactured components that have a BOM line type of item will reflect their standard order quantity.</span></span>
-   <span data-ttu-id="500ed-117">Cantidad de cálculo de "hacer para pedir" especificada en el cálculo de L. MAT de un artículo: la cantidad de cálculo especificada actúa como el tamaño de lote de gestión de costes para el artículo y sus componentes fabricados cuando los cálculos de L. MAT usan un modo de expansión de "hacer para pedir".</span><span class="sxs-lookup"><span data-stu-id="500ed-117">Specified make-to-order calculation quantity in an item’s BOM calculation − The specified calculation quantity acts as the costing lot size for the item and its manufactured components when BOM calculations use a make-to-order explosion mode.</span></span> <span data-ttu-id="500ed-118">Se supone que va a producir los componentes fabricados en la cantidad exacta, al igual que un componente fabricado con un tipo de línea de L. MAT de producción.</span><span class="sxs-lookup"><span data-stu-id="500ed-118">It is assumed that the manufactured components will be produced to the exact quantity, just like a manufactured component that has a BOM line type of production.</span></span>
-   <span data-ttu-id="500ed-119">Cantidad de cálculo especificada en el cálculo de L. MAT específico de un pedido: un cálculo de L. MAT específico de un pedido se puede realizar para una línea de artículo de un pedido de ventas, un presupuesto de ventas o un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="500ed-119">Specified calculation quantity in an order-specific BOM calculation − An order-specific BOM calculation can be performed for a line item on a sales order, sales quotation, or service order.</span></span> <span data-ttu-id="500ed-120">La cantidad de cálculo especificada utiliza la cantidad del artículo de línea de origen, pero la cantidad predeterminada se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="500ed-120">The specified calculation quantity uses the quantity on the originating line item, but the default quantity can be overridden.</span></span> <span data-ttu-id="500ed-121">Puede seleccionar si el cálculo de L. MAT específico del pedido utiliza un modo de expansión de "hacer para pedir" o multinivel.</span><span class="sxs-lookup"><span data-stu-id="500ed-121">You can select whether the order-specific BOM calculation uses a make-to-order or multilevel explosion mode.</span></span>

<span data-ttu-id="500ed-122">El importe calculado de los costes constantes amortizados de un artículo se denomina gastos.</span><span class="sxs-lookup"><span data-stu-id="500ed-122">The calculated amount of a manufactured item’s amortized constant costs is termed charges.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]