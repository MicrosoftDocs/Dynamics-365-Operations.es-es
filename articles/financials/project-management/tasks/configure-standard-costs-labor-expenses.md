---
title: Configuración de los costes estándar para el trabajo y los gastos
description: Este procedimiento muestra cómo configurar los costes estándar del trabajo y los gastos de un proyecto.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: b76956e9b1ce1a1e977aaa7c4974e73754e0d261
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845906"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a><span data-ttu-id="175fe-103">Configuración de los costes estándar para el trabajo y los gastos</span><span class="sxs-lookup"><span data-stu-id="175fe-103">Configure standard costs for labor and expenses</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="175fe-104">Este procedimiento muestra cómo configurar los costes estándar del trabajo y los gastos de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="175fe-104">This procedure shows you how to set up standard costs for labor and expenses for a project.</span></span> <span data-ttu-id="175fe-105">Esta tarea usa el conjunto de datos USSI.</span><span class="sxs-lookup"><span data-stu-id="175fe-105">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="175fe-106">Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (hora).</span><span class="sxs-lookup"><span data-stu-id="175fe-106">Go to Project management and accounting > Setup > Prices > Cost price (hour).</span></span>
2. <span data-ttu-id="175fe-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="175fe-107">Click New.</span></span>
3. <span data-ttu-id="175fe-108">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="175fe-108">In the Effective date field, enter a date.</span></span>
4. <span data-ttu-id="175fe-109">En el campo Precio de coste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="175fe-109">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="175fe-110">Puede configurar un precio de coste estándar para la categoría del proyecto o puede configurar un precio de coste por número de trabajador, número de proyecto, categoría, fecha o cualquier combinación de los anteriores.</span><span class="sxs-lookup"><span data-stu-id="175fe-110">You can set up a standard cost price for the project category, or you can set up a cost price by worker number, project number, category, date, or any combination of these.</span></span> <span data-ttu-id="175fe-111">El precio de coste que se aplica es el precio de coste con el mayor nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="175fe-111">The cost price that is applied is the cost price with the highest level of detail.</span></span>  
5. <span data-ttu-id="175fe-112">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="175fe-112">Click Save.</span></span>
6. <span data-ttu-id="175fe-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="175fe-113">Close the page.</span></span>
7. <span data-ttu-id="175fe-114">Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (hora).</span><span class="sxs-lookup"><span data-stu-id="175fe-114">Go to Project management and accounting > Setup > Prices > Sales price (hour).</span></span>
8. <span data-ttu-id="175fe-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="175fe-115">Click New.</span></span>
9. <span data-ttu-id="175fe-116">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="175fe-116">In the Effective date field, enter a date.</span></span>
10. <span data-ttu-id="175fe-117">En el campo Válido para, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="175fe-117">In the Valid for field, select an option.</span></span>
11. <span data-ttu-id="175fe-118">Escriba un número en el campo Precio.</span><span class="sxs-lookup"><span data-stu-id="175fe-118">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="175fe-119">Puede configurar un precio de ventas estándar para las transacciones por horas o para una categoría de proyecto.</span><span class="sxs-lookup"><span data-stu-id="175fe-119">You can set up a standard sales price for hour transactions or for a project category.</span></span> <span data-ttu-id="175fe-120">También puede configurar los precios de ventas por número de trabajador, número de proyecto, categoría, fecha de transacción o cualquier combinación de los anteriores.</span><span class="sxs-lookup"><span data-stu-id="175fe-120">You can also set up sales prices by worker number, project number, category, transaction date, or any combination of these.</span></span> <span data-ttu-id="175fe-121">El precio de venta real, que se aplica cuando un trabajador escribe una transacción en el diario de Horas, es el precio de venta con el mayor nivel de detalle.</span><span class="sxs-lookup"><span data-stu-id="175fe-121">The actual sales price, which is applied when a worker enters a transaction in the Hour journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="175fe-122">Por ejemplo, si están establecidos un precio de ventas general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.</span><span class="sxs-lookup"><span data-stu-id="175fe-122">For example, if both a general sales price and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
12. <span data-ttu-id="175fe-123">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="175fe-123">Click Save.</span></span>
13. <span data-ttu-id="175fe-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="175fe-124">Close the page.</span></span>
14. <span data-ttu-id="175fe-125">Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de coste (gasto).</span><span class="sxs-lookup"><span data-stu-id="175fe-125">Go to Project management and accounting > Setup > Prices > Cost price (expense).</span></span>
15. <span data-ttu-id="175fe-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="175fe-126">Click New.</span></span>
16. <span data-ttu-id="175fe-127">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="175fe-127">In the Effective date field, enter a date.</span></span>
17. <span data-ttu-id="175fe-128">En el campo Precio de coste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="175fe-128">In the Cost price field, enter a number.</span></span>
    * <span data-ttu-id="175fe-129">Se pueden rellenar distintos campos, pero éste es el mínimo necesario para guardar el registro.</span><span class="sxs-lookup"><span data-stu-id="175fe-129">Multiple fields can be filled in, but this is the minimum needed to save the record.</span></span>  
18. <span data-ttu-id="175fe-130">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="175fe-130">Click Save.</span></span>
19. <span data-ttu-id="175fe-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="175fe-131">Close the page.</span></span>
20. <span data-ttu-id="175fe-132">Vaya a Administración de proyectos y contabilidad > Configuración > Precios > Precio de venta (gasto).</span><span class="sxs-lookup"><span data-stu-id="175fe-132">Go to Project management and accounting > Setup > Prices > Sales price (expense).</span></span>
21. <span data-ttu-id="175fe-133">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="175fe-133">Click New.</span></span>
22. <span data-ttu-id="175fe-134">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="175fe-134">In the Effective date field, enter a date.</span></span>
23. <span data-ttu-id="175fe-135">En el campo Válido para, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="175fe-135">In the Valid for field, select an option.</span></span>
24. <span data-ttu-id="175fe-136">Escriba un número en el campo Precio.</span><span class="sxs-lookup"><span data-stu-id="175fe-136">In the Pricing field, enter a number.</span></span>
    * <span data-ttu-id="175fe-137">El precio de venta real, que se aplica cuando un trabajador especifica transacciones de gasto en un diario de gastos, es el precio de ventas con el nivel de detalle más alto.</span><span class="sxs-lookup"><span data-stu-id="175fe-137">The actual sales price, which is applied when a worker enters transactions in an expense journal, is the sales price with the highest level of detail.</span></span> <span data-ttu-id="175fe-138">Por ejemplo, si están establecidos un precio general y un precio de ventas específico de cada trabajador, se utiliza el precio de ventas específico del trabajador.</span><span class="sxs-lookup"><span data-stu-id="175fe-138">For example, if both a general and a worker-specific sales price are set up, the worker-specific sales price is used.</span></span>  
25. <span data-ttu-id="175fe-139">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="175fe-139">Click Save.</span></span>

