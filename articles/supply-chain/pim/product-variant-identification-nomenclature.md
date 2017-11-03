---
title: "Nomenclatura de los nombres y los números de variante de los productos"
description: "En este tema se describe cómo se puede configurar una nomenclatura de número de producto para reemplazar el formato fijo [Número de producto maestro - Configuración - Tamaño - Color - Estilo]. La nueva nomenclatura tiene el formato destinado que incluye el número de producto maestro, las dimensiones de producto activo y los delimitadores de texto de su elección. También puede crear una nomenclatura para los nombres de producto. Por último, también puede crear una nomenclatura para identificar configuraciones creadas por el configurador de producto basado en restricciones. Estas nomenclaturas pueden contener atributos de su elección."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: db01d26376ec3ca6997b1ad2cb62e7b3ecc4b330
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="075b3-107">Nomenclatura de los nombres y los números de variante de los productos</span><span class="sxs-lookup"><span data-stu-id="075b3-107">Nomenclature of product variant numbers and names</span></span>

<span data-ttu-id="075b3-108">En este tema se describe cómo se puede configurar una nomenclatura de número de producto para reemplazar el formato fijo [Número de producto maestro - Configuración - Tamaño - Color - Estilo].</span><span class="sxs-lookup"><span data-stu-id="075b3-108">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="075b3-109">La nueva nomenclatura tiene el formato destinado que incluye el número de producto maestro, las dimensiones de producto activo y los delimitadores de texto de su elección.</span><span class="sxs-lookup"><span data-stu-id="075b3-109">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="075b3-110">También puede crear una nomenclatura para los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-110">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="075b3-111">Por último, también puede crear una nomenclatura para identificar configuraciones creadas por el configurador de producto basado en restricciones.</span><span class="sxs-lookup"><span data-stu-id="075b3-111">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="075b3-112">Estas nomenclaturas pueden contener atributos de su elección.</span><span class="sxs-lookup"><span data-stu-id="075b3-112">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="075b3-113">Las nuevas nomenclaturas para números y nombres de variante de producto permiten incluir segmentos en los identificadores de variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-113">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="075b3-114">Estos segmentos pueden incluir el número y el nombre del producto maestro, identificadores y nombres de dimensiones de producto, secuencias numéricas, constantes de texto y atributos.</span><span class="sxs-lookup"><span data-stu-id="075b3-114">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="075b3-115">Esta funcionalidad permite encontrar rápidamente una variante de producto específica al crear un pedido de ventas o un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="075b3-115">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="075b3-116">Puede crear nomenclaturas para números y nombres de variante de producto en la página **Nomenclatura de producto** .</span><span class="sxs-lookup"><span data-stu-id="075b3-116">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="075b3-117">Para abrir esta página, haga clic en **Gestión de información de productos** &gt; **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="075b3-117">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="075b3-118">Nomenclatura de variantes del producto predefinidas</span><span class="sxs-lookup"><span data-stu-id="075b3-118">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="075b3-119">Las variantes del producto se generan para los productos principales de acuerdo a una de estas tres tecnologías de configuración:</span><span class="sxs-lookup"><span data-stu-id="075b3-119">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="075b3-120">Variantes predefinidas</span><span class="sxs-lookup"><span data-stu-id="075b3-120">Predefined variants</span></span>
-   <span data-ttu-id="075b3-121">Basada en restricciones</span><span class="sxs-lookup"><span data-stu-id="075b3-121">Constraint-based</span></span>
-   <span data-ttu-id="075b3-122">Basada en dimensiones</span><span class="sxs-lookup"><span data-stu-id="075b3-122">Dimension-based</span></span>

<span data-ttu-id="075b3-123">Cada variante de producto tiene un número y un nombre, y las nomenclaturas de identificación de variante de producto permite seleccionar los segmentos que se incluirán en cada número o nombre de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-123">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="075b3-124">Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:</span><span class="sxs-lookup"><span data-stu-id="075b3-124">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="075b3-125">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="075b3-125">Product master number</span></span>
-   <span data-ttu-id="075b3-126">Nombre del producto maestro</span><span class="sxs-lookup"><span data-stu-id="075b3-126">Product master name</span></span>
-   <span data-ttu-id="075b3-127">Valor de secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="075b3-127">Number sequence value</span></span>
-   <span data-ttu-id="075b3-128">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="075b3-128">Text constant</span></span>
-   <span data-ttu-id="075b3-129">Dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="075b3-129">Product dimensions</span></span>
    -   <span data-ttu-id="075b3-130">Id. o nombre de configuración</span><span class="sxs-lookup"><span data-stu-id="075b3-130">Configuration ID or name</span></span>
    -   <span data-ttu-id="075b3-131">Id. o nombre de color</span><span class="sxs-lookup"><span data-stu-id="075b3-131">Color ID or name</span></span>
    -   <span data-ttu-id="075b3-132">Id. o nombre de tamaño</span><span class="sxs-lookup"><span data-stu-id="075b3-132">Size ID or name</span></span>
    -   <span data-ttu-id="075b3-133">Id. o nombre de estilo</span><span class="sxs-lookup"><span data-stu-id="075b3-133">Style ID or name</span></span>

<span data-ttu-id="075b3-134">Trras definir una nomenclatura de identificación de variante de producto, puede asociarla a un grupo de dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-134">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="075b3-135">Se asignará a todos los productos maestros que hagan referencia a este grupo de dimensiones de producto un número de variante de producto de acuerdo con la nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="075b3-135">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="075b3-136">Sin embargo, las nomenclaturas de nombre de variante de producto no se pueden asociar a los grupos de dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-136">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="075b3-137">También puede asignar directamente una nomenclatura de identificación de variante de producto a un producto maestro.</span><span class="sxs-lookup"><span data-stu-id="075b3-137">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="075b3-138">En este caso, se asignarán números y nombres de variante de producto a las variantes de producto que pertenecen al producto maestro, de acuerdo con las nomenclaturas.</span><span class="sxs-lookup"><span data-stu-id="075b3-138">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="075b3-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="075b3-139">Example</span></span>

<span data-ttu-id="075b3-140">Una camiseta (TS1234) se genera en tres tamaños (S, M, L), cuatro colores (Rojo, Verde, Azul, Amarillo) y dos estilo (Polo, V).</span><span class="sxs-lookup"><span data-stu-id="075b3-140">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="075b3-141">Por lo tanto, hay 24 variantes de producto (= 3 × 4 × 2).</span><span class="sxs-lookup"><span data-stu-id="075b3-141">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="075b3-142">Va a crear una nomenclatura de número de variante de producto con los segmentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="075b3-142">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="075b3-143">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="075b3-143">Product master number</span></span>
2.  <span data-ttu-id="075b3-144">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="075b3-144">Text constant: "-"</span></span>
3.  <span data-ttu-id="075b3-145">Color</span><span class="sxs-lookup"><span data-stu-id="075b3-145">Color</span></span>
4.  <span data-ttu-id="075b3-146">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="075b3-146">Text constant: "-"</span></span>
5.  <span data-ttu-id="075b3-147">Tamaño</span><span class="sxs-lookup"><span data-stu-id="075b3-147">Size</span></span>
6.  <span data-ttu-id="075b3-148">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="075b3-148">Text constant: "-"</span></span>
7.  <span data-ttu-id="075b3-149">Estilo</span><span class="sxs-lookup"><span data-stu-id="075b3-149">Style</span></span>

<span data-ttu-id="075b3-150">En este caso, el número de variante de producto para una camiseta de tipo polo, talla pequeña y color rojo sería TS1234-Rojo-Pequeña-Polo.</span><span class="sxs-lookup"><span data-stu-id="075b3-150">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraintbased-configurations"></a><span data-ttu-id="075b3-151">Configuraciones de nomenclatura basada en restricciones</span><span class="sxs-lookup"><span data-stu-id="075b3-151">Nomenclature of constraintbased configurations</span></span>
<span data-ttu-id="075b3-152">Para configuraciones basadas en restricciones puede crear una nomenclatura dedicada para la dimensión de producto de configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-152">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="075b3-153">Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:</span><span class="sxs-lookup"><span data-stu-id="075b3-153">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="075b3-154">Valor de secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="075b3-154">Number sequence value</span></span>
-   <span data-ttu-id="075b3-155">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="075b3-155">Text constant</span></span>
-   <span data-ttu-id="075b3-156">Valor de atributo</span><span class="sxs-lookup"><span data-stu-id="075b3-156">Attribute value</span></span>

<span data-ttu-id="075b3-157">Cada componente de un modelo de configuración de productos puede tener su propia nomenclatura de configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-157">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="075b3-158">Solo pueden usarse atributos que pertenezcan al componente.</span><span class="sxs-lookup"><span data-stu-id="075b3-158">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="075b3-159">No se pueden usar atributos de subcomponentes o de requisitos de usuario.</span><span class="sxs-lookup"><span data-stu-id="075b3-159">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="075b3-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="075b3-160">Example</span></span>

<span data-ttu-id="075b3-161">Un modelo de confuguración del producto tiene un componente raíz con dos atributos:</span><span class="sxs-lookup"><span data-stu-id="075b3-161">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="075b3-162">Material (Plástico, Madera, Acero)</span><span class="sxs-lookup"><span data-stu-id="075b3-162">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="075b3-163">Longitud (10...100)</span><span class="sxs-lookup"><span data-stu-id="075b3-163">Length (10...100)</span></span>

<span data-ttu-id="075b3-164">Va a crear una nomenclatura de configuración con los segmentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="075b3-164">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="075b3-165">Valor de atributo: Material</span><span class="sxs-lookup"><span data-stu-id="075b3-165">Attribute value: Material</span></span>
2.  <span data-ttu-id="075b3-166">Constante de texto: "AAA"</span><span class="sxs-lookup"><span data-stu-id="075b3-166">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="075b3-167">Valor de atributo: Longitud</span><span class="sxs-lookup"><span data-stu-id="075b3-167">Attribute value: Length</span></span>

<span data-ttu-id="075b3-168">En este caso, el identificador de configuración para el material de madera que tiene una longitud de 78 será MaderaAAA78.</span><span class="sxs-lookup"><span data-stu-id="075b3-168">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimensionbased-configurations"></a><span data-ttu-id="075b3-169">Configuraciones de nomenclatura basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="075b3-169">Nomenclature of dimensionbased configurations</span></span>
<span data-ttu-id="075b3-170">Para configuraciones basadas en dimensiones puede crear una nomenclatura dedicada para la dimensión de producto de configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-170">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="075b3-171">Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:</span><span class="sxs-lookup"><span data-stu-id="075b3-171">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="075b3-172">Valor de secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="075b3-172">Number sequence value</span></span>
-   <span data-ttu-id="075b3-173">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="075b3-173">Text constant</span></span>
-   <span data-ttu-id="075b3-174">Elemento de grupo de configuración</span><span class="sxs-lookup"><span data-stu-id="075b3-174">Configuration group item</span></span>

<span data-ttu-id="075b3-175">Puede definir una nomenclatura de configuración para una lista de materiales (L.M.)</span><span class="sxs-lookup"><span data-stu-id="075b3-175">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="075b3-176">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="075b3-176">Example</span></span>

<span data-ttu-id="075b3-177">Una lista de materiales tiene cuatro líneas de L.M. que se dividen en dos grupos de configuración:</span><span class="sxs-lookup"><span data-stu-id="075b3-177">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="075b3-178">Línea de L.M.: M0007, Armario estándar</span><span class="sxs-lookup"><span data-stu-id="075b3-178">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="075b3-179">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="075b3-179">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="075b3-180">Línea de L.M.: M0008, Armario de gama alta</span><span class="sxs-lookup"><span data-stu-id="075b3-180">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="075b3-181">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="075b3-181">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="075b3-182">Línea de L.M.: M0021, Tela en rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="075b3-182">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="075b3-183">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="075b3-183">Configuration group: Front grill</span></span>
-   <span data-ttu-id="075b3-184">Línea de L.M.: M0022, Metal en rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="075b3-184">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="075b3-185">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="075b3-185">Configuration group: Front grill</span></span>

<span data-ttu-id="075b3-186">Va a crear una nomenclatura de configuración con los segmentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="075b3-186">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="075b3-187">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="075b3-187">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="075b3-188">Constante de texto: "&"</span><span class="sxs-lookup"><span data-stu-id="075b3-188">Text constant: "&"</span></span>
3.  <span data-ttu-id="075b3-189">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="075b3-189">Configuration group: Front grill</span></span>

<span data-ttu-id="075b3-190">En este caso, el identificador de configuración para un armario estándar con tela en la rejilla delantera será: M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="075b3-190">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="075b3-191">Nomenclatura para una combinación de variantes del producto y configuraciones</span><span class="sxs-lookup"><span data-stu-id="075b3-191">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="075b3-192">Cuando usa la tecnología de configuración basada en restricciones o en dimensiones para configurar las variantes de producto de un producto maestro, los números de variante de producto o las variantes del producto pueden incluir la nomenclatura de la dimensión de configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-192">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="075b3-193">Siga estos pasos para configurar las variantes.</span><span class="sxs-lookup"><span data-stu-id="075b3-193">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="075b3-194">En la página **Nomenclatura de producto**, defina una nomenclatura de número de variante de producto que incluya la dimensión de configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-194">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="075b3-195">Asigne esta nomenclatura un grupo de dimensiones de producto que tenga la dimensión de configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-195">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="075b3-196">Defina una nomenclatura de configuración para los componentes o L.M. que se usarán para configurar las variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-196">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="075b3-197">También puede crear nomenclaturas para los nombres de variante de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-197">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="075b3-198">Los nombres de variante de producto se pueden configurar para incluir el identificador de configuración o el nombre.</span><span class="sxs-lookup"><span data-stu-id="075b3-198">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="075b3-199">Ejemplo de configuraciones basadas en restricciones</span><span class="sxs-lookup"><span data-stu-id="075b3-199">Example for constraint-based configurations</span></span>

<span data-ttu-id="075b3-200">En este ejemplo, puede usar una nomenclatura de número de variante de producto que consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="075b3-200">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="075b3-201">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="075b3-201">Product master number</span></span>
2.  <span data-ttu-id="075b3-202">Constante de texto: "\_"</span><span class="sxs-lookup"><span data-stu-id="075b3-202">Text constant "\_"</span></span>
3.  <span data-ttu-id="075b3-203">Configuración</span><span class="sxs-lookup"><span data-stu-id="075b3-203">Configuration</span></span>

<span data-ttu-id="075b3-204">La nomenclatura de configuración consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="075b3-204">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="075b3-205">Valor de atributo: Material</span><span class="sxs-lookup"><span data-stu-id="075b3-205">Attribute value: Material</span></span>
2.  <span data-ttu-id="075b3-206">Constante de texto: "AAA"</span><span class="sxs-lookup"><span data-stu-id="075b3-206">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="075b3-207">Valor de atributo: Longitud</span><span class="sxs-lookup"><span data-stu-id="075b3-207">Attribute value: Length</span></span>

<span data-ttu-id="075b3-208">Puede especificar los siguientes valores de los segmentos:</span><span class="sxs-lookup"><span data-stu-id="075b3-208">You enter the following values for segments:</span></span>

-   <span data-ttu-id="075b3-209">Número de producto maestro = **M0099**</span><span class="sxs-lookup"><span data-stu-id="075b3-209">Product master number = **M0099**</span></span>
-   <span data-ttu-id="075b3-210">Material = **Plástico**</span><span class="sxs-lookup"><span data-stu-id="075b3-210">Material = **Plastic**</span></span>
-   <span data-ttu-id="075b3-211">Longitud = **12**</span><span class="sxs-lookup"><span data-stu-id="075b3-211">Length = **12**</span></span>

<span data-ttu-id="075b3-212">En este caso, el número de la variante del producto se convertirá en: M0099\_PlásticoAAA12.</span><span class="sxs-lookup"><span data-stu-id="075b3-212">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="075b3-213">Ejemplo de configuraciones basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="075b3-213">Example for dimension-based configurations</span></span>

<span data-ttu-id="075b3-214">En este ejemplo, puede usar una nomenclatura de número de variante de producto que consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="075b3-214">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="075b3-215">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="075b3-215">Product master number</span></span>
2.  <span data-ttu-id="075b3-216">Constante de texto: "//"</span><span class="sxs-lookup"><span data-stu-id="075b3-216">Text constant "//"</span></span>
3.  <span data-ttu-id="075b3-217">Configuración</span><span class="sxs-lookup"><span data-stu-id="075b3-217">Configuration</span></span>

<span data-ttu-id="075b3-218">La nomenclatura de configuración consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="075b3-218">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="075b3-219">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="075b3-219">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="075b3-220">Constante de texto: "&"</span><span class="sxs-lookup"><span data-stu-id="075b3-220">Text constant: "&"</span></span>
3.  <span data-ttu-id="075b3-221">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="075b3-221">Configuration group: Front grill</span></span>

<span data-ttu-id="075b3-222">Puede especificar los siguientes valores de los segmentos:</span><span class="sxs-lookup"><span data-stu-id="075b3-222">You enter the following values for segments:</span></span>

-   <span data-ttu-id="075b3-223">Número de producto maestro = **D0123**</span><span class="sxs-lookup"><span data-stu-id="075b3-223">Product master number = **D0123**</span></span>
-   <span data-ttu-id="075b3-224">Armario = **M0008**</span><span class="sxs-lookup"><span data-stu-id="075b3-224">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="075b3-225">Rejilla delantera = **M0022**</span><span class="sxs-lookup"><span data-stu-id="075b3-225">Front grill = **M0022**</span></span>

<span data-ttu-id="075b3-226">En este caso, el número de la variante del producto será D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="075b3-226">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="075b3-227">Numeración de conflictos</span><span class="sxs-lookup"><span data-stu-id="075b3-227">Numbering conflicts</span></span>
<span data-ttu-id="075b3-228">En algunos casos, es posible configurar una nomenclatura de número de variante de producto que no genere números únicos de variante de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-228">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="075b3-229">Por ejemplo, los números de variante de producto no serán únicos si una dimensión de producto activo no se incluye en la nomenclatura para un producto maestro que utilice la tecnología de configuración de variantes predefinida.</span><span class="sxs-lookup"><span data-stu-id="075b3-229">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="075b3-230">La forma de solucionar conflictos variará en función de la tecnología de configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-230">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="075b3-231">Variantes predefinidas</span><span class="sxs-lookup"><span data-stu-id="075b3-231">Predefined variants</span></span>

<span data-ttu-id="075b3-232">Se producirá un error si intenta generar variantes de producto manualmente o automáticamente, y más de una variante de producto terminará con el mismo número.</span><span class="sxs-lookup"><span data-stu-id="075b3-232">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="075b3-233">Para evitar este escenario, debe utilizar todas las dimensiones de producto activo del grupo de dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="075b3-233">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="075b3-234">Como alternativa, incluya una secuencia numérica para asegurarse de que los números de variante de producto sean únicos.</span><span class="sxs-lookup"><span data-stu-id="075b3-234">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="075b3-235">Configuraciones basadas en restricciones</span><span class="sxs-lookup"><span data-stu-id="075b3-235">Constraint-based configurations</span></span>

<span data-ttu-id="075b3-236">En función de la nomenclatura, el sistema puede intentar asignar un número de variante de producto que no es único a una configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-236">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="075b3-237">En este caso, el sistema utilizará la secuencia numérica para la dimensión de configuración como número de variante de producto. ESto generará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="075b3-237">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="075b3-238">Para evitar este escenario debe incluir suficientes atributos en la nomenclatura para asegurarse de que se generen números de variante de producto únicos.</span><span class="sxs-lookup"><span data-stu-id="075b3-238">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="075b3-239">También debe asegurarse de que la opción **Reutilizar** esté activada para el componente.</span><span class="sxs-lookup"><span data-stu-id="075b3-239">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="075b3-240">Configuraciones basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="075b3-240">Dimension-based configurations</span></span>

<span data-ttu-id="075b3-241">En uno de los pasos del proceso de configuración, el sistema sugiere un valor de configuración según la nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="075b3-241">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="075b3-242">En dicho paso, puede cambiar manualmente el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="075b3-242">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="075b3-243">Cuando guarde la configuración, el sistema comprobará si el valor de configuración es único.</span><span class="sxs-lookup"><span data-stu-id="075b3-243">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="075b3-244">Si el valor que ha especificado no es único, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="075b3-244">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="075b3-245">Para poder guardar la configuración debe especificar un valor de configuración único.</span><span class="sxs-lookup"><span data-stu-id="075b3-245">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="see-also"></a><span data-ttu-id="075b3-246">Consulte también</span><span class="sxs-lookup"><span data-stu-id="075b3-246">See also</span></span>
--------

[<span data-ttu-id="075b3-247">Crear una nomenclatura del número de producto para las variantes de producto predefinidas</span><span class="sxs-lookup"><span data-stu-id="075b3-247">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="075b3-248">Crear una nomenclatura del número de producto para las variantes de producto configuradas</span><span class="sxs-lookup"><span data-stu-id="075b3-248">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)


