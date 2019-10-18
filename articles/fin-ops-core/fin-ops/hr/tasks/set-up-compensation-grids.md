---
title: Configuración de cuadrículas de compensación
description: Las cuadrículas de compensación se usan para definir y mantener las estructuras de pagos para los planes de compensación fija.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRCCompGrid, HRCCompGridView
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f0caebb2dfbff12545610aa6438dccbec84db3f9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190359"
---
# <a name="set-up-compensation-grids"></a><span data-ttu-id="6dd31-103">Configuración de cuadrículas de compensación</span><span class="sxs-lookup"><span data-stu-id="6dd31-103">Set up compensation grids</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6dd31-104">Las cuadrículas de compensación se usan para definir y mantener las estructuras de pagos para los planes de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="6dd31-104">Compensation grids are used to define and maintain the pay structures for fixed compensation plans.</span></span> <span data-ttu-id="6dd31-105">Las cuadrículas de compensación se pueden compartir entre varios planes o copiarse al crear un nuevo plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="6dd31-105">Compensation grids can be shared between multiple plans or copied when creating a new compensation plan.</span></span>  <span data-ttu-id="6dd31-106">Antes de crear una cuadrícula de compensación, los niveles y los puntos de referencia deben estar configurados.</span><span class="sxs-lookup"><span data-stu-id="6dd31-106">Before creating a compensation grid, Levels and Reference points must be set up.</span></span> <span data-ttu-id="6dd31-107">Este ejemplo creará un nuevo tipo de categoría de cuadrícula de compensación con los datos de demostración para los niveles y los puntos de referencia.</span><span class="sxs-lookup"><span data-stu-id="6dd31-107">This example will create a new Grade type of compensation grid using demo data for the Levels and Reference points.</span></span> <span data-ttu-id="6dd31-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="6dd31-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-information-about-the-compensation-grid"></a><span data-ttu-id="6dd31-109">Configurar información sobre la cuadrícula de compensación</span><span class="sxs-lookup"><span data-stu-id="6dd31-109">Set up information about the compensation grid</span></span>
1. <span data-ttu-id="6dd31-110">Vaya a Recursos humanos > Compensación > Compensación fija > Cuadrículas de compensación.</span><span class="sxs-lookup"><span data-stu-id="6dd31-110">Go to Human resources > Compensation > Fixed compensation > Compensation grids.</span></span>
2. <span data-ttu-id="6dd31-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6dd31-111">Click New.</span></span>
3. <span data-ttu-id="6dd31-112">En el campo Cuadrícula, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-112">In the Grid field, type a value.</span></span>
4. <span data-ttu-id="6dd31-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="6dd31-114">En el campo Tipo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="6dd31-114">In the Type field, select an option.</span></span>
6. <span data-ttu-id="6dd31-115">En el campo Configuración de referencia, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-115">In the Reference setup field, enter or select a value.</span></span>
7. <span data-ttu-id="6dd31-116">En el campo Divisa, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-116">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="6dd31-117">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-117">In the Currency field, type a value.</span></span>
9. <span data-ttu-id="6dd31-118">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="6dd31-118">In the Effective date field, enter a date.</span></span>

## <a name="add-levels-to-the-compensation-structure"></a><span data-ttu-id="6dd31-119">Agregar niveles a la estructura de compensación</span><span class="sxs-lookup"><span data-stu-id="6dd31-119">Add levels to the compensation structure</span></span>
1. <span data-ttu-id="6dd31-120">Haga clic en Estructura de compensación.</span><span class="sxs-lookup"><span data-stu-id="6dd31-120">Click Compensation structure.</span></span>
2. <span data-ttu-id="6dd31-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6dd31-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="6dd31-122">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-122">In the Level field, enter or select a value.</span></span>
4. <span data-ttu-id="6dd31-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6dd31-123">Click New.</span></span>
5. <span data-ttu-id="6dd31-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6dd31-124">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="6dd31-125">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-125">In the Level field, enter or select a value.</span></span>
7. <span data-ttu-id="6dd31-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6dd31-126">Click New.</span></span>
8. <span data-ttu-id="6dd31-127">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6dd31-127">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="6dd31-128">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-128">In the Level field, enter or select a value.</span></span>
10. <span data-ttu-id="6dd31-129">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6dd31-129">Click New.</span></span>
11. <span data-ttu-id="6dd31-130">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6dd31-130">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="6dd31-131">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-131">In the Level field, enter or select a value.</span></span>
13. <span data-ttu-id="6dd31-132">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6dd31-132">Click New.</span></span>
14. <span data-ttu-id="6dd31-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6dd31-133">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="6dd31-134">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-134">In the Level field, enter or select a value.</span></span>

## <a name="fill-in-the-compensation-structure-with-values"></a><span data-ttu-id="6dd31-135">Rellenar la estructura de compensación con valores</span><span class="sxs-lookup"><span data-stu-id="6dd31-135">Fill in the compensation structure with values</span></span>
1. <span data-ttu-id="6dd31-136">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6dd31-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="6dd31-137">En este momento, los valores de compensación se pueden especificar manualmente en cada campo de la tabla o la funcionalidad de cambio masivo se puede usar para rellenar fácilmente varios campos y realizar cálculos básicos.</span><span class="sxs-lookup"><span data-stu-id="6dd31-137">At this point, compensation values can manually be entered into each field in the table, or the Mass change functionality can be used to easily fill in multiple fields and perform basic calculations.</span></span>  
2. <span data-ttu-id="6dd31-138">Haga clic en Cambio masivo.</span><span class="sxs-lookup"><span data-stu-id="6dd31-138">Click Mass change.</span></span>
    * <span data-ttu-id="6dd31-139">Para esta cuadrícula, aplicaremos primero el valor para punto medio del primer nivel a todos los campos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6dd31-139">For this grid, we'll first apply the value for the midpoint of the first level's to all the fields in the table.</span></span> <span data-ttu-id="6dd31-140">Esta será la base para la matriz de compensación.</span><span class="sxs-lookup"><span data-stu-id="6dd31-140">This will be the basis for the compensation matrix.</span></span>  
3. <span data-ttu-id="6dd31-141">En el campo Tipo de ajuste, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="6dd31-141">In the Adjustment type field, select an option.</span></span>
4. <span data-ttu-id="6dd31-142">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="6dd31-142">In the Adjustment amount field, enter a number.</span></span>
5. <span data-ttu-id="6dd31-143">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="6dd31-143">In the list, mark or unmark all rows.</span></span>
6. <span data-ttu-id="6dd31-144">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6dd31-144">Click Apply to grid.</span></span>
    * <span data-ttu-id="6dd31-145">Ahora utilizaremos la función de cambio masivo para incrementar los importes en cada nivel posterior por un porcentaje o importe determinado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-145">Now we'll use the mass change function to increment the amounts in each subsequent level by a certain percentage or amount.</span></span> <span data-ttu-id="6dd31-146">En este ejemplo, cada categoría tendrá una propagación del 12,5 % entre los puntos medios.</span><span class="sxs-lookup"><span data-stu-id="6dd31-146">In this example, each grade will have a 12.5% spread between their midpoints.</span></span>  
7. <span data-ttu-id="6dd31-147">En el campo Tipo de ajuste, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="6dd31-147">In the Adjustment type field, select an option.</span></span>
8. <span data-ttu-id="6dd31-148">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="6dd31-148">In the Adjustment amount field, enter a number.</span></span>
9. <span data-ttu-id="6dd31-149">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-149">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="6dd31-150">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-150">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="6dd31-151">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-151">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="6dd31-152">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-152">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="6dd31-153">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6dd31-153">Click Apply to grid.</span></span>
14. <span data-ttu-id="6dd31-154">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-154">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="6dd31-155">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-155">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="6dd31-156">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-156">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="6dd31-157">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6dd31-157">Click Apply to grid.</span></span>
18. <span data-ttu-id="6dd31-158">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-158">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="6dd31-159">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-159">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="6dd31-160">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6dd31-160">Click Apply to grid.</span></span>
21. <span data-ttu-id="6dd31-161">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6dd31-161">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="6dd31-162">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6dd31-162">Click Apply to grid.</span></span>
    * <span data-ttu-id="6dd31-163">Ahora utilizaremos la función de cambio masivo para ajustar los puntos de referencia mínimo y máximo para cada nivel.</span><span class="sxs-lookup"><span data-stu-id="6dd31-163">Now we'll use the mass change function to adjust the Minimum and Maximum reference points for each level.</span></span> <span data-ttu-id="6dd31-164">Este ejemplo utilizará una propagación del 50 % de manera que el punto de referencia mínimo se ajustará un -20 % y el máximo se ajustará un +20 %.</span><span class="sxs-lookup"><span data-stu-id="6dd31-164">This example will use a 50% spread so the Minimum reference point will be adjusted -20% and the Maximum will be adjusted +20%.</span></span>  
23. <span data-ttu-id="6dd31-165">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="6dd31-165">In the Adjustment amount field, enter a number.</span></span>
24. <span data-ttu-id="6dd31-166">En el campo Punto de referencia, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-166">In the Reference point field, enter or select a value.</span></span>
25. <span data-ttu-id="6dd31-167">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="6dd31-167">In the list, mark or unmark all rows.</span></span>
26. <span data-ttu-id="6dd31-168">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6dd31-168">Click Apply to grid.</span></span>
27. <span data-ttu-id="6dd31-169">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="6dd31-169">In the Adjustment amount field, enter a number.</span></span>
28. <span data-ttu-id="6dd31-170">En el campo Punto de referencia, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6dd31-170">In the Reference point field, enter or select a value.</span></span>
29. <span data-ttu-id="6dd31-171">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="6dd31-171">In the list, mark or unmark all rows.</span></span>
30. <span data-ttu-id="6dd31-172">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6dd31-172">Click Apply to grid.</span></span>

