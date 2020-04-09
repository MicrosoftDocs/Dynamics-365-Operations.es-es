---
title: Crear una nomenclatura de números de producto para las variantes de producto configuradas
description: Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a837721db5281b0626f37b7a793349b91afa6f85
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147765"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="a2124-103">Crear una nomenclatura de números de producto para las variantes de producto configuradas</span><span class="sxs-lookup"><span data-stu-id="a2124-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2124-104">Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.</span><span class="sxs-lookup"><span data-stu-id="a2124-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="a2124-105">Este procedimiento también demuestra la manera de crear una nomenclatura de la configuración para un componente del modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="a2124-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="a2124-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="a2124-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a2124-107">La nueva nomenclatura del número de producto se asigna al producto maestro D0004.</span><span class="sxs-lookup"><span data-stu-id="a2124-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="a2124-108">Esta tarea normalmente la realiza un diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="a2124-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="a2124-109">Crear una nomenclatura de número de producto</span><span class="sxs-lookup"><span data-stu-id="a2124-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="a2124-110">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="a2124-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="a2124-111">Haga clic en Nomenclatura de producto.</span><span class="sxs-lookup"><span data-stu-id="a2124-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="a2124-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a2124-112">Click New.</span></span>
4. <span data-ttu-id="a2124-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="a2124-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="a2124-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-115">Click Add.</span></span>
7. <span data-ttu-id="a2124-116">Haga clic en Número de producto maestro.</span><span class="sxs-lookup"><span data-stu-id="a2124-116">Click Product master number.</span></span>
8. <span data-ttu-id="a2124-117">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-117">Click Add.</span></span>
9. <span data-ttu-id="a2124-118">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="a2124-118">Click Text constant.</span></span>
10. <span data-ttu-id="a2124-119">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="a2124-120">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="a2124-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-121">Click Add.</span></span>
13. <span data-ttu-id="a2124-122">Haga clic en Configuración.</span><span class="sxs-lookup"><span data-stu-id="a2124-122">Click Configuration.</span></span>
14. <span data-ttu-id="a2124-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2124-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="a2124-124">Asignar la nomenclatura del número de producto a un producto maestro</span><span class="sxs-lookup"><span data-stu-id="a2124-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="a2124-125">Haga clic en Productos maestros.</span><span class="sxs-lookup"><span data-stu-id="a2124-125">Click Product masters.</span></span>
2. <span data-ttu-id="a2124-126">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="a2124-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a2124-127">Por ejemplo, filtre por el campo Número de producto con un valor de "D".</span><span class="sxs-lookup"><span data-stu-id="a2124-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="a2124-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a2124-129">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="a2124-129">Click Edit.</span></span>
5. <span data-ttu-id="a2124-130">Seleccione Sí en el campo Usar nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="a2124-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="a2124-131">En el campo Nomenclatura del número de variante del producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="a2124-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2124-132">Close the page.</span></span>
8. <span data-ttu-id="a2124-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2124-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="a2124-134">Crear una nomenclatura para un componente de modelo de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="a2124-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="a2124-135">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="a2124-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="a2124-136">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a2124-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="a2124-137">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="a2124-138">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="a2124-138">Click Edit.</span></span>
5. <span data-ttu-id="a2124-139">Seleccione Sí en el campo Usar nomenclatura de configuración.</span><span class="sxs-lookup"><span data-stu-id="a2124-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="a2124-140">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-140">Click Add.</span></span>
7. <span data-ttu-id="a2124-141">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="a2124-141">Click Attribute value.</span></span>
8. <span data-ttu-id="a2124-142">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="a2124-143">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="a2124-144">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-144">Click Add.</span></span>
11. <span data-ttu-id="a2124-145">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="a2124-145">Click Text constant.</span></span>
12. <span data-ttu-id="a2124-146">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="a2124-147">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="a2124-148">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-148">Click Add.</span></span>
15. <span data-ttu-id="a2124-149">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="a2124-149">Click Attribute value.</span></span>
16. <span data-ttu-id="a2124-150">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="a2124-151">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="a2124-152">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-152">Click Add.</span></span>
19. <span data-ttu-id="a2124-153">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="a2124-153">Click Text constant.</span></span>
20. <span data-ttu-id="a2124-154">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="a2124-155">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="a2124-156">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-156">Click Add.</span></span>
23. <span data-ttu-id="a2124-157">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="a2124-157">Click Attribute value.</span></span>
24. <span data-ttu-id="a2124-158">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="a2124-159">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="a2124-160">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-160">Click Add.</span></span>
27. <span data-ttu-id="a2124-161">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="a2124-161">Click Text constant.</span></span>
28. <span data-ttu-id="a2124-162">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="a2124-163">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="a2124-164">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-164">Click Add.</span></span>
31. <span data-ttu-id="a2124-165">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="a2124-165">Click Attribute value.</span></span>
32. <span data-ttu-id="a2124-166">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="a2124-167">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="a2124-168">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-168">Click Add.</span></span>
35. <span data-ttu-id="a2124-169">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="a2124-169">Click Text constant.</span></span>
36. <span data-ttu-id="a2124-170">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="a2124-171">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="a2124-172">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="a2124-172">Click Add.</span></span>
39. <span data-ttu-id="a2124-173">Haga clic en Valor de secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="a2124-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="a2124-174">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a2124-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="a2124-175">En el campo Código de secuencia numérica, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a2124-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="a2124-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2124-176">Close the page.</span></span>
43. <span data-ttu-id="a2124-177">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2124-177">Close the page.</span></span>
44. <span data-ttu-id="a2124-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a2124-178">Close the page.</span></span>

