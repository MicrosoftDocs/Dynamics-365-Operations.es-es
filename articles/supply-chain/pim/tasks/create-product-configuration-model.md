---
title: Crear un modelo de configuración de productos
description: Este procedimiento muestra cómo crear un modelo de configuración de productos y especificar información básica como atributos y subcomponentes.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb9e33d7bab6ca9cd378ec40baa796d1a933ece
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921374"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="307d4-103">Crear un modelo de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="307d4-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="307d4-104">Este procedimiento muestra cómo crear un modelo de configuración de productos y especificar información básica como atributos y subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="307d4-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="307d4-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="307d4-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="307d4-106">Crear un modelo de producto</span><span class="sxs-lookup"><span data-stu-id="307d4-106">Create a product model</span></span>

1. <span data-ttu-id="307d4-107">Vaya a **Gestión de información de productos \> Productos \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="307d4-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="307d4-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="307d4-108">Select **New**.</span></span>
1. <span data-ttu-id="307d4-109">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-109">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="307d4-110">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-110">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="307d4-111">En el campo **Estrategia de solucionador**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="307d4-111">In the **Solver strategy** field, select an option.</span></span>
    * <span data-ttu-id="307d4-112">La estrategia de solucionador determina la manera en que se procesan las restricciones de un modelo de configuración de productos basado en restricciones.</span><span class="sxs-lookup"><span data-stu-id="307d4-112">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="307d4-113">Esta selección puede tener un impacto en el rendimiento del modelo de configuración de productos.</span><span class="sxs-lookup"><span data-stu-id="307d4-113">This selection can have an impact on the performance of the product configuration model.</span></span>  
1. <span data-ttu-id="307d4-114">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-114">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="307d4-115">El componente raíz representa el modelo de configuración de productos, pero también se puede usar en otros modelos de productos.</span><span class="sxs-lookup"><span data-stu-id="307d4-115">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
1. <span data-ttu-id="307d4-116">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="307d4-116">Select **OK**.</span></span>
1. <span data-ttu-id="307d4-117">En el campo **Volver a utilizar configuraciones**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="307d4-117">In the **Reuse configurations** field, select an option.</span></span>
    * <span data-ttu-id="307d4-118">Si el parámetro Volver a utilizar configuraciones se establece Sí, el sistema comprobará las configuraciones idénticas después de cada sesión y las volverá a utilizar si se encuentra una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="307d4-118">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="307d4-119">Agregar atributos</span><span class="sxs-lookup"><span data-stu-id="307d4-119">Add attributes</span></span>

1. <span data-ttu-id="307d4-120">Expanda la sección **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="307d4-120">Expand the **Attributes** section.</span></span>
2. <span data-ttu-id="307d4-121">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="307d4-121">Select **Add**.</span></span>
3. <span data-ttu-id="307d4-122">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="307d4-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="307d4-123">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-123">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="307d4-124">En el campo **Nombre del solucionador**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-124">In the **Solver name** field, type a value.</span></span>
    * <span data-ttu-id="307d4-125">El nombre del solucionador lo usa el resolvedor de restricciones del configurador de productos.</span><span class="sxs-lookup"><span data-stu-id="307d4-125">The solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="307d4-126">No debe incluir espacios ni caracteres especiales excepto _ (guión bajo).</span><span class="sxs-lookup"><span data-stu-id="307d4-126">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="307d4-127">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-127">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="307d4-128">El texto de la descripción se muestra al usuario de configuración y puede por tanto servir de ayuda en la selección del valor del atributo correcto.</span><span class="sxs-lookup"><span data-stu-id="307d4-128">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="307d4-129">En el campo **Tipo de atributo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-129">In the **Attribute type** field, enter or select a value.</span></span>
    * <span data-ttu-id="307d4-130">El tipo de atributo determina qué valores están disponibles para el atributo.</span><span class="sxs-lookup"><span data-stu-id="307d4-130">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="307d4-131">Active la casilla **Incluir en reutilización**.</span><span class="sxs-lookup"><span data-stu-id="307d4-131">Select the **Include in reuse** check box.</span></span>
    * <span data-ttu-id="307d4-132">Esta opción solo está disponible si se ha seleccionado la opción Volver a utilizar configuraciones.</span><span class="sxs-lookup"><span data-stu-id="307d4-132">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="307d4-133">Incluir el atributo en la casilla de volver a utilizar significa que este atributo se considerará cuando el sistema busque una coincidencia exacta.</span><span class="sxs-lookup"><span data-stu-id="307d4-133">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="307d4-134">Agregar subcomponentes</span><span class="sxs-lookup"><span data-stu-id="307d4-134">Add subcomponents</span></span>

1. <span data-ttu-id="307d4-135">Expanda la sección **Subcomponentes**.</span><span class="sxs-lookup"><span data-stu-id="307d4-135">Expand the **Subcomponents** section.</span></span>
2. <span data-ttu-id="307d4-136">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="307d4-136">Select **Add**.</span></span>
3. <span data-ttu-id="307d4-137">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="307d4-137">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="307d4-138">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="307d4-139">En el campo **Nombre del solucionador**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-139">In the **Solver name** field, type a value.</span></span>
6. <span data-ttu-id="307d4-140">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-140">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="307d4-141">En el campo **Componente**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-141">In the **Component** field, enter or select a value.</span></span>
    * <span data-ttu-id="307d4-142">Cada subcomponente debe hacer referencia a una definición del componente.</span><span class="sxs-lookup"><span data-stu-id="307d4-142">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="307d4-143">Este diseño admite los componentes reutilizables y garantiza que una vez que se ha definido un componente puede usarse en muchos modelos de productos.</span><span class="sxs-lookup"><span data-stu-id="307d4-143">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="307d4-144">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="307d4-144">Select **Save**.</span></span>
9. <span data-ttu-id="307d4-145">Seleccione **Detalles de línea de L. MAT.**.</span><span class="sxs-lookup"><span data-stu-id="307d4-145">Select **BOM line details**.</span></span>
    * <span data-ttu-id="307d4-146">El formulario Detalles de línea de L. MAT permite al usuario seleccionar las propiedades necesarias para el subcomponente.</span><span class="sxs-lookup"><span data-stu-id="307d4-146">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="307d4-147">A cada propiedad se le puede dar un valor fijo o asignar a un atributo.</span><span class="sxs-lookup"><span data-stu-id="307d4-147">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="307d4-148">La asignación a un atributo hará que la propiedad de la línea de L. MAT obtenga valores diferentes en función de la selección de la configuración.</span><span class="sxs-lookup"><span data-stu-id="307d4-148">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="307d4-149">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="307d4-149">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="307d4-150">Cada subcomponente representa un producto maestro configurable con tecnología de configuración basada en restricciones.</span><span class="sxs-lookup"><span data-stu-id="307d4-150">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="307d4-151">La referencia se realiza a través del código de artículo.</span><span class="sxs-lookup"><span data-stu-id="307d4-151">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="307d4-152">Seleccione la casilla **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="307d4-152">Select the **Set** check box.</span></span>
12. <span data-ttu-id="307d4-153">Seleccione **Sí** en el campo **Cálculo**.</span><span class="sxs-lookup"><span data-stu-id="307d4-153">Select **Yes** in the **Calculation** field.</span></span>
    * <span data-ttu-id="307d4-154">La configuración de la opción de cálculo garantiza que se incluirá el producto al ejecutar un cálculo de coste para el producto.</span><span class="sxs-lookup"><span data-stu-id="307d4-154">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="307d4-155">Seleccione la pestaña **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="307d4-155">Select the **Setup** tab.</span></span>
14. <span data-ttu-id="307d4-156">Seleccione la casilla **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="307d4-156">Select the **Set** check box.</span></span>
15. <span data-ttu-id="307d4-157">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="307d4-157">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="307d4-158">El campo de cantidad determina cuánto de este producto se consumirá en el producto configurado.</span><span class="sxs-lookup"><span data-stu-id="307d4-158">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="307d4-159">Seleccione la casilla **Establecer**.</span><span class="sxs-lookup"><span data-stu-id="307d4-159">Select the **Set** check box.</span></span>
17. <span data-ttu-id="307d4-160">En el campo **Por serie**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="307d4-160">In the **Per series** field, enter a number.</span></span>
18. <span data-ttu-id="307d4-161">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="307d4-161">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]