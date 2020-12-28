---
title: Conversión de unidad de medida por variante del producto
description: Este tema explica cómo configurar las conversiones de unidades de medida para variantes de producto. Incluye un ejemplo de configuración.
author: johanhoffmann
manager: tfehr
ms.date: 05/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: 71d35d47a703f0931ba3b4ab5df21c7199c7ea5b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437141"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a><span data-ttu-id="9b246-104">Conversión de unidad de medida por variante del producto</span><span class="sxs-lookup"><span data-stu-id="9b246-104">Unit of measure conversion per product variant</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b246-105">Este tema explica cómo configurar las conversiones de unidades de medida para diversas variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="9b246-105">This topic explains how to set up unit of measure conversions for various product variants.</span></span>

<span data-ttu-id="9b246-106">En lugar de crear varios productos individuales que deberán mantenerse, puede usar variantes del producto para crear variaciones de un único producto.</span><span class="sxs-lookup"><span data-stu-id="9b246-106">Instead of creating multiple individual products that must be maintained, you can use product variants to create variations of a single product.</span></span> <span data-ttu-id="9b246-107">Por ejemplo, una variante del producto podría ser una camiseta de un tamaño y color determinados.</span><span class="sxs-lookup"><span data-stu-id="9b246-107">For example, a product variant might be a T-shirt of a given size and color.</span></span>

<span data-ttu-id="9b246-108">Anteriormente, las conversiones de unidades solo se podían configurar en el producto maestro.</span><span class="sxs-lookup"><span data-stu-id="9b246-108">Previously, unit conversions could be set up only on the product master.</span></span> <span data-ttu-id="9b246-109">Por lo tanto, todas las variantes de producto tenían las mismas reglas de conversión de unidades.</span><span class="sxs-lookup"><span data-stu-id="9b246-109">Therefore, all product variants had the same unit conversion rules.</span></span> <span data-ttu-id="9b246-110">Sin embargo, cuando la función *Conversiones de unidades de medida para variantes de producto* está activada, si sus camisetas se venden en cajas y la cantidad de camisetas que se pueden empaquetar en una caja depende del tamaño de las camisetas, ahora puede configurar conversiones de unidades entre las diferentes tamaños de camisetas y las cajas que se utilizan para el empaquetado.</span><span class="sxs-lookup"><span data-stu-id="9b246-110">However, when the *Unit of measure conversions for product variants* feature is turned on, if your T-shirts are sold in boxes, and the number of T-shirts that can be packed in a box depends on the size of the T-shirts, you can now set up unit conversions between the different shirt sizes and the boxes that are used for packaging.</span></span>

## <a name="turn-on-the-feature-in-your-system"></a><span data-ttu-id="9b246-111">Activar la función en el sistema</span><span class="sxs-lookup"><span data-stu-id="9b246-111">Turn on the feature in your system</span></span>

<span data-ttu-id="9b246-112">Si ya no ve esta función en su sistema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la función *Conversiones de unidades de medida para variantes de producto*.</span><span class="sxs-lookup"><span data-stu-id="9b246-112">If you don't already see this feature in your system, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the *Unit of measure conversions for product variants* feature.</span></span>

## <a name="set-up-a-product-for-unit-conversion-per-variant"></a><span data-ttu-id="9b246-113">Configurar un producto para la conversión de unidades por variante</span><span class="sxs-lookup"><span data-stu-id="9b246-113">Set up a product for unit conversion per variant</span></span>

<span data-ttu-id="9b246-114">Las variantes de producto solo se pueden crear solo para productos que sean productos maestro.</span><span class="sxs-lookup"><span data-stu-id="9b246-114">Product variants can be created only for products that are product masters.</span></span> <span data-ttu-id="9b246-115">Para obtener más información, consulte [Crear un producto maestro](tasks/create-product-master.md).</span><span class="sxs-lookup"><span data-stu-id="9b246-115">For more information, see [Create a product master](tasks/create-product-master.md).</span></span> <span data-ttu-id="9b246-116">La función *Conversiones de unidades de medida para variantes de producto* no está disponible para productos que están configurados para procesos de captura de peso.</span><span class="sxs-lookup"><span data-stu-id="9b246-116">The *Unit of measure conversions for product variants* feature isn't available for products that are set up for catch-weight processes.</span></span>

<span data-ttu-id="9b246-117">Para configurar un producto maestro para admitir la conversión de unidades por variante, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9b246-117">To configure a product master to support unit conversion per variant, follow these steps.</span></span>

1. <span data-ttu-id="9b246-118">Vaya a **Gestión de información de productos \> Productos \> Productos maestros**.</span><span class="sxs-lookup"><span data-stu-id="9b246-118">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="9b246-119">Cree o abra un producto maestro para ir a su página **Detalles de producto**.</span><span class="sxs-lookup"><span data-stu-id="9b246-119">Create or open a product master to go to its **Product details** page.</span></span>
1. <span data-ttu-id="9b246-120">Seleccione la opción **Habilitar conversiones de unidades de medida** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="9b246-120">Set the **Enable unit of measure conversions** option to *Yes*.</span></span>
1. <span data-ttu-id="9b246-121">En el panel Acciones, en la pestaña **Producto** del grupo **Configurar**, haga clic en **Conversiones de unidades**.</span><span class="sxs-lookup"><span data-stu-id="9b246-121">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Unit conversions**.</span></span>
1. <span data-ttu-id="9b246-122">Se abrirá la página **Conversiones de unidades**.</span><span class="sxs-lookup"><span data-stu-id="9b246-122">The **Unit conversions** page opens.</span></span> <span data-ttu-id="9b246-123">Seleccione una de las pestañas siguientes:</span><span class="sxs-lookup"><span data-stu-id="9b246-123">Select one of the following tabs:</span></span>

    - <span data-ttu-id="9b246-124">**Conversiones intraclase**: seleccione esta pestaña para convertir entre unidades que pertenecen a la misma clase de unidades.</span><span class="sxs-lookup"><span data-stu-id="9b246-124">**Intra-class conversions** – Select this tab to convert between units that belong to the same unit class.</span></span>
    - <span data-ttu-id="9b246-125">**Conversiones interclase**: seleccione esta pestaña para convertir entre unidades que pertenecen a diferentes clases de unidades.</span><span class="sxs-lookup"><span data-stu-id="9b246-125">**Inter-class conversions** – Select this tab to convert between units that belong to different unit classes.</span></span>

1. <span data-ttu-id="9b246-126">Para agregar una unidad de conversión nueva, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9b246-126">Select **New** to add a new unit conversion.</span></span>
1. <span data-ttu-id="9b246-127">Seleccione el campo **Crear conversión para** en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="9b246-127">Set the **Create conversion for** field to one of the following values:</span></span>

    - <span data-ttu-id="9b246-128">**Producto**: si selecciona este valor, puede configurar una conversión de unidades para el producto maestro.</span><span class="sxs-lookup"><span data-stu-id="9b246-128">**Product** – If you select this value, you can set up a unit conversion for the product master.</span></span> <span data-ttu-id="9b246-129">Esa conversión de unidades se utilizará como alternativa para todas las variantes de producto para las que no esté definida ninguna conversión de unidades.</span><span class="sxs-lookup"><span data-stu-id="9b246-129">That unit conversion will be used as a fallback for all product variants that no unit conversion is defined for.</span></span>
    - <span data-ttu-id="9b246-130">**Variante del producto**: si selecciona este valor, puede configurar una conversión de unidades para una variante del producto específica.</span><span class="sxs-lookup"><span data-stu-id="9b246-130">**Product variant** – If you select this value, you can set up a unit conversion for a specific product variant.</span></span> <span data-ttu-id="9b246-131">Utilicer el campo **Variante del producto** para seleccionar la variante.</span><span class="sxs-lookup"><span data-stu-id="9b246-131">Use the **Product variant** field to select the variant.</span></span>

    ![![Agregar una nueva conversión de unidades](media/uom-new-conversion.png "Agregar una nueva conversión de unidades")](media/uom-new-conversion.png "Adding a new unit conversion")

1. <span data-ttu-id="9b246-133">Use los otros campos que se proporcionan para configurar su conversión de unidades.</span><span class="sxs-lookup"><span data-stu-id="9b246-133">Use the other fields that are provided to set up your unit conversion.</span></span>
1. <span data-ttu-id="9b246-134">Seleccione **Aceptar** para guardar la nueva conversión de unidades.</span><span class="sxs-lookup"><span data-stu-id="9b246-134">Select **OK** to save the new unit conversion.</span></span>

> [!TIP]
> <span data-ttu-id="9b246-135">Puede abrir la página **Conversiones de unidades** para un producto o una variante de producto desde cualquiera de las siguientes páginas:</span><span class="sxs-lookup"><span data-stu-id="9b246-135">You can open the **Unit conversions** page for a product or a product variant from any of the following pages:</span></span>
> 
> - <span data-ttu-id="9b246-136">Detalles de producto</span><span class="sxs-lookup"><span data-stu-id="9b246-136">Product details</span></span>
> - <span data-ttu-id="9b246-137">Detalles de productos despachados</span><span class="sxs-lookup"><span data-stu-id="9b246-137">Released products details</span></span>
> - <span data-ttu-id="9b246-138">Variantes de Productos despachados</span><span class="sxs-lookup"><span data-stu-id="9b246-138">Released product variants</span></span>

## <a name="example-scenario"></a><span data-ttu-id="9b246-139">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b246-139">Example scenario</span></span>

<span data-ttu-id="9b246-140">En este escenario, una empresa vende camisetas de tamaños pequeño, mediano, grande y extragrande.</span><span class="sxs-lookup"><span data-stu-id="9b246-140">In this scenario, a company sells T-shirts in sizes small, medium, large, and extra-large.</span></span> <span data-ttu-id="9b246-141">La camiseta se define como un producto, y los distintos tamaños se definen como variantes de ese producto.</span><span class="sxs-lookup"><span data-stu-id="9b246-141">The T-shirt is defined as a product, and the different sizes are defined as variants of that product.</span></span> <span data-ttu-id="9b246-142">Las camisas se empaquetan en cajas.</span><span class="sxs-lookup"><span data-stu-id="9b246-142">The shirts are packed in boxes.</span></span> <span data-ttu-id="9b246-143">Para los tamaños pequeño, mediano y grande, puede haber cinco camisetas en cada caja.</span><span class="sxs-lookup"><span data-stu-id="9b246-143">For sizes small, medium, and large, there can be five shirts in each box.</span></span> <span data-ttu-id="9b246-144">Sin embargo, para el tamaño extragrande, hay espacio para solo cuatro camisetas en cada caja.</span><span class="sxs-lookup"><span data-stu-id="9b246-144">However, for size extra-large, there is space for only four shirts in each box.</span></span>

<span data-ttu-id="9b246-145">La empresa desea realizar un seguimiento de las distintas variantes en la unidad *Piezas*, pero las está vendiendo en la unidad *Cajas*.</span><span class="sxs-lookup"><span data-stu-id="9b246-145">The company wants to track the different variants in the *Pieces* unit, but it's selling them in the *Boxes* unit.</span></span> <span data-ttu-id="9b246-146">Para los tamaños pequeño, mediano y grande, la conversión entre la unidad de inventario y la unidad de ventas es de 1 caja = 5 piezas.</span><span class="sxs-lookup"><span data-stu-id="9b246-146">For sizes small, medium, and large, the conversion between the inventory unit and the sales unit is 1 Box = 5 Pieces.</span></span> <span data-ttu-id="9b246-147">Para tamaño extragrande, la conversión es 1 caja = 4 piezas.</span><span class="sxs-lookup"><span data-stu-id="9b246-147">For size extra-large, the conversion is 1 Box = 4 Pieces.</span></span>

1. <span data-ttu-id="9b246-148">Desde la página **Detalles de producto despachado** del producto **Camiseta**, abra la página la página **Conversión de unidades**.</span><span class="sxs-lookup"><span data-stu-id="9b246-148">From the **Released product details** page for the **T-Shirt** product, open the **Unit conversions** page.</span></span>
1. <span data-ttu-id="9b246-149">En la página **Conversión de unidades**, configure la siguiente conversión de unidades para la variante del producto despachada **Extragrande**.</span><span class="sxs-lookup"><span data-stu-id="9b246-149">On the **Unit conversions** page, set up the following unit conversion for the **X-Large** released product variant.</span></span>

    | <span data-ttu-id="9b246-150">Campo</span><span class="sxs-lookup"><span data-stu-id="9b246-150">Field</span></span>                 | <span data-ttu-id="9b246-151">Configuración</span><span class="sxs-lookup"><span data-stu-id="9b246-151">Setting</span></span>                 |
    |-----------------------|-------------------------|
    | <span data-ttu-id="9b246-152">Crear conversión para</span><span class="sxs-lookup"><span data-stu-id="9b246-152">Create conversion for</span></span> | <span data-ttu-id="9b246-153">Variante del producto</span><span class="sxs-lookup"><span data-stu-id="9b246-153">Product variant</span></span>         |
    | <span data-ttu-id="9b246-154">Variante del producto</span><span class="sxs-lookup"><span data-stu-id="9b246-154">Product variant</span></span>       | <span data-ttu-id="9b246-155">Camiseta : : extragrande : :</span><span class="sxs-lookup"><span data-stu-id="9b246-155">T-Shirt : : X-Large : :</span></span> |
    | <span data-ttu-id="9b246-156">Desde unidad</span><span class="sxs-lookup"><span data-stu-id="9b246-156">From unit</span></span>             | <span data-ttu-id="9b246-157">Cajas</span><span class="sxs-lookup"><span data-stu-id="9b246-157">Boxes</span></span>                   |
    | <span data-ttu-id="9b246-158">Factor</span><span class="sxs-lookup"><span data-stu-id="9b246-158">Factor</span></span>                | <span data-ttu-id="9b246-159">4</span><span class="sxs-lookup"><span data-stu-id="9b246-159">4</span></span>                       |
    | <span data-ttu-id="9b246-160">Hasta unidad</span><span class="sxs-lookup"><span data-stu-id="9b246-160">To Unit</span></span>               | <span data-ttu-id="9b246-161">Piezas</span><span class="sxs-lookup"><span data-stu-id="9b246-161">Pieces</span></span>                  |

1. <span data-ttu-id="9b246-162">Dado que las variantes del producto **Pequeña**, **Mediana** y **Grande** tienen todas la misma conversión de unidades entre las unidades *Caja* y *Piezas*, puede definir la siguiente conversión de unidades para ellas en el producto maestro.</span><span class="sxs-lookup"><span data-stu-id="9b246-162">Because the **Small**, **Medium**, and **Large** product variants all have the same unit conversion between the *Box* and *Pieces* units, you can define the following unit conversion for them on the product master.</span></span>

    | <span data-ttu-id="9b246-163">Campo</span><span class="sxs-lookup"><span data-stu-id="9b246-163">Field</span></span>                 | <span data-ttu-id="9b246-164">Configuración</span><span class="sxs-lookup"><span data-stu-id="9b246-164">Setting</span></span> |
    |-----------------------|---------|
    | <span data-ttu-id="9b246-165">Crear conversión para</span><span class="sxs-lookup"><span data-stu-id="9b246-165">Create conversion for</span></span> | <span data-ttu-id="9b246-166">Producto</span><span class="sxs-lookup"><span data-stu-id="9b246-166">Product</span></span> |
    | <span data-ttu-id="9b246-167">Producto</span><span class="sxs-lookup"><span data-stu-id="9b246-167">Product</span></span>               | <span data-ttu-id="9b246-168">Camiseta</span><span class="sxs-lookup"><span data-stu-id="9b246-168">T-Shirt</span></span> |
    | <span data-ttu-id="9b246-169">Desde unidad</span><span class="sxs-lookup"><span data-stu-id="9b246-169">From unit</span></span>             | <span data-ttu-id="9b246-170">Cajas</span><span class="sxs-lookup"><span data-stu-id="9b246-170">Boxes</span></span>   |
    | <span data-ttu-id="9b246-171">Factor</span><span class="sxs-lookup"><span data-stu-id="9b246-171">Factor</span></span>                | <span data-ttu-id="9b246-172">5</span><span class="sxs-lookup"><span data-stu-id="9b246-172">5</span></span>       |
    | <span data-ttu-id="9b246-173">Hasta unidad</span><span class="sxs-lookup"><span data-stu-id="9b246-173">To Unit</span></span>               | <span data-ttu-id="9b246-174">Piezas</span><span class="sxs-lookup"><span data-stu-id="9b246-174">Pieces</span></span>  |

## <a name="using-excel-to-update-the-unit-conversions"></a><span data-ttu-id="9b246-175">Uso de Excel para actualizar las conversiones de unidades</span><span class="sxs-lookup"><span data-stu-id="9b246-175">Using Excel to update the unit conversions</span></span>

<span data-ttu-id="9b246-176">Si un producto tiene muchas variantes de producto que tienen conversiones de unidades diferentes, es una buena idea exportar las conversiones de unidades al libro de trabajo Microsoft Excel, actualizarlas y luego volver a a publicarlas en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="9b246-176">If a product has many product variants that have different unit conversions, it's a good idea to export the unit conversions to a Microsoft Excel workbook, update them, and then publish them back to Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="9b246-177">Para exportar conversiones de unidades a Excel, en la página **Conversiones de unidades**, en el panel Acciones, seleccione **Abrir en Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="9b246-177">To export unit conversions to Excel, on the **Unit conversions** page, on the Action Pane, select **Open in Microsoft Office**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b246-178">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9b246-178">Additional resources</span></span>

[<span data-ttu-id="9b246-179">Gestionar la unidad de medida</span><span class="sxs-lookup"><span data-stu-id="9b246-179">Manage unit of measure</span></span>](tasks/manage-unit-measure.md)
