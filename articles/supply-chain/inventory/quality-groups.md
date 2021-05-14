---
title: Grupos de calidad de artículos
description: Este tema describe cómo usar y crear grupos de calidad de artículos para agrupar productos de manera lógica de modo que puedan asignarse a asociaciones de calidad para la generación automática de pedidos de calidad.
author: rachel-profitt
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestQualityGroup, InventTestItemQualityGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3074a6a8cc054be045bf593b509e76a1043af0b7
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956815"
---
# <a name="item-quality-groups"></a><span data-ttu-id="29511-103">Grupos de calidad de artículos</span><span class="sxs-lookup"><span data-stu-id="29511-103">Item quality groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29511-104">Un grupo de calidad representa requisitos de prueba comunes para los artículos.</span><span class="sxs-lookup"><span data-stu-id="29511-104">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="29511-105">Este tema describe cómo usar y crear grupos de calidad de artículos para agrupar productos de manera lógica de modo que puedan asignarse a asociaciones de calidad para la generación automática de pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="29511-105">This topic describes how to use and create item quality groups to logically group products so that they can be assigned to quality associations for the automatic generation of quality orders.</span></span>

<span data-ttu-id="29511-106">Para configurar, editar y ver los artículos asignados a un grupo de calidad o los grupos de calidad asignados a un artículo, vaya a **Gestión de inventario \> Configuración \> Grupos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="29511-106">To set up, edit, and view the items that are assigned to a quality group, or the quality groups that are assigned to an item, go to **Inventory management \> Setup \> Quality groups**.</span></span> <span data-ttu-id="29511-107">Cuando haya definido los requisitos de prueba en la página **Grupos de prueba**, puede definir las reglas para generar automáticamente pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="29511-107">After you define the test requirements on the **Test groups** page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="29511-108">Para simplificar el proceso, no se definen reglas para artículos individuales.</span><span class="sxs-lookup"><span data-stu-id="29511-108">To simplify the process, you don't define rules for individual items.</span></span> <span data-ttu-id="29511-109">En su lugar, puede definir las reglas para un grupo de calidad en la página **Asociaciones de calidad**.</span><span class="sxs-lookup"><span data-stu-id="29511-109">Instead, you can define the rules for a quality group on the **Quality associations** page.</span></span>

## <a name="example-of-an-item-quality-group"></a><span data-ttu-id="29511-110">Ejemplo de un grupo de calidad de artículos</span><span class="sxs-lookup"><span data-stu-id="29511-110">Example of an item quality group</span></span>

<span data-ttu-id="29511-111">Un fabricante compra varias materias primas con los mismos requisitos de prueba para una inspección entrante.</span><span class="sxs-lookup"><span data-stu-id="29511-111">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="29511-112">Por consiguiente, la empresa define un grupo de calidad y, después, le asigna números de artículo asociados con los materiales sin procesar para ese grupo.</span><span class="sxs-lookup"><span data-stu-id="29511-112">Therefore, the company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="29511-113">Más adelante, la empresa compra un nuevo tipo de materia prima con los mismos requisitos de prueba.</span><span class="sxs-lookup"><span data-stu-id="29511-113">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="29511-114">En lugar de configurar requisitos de prueba nuevos para el nuevo material, la empresa añade el número de artículo del nuevo material al grupo de calidad existente.</span><span class="sxs-lookup"><span data-stu-id="29511-114">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span>

<span data-ttu-id="29511-115">La misma empresa también produce artículos con los mismos requisitos de prueba y envía artículos con los mismos requisitos para las pruebas anteriores al envío.</span><span class="sxs-lookup"><span data-stu-id="29511-115">The same company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="29511-116">Por consiguiente, la empresa define dos grupos de calidad adicionales y, después, asigna números de artículo pertinentes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="29511-116">Therefore, the company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span>

## <a name="create-a-quality-group"></a><span data-ttu-id="29511-117">Crear un grupo de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-117">Create a quality group</span></span>

<span data-ttu-id="29511-118">Para crear un grupo de calidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="29511-118">To create a quality group, follow these steps.</span></span>

1. <span data-ttu-id="29511-119">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="29511-119">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="29511-120">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29511-120">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="29511-121">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="29511-121">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="29511-122">**Grupo de calidad**: introduzca un id. o nombre único para el grupo de calidad.</span><span class="sxs-lookup"><span data-stu-id="29511-122">**Quality group** – Enter a unique ID or name for the quality group.</span></span>
    - <span data-ttu-id="29511-123">**Descripción**: escriba una descripción detallada del grupo de calidad.</span><span class="sxs-lookup"><span data-stu-id="29511-123">**Description** – Enter a detailed description of the quality group.</span></span>

1. <span data-ttu-id="29511-124">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="29511-124">Close the page.</span></span>

## <a name="manually-add-items-to-a-quality-group"></a><span data-ttu-id="29511-125">Agregar manualmente artículos a un grupo de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-125">Manually add items to a quality group</span></span>

<span data-ttu-id="29511-126">Para agregar artículos manualmente a un grupo de calidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="29511-126">To manually add items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="29511-127">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="29511-127">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="29511-128">Seleccione el grupo de calidad al que desea agregar artículos.</span><span class="sxs-lookup"><span data-stu-id="29511-128">Select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="29511-129">En el panel de acciones, haga clic en **Artículos**.</span><span class="sxs-lookup"><span data-stu-id="29511-129">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="29511-130">En la página **Artículos en grupos de calidad**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29511-130">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="29511-131">Luego, para la nueva fila, establezca el campo **Número de artículo** campo en el número de artículo que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="29511-131">Then, for the new row, set the **Item number** field to the item number that you want to add.</span></span>
1. <span data-ttu-id="29511-132">Repita el paso anterior para cada elemento adicional que deba agregarse.</span><span class="sxs-lookup"><span data-stu-id="29511-132">Repeat the previous step for each additional item that must be added.</span></span>
1. <span data-ttu-id="29511-133">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="29511-133">Close the pages.</span></span>

## <a name="add-multiple-items-to-a-quality-group"></a><span data-ttu-id="29511-134">Agregar varios artículos a un grupo de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-134">Add multiple items to a quality group</span></span>

<span data-ttu-id="29511-135">Para agregar varios artículos a un grupo de calidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="29511-135">To add multiple items to a quality group, follow these steps.</span></span>

1. <span data-ttu-id="29511-136">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad**.</span><span class="sxs-lookup"><span data-stu-id="29511-136">Go to **Inventory management \> Setup \> Quality control \> Quality groups**.</span></span>
1. <span data-ttu-id="29511-137">Cree o seleccione el grupo de calidad al que desea agregar artículos.</span><span class="sxs-lookup"><span data-stu-id="29511-137">Create or select the quality group that you want to add items to.</span></span>
1. <span data-ttu-id="29511-138">En el panel de acciones, haga clic en **Agregar artículos**.</span><span class="sxs-lookup"><span data-stu-id="29511-138">On the Action Pane, select **Add items**.</span></span>
1. <span data-ttu-id="29511-139">En el cuadro de diálogo **Consulta**, introduzca los criterios de filtrado para los elementos que desea agregar.</span><span class="sxs-lookup"><span data-stu-id="29511-139">In the **Inquiry** dialog box, enter the filter criteria for the items that you want to add.</span></span> <span data-ttu-id="29511-140">Por ejemplo, puede filtrar todos los artículos de un grupo de artículos específico.</span><span class="sxs-lookup"><span data-stu-id="29511-140">For example, you might filter for all items in a specific item group.</span></span>
1. <span data-ttu-id="29511-141">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="29511-141">Select **OK**.</span></span>
1. <span data-ttu-id="29511-142">En el cuadro de diálogo **Agregar artículos**, una cuadrícula muestra todos los artículos que coinciden con su consulta.</span><span class="sxs-lookup"><span data-stu-id="29511-142">In the **Add items** dialog box, a grid shows all the items that match your query.</span></span> <span data-ttu-id="29511-143">Revise los resultados.</span><span class="sxs-lookup"><span data-stu-id="29511-143">Review the results.</span></span>

    <span data-ttu-id="29511-144">Si se requieren cambios, seleccione **Seleccionar** para volver al cuadro de diálogo **Consulta** y ajuste su consulta.</span><span class="sxs-lookup"><span data-stu-id="29511-144">If any changes are required, select **Select** to return to the **Inquiry** dialog box, and adjust your query.</span></span>

1. <span data-ttu-id="29511-145">Cuando los resultados incluyan todos los elementos que desea agregar, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="29511-145">When the results include all the items that you want to add, select **OK**.</span></span>
1. <span data-ttu-id="29511-146">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="29511-146">Close the page.</span></span>

## <a name="manually-associate-an-item-with-a-quality-group"></a><span data-ttu-id="29511-147">Asociar manualmente un artículo con un grupo de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-147">Manually associate an item with a quality group</span></span>

<span data-ttu-id="29511-148">Para asociar manualmente un artículo a un grupo de calidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="29511-148">To manually associate an item with a quality group, follow these steps.</span></span>

1. <span data-ttu-id="29511-149">Vaya a **Gestión del inventario \> Configurar \> Control de calidad \> Grupos de calidad de artículos**.</span><span class="sxs-lookup"><span data-stu-id="29511-149">Go to **Inventory management \> Setup \> Quality control \> Item quality groups**.</span></span>
1. <span data-ttu-id="29511-150">En el Panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29511-150">On the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="29511-151">Entonces establezca los siguientes campos para la fila nueva:</span><span class="sxs-lookup"><span data-stu-id="29511-151">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="29511-152">**Número de artículo**: seleccione el número de artículo a agregar.</span><span class="sxs-lookup"><span data-stu-id="29511-152">**Item number** – Select the item number to add.</span></span>
    - <span data-ttu-id="29511-153">**Grupo de calidad**: seleccione el grupo de calidad a asignar al artículo.</span><span class="sxs-lookup"><span data-stu-id="29511-153">**Quality group** – Select the quality group to assign to the item.</span></span>

1. <span data-ttu-id="29511-154">Repita el paso anterior para cada combinación adicional de un artículo y un grupo de calidad que deba agregar.</span><span class="sxs-lookup"><span data-stu-id="29511-154">Repeat the previous step for each additional combination of an item and a quality group that must be added.</span></span>
1. <span data-ttu-id="29511-155">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="29511-155">Close the pages.</span></span>

## <a name="manually-add-a-quality-group-from-the-released-products-page"></a><span data-ttu-id="29511-156">Agregue manualmente un grupo de calidad desde la página de productos liberados</span><span class="sxs-lookup"><span data-stu-id="29511-156">Manually add a quality group from the Released products page</span></span>

<span data-ttu-id="29511-157">Para agregar manualmente un grupo de calidad desde la página **Productos liberados**, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="29511-157">To manually add a quality group from the **Released products** page, follow these steps.</span></span>

1. <span data-ttu-id="29511-158">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="29511-158">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="29511-159">Seleccione el producto al que desea asignar un grupo de calidad.</span><span class="sxs-lookup"><span data-stu-id="29511-159">Select the product that you want to assign a quality group to.</span></span>
1. <span data-ttu-id="29511-160">En el panel de acciones, en la pestaña **Administrar inventario**, en el grupo **Calidad**, seleccione **Grupos de calidad de artículos**.</span><span class="sxs-lookup"><span data-stu-id="29511-160">On the Action Pane, on the **Manage inventory** tab, in the **Quality** group, select **Item quality groups**.</span></span>
1. <span data-ttu-id="29511-161">En la página **Artículos en grupos de calidad**, en el panel de acciones, seleccione **Nuevo** para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="29511-161">On the **Items in quality groups** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="29511-162">Luego, para la nueva fila, establezca el campo **Grupo de calidad** en el grupo de calidad que desea asignar al producto.</span><span class="sxs-lookup"><span data-stu-id="29511-162">Then, for the new row, set the **Quality group** field to the quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="29511-163">Repita el paso anterior para cada grupo de calidad adicional que desee asignar al producto.</span><span class="sxs-lookup"><span data-stu-id="29511-163">Repeat the previous step for each additional quality group that you want to assign to the product.</span></span>
1. <span data-ttu-id="29511-164">Cierre las páginas.</span><span class="sxs-lookup"><span data-stu-id="29511-164">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="29511-165">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="29511-165">Additional resources</span></span>

- [<span data-ttu-id="29511-166">Instrumentos de prueba de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-166">Quality management test instruments</span></span>](quality-test-instruments.md)
- [<span data-ttu-id="29511-167">Pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-167">Quality management tests</span></span>](quality-tests.md)
- [<span data-ttu-id="29511-168">Grupos de pruebas de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-168">Quality management test groups</span></span>](quality-test-groups.md)
- [<span data-ttu-id="29511-169">Variables de prueba de gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-169">Quality management test variables</span></span>](quality-test-variables.md)
- [<span data-ttu-id="29511-170">Asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="29511-170">Quality associations</span></span>](quality-associations.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
