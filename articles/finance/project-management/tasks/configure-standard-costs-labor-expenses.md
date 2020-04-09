---
title: Configuración de los costes estándar para el trabajo y los gastos
description: Este tema explica cómo configurar los costes estándar del trabajo y los gastos de un proyecto.
author: KimANelson
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51bbe52d70bae11cb0c95e9544f951f0fcc605f5
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140102"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="82a6e-103">Configuración de los costes estándar para el trabajo y los gastos</span><span class="sxs-lookup"><span data-stu-id="82a6e-103">Configure standard costs for labor and expenses</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82a6e-104">Este tema explica cómo configurar los costes estándar del trabajo y los gastos de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="82a6e-104">This topic explains how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="82a6e-105">Esta tarea usa el conjunto de datos USSI.</span><span class="sxs-lookup"><span data-stu-id="82a6e-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="82a6e-106">En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de coste (hora)**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-106">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (hour)**.</span></span>
2. <span data-ttu-id="82a6e-107">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-107">Select **New**.</span></span>
3. <span data-ttu-id="82a6e-108">En el campo **Fecha de vigencia**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="82a6e-108">In the **Effective date** field, enter a date.</span></span>
4. <span data-ttu-id="82a6e-109">En el campo **Precio de coste**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="82a6e-109">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="82a6e-110">Puede configurar un precio de coste estándar para la categoría del proyecto o puede configurar un precio de coste por número de trabajador, número de proyecto, categoría, fecha o cualquier combinación de los anteriores.</span><span class="sxs-lookup"><span data-stu-id="82a6e-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="82a6e-111">El precio de coste que se aplica es el precio de coste con el mayor nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="82a6e-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="82a6e-112">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-112">Select **Save**.</span></span>
6. <span data-ttu-id="82a6e-113">En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (hora)**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-113">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (hour)**.</span></span>
7. <span data-ttu-id="82a6e-114">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-114">Select **New**.</span></span>
8. <span data-ttu-id="82a6e-115">En el campo **Fecha de vigencia**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="82a6e-115">In the **Effective date** field, enter a date.</span></span>
9. <span data-ttu-id="82a6e-116">En el campo **Válido para**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="82a6e-116">In the **Valid for** field, select an option.</span></span>
10. <span data-ttu-id="82a6e-117">Escriba un número en el campo **Precio**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-117">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="82a6e-118">Puede configurar un precio de ventas estándar para las transacciones por horas o para una categoría de proyecto.</span><span class="sxs-lookup"><span data-stu-id="82a6e-118">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="82a6e-119">También puede configurar los precios de ventas por número de trabajador, número de proyecto, categoría, fecha de transacción o cualquier combinación de los anteriores.</span><span class="sxs-lookup"><span data-stu-id="82a6e-119">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="82a6e-120">El precio de venta real, que se aplica cuando un trabajador escribe una transacción en el diario de Horas, es el precio de venta con el mayor nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="82a6e-120">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="82a6e-121">Por ejemplo, si están establecidos un precio de ventas general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.</span><span class="sxs-lookup"><span data-stu-id="82a6e-121">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
11. <span data-ttu-id="82a6e-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-122">Select **Save**.</span></span>
12. <span data-ttu-id="82a6e-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="82a6e-123">Close the page.</span></span>
13. <span data-ttu-id="82a6e-124">En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de coste (gasto)**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-124">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Cost price (expense)**.</span></span>
14. <span data-ttu-id="82a6e-125">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-125">Select **New**.</span></span>
15. <span data-ttu-id="82a6e-126">En el campo **Fecha de vigencia**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="82a6e-126">In the **Effective date** field, enter a date.</span></span>
16. <span data-ttu-id="82a6e-127">En el campo **Precio de coste**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="82a6e-127">In the **Cost price** field, enter a number.</span></span> <span data-ttu-id="82a6e-128">Se pueden rellenar distintos campos, pero éste es el mínimo necesario para guardar el registro.</span><span class="sxs-lookup"><span data-stu-id="82a6e-128">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
17. <span data-ttu-id="82a6e-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-129">Select **Save**.</span></span>
18. <span data-ttu-id="82a6e-130">En el panel de exploración, vaya a **Módulos > Administración de proyectos y contabilidad > Configuración > Precios > Precio de ventas (gasto)**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-130">In the navigation pane, go to **Modules > Project management and accounting > Setup > Prices > Sales price (expense)**.</span></span>
19. <span data-ttu-id="82a6e-131">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-131">Select **New**.</span></span>
20. <span data-ttu-id="82a6e-132">En el campo **Fecha de vigencia**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="82a6e-132">In the **Effective date** field, enter a date.</span></span>
21. <span data-ttu-id="82a6e-133">En el campo **Válido para**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="82a6e-133">In the **Valid for** field, select an option.</span></span>
22. <span data-ttu-id="82a6e-134">Escriba un número en el campo **Precio**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-134">In the **Pricing** field, enter a number.</span></span> <span data-ttu-id="82a6e-135">El precio de venta real, que se aplica cuando un trabajador especifica transacciones de gasto en un diario de gastos, es el precio de ventas con el nivel de detalle más alto.</span><span class="sxs-lookup"><span data-stu-id="82a6e-135">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="82a6e-136">Por ejemplo, si están establecidos un precio general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.</span><span class="sxs-lookup"><span data-stu-id="82a6e-136">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
23. <span data-ttu-id="82a6e-137">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="82a6e-137">Select **Save**.</span></span>

