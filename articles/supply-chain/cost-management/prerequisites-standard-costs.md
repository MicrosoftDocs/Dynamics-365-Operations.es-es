---
title: Visión general de los requisitos previos de los costes estándar
description: Este tema describe los pasos básicos para el uso de costes estándar.
author: AndersGirke
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f66f7061c608379689016e3c0b9c5ba4ad23dc9e
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214530"
---
# <a name="prerequisites-for-standard-costs-overview"></a><span data-ttu-id="a9fcd-103">Visión general de los requisitos previos de los costes estándar</span><span class="sxs-lookup"><span data-stu-id="a9fcd-103">Prerequisites for standard costs overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9fcd-104">Este tema describe los pasos básicos para el uso de costes estándar.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-104">This topic describes the basic steps for using standard costs.</span></span> <span data-ttu-id="a9fcd-105">Los pasos posteriores dependen de las operaciones de la empresa.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-105">Subsequent steps depend on the company's operations.</span></span> <span data-ttu-id="a9fcd-106">Por ejemplo, los pasos difieren para un entorno de no fabricación, un entorno de fabricación que no usa enrutamientos y un entorno de fabricación que usa enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-106">For example, the steps differ for a nonmanufacturing environment, a manufacturing environment that doesn't use routings, and a manufacturing environment that uses routings.</span></span> 

<span data-ttu-id="a9fcd-107">Para establecer los costes estándar, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-107">To set up standard costs, follow these steps.</span></span>

<span data-ttu-id="a9fcd-108">**1. Cree un grupo de modelos de artículos para los costes estándar.**</span><span class="sxs-lookup"><span data-stu-id="a9fcd-108">**1. Create an item model group for standard costs.**</span></span>

<span data-ttu-id="a9fcd-109">Use el formulario **Grupos de modelos de artículo** para crear un nuevo grupo de costes estándar y asignar un modelo de inventario de **Coste estándar**.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-109">Use the **Item model groups** page to create a new group for standard costs, and assign an inventory model of **Standard cost**.</span></span> <span data-ttu-id="a9fcd-110">El identificador del grupo de modelos de artículos debería tener significado, como por ejemplo **Coste est**.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-110">The identifier for the item model group should be meaningful, such as **Std Cost**.</span></span> <span data-ttu-id="a9fcd-111">Active las casillas para indicar que el grupo debe permitir inventario negativo financiero, y ese debe registrar el inventario físico y el inventario financiero.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-111">Select the check boxes to indicate that the group should allow financial negative inventory, and that it should post physical inventory and financial inventory.</span></span> <span data-ttu-id="a9fcd-112">Este grupo de costes estándar se asignará a los artículos.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-112">This standard cost group will be assigned to items.</span></span>

<span data-ttu-id="a9fcd-113">**2. Defina las cuentas contables relacionadas con las desviaciones de coste estándar.**</span><span class="sxs-lookup"><span data-stu-id="a9fcd-113">**2. Define ledger accounts that are related to standard cost variances.**</span></span> 

<span data-ttu-id="a9fcd-114">Use la página **Plan de cuentas** para definir las cuentas contables relacionadas con las desviaciones de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-114">Use the **Chart of accounts** page to define ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="a9fcd-115">Estas cuentas contables deben definirse antes de que puedan asignarse en la página **Registro**.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-115">These ledger accounts must be defined before they can be assigned on the **Posting** page.</span></span> <span data-ttu-id="a9fcd-116">Las cuentas contables pueden reflejar grupos de artículos y grupos de coste.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-116">The ledger accounts can reflect item groups and cost groups.</span></span>

<span data-ttu-id="a9fcd-117">**3. Asigne cuentas contables a los registros de artículos relacionados con las desviaciones de coste estándar.**</span><span class="sxs-lookup"><span data-stu-id="a9fcd-117">**3. Assign ledger accounts to item postings that are related to standard cost variances.**</span></span> 

<span data-ttu-id="a9fcd-118">Use la página **Registro** para asignar las cuentas contables relacionadas con desviaciones de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-118">Use the **Posting** page to assign the ledger accounts that are related to standard cost variances.</span></span> <span data-ttu-id="a9fcd-119">Puede especificar la cuenta contable de la desviación por artículo (o grupo de artículos) y por grupo de costes (o tipo de grupo de costes), o puede especificar que la cuenta contable se aplicará a todos los artículos y todos los grupos de costes.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-119">You can specify a variance's ledger account by item (or item group) and by cost group (or cost group type), or you can specify that the ledger account applies to all items and all cost groups.</span></span> <span data-ttu-id="a9fcd-120">Estas opciones corresponden a las relaciones de coste para tablas, grupos y todo.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-120">These options correspond to cost relations for tables, groups, and all.</span></span> 

<span data-ttu-id="a9fcd-121">Antes de definir las reglas de registro de artículos, utilice la página **Combinaciones de transacción** para habilitar las relaciones de costes (para tablas, grupos y todo).</span><span class="sxs-lookup"><span data-stu-id="a9fcd-121">Before you define the item posting rules, use the **Transaction combinations** page to enable cost relations (for tables, groups, and all).</span></span>

<span data-ttu-id="a9fcd-122">**4. Defina los parámetros de inventario relacionados con los costes estándar.**</span><span class="sxs-lookup"><span data-stu-id="a9fcd-122">**4. Define inventory parameters that are related to standard costs.**</span></span> 

-  <span data-ttu-id="a9fcd-123">Utilice la pestaña **Contabilidad de inventario** en la página **Configuración de directivas de contabilidad de inventario > Parámetros** para definir los parámetros de control de costes relacionados con los costes estándar.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-123">Use the **Inventory accounting** tab on the **Inventory accounting policies setup > Parameters** page to define two cost control parameters that are related to standard costs.</span></span>

    -  <span data-ttu-id="a9fcd-124">En el campo **Análisis de costes**, seleccione **Ninguno** o **Sublibro de contabilidad**.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-124">In the **Cost breakdown** field, select **None** or **Sub ledger**.</span></span> <span data-ttu-id="a9fcd-125">Si selecciona **Sublibro de contabilidad**, el análisis de costes es un análisis de costes *activo* .</span><span class="sxs-lookup"><span data-stu-id="a9fcd-125">If you select **Sub ledger**, the cost breakdown is an *active* cost breakdown.</span></span> <span data-ttu-id="a9fcd-126">El análisis de costes activo es fundamental para calcular, conservar y ver la segmentación de grupos de costes en la estructura de productos de múltiples niveles de los artículos de costes estándar.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-126">An active cost breakdown is critical for calculating, retaining, and viewing cost group segmentation across a multilevel product structure for standard cost items.</span></span> <span data-ttu-id="a9fcd-127">La activación del análisis de costes le permite notificar y analizar el inventario, el trabajo en proceso (WIP) y el coste de las mercancías vendidas (COGS) por grupo de costes en un solo nivel, en múltiples niveles o en un formato único.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-127">When the cost breakdown is active, you can report and analyze inventory, work in process (WIP), and cost of goods sold (COGS) per cost group in a single-level, multilevel, or total format.</span></span> <span data-ttu-id="a9fcd-128">Cuando el análisis de costes es activo, si activa el cote del artículo fabricado, la segmentación de grupo de costes se almacenará en el registro de costes del artículo.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-128">When the cost breakdown is active, if you activate a manufactured item's cost, the cost group segmentation will be stored in the item's cost record.</span></span> 

    -  <span data-ttu-id="a9fcd-129">Si selecciona **Ninguno**, la segmentación del grupo de costes no se mantendrá para los artículos de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-129">If you select **None**, cost group segmentation won't be maintained for standard cost items.</span></span> <span data-ttu-id="a9fcd-130">Es decir, el coste estándar de un artículo fabricado se calculará y mantendrá como un importe único, sin la segmentación de grupos de costes.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-130">In other words, a manufactured item's standard cost will be calculated and maintained as a single amount, without cost group segmentation.</span></span> <span data-ttu-id="a9fcd-131">Las contribuciones de costes de los componentes fabricados se agregarán al importe único.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-131">The cost contributions of manufactured components will be aggregated into the single amount.</span></span>

-  <span data-ttu-id="a9fcd-132">En el campo **Desviaciones a estándar**, seleccione **Resumido** o **Por grupo de costes**.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-132">In the **Variances to standard** field, select **Summarized** or **Per cost group**.</span></span> <span data-ttu-id="a9fcd-133">Si selecciona **Por grupo de costes**, puede identificar desviaciones de precio de compra y desviaciones de producción por grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-133">If you select **Per cost group**, you can identify purchase price variances and production variances by cost group.</span></span> <span data-ttu-id="a9fcd-134">También puede identificar los cuatro tipos de desviaciones de producción: el tamaño de lote, la cantidad, el precio y las desviaciones de sustitución.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-134">You can also identify the four types of production variances: the lot size, quantity, price, and substitution variances.</span></span> <span data-ttu-id="a9fcd-135">Si selecciona **Resumido**, no podrá identificar las desviaciones por grupo de costes ni los cuatro tipos de desviaciones de la producción.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-135">If you select **Summarized**, you can't identify variances by cost group, and you can't identify the four types of production variances.</span></span> <span data-ttu-id="a9fcd-136">Solo podrá ver información resumida de las desviaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-136">You can just view a summarized production variance.</span></span>

-  <span data-ttu-id="a9fcd-137">Las directivas sobre desviaciones a estándar son independientes de las directivas de análisis de costes.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-137">The policy about variance to standard works independently of the cost breakdown policy.</span></span> <span data-ttu-id="a9fcd-138">Es decir, puede seleccionar una directiva de análisis de costes de **Ninguno** y seleccionar desviaciones por grupo de costes, de forma que sigan mostrándose las desviaciones de la producción por grupo de coste.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-138">In other words, you can select a cost breakdown policy of **None** and select variances per cost group, so that production variances by cost group will still be captured.</span></span>

<span data-ttu-id="a9fcd-139">**5. Cree versiones de gestión de costes para los costes estándar.**</span><span class="sxs-lookup"><span data-stu-id="a9fcd-139">**5. Create costing versions for standard costs.**</span></span> 

<span data-ttu-id="a9fcd-140">Use el formulario **Configuración de la versión de gestión de costes** para crear una o más versiones de gestión de costes para los costes estándar.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-140">Use the **Costing version setup** page to create one or more costing versions for standard costs.</span></span> <span data-ttu-id="a9fcd-141">A cada versión se debe designar un tipo de gestión de costes de **Costes estándar** y permitir contenido para incluir datos de coste.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-141">Each costing version must be designated by a costing type of **Standard cost** and must allow content to include cost data.</span></span>

<span data-ttu-id="a9fcd-142">**6. Preparar un cliente estándar para usar costes estándar.**</span><span class="sxs-lookup"><span data-stu-id="a9fcd-142">**6. Prepare an existing customer to use standard costs.**</span></span> 

<span data-ttu-id="a9fcd-143">Los clientes que deseen modificar sus artículos existentes a un modelo de inventario de costes estándar deberán usar la página **Conversiones de costes estándar**.</span><span class="sxs-lookup"><span data-stu-id="a9fcd-143">Customers who want to change their existing items to a standard cost inventory model must use the **Standard cost conversions** page.</span></span>


<a name="related-topics"></a><span data-ttu-id="a9fcd-144">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="a9fcd-144">Related topics</span></span>
--------

[<span data-ttu-id="a9fcd-145">Visión general de conversión de costes estándares</span><span class="sxs-lookup"><span data-stu-id="a9fcd-145">Standard cost conversion overview</span></span>](standard-cost-conversion-overview.md)

### <a name="blogs"></a><span data-ttu-id="a9fcd-146">Blogs</span><span class="sxs-lookup"><span data-stu-id="a9fcd-146">Blogs</span></span>

#### <a name="community-blogs"></a><span data-ttu-id="a9fcd-147">Blogs de la comunidad</span><span class="sxs-lookup"><span data-stu-id="a9fcd-147">Community blogs</span></span>

- [<span data-ttu-id="a9fcd-148">Cómo configurar los costes estándar de materiales directos en Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a9fcd-148">How to set up standard costs for direct materials in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/06/07/how-to-set-up-standard-costs-for-direct-materials-in-dynamics-365-for-finance-and-operations)
- [<span data-ttu-id="a9fcd-149">Costes laborales directos estándar en Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a9fcd-149">Standard direct labor costs in Dynamics 365 for Finance and Operations</span></span>](https://financefunction.tech/2018/07/16/standard-direct-labor-cost-in-dynamics-365-for-finance-and-operations)
