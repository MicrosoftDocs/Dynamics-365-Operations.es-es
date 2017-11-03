---
title: "Asignar miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión"
description: "Asignando diferentes miembros de la dimensión del elemento de coste a un conjunto común de miembros de la dimensión del elemento de coste, los datos se combinan en un formato común para los análisis."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension, CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 223234
ms.assetid: 4c66a231-aed2-48b5-9727-b3eb4fe6e6aa
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6f2384155a07d17004c640160aee90b1e8bdb9f8
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="map-cost-element-dimension-members-to-a-common-set-of-dimension-members"></a><span data-ttu-id="2ff33-103">Asignar miembros de dimensión de elemento de coste a un conjunto común de miembros de dimensión</span><span class="sxs-lookup"><span data-stu-id="2ff33-103">Map cost element dimension members to a common set of dimension members</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2ff33-104">Asignando diferentes miembros de la dimensión del elemento de coste a un conjunto común de miembros de la dimensión del elemento de coste, los datos se combinan en un formato común para los análisis.</span><span class="sxs-lookup"><span data-stu-id="2ff33-104">By mapping different cost element dimension members to a common set of cost element dimension members, you merge data into a common format for analysis purposes.</span></span>

<span data-ttu-id="2ff33-105">Si es una empresa global y cumple con los requisitos estatutarios de contabilidad, puede usar múltiples planes contables.</span><span class="sxs-lookup"><span data-stu-id="2ff33-105">If you're a global company and comply with statutory accounting requirements, you might use multiple charts of accounts.</span></span> <span data-ttu-id="2ff33-106">Al importar los miembros de dimensión de elemento de coste desde diferentes planes contables, puede terminar con una mezcla de cuentas.</span><span class="sxs-lookup"><span data-stu-id="2ff33-106">When you import cost element dimension members from different charts of accounts, you can end up with a mix of accounts.</span></span> <span data-ttu-id="2ff33-107">Sin embargo, estas cuentas podrían tener la misma naturaleza y es posible que desee analizar y asignar costes para ellas mediante un formato común.</span><span class="sxs-lookup"><span data-stu-id="2ff33-107">However, these accounts might actually have the same nature, and you might want to analyze and allocate costs for them by using a common format.</span></span>

## <a name="map-cost-element-dimension-members-to-a-common-format"></a><span data-ttu-id="2ff33-108">Asigne miembros de dimensión de elemento de coste a un formato común</span><span class="sxs-lookup"><span data-stu-id="2ff33-108">Map cost element dimension members to a common format</span></span>
<span data-ttu-id="2ff33-109">El siguiente ejemplo le muestra cómo siendo controlador de coste, puede crear una nueva dimensión de elemento de coste en Contabilidad de costes que asigne a los miembros de la dimensión del elemento de coste desde la estructura del plan contable de Estados Unidos y la estructura francesa a un conjunto común de miembros de dimensión de elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="2ff33-109">The following example shows how you, as a cost controller, can create a new cost element dimension in Cost accounting that maps cost element dimension members from the US chart of accounts structure and the French chart of accounts structure to a common set of cost element dimension members.</span></span> <span data-ttu-id="2ff33-110">Puede utilizar el conjunto de común de miembros de la dimensión del elemento de coste para analizar datos de coste de las dos entidades jurídicas en un libro mayor de costes.</span><span class="sxs-lookup"><span data-stu-id="2ff33-110">You can then use the common set of cost element dimension members to analyze cost data from the two legal entities in a cost accounting ledger.</span></span>

| <span data-ttu-id="2ff33-111">Origen: plan contable de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="2ff33-111">Source: US chart of accounts</span></span>                                          | <span data-ttu-id="2ff33-112">Origen: plan contable francés</span><span class="sxs-lookup"><span data-stu-id="2ff33-112">Source: French chart of accounts</span></span>                                          | <span data-ttu-id="2ff33-113">Nuevo conjunto común de miembros de la dimensión del elemento de coste</span><span class="sxs-lookup"><span data-stu-id="2ff33-113">New common set of cost element dimension members</span></span>                        |
|-----------------------------------------------------------------------|---------------------------------------------------------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="2ff33-114">Miembros de dimensión del elemento de coste importados del plan contable de Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="2ff33-114">Imported cost element dimension members from the US chart of accounts</span></span> | <span data-ttu-id="2ff33-115">Miembros de dimensión del elemento de coste importados del plan contable francés.</span><span class="sxs-lookup"><span data-stu-id="2ff33-115">Imported cost element dimension members from the French chart of accounts</span></span> | <span data-ttu-id="2ff33-116">Asignación de miembros de dimensión de elemento de coste de Estados Unidos y francés a un conjunto común</span><span class="sxs-lookup"><span data-stu-id="2ff33-116">Mapping of US and French cost element dimension members to a common set</span></span> |
| <span data-ttu-id="2ff33-117">5001: Ventas</span><span class="sxs-lookup"><span data-stu-id="2ff33-117">5001: Sales</span></span>                                                           | <span data-ttu-id="2ff33-118">5001: Ventas y publicidad</span><span class="sxs-lookup"><span data-stu-id="2ff33-118">5001: Sales and advertising</span></span>                                               | <span data-ttu-id="2ff33-119">5000: Ventas y publicidad</span><span class="sxs-lookup"><span data-stu-id="2ff33-119">5000: Sales and advertising</span></span>                                             |
| <span data-ttu-id="2ff33-120">5030: Publicidad</span><span class="sxs-lookup"><span data-stu-id="2ff33-120">5030: Advertising</span></span>                                                     | <span data-ttu-id="2ff33-121">6390: Compra de existencias\*</span><span class="sxs-lookup"><span data-stu-id="2ff33-121">6390: Stock purchase\*</span></span>                                                    | <span data-ttu-id="2ff33-122">7000: Gastos de limpieza</span><span class="sxs-lookup"><span data-stu-id="2ff33-122">7000: Cleaning expenses</span></span>                                                 |
| <span data-ttu-id="2ff33-123">7001: Gastos de limpieza</span><span class="sxs-lookup"><span data-stu-id="2ff33-123">7001: Cleaning expenses</span></span>                                               | <span data-ttu-id="2ff33-124">7001: Gastos de viaje</span><span class="sxs-lookup"><span data-stu-id="2ff33-124">7001: Travel expense</span></span>                                                      | <span data-ttu-id="2ff33-125">7001: Gastos de viaje</span><span class="sxs-lookup"><span data-stu-id="2ff33-125">7001: Travel expenses</span></span>                                                   |

<span data-ttu-id="2ff33-126">\*No se ha asignado el miembro de la dimensión del elemento de coste francés de la Compra de existencias.</span><span class="sxs-lookup"><span data-stu-id="2ff33-126">\*The Stock purchase French cost element dimension member isn't mapped.</span></span>

## <a name="currency-conversion"></a><span data-ttu-id="2ff33-127">Conversión de divisas</span><span class="sxs-lookup"><span data-stu-id="2ff33-127">Currency conversion</span></span>
<span data-ttu-id="2ff33-128">Los distintos planes contables que use se pueden configurar para utilizar distintas divisas.</span><span class="sxs-lookup"><span data-stu-id="2ff33-128">The various charts of accounts that you use might be set up to use different currencies.</span></span> <span data-ttu-id="2ff33-129">En este caso, asegúrese de especificar una conversión de divisa, para procesar los datos de coste en la divisa correcta, como se define en el libro mayor de la contabilidad de costes donde se usan los miembros de la dimensión del elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="2ff33-129">In this case, be sure to specify a currency conversion, so that cost data is processed by using the correct currency, as defined in the cost accounting ledger where the cost element dimension members are used.</span></span> <span data-ttu-id="2ff33-130">En el ejemplo anterior, si se utilizan dólares estadounidenses (USD) en la contabilidad de la contabilidad de costes, debe crear una conversión de divisa de USD a euros (EUR) para procesar transacciones para los miembros de dimensión del elemento de coste asignados.</span><span class="sxs-lookup"><span data-stu-id="2ff33-130">In the preceding example, if US dollars (USD) are used in the cost accounting ledger, you must create a currency conversion from USD to euros (EUR) to process transactions for the mapped cost element dimension members.</span></span>

## <a name="update-mappings-at-any-time"></a><span data-ttu-id="2ff33-131">Actualizar las asignaciones en cualquier momento</span><span class="sxs-lookup"><span data-stu-id="2ff33-131">Update mappings at any time</span></span>
<span data-ttu-id="2ff33-132">Puede actualizar las definiciones de asignación para una dimensión de elemnto de coste en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="2ff33-132">You can update the mapping definitions for a cost element dimension at any time.</span></span> <span data-ttu-id="2ff33-133">Dado que las asignaciones no son fechas efectivas, los cambios se aplican la próxima vez que procesa transacciones de coste o ejecuta cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="2ff33-133">Because mappings aren't date-effective, changes are applied the next time that you process cost transactions or run cost calculations.</span></span>




