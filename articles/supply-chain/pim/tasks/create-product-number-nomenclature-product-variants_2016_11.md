---
title: Crear una nomenclatura de números de producto para las variantes de producto configuradas
description: Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f342831d95f9988f9bb7807bac986e43cb317e0f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820018"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="39f3e-103">Crear una nomenclatura de números de producto para las variantes de producto configuradas</span><span class="sxs-lookup"><span data-stu-id="39f3e-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="39f3e-104">Este procedimiento muestra cómo configurar una nomenclatura del número de producto para las variantes de producto configuradas y cómo se puede adjuntar a un producto maestro configurable.</span><span class="sxs-lookup"><span data-stu-id="39f3e-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="39f3e-105">Este procedimiento también demuestra la manera de crear una nomenclatura de la configuración para un componente del modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="39f3e-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="39f3e-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="39f3e-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="39f3e-107">La nueva nomenclatura del número de producto se asigna al producto maestro D0004.</span><span class="sxs-lookup"><span data-stu-id="39f3e-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="39f3e-108">Esta tarea normalmente la realiza un diseñador de productos.</span><span class="sxs-lookup"><span data-stu-id="39f3e-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="39f3e-109">Crear una nomenclatura de número de producto</span><span class="sxs-lookup"><span data-stu-id="39f3e-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="39f3e-110">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="39f3e-111">Haga clic en Nomenclatura de producto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="39f3e-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="39f3e-112">Click New.</span></span>
4. <span data-ttu-id="39f3e-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="39f3e-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="39f3e-115">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-115">Click Add.</span></span>
7. <span data-ttu-id="39f3e-116">Haga clic en Número de producto maestro.</span><span class="sxs-lookup"><span data-stu-id="39f3e-116">Click Product master number.</span></span>
8. <span data-ttu-id="39f3e-117">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-117">Click Add.</span></span>
9. <span data-ttu-id="39f3e-118">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-118">Click Text constant.</span></span>
10. <span data-ttu-id="39f3e-119">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="39f3e-120">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="39f3e-121">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-121">Click Add.</span></span>
13. <span data-ttu-id="39f3e-122">Haga clic en Configuración.</span><span class="sxs-lookup"><span data-stu-id="39f3e-122">Click Configuration.</span></span>
14. <span data-ttu-id="39f3e-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39f3e-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="39f3e-124">Asignar la nomenclatura del número de producto a un producto maestro</span><span class="sxs-lookup"><span data-stu-id="39f3e-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="39f3e-125">Haga clic en Productos maestros.</span><span class="sxs-lookup"><span data-stu-id="39f3e-125">Click Product masters.</span></span>
2. <span data-ttu-id="39f3e-126">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="39f3e-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="39f3e-127">Por ejemplo, filtre por el campo Número de producto con un valor de "D".</span><span class="sxs-lookup"><span data-stu-id="39f3e-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="39f3e-128">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="39f3e-129">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-129">Click Edit.</span></span>
5. <span data-ttu-id="39f3e-130">Seleccione Sí en el campo Usar nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="39f3e-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="39f3e-131">En el campo Nomenclatura del número de variante del producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="39f3e-132">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39f3e-132">Close the page.</span></span>
8. <span data-ttu-id="39f3e-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39f3e-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="39f3e-134">Crear una nomenclatura para un componente de modelo de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="39f3e-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="39f3e-135">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="39f3e-136">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="39f3e-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="39f3e-137">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="39f3e-138">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-138">Click Edit.</span></span>
5. <span data-ttu-id="39f3e-139">Seleccione Sí en el campo Usar nomenclatura de configuración.</span><span class="sxs-lookup"><span data-stu-id="39f3e-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="39f3e-140">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-140">Click Add.</span></span>
7. <span data-ttu-id="39f3e-141">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="39f3e-141">Click Attribute value.</span></span>
8. <span data-ttu-id="39f3e-142">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="39f3e-143">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="39f3e-144">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-144">Click Add.</span></span>
11. <span data-ttu-id="39f3e-145">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-145">Click Text constant.</span></span>
12. <span data-ttu-id="39f3e-146">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="39f3e-147">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="39f3e-148">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-148">Click Add.</span></span>
15. <span data-ttu-id="39f3e-149">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="39f3e-149">Click Attribute value.</span></span>
16. <span data-ttu-id="39f3e-150">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="39f3e-151">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="39f3e-152">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-152">Click Add.</span></span>
19. <span data-ttu-id="39f3e-153">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-153">Click Text constant.</span></span>
20. <span data-ttu-id="39f3e-154">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="39f3e-155">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="39f3e-156">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-156">Click Add.</span></span>
23. <span data-ttu-id="39f3e-157">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="39f3e-157">Click Attribute value.</span></span>
24. <span data-ttu-id="39f3e-158">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="39f3e-159">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="39f3e-160">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-160">Click Add.</span></span>
27. <span data-ttu-id="39f3e-161">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-161">Click Text constant.</span></span>
28. <span data-ttu-id="39f3e-162">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="39f3e-163">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="39f3e-164">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-164">Click Add.</span></span>
31. <span data-ttu-id="39f3e-165">Haga clic en Valor de atributo.</span><span class="sxs-lookup"><span data-stu-id="39f3e-165">Click Attribute value.</span></span>
32. <span data-ttu-id="39f3e-166">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="39f3e-167">En el campo Atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="39f3e-168">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-168">Click Add.</span></span>
35. <span data-ttu-id="39f3e-169">Haga clic en Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="39f3e-169">Click Text constant.</span></span>
36. <span data-ttu-id="39f3e-170">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="39f3e-171">En el campo Texto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="39f3e-172">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="39f3e-172">Click Add.</span></span>
39. <span data-ttu-id="39f3e-173">Haga clic en Valor de secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="39f3e-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="39f3e-174">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="39f3e-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="39f3e-175">En el campo Código de secuencia numérica, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="39f3e-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="39f3e-176">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39f3e-176">Close the page.</span></span>
43. <span data-ttu-id="39f3e-177">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39f3e-177">Close the page.</span></span>
44. <span data-ttu-id="39f3e-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="39f3e-178">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]