---
title: Dimensiones de elemento de coste
description: "Como uno de los pilares básicos de la Contabilidad de costes, las dimensiones del elemento de coste se utilizan para clasificar y realizar un seguimiento de a dónde fluyen los costes."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223204
ms.assetid: 1eda0e62-760b-4737-9dfd-3c3c38d80c1a
ms.search.region: global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 9e13fc9fa7e51a1299ca8698f581de979b680a7b
ms.openlocfilehash: 00a09120116183785d96ed1e18c577d5430fa16b
ms.contentlocale: es-es
ms.lasthandoff: 09/18/2017

---

# <a name="cost-element-dimensions"></a><span data-ttu-id="847d9-103">Dimensiones de elemento de coste</span><span class="sxs-lookup"><span data-stu-id="847d9-103">Cost element dimensions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="847d9-104">Como uno de los pilares básicos de la Contabilidad de costes, las dimensiones del elemento de coste se utilizan para clasificar y realizar un seguimiento de a dónde fluyen los costes.</span><span class="sxs-lookup"><span data-stu-id="847d9-104">As one of the core pillars in Cost accounting, cost element dimensions are used to categorize and track where costs flow to.</span></span> 

<span data-ttu-id="847d9-105">Un elemento de coste corresponde a un artículo de coste relevante del plan contable.</span><span class="sxs-lookup"><span data-stu-id="847d9-105">A cost element corresponds to a cost-relevant item in the chart of accounts.</span></span> <span data-ttu-id="847d9-106">Básicamente, puede ser cualquier tipo de elemento del nivel más bajo de un negocio a donde los costes pueden fluir.</span><span class="sxs-lookup"><span data-stu-id="847d9-106">Basically, it can be any type of element at the lowest level in a business where costs can flow to.</span></span> <span data-ttu-id="847d9-107">Los elementos de coste como concepto oscilan entre cuentas contables a todos los recursos de coste relevantes.</span><span class="sxs-lookup"><span data-stu-id="847d9-107">Cost elements as a concept range from ledger accounts to all cost-relevant resources.</span></span> <span data-ttu-id="847d9-108">Actualmente, la Contabilidad de costes admite cuentas contables.</span><span class="sxs-lookup"><span data-stu-id="847d9-108">Currently, Cost accounting supports ledger accounts.</span></span>

## <a name="two-types-of-cost-elements"></a><span data-ttu-id="847d9-109">Dos tipos de elementos de coste</span><span class="sxs-lookup"><span data-stu-id="847d9-109">Two types of cost elements</span></span>
<span data-ttu-id="847d9-110">Existen dos tipos de elementos de coste: elementos de coste principales y elementos de coste secundarios.</span><span class="sxs-lookup"><span data-stu-id="847d9-110">There are two types of cost elements: primary cost elements and secondary cost elements.</span></span> <span data-ttu-id="847d9-111">En la tabla siguiente se describe la diferencia entre los dos tipos.</span><span class="sxs-lookup"><span data-stu-id="847d9-111">The following table describes the difference between the two types.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="847d9-112"><strong>Elementos de coste principales</strong></span><span class="sxs-lookup"><span data-stu-id="847d9-112"><strong>Primary cost elements</strong></span></span></td>
<td><span data-ttu-id="847d9-113"><strong>Elementos de costes secundarios</strong></span><span class="sxs-lookup"><span data-stu-id="847d9-113"><strong>Secondary cost elements</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="847d9-114">Los elementos de coste principales representan el flujo de costes de la contabilidad financiera a la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="847d9-114">The primary cost elements represent the flow of costs from financial accounting to cost accounting.</span></span> <span data-ttu-id="847d9-115">La estructura del elemento de coste corresponde a la estructura de la cuenta de pérdidas y ganancias en la contabilidad general, donde un elemento de costes puede corresponder a una cuenta principal.</span><span class="sxs-lookup"><span data-stu-id="847d9-115">The cost element structure corresponds to the profit and loss account structure in the general ledger, where a cost element can correspond to a main account.</span></span> <span data-ttu-id="847d9-116">No todas las cuentas principales pueden ser representadas necesariamente como elementos de coste en función de las necesidades del negocio.</span><span class="sxs-lookup"><span data-stu-id="847d9-116">Not all main accounts may necessarily be represented as cost elements depending on the business needs.</span></span> <span data-ttu-id="847d9-117">Ejemplos de elementos de coste principales incluyen:</span><span class="sxs-lookup"><span data-stu-id="847d9-117">Examples of primary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="847d9-118">Costes de mercancías vendidas (COG)</span><span class="sxs-lookup"><span data-stu-id="847d9-118">Costs of goods sold (COGs)</span></span></li>
<li><span data-ttu-id="847d9-119">Costes indirectos de material</span><span class="sxs-lookup"><span data-stu-id="847d9-119">Indirect material costs</span></span></li>
<li><span data-ttu-id="847d9-120">Costes de personal</span><span class="sxs-lookup"><span data-stu-id="847d9-120">Personnel costs</span></span></li>
<li><span data-ttu-id="847d9-121">Costes de energía</span><span class="sxs-lookup"><span data-stu-id="847d9-121">Energy costs</span></span></li>
</ul></td>
<td><span data-ttu-id="847d9-122">Los elementos de coste secundarios representan el flujo de costes internamente, ya que estos costes se crean y se usan solo en la Contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="847d9-122">The secondary cost elements represent the flow of costs internally because these costs are created and used only in Cost accounting.</span></span> <span data-ttu-id="847d9-123">Se utilizan para garantizar que el origen de costes se pueda seguir.</span><span class="sxs-lookup"><span data-stu-id="847d9-123">They are used to secure that the source of costs can be traced.</span></span> <span data-ttu-id="847d9-124">Dichos elementos de costes se utilizan en asignaciones de costes y cálculos de gastos generales.</span><span class="sxs-lookup"><span data-stu-id="847d9-124">These cost elements are used in cost allocations and overhead calculations.</span></span> <span data-ttu-id="847d9-125">Ejemplos de elementos de coste secundarios incluyen:</span><span class="sxs-lookup"><span data-stu-id="847d9-125">Examples of secondary cost elements include:</span></span>
<ul>
<li><span data-ttu-id="847d9-126">Costes de producción</span><span class="sxs-lookup"><span data-stu-id="847d9-126">Production costs</span></span></li>
<li><span data-ttu-id="847d9-127">Gastos generales de producción, materiales y marketing</span><span class="sxs-lookup"><span data-stu-id="847d9-127">Production, material, and marketing overheads</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cost-element-dimensions-and-cost-element-dimension-members"></a><span data-ttu-id="847d9-128">Dimensiones del elemento de coste y miembros de la dimensión del elemento de coste</span><span class="sxs-lookup"><span data-stu-id="847d9-128">Cost element dimensions and cost element dimension members</span></span>
<span data-ttu-id="847d9-129">Se hace referencia a los elementos de coste como *dimensiones del elemento de coste* .</span><span class="sxs-lookup"><span data-stu-id="847d9-129">Cost elements are referred to as *cost element dimensions* .</span></span> <span data-ttu-id="847d9-130">Los valores de dimensión individuales se denominan *miembros de dimensión de elemento de coste*.</span><span class="sxs-lookup"><span data-stu-id="847d9-130">The individual dimension values are called *cost element dimension members*.</span></span> <span data-ttu-id="847d9-131">Por ejemplo, si tiene una estructura del plan contable de Estados Unidos. (COA) que es la base de sus informes estatutarios.</span><span class="sxs-lookup"><span data-stu-id="847d9-131">For example, you have a US chart of accounts structure (COA) that is the base for your statutory reporting.</span></span> <span data-ttu-id="847d9-132">Este COA se usa como la dimensión del elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="847d9-132">This COA is used as the cost element dimension.</span></span> <span data-ttu-id="847d9-133">Las cuentas, que son elementos de coste principales, se representan como miembros de dimensión del elemento de coste en la Contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="847d9-133">The accounts, which are primary cost elements, are represented as the cost element dimension members in Cost accounting.</span></span> <span data-ttu-id="847d9-134">El captura de pantalla siguiente muestra un ejemplo de Cuentas principales como dimensión de elemento de coste con sus cuentas principales como miembros de dimensión de elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="847d9-134">The following screenshot shows an example of Main Accounts as the cost element dimension with its actual main accounts as the cost element dimension members.</span></span> 

<span data-ttu-id="847d9-135">[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="847d9-135">[![cost-element-dimensions](./media/cost-element-dimensions.png)](./media/cost-element-dimensions.png)</span></span>

## <a name="import-cost-element-dimension-members-through-data-connectors"></a><span data-ttu-id="847d9-136">Importar miembros de dimensión de elemento de coste mediante conectores de datos</span><span class="sxs-lookup"><span data-stu-id="847d9-136">Import cost element dimension members through data connectors</span></span>
<span data-ttu-id="847d9-137">Para facilitar la configuración de los miembros de la dimensión del elemento de coste en la Contabilidad de costes, puede usar los conectores de datos que se han generado previamente o los que ha personalizado para recuperar los elementos de coste principales de uno o más sistemas de origen.</span><span class="sxs-lookup"><span data-stu-id="847d9-137">To ease the setup of cost element dimension members in Cost accounting, you can use data connectors that are either pre-built or your custom build to retrieve the primary cost elements from one or more source systems.</span></span>

## <a name="implementation-considerations"></a><span data-ttu-id="847d9-138">Consideraciones sobre la implementación</span><span class="sxs-lookup"><span data-stu-id="847d9-138">Implementation considerations</span></span>
<span data-ttu-id="847d9-139">Ya que los elementos de coste representan el valor mínimo de los detalles de coste, deberá asegurarse de que todos los elementos de coste requeridos para hacer el informe de gestión se incluirán cuando implemente la estructura de elementos de coste.</span><span class="sxs-lookup"><span data-stu-id="847d9-139">As cost elements represent the lowest level of cost details, you should make sure that all the cost elements required to make the managerial reporting are included when you implement the cost elements structure.</span></span> <span data-ttu-id="847d9-140">Encontrar el número adecuado de elementos de coste puede suponer un desafío para el control de costes.</span><span class="sxs-lookup"><span data-stu-id="847d9-140">It can be a challenge to find an appropriate number of cost elements for cost control.</span></span> <span data-ttu-id="847d9-141">Disponer de miles de elementos de costes puede dificultar el control de cada elemento de coste.</span><span class="sxs-lookup"><span data-stu-id="847d9-141">Having thousands of cost elements can make it difficult to control each cost element.</span></span> <span data-ttu-id="847d9-142">Como alternativa, puede agrupar elementos de coste y gestionar el control de coste a nivel agregado.</span><span class="sxs-lookup"><span data-stu-id="847d9-142">As an alternative, you can group cost elements and manage cost control at an aggregated level.</span></span>




