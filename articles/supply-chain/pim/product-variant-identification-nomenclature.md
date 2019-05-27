---
title: Nomenclatura de los nombres y los números de variante de los productos
description: En este tema se describe cómo se puede configurar una nomenclatura de número de producto para reemplazar el formato fijo [Número de producto maestro - Configuración - Tamaño - Color - Estilo].
author: roxanadiaconu
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResNomenclature, EcoResProductDimensionGroup, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 220104
ms.assetid: 3fe69fb7-5c32-423c-98a8-2f53186cda68
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: f84b6982af8b81ff83086d163a77e1c2f58ca478
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563560"
---
# <a name="nomenclature-of-product-variant-numbers-and-names"></a><span data-ttu-id="f9e86-103">Nomenclatura de los nombres y los números de variante de los productos</span><span class="sxs-lookup"><span data-stu-id="f9e86-103">Nomenclature of product variant numbers and names</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9e86-104">En este tema se describe cómo se puede configurar una nomenclatura de número de producto para reemplazar el formato fijo [Número de producto maestro - Configuración - Tamaño - Color - Estilo].</span><span class="sxs-lookup"><span data-stu-id="f9e86-104">This topic describes how you can set up a product number nomenclature to replace the fixed [Product master number - Configuration - Size - Color - Style] format.</span></span> <span data-ttu-id="f9e86-105">La nueva nomenclatura tiene el formato destinado que incluye el número de producto maestro, las dimensiones de producto activo y los delimitadores de texto de su elección.</span><span class="sxs-lookup"><span data-stu-id="f9e86-105">The new nomenclature has a targeted format that includes the product master number, active product dimensions, and text delimiters of your choice.</span></span> <span data-ttu-id="f9e86-106">También puede crear una nomenclatura para los nombres de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-106">You can also create a nomenclature for product names.</span></span> <span data-ttu-id="f9e86-107">Por último, también puede crear una nomenclatura para identificar configuraciones creadas por el configurador de producto basado en restricciones.</span><span class="sxs-lookup"><span data-stu-id="f9e86-107">Finally, you can build a nomenclature to identify configurations that are created by the constraint-based product configurator.</span></span> <span data-ttu-id="f9e86-108">Estas nomenclaturas pueden contener atributos de su elección.</span><span class="sxs-lookup"><span data-stu-id="f9e86-108">These nomenclatures can contain attributes of your choice.</span></span>

<span data-ttu-id="f9e86-109">Las nuevas nomenclaturas para números y nombres de variante de producto permiten incluir segmentos en los identificadores de variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-109">The new nomenclatures for product variant numbers and product variant names let you include segments in the identifiers for product variants.</span></span> <span data-ttu-id="f9e86-110">Estos segmentos pueden incluir el número y el nombre del producto maestro, identificadores y nombres de dimensiones de producto, secuencias numéricas, constantes de texto y atributos.</span><span class="sxs-lookup"><span data-stu-id="f9e86-110">These segments can include the product master number and name, product dimension IDs and names, number sequences, text constants, and attributes.</span></span> <span data-ttu-id="f9e86-111">Esta funcionalidad permite encontrar rápidamente una variante de producto específica al crear un pedido de ventas o un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f9e86-111">This functionality lets you quickly find a specific product variant when you create a sales order or a purchase order.</span></span> <span data-ttu-id="f9e86-112">Puede crear nomenclaturas para números y nombres de variante de producto en la página **Nomenclatura de producto** .</span><span class="sxs-lookup"><span data-stu-id="f9e86-112">You create nomenclatures for both product variant numbers and product variant names by using the **Product nomenclature** page.</span></span> <span data-ttu-id="f9e86-113">Para abrir esta página, haga clic en **Gestión de información de productos** &gt; **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="f9e86-113">To open this page, click **Product information management** &gt; **Setup**.</span></span>

## <a name="nomenclature-of-predefined-product-variants"></a><span data-ttu-id="f9e86-114">Nomenclatura de variantes del producto predefinidas</span><span class="sxs-lookup"><span data-stu-id="f9e86-114">Nomenclature of predefined product variants</span></span>
<span data-ttu-id="f9e86-115">Las variantes del producto se generan para los productos principales de acuerdo a una de estas tres tecnologías de configuración:</span><span class="sxs-lookup"><span data-stu-id="f9e86-115">Product variants are generated for product masters according to one of three configuration technologies:</span></span>

-   <span data-ttu-id="f9e86-116">Variantes predefinidas</span><span class="sxs-lookup"><span data-stu-id="f9e86-116">Predefined variants</span></span>
-   <span data-ttu-id="f9e86-117">Basada en restricciones</span><span class="sxs-lookup"><span data-stu-id="f9e86-117">Constraint-based</span></span>
-   <span data-ttu-id="f9e86-118">Basada en dimensiones</span><span class="sxs-lookup"><span data-stu-id="f9e86-118">Dimension-based</span></span>

<span data-ttu-id="f9e86-119">Cada variante de producto tiene un número y un nombre, y las nomenclaturas de identificación de variante de producto permite seleccionar los segmentos que se incluirán en cada número o nombre de variante del producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-119">Each product variant has a number and a name, and the product variant identification nomenclatures let you select the segments that will be included in each product variant number or name.</span></span> <span data-ttu-id="f9e86-120">Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:</span><span class="sxs-lookup"><span data-stu-id="f9e86-120">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="f9e86-121">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="f9e86-121">Product master number</span></span>
-   <span data-ttu-id="f9e86-122">Nombre del producto maestro</span><span class="sxs-lookup"><span data-stu-id="f9e86-122">Product master name</span></span>
-   <span data-ttu-id="f9e86-123">Valor de secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="f9e86-123">Number sequence value</span></span>
-   <span data-ttu-id="f9e86-124">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="f9e86-124">Text constant</span></span>
-   <span data-ttu-id="f9e86-125">Dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="f9e86-125">Product dimensions</span></span>
    -   <span data-ttu-id="f9e86-126">Id. o nombre de configuración</span><span class="sxs-lookup"><span data-stu-id="f9e86-126">Configuration ID or name</span></span>
    -   <span data-ttu-id="f9e86-127">Id. o nombre de color</span><span class="sxs-lookup"><span data-stu-id="f9e86-127">Color ID or name</span></span>
    -   <span data-ttu-id="f9e86-128">Id. o nombre de tamaño</span><span class="sxs-lookup"><span data-stu-id="f9e86-128">Size ID or name</span></span>
    -   <span data-ttu-id="f9e86-129">Id. o nombre de estilo</span><span class="sxs-lookup"><span data-stu-id="f9e86-129">Style ID or name</span></span>

<span data-ttu-id="f9e86-130">Trras definir una nomenclatura de identificación de variante de producto, puede asociarla a un grupo de dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-130">After you define a product variant identification number nomenclature, you can associate it with a product dimension group.</span></span> <span data-ttu-id="f9e86-131">Se asignará a todos los productos maestros que hagan referencia a este grupo de dimensiones de producto un número de variante de producto de acuerdo con la nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="f9e86-131">All product masters that reference this product dimension group will then be assigned product variant numbers according to the nomenclature.</span></span> <span data-ttu-id="f9e86-132">Sin embargo, las nomenclaturas de nombre de variante de producto no se pueden asociar a los grupos de dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-132">However, product variant name nomenclatures can't be associated with product dimension groups.</span></span> <span data-ttu-id="f9e86-133">También puede asignar directamente una nomenclatura de identificación de variante de producto a un producto maestro.</span><span class="sxs-lookup"><span data-stu-id="f9e86-133">You can also assign a product variant identification nomenclature directly to a product master.</span></span> <span data-ttu-id="f9e86-134">En este caso, se asignarán números y nombres de variante de producto a las variantes de producto que pertenecen al producto maestro, de acuerdo con las nomenclaturas.</span><span class="sxs-lookup"><span data-stu-id="f9e86-134">In this case, the product variants that belong to the product master will be assigned product variant numbers and names according to the nomenclatures.</span></span>

### <a name="example"></a><span data-ttu-id="f9e86-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9e86-135">Example</span></span>

<span data-ttu-id="f9e86-136">Una camiseta (TS1234) se genera en tres tamaños (S, M, L), cuatro colores (Rojo, Verde, Azul, Amarillo) y dos estilo (Polo, V).</span><span class="sxs-lookup"><span data-stu-id="f9e86-136">A T-shirt (TS1234) is produced in three sizes (S, M, L), four colors (Red, Green, Blue, Yellow), and two styles (Polo, V).</span></span> <span data-ttu-id="f9e86-137">Por lo tanto, hay 24 variantes de producto (= 3 × 4 × 2).</span><span class="sxs-lookup"><span data-stu-id="f9e86-137">Therefore, 24 product variants are possible (= 3 × 4 × 2).</span></span> <span data-ttu-id="f9e86-138">Va a crear una nomenclatura de número de variante de producto con los segmentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9e86-138">You create a product variant number nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="f9e86-139">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="f9e86-139">Product master number</span></span>
2.  <span data-ttu-id="f9e86-140">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="f9e86-140">Text constant: "-"</span></span>
3.  <span data-ttu-id="f9e86-141">Color</span><span class="sxs-lookup"><span data-stu-id="f9e86-141">Color</span></span>
4.  <span data-ttu-id="f9e86-142">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="f9e86-142">Text constant: "-"</span></span>
5.  <span data-ttu-id="f9e86-143">Tamaño</span><span class="sxs-lookup"><span data-stu-id="f9e86-143">Size</span></span>
6.  <span data-ttu-id="f9e86-144">Constante de texto: "-"</span><span class="sxs-lookup"><span data-stu-id="f9e86-144">Text constant: "-"</span></span>
7.  <span data-ttu-id="f9e86-145">Estilo</span><span class="sxs-lookup"><span data-stu-id="f9e86-145">Style</span></span>

<span data-ttu-id="f9e86-146">En este caso, el número de variante de producto para una camiseta de tipo polo, talla pequeña y color rojo sería TS1234-Rojo-Pequeña-Polo.</span><span class="sxs-lookup"><span data-stu-id="f9e86-146">In this case, the product variant number for a red, small, polo T-shirt will be TS1234-Red-Small-Polo.</span></span>

## <a name="nomenclature-of-constraint-based-configurations"></a><span data-ttu-id="f9e86-147">Configuraciones de nomenclatura basada en restricciones</span><span class="sxs-lookup"><span data-stu-id="f9e86-147">Nomenclature of constraint-based configurations</span></span>
<span data-ttu-id="f9e86-148">Para configuraciones basadas en restricciones puede crear una nomenclatura dedicada para la dimensión de producto de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-148">For constraint-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="f9e86-149">Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:</span><span class="sxs-lookup"><span data-stu-id="f9e86-149">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="f9e86-150">Valor de secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="f9e86-150">Number sequence value</span></span>
-   <span data-ttu-id="f9e86-151">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="f9e86-151">Text constant</span></span>
-   <span data-ttu-id="f9e86-152">Valor de atributo</span><span class="sxs-lookup"><span data-stu-id="f9e86-152">Attribute value</span></span>

<span data-ttu-id="f9e86-153">Cada componente de un modelo de configuración de productos puede tener su propia nomenclatura de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-153">Each component in a product configuration model can have its own configuration nomenclature.</span></span> <span data-ttu-id="f9e86-154">Solo pueden usarse atributos que pertenezcan al componente.</span><span class="sxs-lookup"><span data-stu-id="f9e86-154">Only attributes that belong to the component can be used.</span></span> <span data-ttu-id="f9e86-155">No se pueden usar atributos de subcomponentes o de requisitos de usuario.</span><span class="sxs-lookup"><span data-stu-id="f9e86-155">Attributes from subcomponents or user requirements can't be used.</span></span>

### <a name="example"></a><span data-ttu-id="f9e86-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9e86-156">Example</span></span>

<span data-ttu-id="f9e86-157">Un modelo de confuguración del producto tiene un componente raíz con dos atributos:</span><span class="sxs-lookup"><span data-stu-id="f9e86-157">A product configuration model has a root component that has two attributes:</span></span>

-   <span data-ttu-id="f9e86-158">Material (Plástico, Madera, Acero)</span><span class="sxs-lookup"><span data-stu-id="f9e86-158">Material (Plastic, Wood, Steel)</span></span>
-   <span data-ttu-id="f9e86-159">Longitud (10...100)</span><span class="sxs-lookup"><span data-stu-id="f9e86-159">Length (10...100)</span></span>

<span data-ttu-id="f9e86-160">Va a crear una nomenclatura de configuración con los segmentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9e86-160">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="f9e86-161">Valor de atributo: Material</span><span class="sxs-lookup"><span data-stu-id="f9e86-161">Attribute value: Material</span></span>
2.  <span data-ttu-id="f9e86-162">Constante de texto: "AAA"</span><span class="sxs-lookup"><span data-stu-id="f9e86-162">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="f9e86-163">Valor de atributo: Longitud</span><span class="sxs-lookup"><span data-stu-id="f9e86-163">Attribute value: Length</span></span>

<span data-ttu-id="f9e86-164">En este caso, el identificador de configuración para el material de madera que tiene una longitud de 78 será MaderaAAA78.</span><span class="sxs-lookup"><span data-stu-id="f9e86-164">In this case, the configuration ID for wood material that has a length of 78 will be WoodAAA78.</span></span>

## <a name="nomenclature-of-dimension-based-configurations"></a><span data-ttu-id="f9e86-165">Configuraciones de nomenclatura basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="f9e86-165">Nomenclature of dimension-based configurations</span></span>
<span data-ttu-id="f9e86-166">Para configuraciones basadas en dimensiones puede crear una nomenclatura dedicada para la dimensión de producto de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-166">For dimension-based configurations, you can create a dedicated nomenclature for the configuration product dimension.</span></span> <span data-ttu-id="f9e86-167">Puede seleccionar los segmentos siguientes en página **Nomenclatura de producto**:</span><span class="sxs-lookup"><span data-stu-id="f9e86-167">You can select the following segments on the **Product nomenclature** page:</span></span>

-   <span data-ttu-id="f9e86-168">Valor de secuencia numérica</span><span class="sxs-lookup"><span data-stu-id="f9e86-168">Number sequence value</span></span>
-   <span data-ttu-id="f9e86-169">Constante de texto</span><span class="sxs-lookup"><span data-stu-id="f9e86-169">Text constant</span></span>
-   <span data-ttu-id="f9e86-170">Elemento de grupo de configuración</span><span class="sxs-lookup"><span data-stu-id="f9e86-170">Configuration group item</span></span>

<span data-ttu-id="f9e86-171">Puede definir una nomenclatura de configuración para una lista de materiales (L.M.)</span><span class="sxs-lookup"><span data-stu-id="f9e86-171">You can define a configuration nomenclature for a bill of materials (BOM).</span></span>

### <a name="example"></a><span data-ttu-id="f9e86-172">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9e86-172">Example</span></span>

<span data-ttu-id="f9e86-173">Una lista de materiales tiene cuatro líneas de L.M. que se dividen en dos grupos de configuración:</span><span class="sxs-lookup"><span data-stu-id="f9e86-173">A BOM has four BOM lines that are divided into two configuration groups:</span></span>

-   <span data-ttu-id="f9e86-174">Línea de L.M.: M0007, Armario estándar</span><span class="sxs-lookup"><span data-stu-id="f9e86-174">BOM line: M0007, Standard cabinet</span></span>
    -   <span data-ttu-id="f9e86-175">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="f9e86-175">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="f9e86-176">Línea de L.M.: M0008, Armario de gama alta</span><span class="sxs-lookup"><span data-stu-id="f9e86-176">BOM line: M0008, High end cabinet</span></span>
    -   <span data-ttu-id="f9e86-177">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="f9e86-177">Configuration group: Cabinet</span></span>
-   <span data-ttu-id="f9e86-178">Línea de L.M.: M0021, Tela en rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="f9e86-178">BOM line: M0021, Front grill cloth</span></span>
    -   <span data-ttu-id="f9e86-179">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="f9e86-179">Configuration group: Front grill</span></span>
-   <span data-ttu-id="f9e86-180">Línea de L.M.: M0022, Metal en rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="f9e86-180">BOM line: M0022, Front grill metal</span></span>
    -   <span data-ttu-id="f9e86-181">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="f9e86-181">Configuration group: Front grill</span></span>

<span data-ttu-id="f9e86-182">Va a crear una nomenclatura de configuración con los segmentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f9e86-182">You create a configuration nomenclature that has the following segments:</span></span>

1.  <span data-ttu-id="f9e86-183">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="f9e86-183">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="f9e86-184">Constante de texto: "&"</span><span class="sxs-lookup"><span data-stu-id="f9e86-184">Text constant: "&"</span></span>
3.  <span data-ttu-id="f9e86-185">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="f9e86-185">Configuration group: Front grill</span></span>

<span data-ttu-id="f9e86-186">En este caso, el identificador de configuración para un armario estándar con tela en la rejilla delantera será: M0007&M0021.</span><span class="sxs-lookup"><span data-stu-id="f9e86-186">In this case, the configuration ID for a standard cabinet that has a cloth front grill will be M0007&M0021.</span></span>

## <a name="nomenclature-for-a-combination-of-product-variants-and-configurations"></a><span data-ttu-id="f9e86-187">Nomenclatura para una combinación de variantes del producto y configuraciones</span><span class="sxs-lookup"><span data-stu-id="f9e86-187">Nomenclature for a combination of product variants and configurations</span></span>
<span data-ttu-id="f9e86-188">Cuando usa la tecnología de configuración basada en restricciones o en dimensiones para configurar las variantes de producto de un producto maestro, los números de variante de producto o las variantes del producto pueden incluir la nomenclatura de la dimensión de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-188">When you use either the constraint-based configuration technology or the dimension-based configuration technology to configure product variants for a product master, the product variant numbers of the product variants can include the nomenclature from the configuration dimension.</span></span> <span data-ttu-id="f9e86-189">Siga estos pasos para configurar las variantes.</span><span class="sxs-lookup"><span data-stu-id="f9e86-189">Follow these steps to configure variants.</span></span>

1.  <span data-ttu-id="f9e86-190">En la página **Nomenclatura de producto**, defina una nomenclatura de número de variante de producto que incluya la dimensión de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-190">On the **Product nomenclature** page, define a product variant number nomenclature that includes the configuration dimension.</span></span>
2.  <span data-ttu-id="f9e86-191">Asigne esta nomenclatura un grupo de dimensiones de producto que tenga la dimensión de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-191">Assign the nomenclature to a product dimension group that has the configuration dimension.</span></span>
3.  <span data-ttu-id="f9e86-192">Defina una nomenclatura de configuración para los componentes o L.M. que se usarán para configurar las variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-192">Define a configuration nomenclature for the components or BOMs that will be used to configure the product variants.</span></span>

<span data-ttu-id="f9e86-193">También puede crear nomenclaturas para los nombres de variante de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-193">You can also create nomenclatures for the product variant names.</span></span> <span data-ttu-id="f9e86-194">Los nombres de variante de producto se pueden configurar para incluir el identificador de configuración o el nombre.</span><span class="sxs-lookup"><span data-stu-id="f9e86-194">The product variant names can be configured to include the configuration ID or name.</span></span>

### <a name="example-for-constraint-based-configurations"></a><span data-ttu-id="f9e86-195">Ejemplo de configuraciones basadas en restricciones</span><span class="sxs-lookup"><span data-stu-id="f9e86-195">Example for constraint-based configurations</span></span>

<span data-ttu-id="f9e86-196">En este ejemplo, puede usar una nomenclatura de número de variante de producto que consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="f9e86-196">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="f9e86-197">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="f9e86-197">Product master number</span></span>
2.  <span data-ttu-id="f9e86-198">Constante de texto: "\_"</span><span class="sxs-lookup"><span data-stu-id="f9e86-198">Text constant "\_"</span></span>
3.  <span data-ttu-id="f9e86-199">Configuración</span><span class="sxs-lookup"><span data-stu-id="f9e86-199">Configuration</span></span>

<span data-ttu-id="f9e86-200">La nomenclatura de configuración consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="f9e86-200">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="f9e86-201">Valor de atributo: Material</span><span class="sxs-lookup"><span data-stu-id="f9e86-201">Attribute value: Material</span></span>
2.  <span data-ttu-id="f9e86-202">Constante de texto: "AAA"</span><span class="sxs-lookup"><span data-stu-id="f9e86-202">Text constant: "AAA"</span></span>
3.  <span data-ttu-id="f9e86-203">Valor de atributo: Longitud</span><span class="sxs-lookup"><span data-stu-id="f9e86-203">Attribute value: Length</span></span>

<span data-ttu-id="f9e86-204">Puede especificar los siguientes valores de los segmentos:</span><span class="sxs-lookup"><span data-stu-id="f9e86-204">You enter the following values for segments:</span></span>

-   <span data-ttu-id="f9e86-205">Número de producto maestro = **M0099**</span><span class="sxs-lookup"><span data-stu-id="f9e86-205">Product master number = **M0099**</span></span>
-   <span data-ttu-id="f9e86-206">Material = **Plástico**</span><span class="sxs-lookup"><span data-stu-id="f9e86-206">Material = **Plastic**</span></span>
-   <span data-ttu-id="f9e86-207">Longitud = **12**</span><span class="sxs-lookup"><span data-stu-id="f9e86-207">Length = **12**</span></span>

<span data-ttu-id="f9e86-208">En este caso, el número de la variante del producto se convertirá en: M0099\_PlásticoAAA12.</span><span class="sxs-lookup"><span data-stu-id="f9e86-208">In this case, the product variant number will be M0099\_PlasticAAA12.</span></span>

### <a name="example-for-dimension-based-configurations"></a><span data-ttu-id="f9e86-209">Ejemplo de configuraciones basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="f9e86-209">Example for dimension-based configurations</span></span>

<span data-ttu-id="f9e86-210">En este ejemplo, puede usar una nomenclatura de número de variante de producto que consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="f9e86-210">For this example, you use a product variant number nomenclature that consists of the following segments:</span></span>

1.  <span data-ttu-id="f9e86-211">Número de producto maestro</span><span class="sxs-lookup"><span data-stu-id="f9e86-211">Product master number</span></span>
2.  <span data-ttu-id="f9e86-212">Constante de texto: "//"</span><span class="sxs-lookup"><span data-stu-id="f9e86-212">Text constant "//"</span></span>
3.  <span data-ttu-id="f9e86-213">Configuración</span><span class="sxs-lookup"><span data-stu-id="f9e86-213">Configuration</span></span>

<span data-ttu-id="f9e86-214">La nomenclatura de configuración consta de los siguientes segmentos:</span><span class="sxs-lookup"><span data-stu-id="f9e86-214">The configuration nomenclature consists of the following segments:</span></span>

1.  <span data-ttu-id="f9e86-215">Grupo de configuración: Armario</span><span class="sxs-lookup"><span data-stu-id="f9e86-215">Configuration group: Cabinet</span></span>
2.  <span data-ttu-id="f9e86-216">Constante de texto: "&"</span><span class="sxs-lookup"><span data-stu-id="f9e86-216">Text constant: "&"</span></span>
3.  <span data-ttu-id="f9e86-217">Grupo de configuración: Rejilla delantera</span><span class="sxs-lookup"><span data-stu-id="f9e86-217">Configuration group: Front grill</span></span>

<span data-ttu-id="f9e86-218">Puede especificar los siguientes valores de los segmentos:</span><span class="sxs-lookup"><span data-stu-id="f9e86-218">You enter the following values for segments:</span></span>

-   <span data-ttu-id="f9e86-219">Número de producto maestro = **D0123**</span><span class="sxs-lookup"><span data-stu-id="f9e86-219">Product master number = **D0123**</span></span>
-   <span data-ttu-id="f9e86-220">Armario = **M0008**</span><span class="sxs-lookup"><span data-stu-id="f9e86-220">Cabinet = **M0008**</span></span>
-   <span data-ttu-id="f9e86-221">Rejilla delantera = **M0022**</span><span class="sxs-lookup"><span data-stu-id="f9e86-221">Front grill = **M0022**</span></span>

<span data-ttu-id="f9e86-222">En este caso, el número de la variante del producto será D0123//M0008&M0022.</span><span class="sxs-lookup"><span data-stu-id="f9e86-222">In this case, the product variant number will be D0123//M0008&M0022.</span></span>

## <a name="numbering-conflicts"></a><span data-ttu-id="f9e86-223">Numeración de conflictos</span><span class="sxs-lookup"><span data-stu-id="f9e86-223">Numbering conflicts</span></span>
<span data-ttu-id="f9e86-224">En algunos casos, es posible configurar una nomenclatura de número de variante de producto que no genere números únicos de variante de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-224">In some cases, a product variant number nomenclature that you set up might not produce unique product variant numbers.</span></span> <span data-ttu-id="f9e86-225">Por ejemplo, los números de variante de producto no serán únicos si una dimensión de producto activo no se incluye en la nomenclatura para un producto maestro que utilice la tecnología de configuración de variantes predefinida.</span><span class="sxs-lookup"><span data-stu-id="f9e86-225">For example, the product variant numbers won't be unique if one active product dimension isn't included in the nomenclature for a product master that uses the predefined variant configuration technology.</span></span> <span data-ttu-id="f9e86-226">La forma de solucionar conflictos variará en función de la tecnología de configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-226">The way that you handle conflicts varies, depending on the configuration technology.</span></span>

### <a name="predefined-variants"></a><span data-ttu-id="f9e86-227">Variantes predefinidas</span><span class="sxs-lookup"><span data-stu-id="f9e86-227">Predefined variants</span></span>

<span data-ttu-id="f9e86-228">Se producirá un error si intenta generar variantes de producto manualmente o automáticamente, y más de una variante de producto terminará con el mismo número.</span><span class="sxs-lookup"><span data-stu-id="f9e86-228">An error occurs if you try to manually create or automatically generate product variants, and more than one product variant ends up with the same product variant number.</span></span> <span data-ttu-id="f9e86-229">Para evitar este escenario, debe utilizar todas las dimensiones de producto activo del grupo de dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="f9e86-229">To avoid this scenario, you should use all active product dimensions in the product dimension group.</span></span> <span data-ttu-id="f9e86-230">Como alternativa, incluya una secuencia numérica para asegurarse de que los números de variante de producto sean únicos.</span><span class="sxs-lookup"><span data-stu-id="f9e86-230">Alternatively, include a number sequence to help guarantee that the product variant numbers are unique.</span></span>

### <a name="constraint-based-configurations"></a><span data-ttu-id="f9e86-231">Configuraciones basadas en restricciones</span><span class="sxs-lookup"><span data-stu-id="f9e86-231">Constraint-based configurations</span></span>

<span data-ttu-id="f9e86-232">En función de la nomenclatura, el sistema puede intentar asignar un número de variante de producto que no es único a una configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-232">Depending on the nomenclature, the system might try to assign a non-unique product variant number to a configuration.</span></span> <span data-ttu-id="f9e86-233">En este caso, el sistema utilizará la secuencia numérica para la dimensión de configuración como número de variante de producto. ESto generará una advertencia.</span><span class="sxs-lookup"><span data-stu-id="f9e86-233">In this case, the system uses the number sequence for the configuration dimension as the product variant number instead, and you receive a warning.</span></span> <span data-ttu-id="f9e86-234">Para evitar este escenario debe incluir suficientes atributos en la nomenclatura para asegurarse de que se generen números de variante de producto únicos.</span><span class="sxs-lookup"><span data-stu-id="f9e86-234">To avoid this scenario, you should include enough attributes in the nomenclature to help guarantee unique product variant numbers.</span></span> <span data-ttu-id="f9e86-235">También debe asegurarse de que la opción **Reutilizar** esté activada para el componente.</span><span class="sxs-lookup"><span data-stu-id="f9e86-235">You should also make sure that the **Reuse** option is turned on for the component.</span></span>

### <a name="dimension-based-configurations"></a><span data-ttu-id="f9e86-236">Configuraciones basadas en dimensiones</span><span class="sxs-lookup"><span data-stu-id="f9e86-236">Dimension-based configurations</span></span>

<span data-ttu-id="f9e86-237">En uno de los pasos del proceso de configuración, el sistema sugiere un valor de configuración según la nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="f9e86-237">During one step of the configuration process, the system suggests a configuration value according to the nomenclature.</span></span> <span data-ttu-id="f9e86-238">En dicho paso, puede cambiar manualmente el valor de la configuración.</span><span class="sxs-lookup"><span data-stu-id="f9e86-238">In this step, you can manually change the configuration value.</span></span> <span data-ttu-id="f9e86-239">Cuando guarde la configuración, el sistema comprobará si el valor de configuración es único.</span><span class="sxs-lookup"><span data-stu-id="f9e86-239">When you save the configuration, the system verifies that the configuration value is unique.</span></span> <span data-ttu-id="f9e86-240">Si el valor que ha especificado no es único, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="f9e86-240">If the value that you entered isn't unique, you receive an error message.</span></span> <span data-ttu-id="f9e86-241">Para poder guardar la configuración debe especificar un valor de configuración único.</span><span class="sxs-lookup"><span data-stu-id="f9e86-241">To save the configuration, you must enter a unique configuration value.</span></span>

<a name="additional-resources"></a><span data-ttu-id="f9e86-242">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f9e86-242">Additional resources</span></span>
--------

[<span data-ttu-id="f9e86-243">Crear una nomenclatura de números de producto para las variantes de producto predefinidas</span><span class="sxs-lookup"><span data-stu-id="f9e86-243">Create a product number nomenclature for predefined product variants</span></span>](tasks/create-product-number-nomenclature-predefined-variants-2016-11.md)

[<span data-ttu-id="f9e86-244">Crear una nomenclatura del número de producto para las variantes de producto configuradas</span><span class="sxs-lookup"><span data-stu-id="f9e86-244">Create a product number nomenclature for configured product variants</span></span>](tasks/create-product-number-nomenclature-product-variants_2016_11.md)

