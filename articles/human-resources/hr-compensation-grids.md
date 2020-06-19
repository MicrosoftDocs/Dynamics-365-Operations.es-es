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
ms.search.form: HRCCompGrid, HRCCompGridView, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5d5ada0817dd73caad38bb2e50302869857c71d8
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3430587"
---
# <a name="set-up-compensation-grids"></a><span data-ttu-id="cab3f-103">Configuración de cuadrículas de compensación</span><span class="sxs-lookup"><span data-stu-id="cab3f-103">Set up compensation grids</span></span>

<span data-ttu-id="cab3f-104">Las cuadrículas de compensación se usan para definir y mantener las estructuras de pagos para los planes de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="cab3f-104">Compensation grids are used to define and maintain the pay structures for fixed compensation plans.</span></span> <span data-ttu-id="cab3f-105">Las cuadrículas de compensación se pueden compartir entre varios planes o copiarse al crear un nuevo plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="cab3f-105">Compensation grids can be shared between multiple plans or copied when creating a new compensation plan.</span></span>  <span data-ttu-id="cab3f-106">Antes de crear una cuadrícula de compensación, los niveles y los puntos de referencia deben estar configurados.</span><span class="sxs-lookup"><span data-stu-id="cab3f-106">Before creating a compensation grid, Levels and Reference points must be set up.</span></span> <span data-ttu-id="cab3f-107">Este ejemplo creará un nuevo tipo de categoría de cuadrícula de compensación con los datos de demostración para los niveles y los puntos de referencia.</span><span class="sxs-lookup"><span data-stu-id="cab3f-107">This example will create a new Grade type of compensation grid using demo data for the Levels and Reference points.</span></span> <span data-ttu-id="cab3f-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="cab3f-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-information-about-the-compensation-grid"></a><span data-ttu-id="cab3f-109">Configurar información sobre la cuadrícula de compensación</span><span class="sxs-lookup"><span data-stu-id="cab3f-109">Set up information about the compensation grid</span></span>
1. <span data-ttu-id="cab3f-110">Vaya a Recursos humanos > Compensación > Compensación fija > Cuadrículas de compensación.</span><span class="sxs-lookup"><span data-stu-id="cab3f-110">Go to Human resources > Compensation > Fixed compensation > Compensation grids.</span></span>
2. <span data-ttu-id="cab3f-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cab3f-111">Click New.</span></span>
3. <span data-ttu-id="cab3f-112">En el campo Cuadrícula, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-112">In the Grid field, type a value.</span></span>
4. <span data-ttu-id="cab3f-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="cab3f-114">En el campo Tipo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cab3f-114">In the Type field, select an option.</span></span>
6. <span data-ttu-id="cab3f-115">En el campo Configuración de referencia, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-115">In the Reference setup field, enter or select a value.</span></span>
7. <span data-ttu-id="cab3f-116">En el campo Divisa, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-116">In the Currency field, enter or select a value.</span></span>
8. <span data-ttu-id="cab3f-117">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-117">In the Currency field, type a value.</span></span>
9. <span data-ttu-id="cab3f-118">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="cab3f-118">In the Effective date field, enter a date.</span></span>

## <a name="add-levels-to-the-compensation-structure"></a><span data-ttu-id="cab3f-119">Agregar niveles a la estructura de compensación</span><span class="sxs-lookup"><span data-stu-id="cab3f-119">Add levels to the compensation structure</span></span>
1. <span data-ttu-id="cab3f-120">Haga clic en Estructura de compensación.</span><span class="sxs-lookup"><span data-stu-id="cab3f-120">Click Compensation structure.</span></span>
2. <span data-ttu-id="cab3f-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cab3f-121">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="cab3f-122">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-122">In the Level field, enter or select a value.</span></span>
4. <span data-ttu-id="cab3f-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cab3f-123">Click New.</span></span>
5. <span data-ttu-id="cab3f-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cab3f-124">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="cab3f-125">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-125">In the Level field, enter or select a value.</span></span>
7. <span data-ttu-id="cab3f-126">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cab3f-126">Click New.</span></span>
8. <span data-ttu-id="cab3f-127">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cab3f-127">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="cab3f-128">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-128">In the Level field, enter or select a value.</span></span>
10. <span data-ttu-id="cab3f-129">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cab3f-129">Click New.</span></span>
11. <span data-ttu-id="cab3f-130">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cab3f-130">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="cab3f-131">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-131">In the Level field, enter or select a value.</span></span>
13. <span data-ttu-id="cab3f-132">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="cab3f-132">Click New.</span></span>
14. <span data-ttu-id="cab3f-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cab3f-133">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="cab3f-134">En el campo Nivel, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-134">In the Level field, enter or select a value.</span></span>

## <a name="fill-in-the-compensation-structure-with-values"></a><span data-ttu-id="cab3f-135">Rellenar la estructura de compensación con valores</span><span class="sxs-lookup"><span data-stu-id="cab3f-135">Fill in the compensation structure with values</span></span>
1. <span data-ttu-id="cab3f-136">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cab3f-136">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="cab3f-137">En este momento, los valores de compensación se pueden especificar manualmente en cada campo de la tabla o la funcionalidad de cambio masivo se puede usar para rellenar fácilmente varios campos y realizar cálculos básicos.</span><span class="sxs-lookup"><span data-stu-id="cab3f-137">At this point, compensation values can manually be entered into each field in the table, or the Mass change functionality can be used to easily fill in multiple fields and perform basic calculations.</span></span>  
2. <span data-ttu-id="cab3f-138">Haga clic en Cambio masivo.</span><span class="sxs-lookup"><span data-stu-id="cab3f-138">Click Mass change.</span></span>
    * <span data-ttu-id="cab3f-139">Para esta cuadrícula, aplicaremos primero el valor para punto medio del primer nivel a todos los campos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="cab3f-139">For this grid, we'll first apply the value for the midpoint of the first level's to all the fields in the table.</span></span> <span data-ttu-id="cab3f-140">Esta será la base para la matriz de compensación.</span><span class="sxs-lookup"><span data-stu-id="cab3f-140">This will be the basis for the compensation matrix.</span></span>  
3. <span data-ttu-id="cab3f-141">En el campo Tipo de ajuste, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cab3f-141">In the Adjustment type field, select an option.</span></span>
4. <span data-ttu-id="cab3f-142">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cab3f-142">In the Adjustment amount field, enter a number.</span></span>
5. <span data-ttu-id="cab3f-143">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="cab3f-143">In the list, mark or unmark all rows.</span></span>
6. <span data-ttu-id="cab3f-144">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="cab3f-144">Click Apply to grid.</span></span>
    * <span data-ttu-id="cab3f-145">Ahora utilizaremos la función de cambio masivo para incrementar los importes en cada nivel posterior por un porcentaje o importe determinado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-145">Now we'll use the mass change function to increment the amounts in each subsequent level by a certain percentage or amount.</span></span> <span data-ttu-id="cab3f-146">En este ejemplo, cada categoría tendrá una propagación del 12,5 % entre los puntos medios.</span><span class="sxs-lookup"><span data-stu-id="cab3f-146">In this example, each grade will have a 12.5% spread between their midpoints.</span></span>  
7. <span data-ttu-id="cab3f-147">En el campo Tipo de ajuste, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="cab3f-147">In the Adjustment type field, select an option.</span></span>
8. <span data-ttu-id="cab3f-148">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cab3f-148">In the Adjustment amount field, enter a number.</span></span>
9. <span data-ttu-id="cab3f-149">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-149">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="cab3f-150">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-150">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="cab3f-151">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-151">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="cab3f-152">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-152">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="cab3f-153">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="cab3f-153">Click Apply to grid.</span></span>
14. <span data-ttu-id="cab3f-154">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-154">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="cab3f-155">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-155">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="cab3f-156">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-156">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="cab3f-157">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="cab3f-157">Click Apply to grid.</span></span>
18. <span data-ttu-id="cab3f-158">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-158">In the list, find and select the desired record.</span></span>
19. <span data-ttu-id="cab3f-159">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-159">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="cab3f-160">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="cab3f-160">Click Apply to grid.</span></span>
21. <span data-ttu-id="cab3f-161">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="cab3f-161">In the list, find and select the desired record.</span></span>
22. <span data-ttu-id="cab3f-162">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="cab3f-162">Click Apply to grid.</span></span>
    * <span data-ttu-id="cab3f-163">Ahora utilizaremos la función de cambio masivo para ajustar los puntos de referencia mínimo y máximo para cada nivel.</span><span class="sxs-lookup"><span data-stu-id="cab3f-163">Now we'll use the mass change function to adjust the Minimum and Maximum reference points for each level.</span></span> <span data-ttu-id="cab3f-164">Este ejemplo utilizará una propagación del 50 % de manera que el punto de referencia mínimo se ajustará un -20 % y el máximo se ajustará un +20 %.</span><span class="sxs-lookup"><span data-stu-id="cab3f-164">This example will use a 50% spread so the Minimum reference point will be adjusted -20% and the Maximum will be adjusted +20%.</span></span>  
23. <span data-ttu-id="cab3f-165">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cab3f-165">In the Adjustment amount field, enter a number.</span></span>
24. <span data-ttu-id="cab3f-166">En el campo Punto de referencia, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-166">In the Reference point field, enter or select a value.</span></span>
25. <span data-ttu-id="cab3f-167">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="cab3f-167">In the list, mark or unmark all rows.</span></span>
26. <span data-ttu-id="cab3f-168">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="cab3f-168">Click Apply to grid.</span></span>
27. <span data-ttu-id="cab3f-169">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="cab3f-169">In the Adjustment amount field, enter a number.</span></span>
28. <span data-ttu-id="cab3f-170">En el campo Punto de referencia, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cab3f-170">In the Reference point field, enter or select a value.</span></span>
29. <span data-ttu-id="cab3f-171">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="cab3f-171">In the list, mark or unmark all rows.</span></span>
30. <span data-ttu-id="cab3f-172">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="cab3f-172">Click Apply to grid.</span></span>

