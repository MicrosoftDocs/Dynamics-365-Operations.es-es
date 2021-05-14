---
title: Variables de prueba de gestión de calidad
description: Este tema describe cómo crear variables de prueba, de modo que se puedan usar para pruebas cualitativas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e94972b41baf3f59a633fa7bbc7434abfb90460
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956819"
---
# <a name="quality-management-test-variables"></a><span data-ttu-id="587f9-103">Variables de prueba de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="587f9-103">Quality management test variables</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="587f9-104">Este tema describe cómo crear variables de prueba, de modo que se puedan usar para pruebas cualitativas en pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="587f9-104">This topic describes how to create test variables that can be used for qualitative tests on quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="587f9-105">Para cada prueba cuallitativa que se define en la página **Pruebas**, debe definir una variable de prueba y sus posibles resultados (resultados).</span><span class="sxs-lookup"><span data-stu-id="587f9-105">For every qualitative test that is defined on the **Tests** page, you must define a test variable and its possible outcomes (results).</span></span> <span data-ttu-id="587f9-106">(Para las pruebas cualitativas, el campo **Tipo** de la página **Pruebas** se establece en *Opción*).</span><span class="sxs-lookup"><span data-stu-id="587f9-106">(For qualitative tests, the **Type** field on the **Tests** page is set to *Option*.)</span></span>

<span data-ttu-id="587f9-107">Utilice la página **Variables de prueba** para configurar, editar y visualizar los resultados posibles de una variable de prueba asociada a una prueba cualitativa.</span><span class="sxs-lookup"><span data-stu-id="587f9-107">You use the **Test variables** page to set up, edit, and view the possible outcomes for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="587f9-108">Para cada resultado, asigna un estado de resultado de *Pasar* o *Fallar*, para indicar si la prueba se supera o no cuando se selecciona ese resultado como resultado de la prueba.</span><span class="sxs-lookup"><span data-stu-id="587f9-108">For each outcome, you assign an outcome status of either *Pass* or *Fail* to indicate whether the test is passed or failed when that outcome is selected as a test result.</span></span> <span data-ttu-id="587f9-109">Utilice la página **Grupos de prueba** para asignar una variable de prueba y un resultado predeterminado de esta en una prueba cualitativa individual.</span><span class="sxs-lookup"><span data-stu-id="587f9-109">You use the **Test groups** page to assign a test variable and a default outcome for it to an individual qualitative test.</span></span>

<span data-ttu-id="587f9-110">Para cada variable de prueba, recomendamos que definan al menos dos resultados: uno que tenga un estado de resultado de *Pasar* y uno que tenga un estado de resultado de *Fallar*.</span><span class="sxs-lookup"><span data-stu-id="587f9-110">For every test variable, we recommend that you define at least two outcomes: one that has an outcome status of *Pass* and one that has an outcome status of *Fail*.</span></span> <span data-ttu-id="587f9-111">No hay límite en el número total de variables o resultados que se pueden definir.</span><span class="sxs-lookup"><span data-stu-id="587f9-111">There is no limit on the total number of variables or outcomes that can be defined.</span></span> <span data-ttu-id="587f9-112">Además, varias pruebas pueden utilizar las mismas variables de prueba para registrar los resultados.</span><span class="sxs-lookup"><span data-stu-id="587f9-112">Additionally, multiple tests can use the same test variables to record results.</span></span>

## <a name="examples-of-test-variables"></a><span data-ttu-id="587f9-113">Ejemplos de variables de prueba</span><span class="sxs-lookup"><span data-stu-id="587f9-113">Examples of test variables</span></span>

### <a name="example-1"></a><span data-ttu-id="587f9-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="587f9-114">Example 1</span></span>

<span data-ttu-id="587f9-115">Una empresa de fabricación realiza dos pruebas en materiales fabricados.</span><span class="sxs-lookup"><span data-stu-id="587f9-115">A manufacturing company performs two tests on manufactured materials.</span></span> <span data-ttu-id="587f9-116">En una prueba, el nivel de pH está asociado con una tira de color.</span><span class="sxs-lookup"><span data-stu-id="587f9-116">In one test, the pH level is associated with a color strip.</span></span> <span data-ttu-id="587f9-117">Los niveles de pH aceptables están en colores más claros y los niveles de pH inaceptables están en colores más oscuros.</span><span class="sxs-lookup"><span data-stu-id="587f9-117">Acceptable pH levels are in lighter colors, and unacceptable pH levels are in darker colors.</span></span> <span data-ttu-id="587f9-118">En otra prueba, se realizan múltiples inspecciones visuales y los trabajadores de calidad usan su juicio para determinar si el artículo pasa o no la inspección visual.</span><span class="sxs-lookup"><span data-stu-id="587f9-118">In another test, multiple visual inspections are performed, and quality workers use their judgement to determine whether the item passes or fails the visual inspection.</span></span>

### <a name="example-2"></a><span data-ttu-id="587f9-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="587f9-119">Example 2</span></span>

<span data-ttu-id="587f9-120">Una fábrica de galletas utiliza una prueba de inspección para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="587f9-120">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="587f9-121">Esta prueba de inspección tiene varias variables.</span><span class="sxs-lookup"><span data-stu-id="587f9-121">This inspection test has several variables.</span></span> <span data-ttu-id="587f9-122">Una variable es el gusto y sus posibles resultados son bueno y malo.</span><span class="sxs-lookup"><span data-stu-id="587f9-122">One variable is taste, and the possible outcomes for it are good and bad.</span></span> <span data-ttu-id="587f9-123">Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</span><span class="sxs-lookup"><span data-stu-id="587f9-123">A second variable is color, and the possible outcomes for it are too dark, too light, and correct.</span></span>

## <a name="create-a-test-variable"></a><span data-ttu-id="587f9-124">Crear una variable de prueba</span><span class="sxs-lookup"><span data-stu-id="587f9-124">Create a test variable</span></span>

<span data-ttu-id="587f9-125">Siga estos pasos para crear una variable de prueba.</span><span class="sxs-lookup"><span data-stu-id="587f9-125">Follow these steps to create a test variable.</span></span>

1. <span data-ttu-id="587f9-126">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Variables de prueba**.</span><span class="sxs-lookup"><span data-stu-id="587f9-126">Go to **Inventory management \> Setup \> Quality control \> Test variables**.</span></span>
1. <span data-ttu-id="587f9-127">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="587f9-127">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="587f9-128">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="587f9-128">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="587f9-129">**Variable**: introduzca un id. o nombre único para la variable.</span><span class="sxs-lookup"><span data-stu-id="587f9-129">**Variable** – Enter a unique ID or name for the variable.</span></span>
    - <span data-ttu-id="587f9-130">**Descripción**: escriba una descripción detallada de la variable.</span><span class="sxs-lookup"><span data-stu-id="587f9-130">**Description** – Enter a detailed description of the variable.</span></span>

1. <span data-ttu-id="587f9-131">Mientras la nueva fila aún está seleccionada, seleccione **Resultados** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="587f9-131">While the new row is still selected, select **Outcomes** on the Action Pane.</span></span>
1. <span data-ttu-id="587f9-132">En la página **Resultados de variable de prueba**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="587f9-132">On the **Test variable outcomes** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="587f9-133">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="587f9-133">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="587f9-134">**Resultado**: introduzca un id. o nombre único para el resultado.</span><span class="sxs-lookup"><span data-stu-id="587f9-134">**Outcome** – Enter a unique ID or name for the outcome.</span></span>
    - <span data-ttu-id="587f9-135">**Descripción**: escriba una descripción detallada del resultado.</span><span class="sxs-lookup"><span data-stu-id="587f9-135">**Description** – Enter a detailed description of the outcome.</span></span>
    - <span data-ttu-id="587f9-136">**Estado del resutado**: seleccione *Pasa* o *Falla*, para indicar si la prueba se supera o no cuando se selecciona ese resultado como resultado de la prueba.</span><span class="sxs-lookup"><span data-stu-id="587f9-136">**Outcome status** – Select either *Pass* or *Fail* to indicate whether the test is passed or failed when the outcome is selected as a test result.</span></span>

1. <span data-ttu-id="587f9-137">Repita el paso anterior para cada resultado adicional.</span><span class="sxs-lookup"><span data-stu-id="587f9-137">Repeat the previous step for each additional outcome.</span></span> <span data-ttu-id="587f9-138">Asegúrese de que al menos un resultado tenga un estado de resultado de *Pasa* y al menos uno tenga un estado de resultado de *Falla*.</span><span class="sxs-lookup"><span data-stu-id="587f9-138">Make sure that at least one outcome has an outcome status of *Pass* and at least one has an outcome status of *Fail*.</span></span>
1. <span data-ttu-id="587f9-139">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="587f9-139">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="587f9-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="587f9-140">Additional resources</span></span>

- [<span data-ttu-id="587f9-141">Instrumentos de prueba de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="587f9-141">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="587f9-142">Pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="587f9-142">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="587f9-143">Grupos de pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="587f9-143">Quality management test groups</span></span>](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
