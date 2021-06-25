---
title: Preparar el mantenimiento de los costes estándar de artículos fabricados
description: Este tema decribe los pasos para prepararse para el mantenimiento de costes de artículos fabricados.
author: AndersGirke
ms.date: 01/17/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a82b0a205ac6b7a86b9aca0771303469c6666c1
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187755"
---
# <a name="prepare-to-maintain-standard-costs-for-manufactured-items"></a><span data-ttu-id="d9f47-103">Preparar el mantenimiento de los costes estándar de artículos fabricados</span><span class="sxs-lookup"><span data-stu-id="d9f47-103">Prepare to maintain standard costs for manufactured items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9f47-104">Este tema decribe los pasos para prepararse para el mantenimiento de costes de artículos fabricados.</span><span class="sxs-lookup"><span data-stu-id="d9f47-104">This topic describes the steps for preparing to maintain costs for manufactured items.</span></span> <span data-ttu-id="d9f47-105">Los pasos para los artículos fabricados varían ligeramente de los pasos de los artículos adquiridos.</span><span class="sxs-lookup"><span data-stu-id="d9f47-105">The steps for manufactured items differ slightly from the steps for purchased items.</span></span>

<span data-ttu-id="d9f47-106">Las directivas que se asignan a los artículos fabricados pueden afectar a los cálculos de coste de los artículos fabricados principales.</span><span class="sxs-lookup"><span data-stu-id="d9f47-106">Policies that are assigned to manufactured items can affect the cost calculations for the parent manufactured items.</span></span> <span data-ttu-id="d9f47-107">Para prepararse para mantener los costes de artículos fabricados, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d9f47-107">To prepare to maintain costs for manufactured items, follow these steps.</span></span>

1. <span data-ttu-id="d9f47-108">Asigne un grupo de modelos de artículos al artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-108">Assign an item model group to the manufactured item.</span></span> 

   <span data-ttu-id="d9f47-109">El grupo de modelos de artículos identifica el uso de esos costes estándar.</span><span class="sxs-lookup"><span data-stu-id="d9f47-109">The item model group identifies that standard costs will be used.</span></span>

2. <span data-ttu-id="d9f47-110">Asigne un grupo de artículos al artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-110">Assign an item group to the manufactured item.</span></span> 

   <span data-ttu-id="d9f47-111">El grupo de artículos contiene cuentas contables que se aplican al artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-111">The item group contains ledger accounts that apply to the manufactured item.</span></span> <span data-ttu-id="d9f47-112">Las cuentas contables de un artículo fabricado que tiene un modelo de inventario de coste estándar incluyen varias desviaciones de producción, la desviación de cambio de coste y la revalorización del coste de inventario.</span><span class="sxs-lookup"><span data-stu-id="d9f47-112">The ledger accounts for a manufactured item that has a standard cost inventory model include several production variances, the cost change variance, and the inventory cost revaluation.</span></span>

3. <span data-ttu-id="d9f47-113">Asigne la unidad de medida de inventario al artículo.</span><span class="sxs-lookup"><span data-stu-id="d9f47-113">Assign the inventory unit of measure to the item.</span></span> 

   <span data-ttu-id="d9f47-114">Los costes del artículo siempre se expresan en la unidad de medida de inventario del artículo.</span><span class="sxs-lookup"><span data-stu-id="d9f47-114">The item's costs are always expressed in the item's inventory unit of measure.</span></span>

4. <span data-ttu-id="d9f47-115">No asigne un grupo de costes al artículo fabricado a menos que el artículo se trate como un artículo comprado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-115">Don't assign a cost group to the manufactured item unless the item will be treated as a purchased item.</span></span>

5. <span data-ttu-id="d9f47-116">Asigne un grupo de cálculo de lista de materiales (L. MAT) al artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-116">Assign a bill of materials (BOM) calculation group to the manufactured item.</span></span> 

   <span data-ttu-id="d9f47-117">El grupo de cálculo de L. MAT del artículo define las condiciones de advertencia que se aplican.</span><span class="sxs-lookup"><span data-stu-id="d9f47-117">The item's BOM calculation group defines warning conditions that apply.</span></span> <span data-ttu-id="d9f47-118">De esa manera, cuando se realiza un cálculo de L. MAT, pueden generarse mensajes de advertencia sobre los posibles orígenes de errores de cálculo.</span><span class="sxs-lookup"><span data-stu-id="d9f47-118">In that way, when a BOM calculation is done, warning messages can be generated about possible sources of calculation errors.</span></span> <span data-ttu-id="d9f47-119">Por ejemplo, un mensaje de advertencia puede identificar cuándo no existen una L. MAT o ruta activas.</span><span class="sxs-lookup"><span data-stu-id="d9f47-119">For example, a warning message can identify when an active BOM or route doesn't exist.</span></span> <span data-ttu-id="d9f47-120">El grupo de cálculos de L. MAT contiene una directiva de detención de la expansión que indica cuándo un artículo fabricado debe tratarse como un artículo comprado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-120">The BOM calculation group contains a stop explosion policy that indicates when a manufactured item should be treated as a purchased item.</span></span>

6. <span data-ttu-id="d9f47-121">Si el artículo fabricado tiene costes constantes, asigne una cantidad de pedido estándar a este.</span><span class="sxs-lookup"><span data-stu-id="d9f47-121">If the manufactured item has constant costs, assign a standard order quantity to it.</span></span> 

   <span data-ttu-id="d9f47-122">La cantidad de pedido estándar es un tamaño del lote de contabilidad para la amortización de costes constantes.</span><span class="sxs-lookup"><span data-stu-id="d9f47-122">The standard order quantity is an accounting lot size for amortizing constant costs.</span></span> <span data-ttu-id="d9f47-123">Los ejemplos de costes constantes incluyen horas de configuración en las operaciones de enrutamiento y una cantidad de componentes constante en la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="d9f47-123">Examples of constant costs include setup times in routing operations and a constant component quantity in the BOM.</span></span>

7. <span data-ttu-id="d9f47-124">Defina la L. MAT para el artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-124">Define the BOM for the manufactured item.</span></span> 

   <span data-ttu-id="d9f47-125">Es posible definir una o más versiones de la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="d9f47-125">One or more BOM versions can be defined for the manufactured item.</span></span> <span data-ttu-id="d9f47-126">Compruebe que las versiones deseadas se marcaron como aprobadas y están activas, y que tengan las fechas de vigencia deseadas.</span><span class="sxs-lookup"><span data-stu-id="d9f47-126">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="d9f47-127">La versión de la L. MAT puede ser para toda la empresa o específica para un sitio.</span><span class="sxs-lookup"><span data-stu-id="d9f47-127">The BOM version can be company-wide or site-specific.</span></span>

8. <span data-ttu-id="d9f47-128">Defina la ruta para el artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="d9f47-128">Define the routing for the manufactured item.</span></span> 

   <span data-ttu-id="d9f47-129">Es posible definir una o más versiones de la ruta.</span><span class="sxs-lookup"><span data-stu-id="d9f47-129">One or more route versions can be defined for the manufactured item.</span></span> <span data-ttu-id="d9f47-130">Compruebe que las versiones deseadas se marcaron como aprobadas y están activas, y que tengan las fechas de vigencia deseadas.</span><span class="sxs-lookup"><span data-stu-id="d9f47-130">Verify that the versions that you want have been marked as approved and active, and that they have the effective dates that you want.</span></span> <span data-ttu-id="d9f47-131">La versión de la ruta debe ser específica para un sitio.</span><span class="sxs-lookup"><span data-stu-id="d9f47-131">The route version must be site-specific.</span></span>

<span data-ttu-id="d9f47-132">Si desea utilizar la información de enrutamiento para la gestión de costes necesitará pasos preparativos adicionales.</span><span class="sxs-lookup"><span data-stu-id="d9f47-132">If you want to use routing information for costing purposes, additional preparation steps are required.</span></span> <span data-ttu-id="d9f47-133">Por ejemplo, las categorías de coste asignadas a las operaciones de enrutamiento deben ser correctas y estar completas.</span><span class="sxs-lookup"><span data-stu-id="d9f47-133">For example, the cost categories that are assigned to routing operations must be correct and completed.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9f47-134">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d9f47-134">Related topics</span></span>

[<span data-ttu-id="d9f47-135">Amortizar los costes constantes para un artículo fabricado</span><span class="sxs-lookup"><span data-stu-id="d9f47-135">Amortize constant costs for a manufactured item</span></span>](amortize-constant-costs-manufactured-item.md)

[<span data-ttu-id="d9f47-136">Configurar productos que pueden fabricarse o suministrarse</span><span class="sxs-lookup"><span data-stu-id="d9f47-136">Set up products that can be produced or procured</span></span>](manufactured-items-treated-as-purchased-items.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]