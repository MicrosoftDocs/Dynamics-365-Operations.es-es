---
title: Crear un modelo de configuración de productos
description: Este procedimiento muestra cómo crear un modelo de configuración de productos y especificar información básica como atributos y subcomponentes.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 199ee5cd20a064bc6e1fd480f52c9c01ced8b1ba
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844762"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="6f5e2-103">Crear un modelo de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="6f5e2-103">Create a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6f5e2-104">Este procedimiento muestra cómo crear un modelo de configuración de productos y especificar información básica como atributos y subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="6f5e2-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="6f5e2-106">Crear un modelo de producto</span><span class="sxs-lookup"><span data-stu-id="6f5e2-106">Create a product model</span></span>
1. <span data-ttu-id="6f5e2-107">Haga clic en Definición de modelo de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="6f5e2-108">Haga clic en Modelos de configuración del producto.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="6f5e2-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-109">Click New.</span></span>
4. <span data-ttu-id="6f5e2-110">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6f5e2-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="6f5e2-112">En el campo Estrategia de solucionador, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="6f5e2-113">La estrategia de solucionador determina la manera en que se procesan las restricciones de un modelo de configuración de productos basado en restricciones.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="6f5e2-114">Esta selección puede tener un impacto en el rendimiento del modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="6f5e2-115">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="6f5e2-116">El componente raíz representa el modelo de configuración de productos, pero también se puede usar en otros modelos de productos.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="6f5e2-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6f5e2-117">Click OK.</span></span>
9. <span data-ttu-id="6f5e2-118">En el campo Volver a utilizar configuraciones, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="6f5e2-119">Si el parámetro Volver a utilizar configuraciones se establece Sí, el sistema comprobará las configuraciones idénticas después de cada sesión y las volverá a utilizar si se encuentra una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="6f5e2-120">Agregar atributos</span><span class="sxs-lookup"><span data-stu-id="6f5e2-120">Add attributes</span></span>
1. <span data-ttu-id="6f5e2-121">Expanda la sección Atributos.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="6f5e2-122">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-122">Click Add.</span></span>
3. <span data-ttu-id="6f5e2-123">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6f5e2-124">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6f5e2-125">En el campo Nombre del solucionador, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="6f5e2-126">El solucionador de restricciones usa el nombre del solucionador del configurador de productos.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="6f5e2-127">No debe incluir espacios ni caracteres especiales excepto _ (guión bajo).</span><span class="sxs-lookup"><span data-stu-id="6f5e2-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="6f5e2-128">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="6f5e2-129">El texto de la descripción se muestra al usuario de configuración y puede por tanto servir de ayuda en la selección del valor del atributo correcto.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="6f5e2-130">En el campo Tipo de atributo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="6f5e2-131">El tipo de atributo determina qué valores están disponibles para el atributo.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="6f5e2-132">Active la casilla Incluir en reutilización.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="6f5e2-133">Esta opción solo está disponible si se ha seleccionado la opción Volver a utilizar configuraciones.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="6f5e2-134">Incluir el atributo en la casilla de volver a utilizar significa que este atributo se considerará cuando el sistema busque una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="6f5e2-135">Agregar subcomponentes</span><span class="sxs-lookup"><span data-stu-id="6f5e2-135">Add subcomponents</span></span>
1. <span data-ttu-id="6f5e2-136">Expanda la sección Subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="6f5e2-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-137">Click Add.</span></span>
3. <span data-ttu-id="6f5e2-138">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="6f5e2-139">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="6f5e2-140">En el campo Nombre del solucionador, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="6f5e2-141">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="6f5e2-142">En el campo Componente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="6f5e2-143">Cada subcomponente debe hacer referencia a una definición del componente.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="6f5e2-144">Este diseño admite los componentes reutilizables y garantiza que una vez que se ha definido un componente puede usarse en muchos modelos de productos.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="6f5e2-145">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-145">Click Save.</span></span>
9. <span data-ttu-id="6f5e2-146">Haga clic en Detalles de línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-146">Click BOM line details.</span></span>
    * <span data-ttu-id="6f5e2-147">El formulario Detalles de línea de L. MAT permite al usuario seleccionar las propiedades necesarias para el subcomponente.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="6f5e2-148">A cada propiedad se le puede dar un valor fijo o asignar a un atributo.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="6f5e2-149">La asignación a un atributo hará que la propiedad de la línea de L. MAT obtenga valores diferentes en función de la selección de la configuración.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="6f5e2-150">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="6f5e2-151">Cada subcomponente representa un producto maestro configurable con tecnología de configuración basada en restricciones.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="6f5e2-152">La referencia se realiza a través del código de artículo.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="6f5e2-153">Active la casilla Establecer.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-153">Select the Set check box.</span></span>
12. <span data-ttu-id="6f5e2-154">Seleccione Sí en el campo Cálculo.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="6f5e2-155">La configuración de la opción de cálculo garantiza que se incluirá el producto al ejecutar un cálculo de coste para el producto.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="6f5e2-156">Haga clic en la pestaña Configurar.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="6f5e2-157">Active la casilla Establecer.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-157">Select the Set check box.</span></span>
15. <span data-ttu-id="6f5e2-158">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="6f5e2-159">El campo de cantidad determina cuánto de este producto se consumirá en el producto configurado.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="6f5e2-160">Active la casilla Establecer.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-160">Select the Set check box.</span></span>
17. <span data-ttu-id="6f5e2-161">En el campo Por serie, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="6f5e2-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="6f5e2-162">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6f5e2-162">Click OK.</span></span>

