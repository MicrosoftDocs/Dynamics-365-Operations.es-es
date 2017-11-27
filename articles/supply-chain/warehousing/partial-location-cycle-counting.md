---
title: "Recuento cíclico de ubicaciones parcial"
description: "Los planes de recuento cíclico dirigen las operaciones de recuento. Puede solicitar que solo los productos específicos y las variantes de producto entren en el recuento en lugar de todos los inventarios disponibles en una ubicación."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0e0f9d81f4d5943a89d8ac87776e05acb32cb8d9
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="partial-location-cycle-counting"></a><span data-ttu-id="0ea24-104">Recuento cíclico de ubicaciones parcial</span><span class="sxs-lookup"><span data-stu-id="0ea24-104">Partial location cycle counting</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0ea24-105">Los planes de recuento cíclico dirigen las operaciones de recuento.</span><span class="sxs-lookup"><span data-stu-id="0ea24-105">Cycle count plans guide the actual counting operations.</span></span> <span data-ttu-id="0ea24-106">Puede solicitar que solo los productos específicos y las variantes de producto entren en el recuento en lugar de todos los inventarios disponibles en una ubicación.</span><span class="sxs-lookup"><span data-stu-id="0ea24-106">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span>

<span data-ttu-id="0ea24-107">Si utiliza los planes de recuento cíclico para crear trabajos de recuento, puede dirigir las operaciones que recuento reales.</span><span class="sxs-lookup"><span data-stu-id="0ea24-107">By using cycle count plans to create counting work, you can guide the actual counting operations.</span></span> <span data-ttu-id="0ea24-108">Puede solicitar que solo los productos específicos y las variantes de producto entren en el recuento en lugar de todos los inventarios disponibles en una ubicación.</span><span class="sxs-lookup"><span data-stu-id="0ea24-108">You can request that only specific products and product variants be counted instead of all on-hand inventory in a location.</span></span> <span data-ttu-id="0ea24-109">Al filtrar según productos específicos, el responsable del almacén puede reducir los costes generales de revisión, evitar errores de consolidación y ahorrar tiempo.</span><span class="sxs-lookup"><span data-stu-id="0ea24-109">By filtering on specific products, the warehouse manager can reduce review overhead, avoid consolidation mistakes, and save time.</span></span>

## <a name="how-to-configure-partial-location-cycle-counting"></a><span data-ttu-id="0ea24-110">Cómo configurar el recuento cíclico de ubicación parcial</span><span class="sxs-lookup"><span data-stu-id="0ea24-110">How to configure partial location cycle counting</span></span>
<span data-ttu-id="0ea24-111">Cuando se usa el proceso de trabajo de almacén para contar operaciones, un encabezado de trabajo se crea para cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="0ea24-111">When you use the warehouse work process for counting operations, a work header is created for each location.</span></span> <span data-ttu-id="0ea24-112">Al definir el plan de ciclo de recuento, puede usar la consulta **Seleccionar ubicaciones** para limitar trabajo de recuento cíclico que se crea.</span><span class="sxs-lookup"><span data-stu-id="0ea24-112">When you define the cycle count plan, you can use the **Select locations** query to limit the cycle counting work that is created.</span></span> <span data-ttu-id="0ea24-113">Al seleccionar los productos para el plan de recuento cíclico, puede seleccionar las consultas de producto y de la variante del producto para limitar lo que entra en el recuento.</span><span class="sxs-lookup"><span data-stu-id="0ea24-113">When you select products for the cycle count plan, you can select both product and product variant queries to refine what is counted.</span></span> 

<span data-ttu-id="0ea24-114">Puede asociar una **plantilla de trabajo** a un plan de recuento cíclico para definir cómo debe crearse el trabajo de recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="0ea24-114">You can associate a **work template** with a cycle count plan to define how the cycle count work should be created.</span></span> <span data-ttu-id="0ea24-115">La plantilla del trabajo para las operaciones de recuento se referencia directamente desde el plan de recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="0ea24-115">The work template for counting operations is directly referenced from the cycle count plan.</span></span> 

<span data-ttu-id="0ea24-116">Cuando defina los detalles de la plantilla de trabajo, puede usar la opción **Saltos de línea de trabajo** para especificar si las líneas de trabajo deben agruparse por número de artículo o número de la variante del producto.</span><span class="sxs-lookup"><span data-stu-id="0ea24-116">When you define the work template details, you can use the **Work line breaks** option to specify whether the counting work lines must be grouped by item number or product variant number.</span></span> <span data-ttu-id="0ea24-117">Se requiere esta configuración si desea hacer el recuento del inventario disponible para los productos específicos en una ubicación.</span><span class="sxs-lookup"><span data-stu-id="0ea24-117">This setup is required if you want to count on-hand inventory only for specific products in a location.</span></span> <span data-ttu-id="0ea24-118">Las líneas de trabajo de recuento cíclico que se crean que tendrá el nivel de información que defina aquí, y la operación de recuento dirigida será administrada en función de este nivel.</span><span class="sxs-lookup"><span data-stu-id="0ea24-118">The cycle counting work lines that are created will have the level of information that you define here, and the guided counting operation will be handled based on this level.</span></span> 

<span data-ttu-id="0ea24-119">Si asocia planes de recuento cíclico a las plantillas de trabajo mediante la opción **Saltos de líneas de trabajo**, el campo **Recuento cíclico parcial** se ha activado para el trabajo de recuento cíclico que se crea, y las líneas de trabajo de recuento cíclico se crearán en función de la definición de la plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0ea24-119">If you associate cycle count plans with work templates by using the **Work lines breaks** option, the **Partial cycle count** field is selected for the cycle counting work that is created, and multiple cycle counting work lines will be created based on the definition of the work template.</span></span> 

<span data-ttu-id="0ea24-120">Antes de que el trabajo de recuento cíclico parcial se pueda procesar, debe, al menos, seleccionar **Mostrar número de artículo** para el elemento de menú del dispositivo móvil como parte de la configuración del recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="0ea24-120">Before partial cycle count work can be processed, you must, at a minimum, select **Display item number** for the mobile device menu item as part of the cycle counting setup.</span></span> <span data-ttu-id="0ea24-121">Se pedirá al operador de almacenes que registre solo la información del recuento relacionada con las líneas de recuento (números de artículo y dimensiones del producto).</span><span class="sxs-lookup"><span data-stu-id="0ea24-121">The warehouse operator will be asked to record only counting information that is related to the counting lines (item numbers and product dimensions).</span></span> <span data-ttu-id="0ea24-122">El resto del inventario disponible será omitido para este proceso de recuento.</span><span class="sxs-lookup"><span data-stu-id="0ea24-122">All other on-hand inventory will be ignored for this counting process.</span></span> 

<span data-ttu-id="0ea24-123">Para el proceso de recuento cíclico parcial, la fecha o la hora de **Último recuento cíclico** no se actualizará para la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0ea24-123">For the partial cycle count process, the **Last cycle count** date/time won’t be updated for the location.</span></span>

## <a name="example"></a><span data-ttu-id="0ea24-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0ea24-124">Example</span></span>
<span data-ttu-id="0ea24-125">Para este ejemplo, solo se debe contar el número de artículo A0001 en el almacén 61.</span><span class="sxs-lookup"><span data-stu-id="0ea24-125">For this example, only item number A0001 must be counted in warehouse 61.</span></span>

1.  <span data-ttu-id="0ea24-126">Se crea una plantilla de trabajo nueva para el recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="0ea24-126">A new work template for cycle counting is created.</span></span> <span data-ttu-id="0ea24-127">La opción **Saltos de línea de trabajo** se usa para agrupar líneas de trabajo de recuento para el número de artículo.</span><span class="sxs-lookup"><span data-stu-id="0ea24-127">The **Work line breaks** option is used to group counting work lines by item number.</span></span> <span data-ttu-id="0ea24-128">Por lo tanto, el trabajo de recuento cíclico que se crea tendrá líneas por número de artículo.</span><span class="sxs-lookup"><span data-stu-id="0ea24-128">Therefore, the cycle counting work that is created will have lines per item number.</span></span> <span data-ttu-id="0ea24-129">También puede agrupar las líneas por número de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="0ea24-129">You can also group the lines by product variant number.</span></span>
2.  <span data-ttu-id="0ea24-130">Un nuevo plan de recuento cíclico se crea que hace referencia a la plantilla de trabajo recién creada.</span><span class="sxs-lookup"><span data-stu-id="0ea24-130">A new cycle counting plan is created that references the newly created work template.</span></span> <span data-ttu-id="0ea24-131">El plan de recuento cíclico incluye todas las ubicaciones en el almacén 61 (consulta **Seleccionar ubicaciones**) que se retienen en inventario para el número de artículo A0001.</span><span class="sxs-lookup"><span data-stu-id="0ea24-131">The cycle counting plan includes all locations in warehouse 61 (**Select locations** query) that hold inventory for item number A0001.</span></span> <span data-ttu-id="0ea24-132">La selección de productos específicos se define en la sección **Selecciones producto de recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="0ea24-132">The selection of specific products is defined in the **Cycle count product selections** section.</span></span>
3.  <span data-ttu-id="0ea24-133">Puede seleccionar productos para sus planes de recuento cíclico estableciendo el campo **Ubicaciones vacías** **Excluir vacío**.</span><span class="sxs-lookup"><span data-stu-id="0ea24-133">You can select products for cycle counting plans by setting the **Empty locations** field to **Exclude empty**.</span></span> <span data-ttu-id="0ea24-134">Cuando el plan de recuento cíclico se procesa, se crea el trabajo de recuento cíclico parcial para el número de artículo A0001.</span><span class="sxs-lookup"><span data-stu-id="0ea24-134">When the cycle counting plan is processed, partial cycle count work for item number A0001 is created.</span></span> <span data-ttu-id="0ea24-135">El proceso de recuento real se puede realizar mediante un elemento de menú del dispositivo móvil para el recuento cíclico dirigido.</span><span class="sxs-lookup"><span data-stu-id="0ea24-135">The actual counting process can be performed by using a mobile device menu item for guided cycle counting.</span></span>



<a name="see-also"></a><span data-ttu-id="0ea24-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0ea24-136">See also</span></span>
--------

[<span data-ttu-id="0ea24-137">Recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="0ea24-137">Cycle counting</span></span>](cycle-counting.md)


