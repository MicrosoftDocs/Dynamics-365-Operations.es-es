--- 
title: "Creación de un plan de materiales para coproductos"
description: "El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula."
author: YuyuScheller
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c8805ca02525ae001fbd5e10ad9405fe60c7473e
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="8e005-103">Creación de un plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="8e005-103">Create a material plan for co-products</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8e005-104">El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="8e005-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="8e005-105">La empresa de datos de demostración utilizada para crear este procedimiento es USP2.</span><span class="sxs-lookup"><span data-stu-id="8e005-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="8e005-106">Creación de un requisito para un coproducto</span><span class="sxs-lookup"><span data-stu-id="8e005-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="8e005-107">Vaya al panel predeterminado.</span><span class="sxs-lookup"><span data-stu-id="8e005-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="8e005-108">Haga clic en Consulta y procesamiento de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="8e005-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="8e005-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8e005-109">Click New.</span></span>
4. <span data-ttu-id="8e005-110">Haga clic en Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="8e005-110">Click Sales order.</span></span>
5. <span data-ttu-id="8e005-111">En el campo Cuenta de cliente, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e005-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="8e005-112">Ejemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="8e005-112">Example: US-001</span></span>  
6. <span data-ttu-id="8e005-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8e005-113">Click OK.</span></span>
7. <span data-ttu-id="8e005-114">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e005-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="8e005-115">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="8e005-115">Example: P6003</span></span>  
8. <span data-ttu-id="8e005-116">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="8e005-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="8e005-117">Ejemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="8e005-117">Example: 50000</span></span>  
9. <span data-ttu-id="8e005-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="8e005-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="8e005-119">Creación de un plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="8e005-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="8e005-120">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="8e005-120">Click Master planning.</span></span>
2. <span data-ttu-id="8e005-121">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="8e005-121">In the Plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="8e005-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8e005-122">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8e005-123">Ejemplo: Plan maestro</span><span class="sxs-lookup"><span data-stu-id="8e005-123">Example: MasterPlan</span></span>  
4. <span data-ttu-id="8e005-124">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="8e005-124">Click Run.</span></span>
5. <span data-ttu-id="8e005-125">Expanda o contraiga la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="8e005-125">Expand or collapse the Records to include section.</span></span>
6. <span data-ttu-id="8e005-126">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="8e005-126">Click Filter.</span></span>
7. <span data-ttu-id="8e005-127">En la lista, seleccione la fila para Campo = Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="8e005-127">In the list, select the row for Field = Item number.</span></span>
8. <span data-ttu-id="8e005-128">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8e005-128">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="8e005-129">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="8e005-129">Example: P6003</span></span>  
9. <span data-ttu-id="8e005-130">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8e005-130">Click OK.</span></span>
10. <span data-ttu-id="8e005-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8e005-131">Click OK.</span></span>
11. <span data-ttu-id="8e005-132">Haga clic en Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="8e005-132">Click Planned orders.</span></span>
12. <span data-ttu-id="8e005-133">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="8e005-133">Use the Quick Filter to find records.</span></span> <span data-ttu-id="8e005-134">Por ejemplo, filtre por el campo Número de artículo con un valor de "P6000".</span><span class="sxs-lookup"><span data-stu-id="8e005-134">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="8e005-135">Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="8e005-135">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
13. <span data-ttu-id="8e005-136">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8e005-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="8e005-137">Seleccione cualquiera de las filas que haya devuelto el filtro.</span><span class="sxs-lookup"><span data-stu-id="8e005-137">Select any of the rows returned by the filter.</span></span>  
14. <span data-ttu-id="8e005-138">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8e005-138">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="8e005-139">Expanda o contraiga la sección Diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="8e005-139">Expand or collapse the Pegging section.</span></span>
16. <span data-ttu-id="8e005-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8e005-140">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8e005-141">El pedido planificado se adjunta al pedido de ventas para el coproducto.</span><span class="sxs-lookup"><span data-stu-id="8e005-141">The planned order is pegged to the sales order for the co-product.</span></span>  
17. <span data-ttu-id="8e005-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8e005-142">Close the page.</span></span>


