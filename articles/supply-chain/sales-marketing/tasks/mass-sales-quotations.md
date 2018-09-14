--- 
title: "Creación masiva de presupuestos de ventas"
description: "Este procedimiento muestra cómo crear de manera eficaz presupuestos que ofrecen un conjunto de productos o servicios que se deben enviar a varios clientes."
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationTemplateGroup, SalesQuotationListPage, SalesCreateQuotation, SalesQuotationTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e0e9ddf38106fce3ed6a6f908826f2196c97a45a
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="mass-create-sales-quotations"></a><span data-ttu-id="a98c5-103">Creación masiva de presupuestos de ventas</span><span class="sxs-lookup"><span data-stu-id="a98c5-103">Mass create sales quotations</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a98c5-104">Este procedimiento muestra cómo crear de manera eficaz presupuestos que ofrecen un conjunto de productos o servicios que se deben enviar a varios clientes.</span><span class="sxs-lookup"><span data-stu-id="a98c5-104">This procedure demonstrates how to efficiently create quotations offering a set of products or services that are to be sent to multiple customers.</span></span> <span data-ttu-id="a98c5-105">Esta creación de presupuesto masiva se basa en las plantillas de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a98c5-105">This mass quotation creation is based on quotation templates.</span></span> <span data-ttu-id="a98c5-106">Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="a98c5-106">You can run this procedure on your own data or in demo data company USMF.</span></span>


## <a name="create-a-quotation-template"></a><span data-ttu-id="a98c5-107">Crear una plantilla de presupuesto</span><span class="sxs-lookup"><span data-stu-id="a98c5-107">Create a quotation template</span></span>
1. <span data-ttu-id="a98c5-108">Vaya a Ventas y marketing > Configuración > Presupuestos > Grupos de plantillas.</span><span class="sxs-lookup"><span data-stu-id="a98c5-108">Go to Sales and marketing > Setup > Quotations > Template groups.</span></span>
2. <span data-ttu-id="a98c5-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a98c5-109">Click New.</span></span>
3. <span data-ttu-id="a98c5-110">En el campo Id. de grupo, escriba el id. que desee.</span><span class="sxs-lookup"><span data-stu-id="a98c5-110">In the Group ID field, type an ID of your choice.</span></span>
4. <span data-ttu-id="a98c5-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a98c5-112">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a98c5-112">Click Save.</span></span>
6. <span data-ttu-id="a98c5-113">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a98c5-113">Close the page.</span></span>
7. <span data-ttu-id="a98c5-114">Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.</span><span class="sxs-lookup"><span data-stu-id="a98c5-114">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
8. <span data-ttu-id="a98c5-115">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a98c5-115">Click New.</span></span>
9. <span data-ttu-id="a98c5-116">En el campo Tipo de cuenta, seleccione 'Cliente'.</span><span class="sxs-lookup"><span data-stu-id="a98c5-116">In the Account type field, select 'Customer'.</span></span>
10. <span data-ttu-id="a98c5-117">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-117">In the Customer account field, enter or select a value.</span></span>
11. <span data-ttu-id="a98c5-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a98c5-118">Click OK.</span></span>
    * <span data-ttu-id="a98c5-119">Para que un presupuesto se convierta en una plantilla debe realizar pasos de configuración en la cabecera de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a98c5-119">For a quotation to become a template you must carry out  setup steps on the quotation header.</span></span> <span data-ttu-id="a98c5-120">Esto se debe realizar antes de agregar líneas al presupuesto.</span><span class="sxs-lookup"><span data-stu-id="a98c5-120">This must be done before you add lines to the quotation.</span></span>   
12. <span data-ttu-id="a98c5-121">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="a98c5-121">On the Action Pane, click Options.</span></span>
13. <span data-ttu-id="a98c5-122">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="a98c5-122">Click Change view.</span></span>
14. <span data-ttu-id="a98c5-123">Haga clic en Visualización de encabezado.</span><span class="sxs-lookup"><span data-stu-id="a98c5-123">Click Header view.</span></span>
15. <span data-ttu-id="a98c5-124">Expanda la sección Configuración.</span><span class="sxs-lookup"><span data-stu-id="a98c5-124">Expand the Setup section.</span></span>
16. <span data-ttu-id="a98c5-125">En el campo Id. de grupo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-125">In the Group ID field, enter or select a value.</span></span>
17. <span data-ttu-id="a98c5-126">En el campo Nombre de plantilla, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-126">In the Template name field, type a value.</span></span>
18. <span data-ttu-id="a98c5-127">Seleccione Sí en el campo Activo.</span><span class="sxs-lookup"><span data-stu-id="a98c5-127">Select Yes in the Active field.</span></span>
    * <span data-ttu-id="a98c5-128">Solo las plantillas activas pueden usarse si se aplica una plantilla a un nuevo presupuesto de ventas.</span><span class="sxs-lookup"><span data-stu-id="a98c5-128">Only active templates can be used when you apply a template to a new sales quotation.</span></span>  
19. <span data-ttu-id="a98c5-129">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="a98c5-129">On the Action Pane, click Options.</span></span>
20. <span data-ttu-id="a98c5-130">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="a98c5-130">Click Change view.</span></span>
21. <span data-ttu-id="a98c5-131">Haga clic en Vista de líneas.</span><span class="sxs-lookup"><span data-stu-id="a98c5-131">Click Line view.</span></span>
22. <span data-ttu-id="a98c5-132">En el campo Artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-132">In the Item field, enter or select a value.</span></span>
23. <span data-ttu-id="a98c5-133">En el campo Artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-133">In the Item field, type a value.</span></span>
24. <span data-ttu-id="a98c5-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a98c5-134">Close the page.</span></span>
25. <span data-ttu-id="a98c5-135">En el campo Porcentaje de descuento, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a98c5-135">In the Discount percent field, enter a number.</span></span>
26. <span data-ttu-id="a98c5-136">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="a98c5-136">Click Add line.</span></span>
27. <span data-ttu-id="a98c5-137">En el campo Artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-137">In the Item field, enter or select a value.</span></span>
28. <span data-ttu-id="a98c5-138">En el campo Artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-138">In the Item field, type a value.</span></span>
29. <span data-ttu-id="a98c5-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a98c5-139">Close the page.</span></span>
30. <span data-ttu-id="a98c5-140">En el campo Precio unitario, especifique un nuevo precio o cambie el actual.</span><span class="sxs-lookup"><span data-stu-id="a98c5-140">In the Unit price field, enter a new price or change the current one.</span></span>
31. <span data-ttu-id="a98c5-141">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="a98c5-141">Click Add line.</span></span>
32. <span data-ttu-id="a98c5-142">En el campo Artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-142">In the Item field, enter or select a value.</span></span>
33. <span data-ttu-id="a98c5-143">En el campo Artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-143">In the Item field, type a value.</span></span>
34. <span data-ttu-id="a98c5-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a98c5-144">Close the page.</span></span>
35. <span data-ttu-id="a98c5-145">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a98c5-145">In the Quantity field, enter a number.</span></span>
36. <span data-ttu-id="a98c5-146">En el campo Descuento, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="a98c5-146">In the Discount field, enter a number.</span></span>
37. <span data-ttu-id="a98c5-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a98c5-147">Click Save.</span></span>

## <a name="apply-the-template-to-create-a-single-quotation"></a><span data-ttu-id="a98c5-148">Aplicar la plantilla para crear un único presupuesto</span><span class="sxs-lookup"><span data-stu-id="a98c5-148">Apply the template to create a single quotation</span></span>
1. <span data-ttu-id="a98c5-149">Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.</span><span class="sxs-lookup"><span data-stu-id="a98c5-149">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="a98c5-150">Tenga en cuenta que el presupuesto que acaba de crear está marcado como plantilla.</span><span class="sxs-lookup"><span data-stu-id="a98c5-150">Note that the quotation you have just created is marked as template.</span></span>  
2. <span data-ttu-id="a98c5-151">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a98c5-151">Click New.</span></span>
3. <span data-ttu-id="a98c5-152">En el campo Tipo de cuenta, seleccione 'Cliente'.</span><span class="sxs-lookup"><span data-stu-id="a98c5-152">In the Account type field, select 'Customer'.</span></span>
4. <span data-ttu-id="a98c5-153">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-153">In the Customer account field, enter or select a value.</span></span>
5. <span data-ttu-id="a98c5-154">Expanda la sección Plantilla.</span><span class="sxs-lookup"><span data-stu-id="a98c5-154">Expand the Template section.</span></span>
6. <span data-ttu-id="a98c5-155">En el campo Id. de grupo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-155">In the Group ID field, enter or select a value.</span></span>
7. <span data-ttu-id="a98c5-156">En el campo Nombre de plantilla, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-156">In the Template name field, enter or select a value.</span></span>
8. <span data-ttu-id="a98c5-157">En el campo Método de cálculo, seleccione “Basado en valores de plantilla”.</span><span class="sxs-lookup"><span data-stu-id="a98c5-157">In the Calculation method field, select 'Based on template values'.</span></span>
9. <span data-ttu-id="a98c5-158">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a98c5-158">Click OK.</span></span>
    * <span data-ttu-id="a98c5-159">Se ha creado el nuevo presupuesto, en función de los datos y las condiciones de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="a98c5-159">The new quotation has now been created, based on the data and terms of the template.</span></span>  
10. <span data-ttu-id="a98c5-160">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a98c5-160">Close the page.</span></span>
11. <span data-ttu-id="a98c5-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a98c5-161">Close the page.</span></span>

## <a name="apply-the-template-to-mass-create-quotations"></a><span data-ttu-id="a98c5-162">Aplicar la plantilla para crear presupuestos de forma masiva</span><span class="sxs-lookup"><span data-stu-id="a98c5-162">Apply the template to mass create quotations</span></span>
1. <span data-ttu-id="a98c5-163">Vaya a Ventas y marketing > Presupuestos de ventas > Actualización de presupuesto > Creación masiva de presupuestos.</span><span class="sxs-lookup"><span data-stu-id="a98c5-163">Go to Sales and marketing > Sales quotations > Quotation update > Mass create quotations.</span></span>
2. <span data-ttu-id="a98c5-164">En el campo Tipo de cuenta, seleccione 'Cliente'.</span><span class="sxs-lookup"><span data-stu-id="a98c5-164">In the Account type field, select 'Customer'.</span></span>
3. <span data-ttu-id="a98c5-165">En el campo Id. de grupo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-165">In the Group ID field, enter or select a value.</span></span>
4. <span data-ttu-id="a98c5-166">En el campo Nombre de plantilla, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a98c5-166">In the Template name field, enter or select a value.</span></span>
5. <span data-ttu-id="a98c5-167">En el campo Método de cálculo, seleccione “Basado en valores de plantilla”.</span><span class="sxs-lookup"><span data-stu-id="a98c5-167">In the Calculation method field, select 'Based on template values'.</span></span>
6. <span data-ttu-id="a98c5-168">Expanda la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="a98c5-168">Expand the Records to include section.</span></span>
7. <span data-ttu-id="a98c5-169">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="a98c5-169">Click Filter.</span></span>
8. <span data-ttu-id="a98c5-170">En el campo Criterios, establezca el filtro para cubrir un intervalo de clientes que desea incluir en esta creación de presupuesto masiva.</span><span class="sxs-lookup"><span data-stu-id="a98c5-170">In the Criteria field, set the filter to cover a range of customers you want to include in this mass quotation creation.</span></span> <span data-ttu-id="a98c5-171">Utilice el siguiente formato "Customer1..CustomerN.</span><span class="sxs-lookup"><span data-stu-id="a98c5-171">Use the following format "Customer1..CustomerN.</span></span>
    * <span data-ttu-id="a98c5-172">Por ejemplo, podría establecer el filtro en: US-001..US-004</span><span class="sxs-lookup"><span data-stu-id="a98c5-172">For example, you could set the filter to: US-001..US-004</span></span>  
9. <span data-ttu-id="a98c5-173">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a98c5-173">Click OK.</span></span>
10. <span data-ttu-id="a98c5-174">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a98c5-174">Click OK.</span></span>
11. <span data-ttu-id="a98c5-175">Vaya a Ventas y marketing > Presupuestos de ventas > Todos los presupuestos.</span><span class="sxs-lookup"><span data-stu-id="a98c5-175">Go to Sales and marketing > Sales quotations > All quotations.</span></span>
    * <span data-ttu-id="a98c5-176">Compruebe que los presupuestos se han creado para todos los clientes especificados en la rutina de actualización masiva, basándose en la plantilla seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a98c5-176">Verify that quotations have been created for all the customers specified in the mass update routine, as based on the selected template.</span></span>  


