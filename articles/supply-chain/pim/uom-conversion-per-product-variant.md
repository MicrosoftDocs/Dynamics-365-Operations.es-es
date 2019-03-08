---
title: Conversión de unidad de medida por variante del producto
description: Este tema explica cómo las conversiones de unidad de medida se pueden configurar en variantes de producto.
author: johanhoffmann
manager: AnnBe
ms.date: 12/18/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 9d5d6fd65717cd886f1c6576aabf2bc59ca4fcaf
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "345936"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="95684-103">Conversión de unidad de medida por variante del producto</span><span class="sxs-lookup"><span data-stu-id="95684-103">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

[!include [pivate-preview](../includes/pivate-preview-banner.md)]

<span data-ttu-id="95684-104">Este tema explica cómo las conversiones de unidad de medida se pueden configurar en variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="95684-104">This topic explains how unit of measure conversions can be set up on product variants.</span></span> <span data-ttu-id="95684-105">Incluye un ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="95684-105">It includes an example of the setup.</span></span>

<span data-ttu-id="95684-106">Esta función permite a las empresas definir una conversión de unidad diferente entre las variantes del mismo producto.</span><span class="sxs-lookup"><span data-stu-id="95684-106">This feature makes it possible for companies to define different unit conversion between the variants of the same product.</span></span> <span data-ttu-id="95684-107">El siguiente ejemplo se usa en este tema.</span><span class="sxs-lookup"><span data-stu-id="95684-107">The following example is used in this topic.</span></span> <span data-ttu-id="95684-108">Una empresa vende camisetas de tamaños pequeños, medios, grande y extragrande.</span><span class="sxs-lookup"><span data-stu-id="95684-108">A company sells T-shirts in sizes Small, Medium, Large, and Extra-Large.</span></span> <span data-ttu-id="95684-109">La camiseta se define como producto, y los distintos tamaños se definen como variantes del producto.</span><span class="sxs-lookup"><span data-stu-id="95684-109">The T-shirt is defined as a product, and the different sizes are defined as variants of the product.</span></span> <span data-ttu-id="95684-110">Las camisetas están embaladas en cajas y puede haber cinco camisetas en una caja, excepto el tamaño extragrande donde solo hay espacio para cuatro camisetas.</span><span class="sxs-lookup"><span data-stu-id="95684-110">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-Large size where there is only space for four T-shirts.</span></span> <span data-ttu-id="95684-111">La empresa desea realizar un seguimiento de las distintos variantes de camisetas en la unidad **Piezas** pero está vendiendo las camisetas en la unidad **Cajas**.</span><span class="sxs-lookup"><span data-stu-id="95684-111">The company wants to track the different variants of the T-shirts in the unit **Pieces** but is selling the T-shirts in the unit **Boxes**.</span></span> <span data-ttu-id="95684-112">La conversión entre la unidad de inventario y la unidad de ventas es 1 caja = 5 unidades, excepto la variante extragrande, donde la conversión es 1 caja = 4 piezas.</span><span class="sxs-lookup"><span data-stu-id="95684-112">The conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces, except for the variant Extra-Large, where the conversion is 1 Box = 4 Pieces.</span></span>

## <a name="setup"></a><span data-ttu-id="95684-113">Configurar</span><span class="sxs-lookup"><span data-stu-id="95684-113">Setup</span></span>

<span data-ttu-id="95684-114">Puede configurar los parámetros para usar la función de productos habilitados para **Todos los procesos** o solo al producto habilitado para **Procesos de almacén** mediante la opción **Habilitar las conversiones de unidad de medida** en la página **Parámetros de la información de producto**.</span><span class="sxs-lookup"><span data-stu-id="95684-114">You can configure the parameters for using the feature for products enabled for **All processes** or only for product enabled for the **Warehouse processes** by using the **Enable unit of measure conversations** option on the **Product information parameters** page.</span></span>

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="95684-115">Configurar un producto para la conversión de unidades por variante</span><span class="sxs-lookup"><span data-stu-id="95684-115">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="95684-116">Las variantes de producto solo se pueden crear para productos del **subtipo producto**: **producto maestro**.</span><span class="sxs-lookup"><span data-stu-id="95684-116">Product variants can only be created for products of **Product subtype**: **Product master**.</span></span> <span data-ttu-id="95684-117">Para obtener más información, consulte [Crear un producto maestro](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="95684-117">For more information, see [Create a product master](tasks/create-product-master.md).</span></span>

<span data-ttu-id="95684-118">La característica no está habilitada para los productos configurados para procesos de peso capturado.</span><span class="sxs-lookup"><span data-stu-id="95684-118">The feature is not enabled for products that are set up for Catch Weight processes.</span></span> 

<span data-ttu-id="95684-119">Durante la creación de un producto maestro habilite la conversión de unidades de medida mediante la opción **Habilitar las conversiones de unidad de medida** en la página **Detalles de producto**.</span><span class="sxs-lookup"><span data-stu-id="95684-119">During the creation of a product master enable unit of measure conversion by using the **Enable unit of measure conversions** option on the **Product details** page.</span></span>

<span data-ttu-id="95684-120">Cuando se crea el producto maestro con variantes de productos emitidos, las conversiones de unidades por variantes se pueden configurar.</span><span class="sxs-lookup"><span data-stu-id="95684-120">When the product master with released products variants is created, unit conversions per variants can be set up.</span></span> <span data-ttu-id="95684-121">Puede encontrar el elemento de menú para abrir la página de conversión de unidades en el contexto de un producto o una variante del producto en las siguientes páginas.</span><span class="sxs-lookup"><span data-stu-id="95684-121">You can find the menu item for opening the unit conversion page in context of a product or a product variant on the following pages.</span></span>

-   <span data-ttu-id="95684-122">Página **Detalles de producto**</span><span class="sxs-lookup"><span data-stu-id="95684-122">**Product details** page</span></span>
-   <span data-ttu-id="95684-123">Página **Administrar detalles de productos**</span><span class="sxs-lookup"><span data-stu-id="95684-123">**Released products details** page</span></span>
-   <span data-ttu-id="95684-124">Página **Variantes del producto publicadas**</span><span class="sxs-lookup"><span data-stu-id="95684-124">**Released product variants** page</span></span>

<span data-ttu-id="95684-125">Al abrir la página **Conversión de unidades** en el contexto de una variante del producto maestro o de producto liberado, puede seleccionar si desea configurar la conversión de unidades del producto o de la variante del producto.</span><span class="sxs-lookup"><span data-stu-id="95684-125">When you open the **Unit conversion** page in context of a product master or released product variant, you can select if you want to set up the unit conversion for the product or for a product variant.</span></span> <span data-ttu-id="95684-126">Esto se hace seleccionando **Variante del producto** o **Producto** en el campo **Crear para la conversión**.</span><span class="sxs-lookup"><span data-stu-id="95684-126">You do that by selecting either **Product variant** or **Product** in the **Create conversion for** field.</span></span>

### <a name="product-variant"></a><span data-ttu-id="95684-127">Variante del producto</span><span class="sxs-lookup"><span data-stu-id="95684-127">Product variant</span></span>

<span data-ttu-id="95684-128">Si se selecciona **Variante del producto,** puede seleccionar para qué variante desea configurar la conversión de unidades en el campo **Variante del producto**.</span><span class="sxs-lookup"><span data-stu-id="95684-128">If you select **Product variant,** then you can select for which variant you want to set up the unit conversion in the **Product variant** field.</span></span>

### <a name="product"></a><span data-ttu-id="95684-129">Producto</span><span class="sxs-lookup"><span data-stu-id="95684-129">Product</span></span>

<span data-ttu-id="95684-130">Si se selecciona **Producto**, puede configurar una conversión de unidades para el producto maestro.</span><span class="sxs-lookup"><span data-stu-id="95684-130">If you select **Product**, then you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="95684-131">Esta conversión de unidades se aplicará a todas las variantes de producto sin conversión de unidad definida.</span><span class="sxs-lookup"><span data-stu-id="95684-131">This unit conversion will apply for all product variants with no defined unit conversion.</span></span>

### <a name="example"></a><span data-ttu-id="95684-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95684-132">Example</span></span>

<span data-ttu-id="95684-133">Un producto maestro, **Camiseta**, tiene cuatro variantes de producto liberadas: pequeños, medios, grande y extragrande.</span><span class="sxs-lookup"><span data-stu-id="95684-133">A product master, **T-Shirt**, has four released products variants Small, Medium, Large, and X-Large.</span></span> <span data-ttu-id="95684-134">Las camisetas están embaladas en cajas y puede haber cinco camisetas en una caja, excepto el tamaño extragrande donde solo hay espacio para cuatro camisetas.</span><span class="sxs-lookup"><span data-stu-id="95684-134">The T-shirts are packed in boxes and there can be five T-shirts in a box, except for the Extra-large size where there is only space for four T-shirts.</span></span>

<span data-ttu-id="95684-135">Primero, abra la página la página **Conversión de unidades** en la página de liberación de detalles de producto para **Camiseta.**</span><span class="sxs-lookup"><span data-stu-id="95684-135">First, open the **Unit conversion** page from the Release product details page for **T-shirt.**</span></span>

<span data-ttu-id="95684-136">En la página **Conversión de unidades**, configure la conversión de unidades para la variante del producto extragrande liberada.</span><span class="sxs-lookup"><span data-stu-id="95684-136">On the **Unit conversion** page, set up the unit conversion for the release product variant X-Large.</span></span>

| <span data-ttu-id="95684-137">**Campo**</span><span class="sxs-lookup"><span data-stu-id="95684-137">**Field**</span></span>             | <span data-ttu-id="95684-138">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="95684-138">**Setting**</span></span>             |
|-----------------------|-------------------------|
| <span data-ttu-id="95684-139">Crear conversión para</span><span class="sxs-lookup"><span data-stu-id="95684-139">Create conversion for</span></span> | <span data-ttu-id="95684-140">Variante del producto</span><span class="sxs-lookup"><span data-stu-id="95684-140">Product variant</span></span>         |
| <span data-ttu-id="95684-141">Variante del producto</span><span class="sxs-lookup"><span data-stu-id="95684-141">Product variant</span></span>       | <span data-ttu-id="95684-142">Camiseta : : extragrande : :</span><span class="sxs-lookup"><span data-stu-id="95684-142">T-Shirt : : X-Large : :</span></span> |
| <span data-ttu-id="95684-143">Desde unidad</span><span class="sxs-lookup"><span data-stu-id="95684-143">From unit</span></span>             | <span data-ttu-id="95684-144">Cajas</span><span class="sxs-lookup"><span data-stu-id="95684-144">Boxes</span></span>                   |
| <span data-ttu-id="95684-145">Factor</span><span class="sxs-lookup"><span data-stu-id="95684-145">Factor</span></span>                | <span data-ttu-id="95684-146">4</span><span class="sxs-lookup"><span data-stu-id="95684-146">4</span></span>                       |
| <span data-ttu-id="95684-147">Hasta unidad</span><span class="sxs-lookup"><span data-stu-id="95684-147">To Unit</span></span>               | <span data-ttu-id="95684-148">Piezas</span><span class="sxs-lookup"><span data-stu-id="95684-148">Pieces</span></span>                  |

<span data-ttu-id="95684-149">Las variantes del producto liberado: pequeños, medios y grandes tienen la misma conversión de unidades entre la caja de unidades y las piezas, lo que significa que puede definir la conversión de unidades de estas variantes de producto en el producto maestro.</span><span class="sxs-lookup"><span data-stu-id="95684-149">The Released product variants Small, Medium, and Large have the same unit conversion between the unit Box and Pieces, which means that you can define the unit conversion for these product variants on the product master.</span></span>

| <span data-ttu-id="95684-150">**Campo**</span><span class="sxs-lookup"><span data-stu-id="95684-150">**Field**</span></span>             | <span data-ttu-id="95684-151">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="95684-151">**Setting**</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="95684-152">Crear conversión para</span><span class="sxs-lookup"><span data-stu-id="95684-152">Create conversion for</span></span> | <span data-ttu-id="95684-153">Producto</span><span class="sxs-lookup"><span data-stu-id="95684-153">Product</span></span>     |
| <span data-ttu-id="95684-154">Producto</span><span class="sxs-lookup"><span data-stu-id="95684-154">Product</span></span>               | <span data-ttu-id="95684-155">Camiseta</span><span class="sxs-lookup"><span data-stu-id="95684-155">T-Shirt</span></span>     |
| <span data-ttu-id="95684-156">Desde unidad</span><span class="sxs-lookup"><span data-stu-id="95684-156">From unit</span></span>             | <span data-ttu-id="95684-157">Cajas</span><span class="sxs-lookup"><span data-stu-id="95684-157">Boxes</span></span>       |
| <span data-ttu-id="95684-158">Factor</span><span class="sxs-lookup"><span data-stu-id="95684-158">Factor</span></span>                | <span data-ttu-id="95684-159">5</span><span class="sxs-lookup"><span data-stu-id="95684-159">5</span></span>           |
| <span data-ttu-id="95684-160">Hasta unidad</span><span class="sxs-lookup"><span data-stu-id="95684-160">To Unit</span></span>               | <span data-ttu-id="95684-161">Piezas</span><span class="sxs-lookup"><span data-stu-id="95684-161">Pieces</span></span>      |

### <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="95684-162">Uso de Excel para actualizar las conversiones de unidades</span><span class="sxs-lookup"><span data-stu-id="95684-162">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="95684-163">Si un producto tiene numerosas variantes de producto con conversiones de unidad diferente, es recomendable exportar las conversiones de unidades de la página **Conversión de unidades** a una hoja de cálculo de Excel, actualizar las conversiones y, a continuación publicarlas de nuevo en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="95684-163">If a product has many product variants with different unit conversions, it's a good idea to export the unit conversions from the **Unit conversion** page to an Excel spreadsheet, update the conversions, and then publish them back to Finance and Operations.</span></span>

<span data-ttu-id="95684-164">La opción para exportar a Excel y publicar las ediciones de nuevo en Finance and Operations se habilita en el elemento de menú **Abrir en Microsoft Office** en el panel de acciones de la página **Conversión de unidades**.</span><span class="sxs-lookup"><span data-stu-id="95684-164">The option to export to Excel and publish the edits back to Finance and Operations is enabled from the **Open in Microsoft office** menu item on the Action Pane on the **Unit conversion** page.</span></span>
