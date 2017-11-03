---
title: Dimensiones de producto
description: "Hay cuatro dimensiones de producto: Color, Configuración, Tamaño y Estilo. Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros. Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 68f4bfcf62b5e7c65cbe361b510c2769b0e9bebb
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="product-dimensions"></a><span data-ttu-id="9cfb2-105">Dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="9cfb2-105">Product dimensions</span></span>

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]


<span data-ttu-id="9cfb2-106">Hay cuatro dimensiones de producto: Color, Configuración, Tamaño y Estilo.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-106">There are four product dimensions -  Color, Configuration, Size and Style.</span></span> <span data-ttu-id="9cfb2-107">Combina dimensiones de producto en grupos de dimensiones y asigna grupos de dimensiones a productos maestros.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-107">You combine product dimensions in dimension groups and assign dimension groups to product masters.</span></span> <span data-ttu-id="9cfb2-108">Las combinaciones de dimensiones de producto determinan la manera en que se definen las variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-108">The combinations of product dimensions determine how product variants are defined.</span></span>

<span data-ttu-id="9cfb2-109">Las dimensiones de un producto son las características que permiten identificar una variante del producto.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-109">Product dimensions are characteristics that serve to identify a product variant.</span></span> <span data-ttu-id="9cfb2-110">Puede utilizar combinaciones de dimensiones de producto para definir variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-110">You can use combinations of product dimensions to define product variants.</span></span> <span data-ttu-id="9cfb2-111">Se debe definir al menos una dimensión del producto para un producto maestro si desea crear una variante del producto.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-111">You must define at least one product dimension for a product master in order to create a product variant.</span></span>
<span data-ttu-id="9cfb2-112">Variantes de producto</span><span class="sxs-lookup"><span data-stu-id="9cfb2-112">Product variants</span></span>
----------------

<span data-ttu-id="9cfb2-113">Las variantes del producto también se conocen como artículos.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-113">Product variants are also referred to as items.</span></span> <span data-ttu-id="9cfb2-114">Un artículo es un producto tangible, que no es igual que el servicio.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-114">An item is a tangible product, which is not the same as a service.</span></span> <span data-ttu-id="9cfb2-115">También es posible definir un producto maestro con el tipo Servicio.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-115">It is also possible to define a product master with the Service type.</span></span> <span data-ttu-id="9cfb2-116">Mediante el tipo Servicio, puede especificar las variantes del producto que incluyen servicios.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-116">By using the Service type, you can specify product variants that include services.</span></span> <span data-ttu-id="9cfb2-117">Por ejemplo, puede especificar un producto maestro para el asesoramiento del trabajo y variantes del producto para el trabajo realizado por los asesores sénior y júnior.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-117">For example, you can specify a product master for Consultancy work and product variants for work that is performed by senior consultants and junior consultants.</span></span>

## <a name="product-dimensions"></a><span data-ttu-id="9cfb2-118">Dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="9cfb2-118">Product dimensions</span></span>
<span data-ttu-id="9cfb2-119">Están disponibles las siguientes dimensiones de producto: Configuración, Color, Tamaño y Estilo.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-119">The following product dimensions are available: Configuration, Color, Size, and Style.</span></span> <span data-ttu-id="9cfb2-120">Se puede generar una variante del producto a partir de los valores de dimensión del producto.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-120">A product variant can be generated based on the product dimension values.</span></span>

<span data-ttu-id="9cfb2-121">Los valores de las dimensiones del producto como tamaño, color y estilo se pueden crear en las páginas **Tamaño**, **Color** y **Estilo**, a las que se puede obtener acceso desde las ubicaciones siguientes: **Gestión de información de productos** &gt; **Configurar** &gt; **Grupos de variantes y dimensiones** &gt; **Tamaños/Colores/Estilos**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-121">Product dimensions values such as Size, Color and Style can be created on the **Size**, **Color** and **Style** pages, which can be accessed from the following locations: **Product information management** &gt; **Setup** &gt; **Dimension and variant Groups** &gt; **Sizes/Colors/Styles**.</span></span> <span data-ttu-id="9cfb2-122">Los valores de dimensión del producto para la dimensión de configuración se crean normalmente mediante el configurador de productos o el configurador basado en dimensiones.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-122">Product dimension values for the Configuration dimension are typically created using either the Product configurator or the Dimension-based configurator.</span></span> <span data-ttu-id="9cfb2-123">Las dimensiones del producto también se pueden crear y mantener en la página **Dimensiones de producto**, a la que se puede tener acceso desde las ubicaciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9cfb2-123">Product dimensions can also be created and maintained on the **Product dimensions** page, which can be accessed from the following locations:</span></span>
-   <span data-ttu-id="9cfb2-124">Haga clic en **Gestión de información de productos** &gt; **Productos** &gt; **Productos maestros**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-124">Click **Product information management** &gt; **Products** &gt; **Product masters**.</span></span> <span data-ttu-id="9cfb2-125">En el **Panel de acciones**, haga clic en **Dimensiones de producto**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-125">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="9cfb2-126">Haga clic en **Gestión de información de productos** &gt; **Productos** &gt; **Todos los productos y productos maestros**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-126">Click **Product information management** &gt; **Products** &gt; **All products and product masters**.</span></span> <span data-ttu-id="9cfb2-127">Seleccione un producto maestro.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-127">Select a product master.</span></span> <span data-ttu-id="9cfb2-128">En el **Panel de acciones**, haga clic en **Dimensiones de producto**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-128">On the **Action Pane**, click **Product dimensions**.</span></span>
-   <span data-ttu-id="9cfb2-129">Haga clic en **Gestión de información de productos** &gt; **Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-129">Click **Product information management** &gt; **Released products**.</span></span> <span data-ttu-id="9cfb2-130">Seleccione un producto maestro.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-130">Select a product master.</span></span> <span data-ttu-id="9cfb2-131">En el **Panel de acciones**, haga clic en **Producto**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-131">On the **Action Pane**, click **Product**.</span></span> <span data-ttu-id="9cfb2-132">En el grupo **Producto maestro**, haga clic en **Dimensiones de producto**.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-132">In the **Product master** group, click **Product dimensions**.</span></span>

<span data-ttu-id="9cfb2-133">El número de variantes que se pueden crear para un artículo está limitado por el número de posibles combinaciones de las dimensiones del producto.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-133">The number of variants that you can create for an item is limited by the number of possible product dimension combinations.</span></span>
| <span data-ttu-id="9cfb2-134">**Sugerencia**</span><span class="sxs-lookup"><span data-stu-id="9cfb2-134">**Tip**</span></span>                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="9cfb2-135">Al utilizar un producto en, por ejemplo, una línea de pedido, seleccione las dimensiones del producto para identificar la variante del producto con la que desee trabajar.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-135">When you use a product on, for example, an order line, you select the product dimensions to identify the product variant that you want to work with.</span></span> |

## <a name="example"></a><span data-ttu-id="9cfb2-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9cfb2-136">Example</span></span>
<span data-ttu-id="9cfb2-137">Una empresa vende pantalones vaqueros.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-137">A company sells denim jeans.</span></span> <span data-ttu-id="9cfb2-138">El artículo, vaqueros, utiliza las dimensiones de producto Color y Tamaño.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-138">The item, Jeans, uses the Color and Size product dimensions.</span></span> <span data-ttu-id="9cfb2-139">Éstos se venden en tres colores distintos y seis tamaños distintos.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-139">The jeans are sold in three different colors and six different sizes.</span></span> <span data-ttu-id="9cfb2-140">Colores: azul, negro, marrón Tamaños: XS, S, M, L, XL, XXL No todos los tamaños están disponibles en los tres colores.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-140">Colors: Blue, Black, Brown Sizes: XS, S, M, L, XL, XXL Not all sizes are available in all the three colors.</span></span> <span data-ttu-id="9cfb2-141">Si todas las combinaciones estuviesen disponibles, el resultado sería de 18 tipos de vaqueros distintos.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-141">If all combinations were available, it would create 18 different types of jeans.</span></span> <span data-ttu-id="9cfb2-142">En este ejemplo solo se producen las nueve combinaciones siguientes de variantes del producto.</span><span class="sxs-lookup"><span data-stu-id="9cfb2-142">In this example, only the following nine product variant combinations are produced.</span></span>

| <span data-ttu-id="9cfb2-143">Color</span><span class="sxs-lookup"><span data-stu-id="9cfb2-143">Color</span></span> | <span data-ttu-id="9cfb2-144">Tamaño</span><span class="sxs-lookup"><span data-stu-id="9cfb2-144">Size</span></span> |
|-------|------|
| <span data-ttu-id="9cfb2-145">Azul</span><span class="sxs-lookup"><span data-stu-id="9cfb2-145">Blue</span></span>  | <span data-ttu-id="9cfb2-146">XS</span><span class="sxs-lookup"><span data-stu-id="9cfb2-146">XS</span></span>   |
| <span data-ttu-id="9cfb2-147">Azul</span><span class="sxs-lookup"><span data-stu-id="9cfb2-147">Blue</span></span>  | <span data-ttu-id="9cfb2-148">S</span><span class="sxs-lookup"><span data-stu-id="9cfb2-148">S</span></span>    |
| <span data-ttu-id="9cfb2-149">Azul</span><span class="sxs-lookup"><span data-stu-id="9cfb2-149">Blue</span></span>  | <span data-ttu-id="9cfb2-150">M</span><span class="sxs-lookup"><span data-stu-id="9cfb2-150">M</span></span>    |
| <span data-ttu-id="9cfb2-151">Negro</span><span class="sxs-lookup"><span data-stu-id="9cfb2-151">Black</span></span> | <span data-ttu-id="9cfb2-152">M</span><span class="sxs-lookup"><span data-stu-id="9cfb2-152">M</span></span>    |
| <span data-ttu-id="9cfb2-153">Negro</span><span class="sxs-lookup"><span data-stu-id="9cfb2-153">Black</span></span> | <span data-ttu-id="9cfb2-154">L</span><span class="sxs-lookup"><span data-stu-id="9cfb2-154">L</span></span>    |
| <span data-ttu-id="9cfb2-155">Negro</span><span class="sxs-lookup"><span data-stu-id="9cfb2-155">Black</span></span> | <span data-ttu-id="9cfb2-156">XL</span><span class="sxs-lookup"><span data-stu-id="9cfb2-156">XL</span></span>   |
| <span data-ttu-id="9cfb2-157">Marrón</span><span class="sxs-lookup"><span data-stu-id="9cfb2-157">Brown</span></span> | <span data-ttu-id="9cfb2-158">L</span><span class="sxs-lookup"><span data-stu-id="9cfb2-158">L</span></span>    |
| <span data-ttu-id="9cfb2-159">Marrón</span><span class="sxs-lookup"><span data-stu-id="9cfb2-159">Brown</span></span> | <span data-ttu-id="9cfb2-160">XL</span><span class="sxs-lookup"><span data-stu-id="9cfb2-160">XL</span></span>   |
| <span data-ttu-id="9cfb2-161">Marrón</span><span class="sxs-lookup"><span data-stu-id="9cfb2-161">Brown</span></span> | <span data-ttu-id="9cfb2-162">XXL</span><span class="sxs-lookup"><span data-stu-id="9cfb2-162">XXL</span></span>  |






