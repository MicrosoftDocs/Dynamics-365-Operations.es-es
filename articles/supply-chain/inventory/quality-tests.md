---
title: Pruebas de gestión de calidad
description: Este tema describe cómo crear pruebas que se puedan usar para pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: b88011f486b6582db4727b85d021868899c6abe1
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956818"
---
# <a name="quality-management-tests"></a><span data-ttu-id="15923-103">Pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="15923-103">Quality management tests</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15923-104">Este tema describe cómo crear pruebas que se puedan usar para pedidos de calidad en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="15923-104">This topic describes how to create tests that can be used for quality orders in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="15923-105">Utilice la página **Pruebas** para definir y visualizar las pruebas individuales que determinan si sus productos cumplen las especificaciones.</span><span class="sxs-lookup"><span data-stu-id="15923-105">You use the **Tests** page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="15923-106">Puede asignar una o varias pruebas individuales a un grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="15923-106">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="15923-107">En este caso, también especifica la información específica de la prueba, como los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="15923-107">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="15923-108">Los valores de medida se utilizan para pruebas cuantitativas.</span><span class="sxs-lookup"><span data-stu-id="15923-108">Measurement values are used for quantitative tests.</span></span> <span data-ttu-id="15923-109">Para las pruebas cualitativas, se utilizan variables de prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-109">For qualitative tests, test variables are used.</span></span>

- <span data-ttu-id="15923-110">Para pruebas cuantitativas, el campo **Tipo** está configurado en *Entero* o *Fracción*.</span><span class="sxs-lookup"><span data-stu-id="15923-110">For quantitative tests, the **Type** field is set to *Integer* or *Fraction*.</span></span> <span data-ttu-id="15923-111">También se especifica una unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="15923-111">A unit of measure is also specified.</span></span> <span data-ttu-id="15923-112">Las especificaciones de calidad y los resultados de la prueba se expresan como números.</span><span class="sxs-lookup"><span data-stu-id="15923-112">Quality specifications and test results are expressed as numbers.</span></span>
- <span data-ttu-id="15923-113">Para las pruebas cualitativas, el campo **Tipo** está establecido en *Opción*.</span><span class="sxs-lookup"><span data-stu-id="15923-113">For qualitative tests, the **Type** field is set to *Option*.</span></span> <span data-ttu-id="15923-114">Las pruebas cualitativas requieren información adicional sobre la variable de prueba que se está midiendo y sus opciones enumeradas.</span><span class="sxs-lookup"><span data-stu-id="15923-114">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="15923-115">Las especificaciones de calidad y los resultados de la prueba se expresan en función de un resultado.</span><span class="sxs-lookup"><span data-stu-id="15923-115">Quality specifications and test results are expressed according to an outcome.</span></span>

<span data-ttu-id="15923-116">Puede asignar opcionalmente un instrumento de prueba a una prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-116">You can optionally assign a test instrument to a test.</span></span> <span data-ttu-id="15923-117">Sin embargo, no se requieren instrumentos de prueba para crear y usar pruebas con pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="15923-117">However, test instruments aren't required to create and use tests with quality orders.</span></span> <span data-ttu-id="15923-118">Para más información, consulte [Instrumentos de prueba de gestión de calidad](quality-test-instruments.md).</span><span class="sxs-lookup"><span data-stu-id="15923-118">For more information, see [Quality management test instruments](quality-test-instruments.md).</span></span>

<span data-ttu-id="15923-119">También puede especificar opcionalmente una unidad para una prueba, para indicar la unidad de medida en la que se registran los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-119">You can also optionally specify a unit for a test, to indicate the unit of measure that test results are recorded in.</span></span> <span data-ttu-id="15923-120">Por ejemplo, una prueba de temperatura puede incluir una unidad de grados Fahrenheit o grados Celsius.</span><span class="sxs-lookup"><span data-stu-id="15923-120">For example, a test for temperature might include a unit of either degrees Fahrenheit or degrees Celsius.</span></span>

## <a name="example-of-a-test"></a><span data-ttu-id="15923-121">Ejemplo de prueba</span><span class="sxs-lookup"><span data-stu-id="15923-121">Example of a test</span></span>

<span data-ttu-id="15923-122">Una empresa de fabricación realiza dos pruebas en el material adquirido: una prueba cuantitativa sobre la calidad del material y una prueba cualitativa de los daños de embalaje.</span><span class="sxs-lookup"><span data-stu-id="15923-122">A manufacturing company performs two tests on purchased material: a quantitative test for material quality and a qualitative test for packaging damage.</span></span> <span data-ttu-id="15923-123">La empresa especifica información adicional sobre la prueba cualitativa para definir la variable de prueba (por ejemplo, embalaje dañado) y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="15923-123">The company specifies additional information about the qualitative test to define the test variable (for example, damaged packaging) and its outcomes.</span></span> <span data-ttu-id="15923-124">La empresa usa la página **Grupos de prueba** para asignar las dos pruebas a un grupo de pruebas y para especificar la información específica de la prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-124">The company uses the **Test groups** page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="15923-125">El grupo de pruebas se asigna a un pedido de calidad, de modo que la empresa puede informar de los resultados de prueba para las dos pruebas.</span><span class="sxs-lookup"><span data-stu-id="15923-125">The test group is assigned to a quality order so that the company can report test results for the two tests.</span></span>

## <a name="create-a-test"></a><span data-ttu-id="15923-126">Crear una prueba</span><span class="sxs-lookup"><span data-stu-id="15923-126">Create a test</span></span>

<span data-ttu-id="15923-127">Siga estos pasos para crear una prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-127">Follow these steps to create a test.</span></span>

1. <span data-ttu-id="15923-128">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Pruebas**.</span><span class="sxs-lookup"><span data-stu-id="15923-128">Go to **Inventory management \> Setup \> Quality control \> Tests**.</span></span>
1. <span data-ttu-id="15923-129">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="15923-129">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="15923-130">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="15923-130">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="15923-131">**Prueba**: introduzca un id. o nombre único para la prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-131">**Test** – Enter a unique ID or name for the test.</span></span>
    - <span data-ttu-id="15923-132">**Descripción**: escriba una descripción detallada de la prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-132">**Description** – Enter a detailed description of the test.</span></span>
    - <span data-ttu-id="15923-133">**Tipo**: seleccione el tipo de resultados que produce la prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-133">**Type** – Select the type of results that the test produces.</span></span> <span data-ttu-id="15923-134">Para pruebas cuantitativas, seleccione *Fracción* o *Entero*.</span><span class="sxs-lookup"><span data-stu-id="15923-134">For quantitative tests, select *Fraction* or *Integer*.</span></span> <span data-ttu-id="15923-135">Para pruebas cualitativas, seleccione *Opción*.</span><span class="sxs-lookup"><span data-stu-id="15923-135">For qualitative tests, select *Option*.</span></span>
    - <span data-ttu-id="15923-136">**Instrumento de prueba**: seleccione un [instrumento de prueba](quality-test-instruments.md) que debe utilizarse para la prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-136">**Test instrument** – Select a [test instrument](quality-test-instruments.md) that should be used for the test.</span></span>
    - <span data-ttu-id="15923-137">**Unidad**: si seleccionó *Fracción* o *Entero* en el campo **Tipo** (es decir, si la prueba es una prueba cuantitativa), seleccione la unidad de medida en la que se deben registrar los resultados de la prueba.</span><span class="sxs-lookup"><span data-stu-id="15923-137">**Unit** – If you selected *Fraction* or *Integer* in the **Type** field (that is, if the test is a quantitative test), select the unit of measure that test results should be recorded in.</span></span>

1. <span data-ttu-id="15923-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="15923-138">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="15923-139">Después de guardar una prueba, ya no puede editar el campo **Tipo** en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="15923-139">After you save a test, you can no longer edit the **Type** field in the grid.</span></span> <span data-ttu-id="15923-140">Si debe cambiar el tipo de resultados de prueba que se registrarán para una prueba, seleccione **Cambiar el tipo de prueba de calidad** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="15923-140">If you must change the type of test results that will be recorded for a test, select **Change quality test type** on the Action Pane.</span></span> <span data-ttu-id="15923-141">En el cuadro de diálogo **Cambiar el tipo de prueba de calidad**, establezca el campo **Nuevo tipo** en el tipo deseado y luego seleccione **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="15923-141">In the **Change quality test type** dialog box, set the **New type** field to the desired type, and then select **OK** to close the dialog box.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15923-142">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="15923-142">Additional resources</span></span>

- [<span data-ttu-id="15923-143">Instrumentos de prueba de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="15923-143">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="15923-144">Grupos de pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="15923-144">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="15923-145">Variables de prueba de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="15923-145">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="15923-146">Asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="15923-146">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
