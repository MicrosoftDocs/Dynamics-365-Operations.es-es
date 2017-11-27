---
title: "Visualización de los gastos para un artículo fabricado"
description: "Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante."
author: AndersGirke
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fe766a2969e647500452ecb64040d2157a155416
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="display-charges-for-a-manufactured-item"></a><span data-ttu-id="62cd3-103">Visualización de los gastos para un artículo fabricado</span><span class="sxs-lookup"><span data-stu-id="62cd3-103">Display charges for a manufactured item</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="62cd3-104">Los costes constantes de un artículo fabricado reflejan los tiempos de preparación de la operación y los componentes con una cantidad constante o un importe residual constante.</span><span class="sxs-lookup"><span data-stu-id="62cd3-104">The constant costs of a manufactured item reflect the operation setup times and the components that have a constant quantity or a constant scrap amount.</span></span>

<span data-ttu-id="62cd3-105">El importe calculado de los gastos del artículo se puede mostrar con los costes unitarios del artículo.</span><span class="sxs-lookup"><span data-stu-id="62cd3-105">The calculated amount of an item's charges can be displayed with the item's unit costs.</span></span> <span data-ttu-id="62cd3-106">No obstante, los gastos se muestran en ocasiones en campos diferentes, y no se incluyen en los costes unitarios del artículo.</span><span class="sxs-lookup"><span data-stu-id="62cd3-106">However, the charges are sometimes displayed as separate fields, and they are not included in the item's unit costs.</span></span> <span data-ttu-id="62cd3-107">Cuando los gastos aparecen en campos diferentes, uno de los campos muestra el importe total de los gastos totales y el otro campo muestra el tamaño del lote de costes que se utiliza para amortizar el importe.</span><span class="sxs-lookup"><span data-stu-id="62cd3-107">When the charges appear as separate fields, one field displays the total amount of charges, and another field displays the costing lot size that is used to amortize the amount.</span></span> <span data-ttu-id="62cd3-108">La página Precio de artículo, por ejemplo, muestra los gastos en dos campos diferentes.</span><span class="sxs-lookup"><span data-stu-id="62cd3-108">The Item price page, for example, displays the charges as two separate fields.</span></span> <span data-ttu-id="62cd3-109">Sin embargo, la página Completado muestra el coste total por unidad del artículo y los costes amortizados se incluyen en los costes unitarios.</span><span class="sxs-lookup"><span data-stu-id="62cd3-109">However, the Complete page displays the item's total cost per unit, and the amortized costs are included in the unit costs.</span></span>

<span data-ttu-id="62cd3-110">Los gastos de un artículo fabricado se incluyen siempre en el coste unitario del artículo con el fin de calcular los costes estándar.</span><span class="sxs-lookup"><span data-stu-id="62cd3-110">The charges for a manufactured item are always included in the item's unit cost for standard cost purposes.</span></span> <span data-ttu-id="62cd3-111">De forma opcional, pueden incluirse para calcular los costes planificados.</span><span class="sxs-lookup"><span data-stu-id="62cd3-111">They can optionally be included for planned cost purposes.</span></span> <span data-ttu-id="62cd3-112">La directiva de la versión de gestión de costes exige incluir los gastos en el coste de un artículo fabricado.</span><span class="sxs-lookup"><span data-stu-id="62cd3-112">A policy in the costing version enforces the inclusion of charges in the cost of a manufactured item.</span></span> <span data-ttu-id="62cd3-113">Cuando se activa el registro de costes de un artículo, deberá actualizar los gastos de la información del coste base del artículo que se muestra en la página Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="62cd3-113">When you activate an item's cost record, you update the charges for the item's base cost information, which is displayed in the Item price page.</span></span> <span data-ttu-id="62cd3-114">Los gastos se muestran en dos campos distintos, y no se incluyen en el coste unitario del artículo.</span><span class="sxs-lookup"><span data-stu-id="62cd3-114">The charges are displayed as two separate fields, and they are not included in the item's unit cost.</span></span> <span data-ttu-id="62cd3-115">Cada activación actualiza la información del coste base del artículo, a pesar de que la activación refleje sitios diferentes.</span><span class="sxs-lookup"><span data-stu-id="62cd3-115">Each activation updates the item's base cost information, even if the activation reflects different sites.</span></span> <span data-ttu-id="62cd3-116">De ahí que la información de coste base deba considerarse como información de referencia.</span><span class="sxs-lookup"><span data-stu-id="62cd3-116">Therefore, you should view the base cost information as reference information.</span></span>






