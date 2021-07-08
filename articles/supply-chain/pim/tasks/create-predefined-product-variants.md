---
title: Crear variantes de productos predefinidas
description: Este procedimiento le guía por la creación de variantes de productos para un producto maestro mediante las combinaciones de dimensiones de productos.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 442a5f5b321833c170cfecc4069e62a1254605cd
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270489"
---
# <a name="predefined-product-variants"></a><span data-ttu-id="4cad7-103">Variantes de productos predefinidas</span><span class="sxs-lookup"><span data-stu-id="4cad7-103">Predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a><span data-ttu-id="4cad7-104">Escenario de ejemplo: crear variantes de productos predefinidas</span><span class="sxs-lookup"><span data-stu-id="4cad7-104">Example scenario: Create predefined product variants</span></span>

<span data-ttu-id="4cad7-105">Este escenario de ejemplo le muestra cómo crear variantes de productos para un producto maestro mediante las combinaciones de dimensiones de productos.</span><span class="sxs-lookup"><span data-stu-id="4cad7-105">This example scenario shows how to create product variants for a product master using a combinations of product dimensions.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="4cad7-106">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="4cad7-106">Make demo data available</span></span>

<span data-ttu-id="4cad7-107">Para seguir este escenario con los valores sugeridos aquí, los datos de demostración deben estar instalados y debe seleccionar la entidad jurídica *USMF*.</span><span class="sxs-lookup"><span data-stu-id="4cad7-107">To follow this scenario using the values suggested here, you must have demo data installed, and you must select the *USMF* legal entity.</span></span>

### <a name="step-1-create-a-product-master"></a><span data-ttu-id="4cad7-108">Paso 1: crear un producto maestro</span><span class="sxs-lookup"><span data-stu-id="4cad7-108">Step 1: Create a product master</span></span>

<span data-ttu-id="4cad7-109">Para crear un producto maestro:</span><span class="sxs-lookup"><span data-stu-id="4cad7-109">To create a product master:</span></span>

1. <span data-ttu-id="4cad7-110">Vaya a **Gestión de información de productos > Productos > Productos maestros**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-110">Go to **Product information management > Products > Product masters**.</span></span>
1. <span data-ttu-id="4cad7-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-111">Select **New**.</span></span>
1. <span data-ttu-id="4cad7-112">Si el campo **Número de producto** aún no muestra un número, en ese caso introduzca un valor.</span><span class="sxs-lookup"><span data-stu-id="4cad7-112">If the **Product number** field doesn't already show a number, then enter a value.</span></span> <span data-ttu-id="4cad7-113">Este paso solo es necesario si no se ha configurado ninguna secuencia numérica para este campo.</span><span class="sxs-lookup"><span data-stu-id="4cad7-113">This is only required if no number sequence has been set for this field.</span></span>
1. <span data-ttu-id="4cad7-114">Introduzca un nombre en el campo **Nombre de producto**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-114">Enter a name in the **Product name** field.</span></span>
1. <span data-ttu-id="4cad7-115">En el campo **Grupo de dimensiones de producto**, seleccione el grupo de dimensiones del producto *SizeCol* (Tamaño y color).</span><span class="sxs-lookup"><span data-stu-id="4cad7-115">In the **Product dimension group** field, select the product dimension group *SizeCol* (Size and Color).</span></span>
1. <span data-ttu-id="4cad7-116">Seleccione **Aceptar** para crear y abrir el nuevo producto maestro.</span><span class="sxs-lookup"><span data-stu-id="4cad7-116">Select **OK** to create and open the new product master.</span></span>

### <a name="step-2-add-product-dimensions"></a><span data-ttu-id="4cad7-117">Paso 2: agregar dimensiones de productos</span><span class="sxs-lookup"><span data-stu-id="4cad7-117">Step 2: Add product dimensions</span></span>

<span data-ttu-id="4cad7-118">Este ejemplo muestra cómo especificar manualmente dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="4cad7-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="4cad7-119">También puede elegir seleccionar un grupo de tamaños, colores o estilos que incluya los valores de dimensiones de productos que desea usar.</span><span class="sxs-lookup"><span data-stu-id="4cad7-119">You can also choose to select a size, color, or style group that includes the product dimension values you want to use.</span></span>

<span data-ttu-id="4cad7-120">Para agregar dimensiones de productos:</span><span class="sxs-lookup"><span data-stu-id="4cad7-120">To add product dimensions:</span></span>

1. <span data-ttu-id="4cad7-121">Con su nuevo producto maestro aún abierto, seleccione **Dimensiones del producto** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="4cad7-121">With your new product master still open, select **Product dimensions** on the Action Pane.</span></span>
1. <span data-ttu-id="4cad7-122">Abra la pestaña **Tamaño** y seleccione **Nuevo** en la barra de herramientas para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4cad7-122">Open the **Size** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="4cad7-123">Realice las siguientes configuraciones para la nueva fila:</span><span class="sxs-lookup"><span data-stu-id="4cad7-123">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="4cad7-124">**Tamaño:** seleccione un valor de tamaño.</span><span class="sxs-lookup"><span data-stu-id="4cad7-124">**Size:** Select a size value.</span></span>
    - <span data-ttu-id="4cad7-125">**Nombre:** escriba un nombre para el tamaño.</span><span class="sxs-lookup"><span data-stu-id="4cad7-125">**Name:** Enter a name for the size.</span></span>
1. <span data-ttu-id="4cad7-126">Seleccione **Nuevo** en la barra de herramientas y agregue un segundo tamaño a la cuadrícula con un nuevo **Tamaño** y **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-126">Select **New** on the toolbar and add a second size to the grid with a new **Size** and **Name**.</span></span>
1. <span data-ttu-id="4cad7-127">Abra la pestaña **Coores** y seleccione **Nuevo** en la barra de herramientas para agregar una fila a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="4cad7-127">Open the **Colors** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="4cad7-128">Realice las siguientes configuraciones para la nueva fila:</span><span class="sxs-lookup"><span data-stu-id="4cad7-128">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="4cad7-129">**Color:** seleccione un valor de color.</span><span class="sxs-lookup"><span data-stu-id="4cad7-129">**Color:** Select a color value.</span></span>
    - <span data-ttu-id="4cad7-130">**Nombre:** escriba un nombre para el color.</span><span class="sxs-lookup"><span data-stu-id="4cad7-130">**Name:** Enter a name for the color.</span></span>
1. <span data-ttu-id="4cad7-131">Seleccione **Nuevo** en la barra de herramientas y agregue un segundo color a la cuadrícula con un nuevo **Color** y **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-131">Select **New** on the toolbar and add a second color to the grid with a new **Color** and **Name**.</span></span>
1. <span data-ttu-id="4cad7-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-132">Select **Save**.</span></span>
1. <span data-ttu-id="4cad7-133">Cierre la página para volver a su nuevo producto maestro.</span><span class="sxs-lookup"><span data-stu-id="4cad7-133">Close the page to return to your new product master.</span></span>

### <a name="step-3-generate-product-variants"></a><span data-ttu-id="4cad7-134">Paso 3: generar variantes de productos</span><span class="sxs-lookup"><span data-stu-id="4cad7-134">Step 3: Generate product variants</span></span>

> [!NOTE]
> <span data-ttu-id="4cad7-135">Esta sección describe cómo generar variantes de producto cuando la función *Mejoras en la página de sugerencias de variantes* no está habilitada.</span><span class="sxs-lookup"><span data-stu-id="4cad7-135">This section describes how to generate product variants when the *Variant suggestions page improvements* feature isn't enabled.</span></span> <span data-ttu-id="4cad7-136">Consulte la siguiente sección para obtener detalles sobre cómo generar variantes de productos cuando esa función está disponible.</span><span class="sxs-lookup"><span data-stu-id="4cad7-136">See the next section for details about how to generate product variants when that feature is available.</span></span>

<span data-ttu-id="4cad7-137">Para generar variantes de productos:</span><span class="sxs-lookup"><span data-stu-id="4cad7-137">To generate product variants:</span></span>

1. <span data-ttu-id="4cad7-138">Con su nuevo producto maestro aún abierto, seleccione **Variantes del producto** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="4cad7-138">With your new product master still open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="4cad7-139">Seleccione **Sugerencias de variantes** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="4cad7-139">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="4cad7-140">El sistema genera una lista con todas las combinaciones posibles de los tamaños y colores que definió para el producto.</span><span class="sxs-lookup"><span data-stu-id="4cad7-140">The system generates a list with all possible combinations of the sizes and colors you defined for the product.</span></span> <span data-ttu-id="4cad7-141">Seleccione **Seleccionar todo** en la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="4cad7-141">Select **Select all** on the toolbar.</span></span>
    - <span data-ttu-id="4cad7-142">En este ejemplo, seleccione todas las variantes posibles.</span><span class="sxs-lookup"><span data-stu-id="4cad7-142">In this example, select all of the possible variants.</span></span> <span data-ttu-id="4cad7-143">Si solo desea utilizar un subconjunto de las posibles combinaciones de dimensiones del producto, seleccione solo las casillas requeridas, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4cad7-143">If you only want to use a subset of the possible product dimension combinations, select only the required check boxes as needed.</span></span>  
1. <span data-ttu-id="4cad7-144">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-144">Select **Create**.</span></span>
1. <span data-ttu-id="4cad7-145">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-145">Select **Save**.</span></span>

## <a name="improved-variant-suggestions"></a><span data-ttu-id="4cad7-146">Sugerencias de variantes mejoradas</span><span class="sxs-lookup"><span data-stu-id="4cad7-146">Improved variant suggestions</span></span>

<span data-ttu-id="4cad7-147">La característica *Mejoras en la página de sugerencias de variantes* mejora la página **Sugerencias de variantes** para abordar problemas de rendimiento y usabilidad para empresas que tienen un gran número de combinaciones de dimensiones de productos.</span><span class="sxs-lookup"><span data-stu-id="4cad7-147">The *Variant suggestions page improvements* feature improves the **Variant suggestions** page to address performance and usability issues for companies that have a high number of product dimension combinations.</span></span> <span data-ttu-id="4cad7-148">El proceso mejorado para seleccionar los valores de dimensión de producto para los que generar sugerencias de variantes hace que sea más rápido y más fácil identificar y liberar el conjunto relevante de variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="4cad7-148">The enhanced process for selecting the product dimension values for which to generate variant suggestions makes it faster and easier to identify and release the relevant set of product variants.</span></span>

<span data-ttu-id="4cad7-149">Esta característica agrega las siguientes mejoras:</span><span class="sxs-lookup"><span data-stu-id="4cad7-149">The following improvements are added by this feature:</span></span>

- <span data-ttu-id="4cad7-150">**Generación diferida de sugerencias de variantes:** la página **Sugerencias de variantes** ya no muestra sugerencias cuando la abre por primera vez.</span><span class="sxs-lookup"><span data-stu-id="4cad7-150">**Deferred generation of variant suggestions:** The **Variant suggestions** page no longer shows suggestions when you first open it.</span></span> <span data-ttu-id="4cad7-151">En su lugar, debe elegir explícitamente qué valores necesitará y luego seleccionar el botón **Sugerir** para generar las combinaciones.</span><span class="sxs-lookup"><span data-stu-id="4cad7-151">Instead, you must explicitly choose which values you will need and then select the **Suggest** button to generate the combinations.</span></span> <span data-ttu-id="4cad7-152">Esto hace que el proceso sea más visible e interactivo.</span><span class="sxs-lookup"><span data-stu-id="4cad7-152">This makes the process more visible and interactive.</span></span>
- <span data-ttu-id="4cad7-153">**Selección de valores de dimensiones:** cuando tiene muchos valores de dimensión, normalmente le interesa generar sugerencias de variantes que incluyan solo algunos de ellos (por ejemplo, al introducir un nuevo conjunto de colores o estilos).</span><span class="sxs-lookup"><span data-stu-id="4cad7-153">**Selection of dimensions values:** When you have many dimension values, you are typically interested in generating variant suggestions that include just a few of them (such as when introducing a new set of colors or styles).</span></span> <span data-ttu-id="4cad7-154">Con el diseño mejorado, puede seleccionar los valores de dimensión para los que desea generar sugerencias de variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="4cad7-154">With the improved design, you can select the dimension values for which you want to generate product variant suggestions.</span></span> <span data-ttu-id="4cad7-155">Esto aumenta enormemente la relevancia de las variantes sugeridas y mejora tanto el rendimiento del sistema como la productividad del usuario.</span><span class="sxs-lookup"><span data-stu-id="4cad7-155">This greatly increases the relevance of the suggested variants and improves both system performance and user productivity.</span></span>

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a><span data-ttu-id="4cad7-156">Active la función de mejoras de la página de sugerencias de variantes</span><span class="sxs-lookup"><span data-stu-id="4cad7-156">Turn on the Variant suggestions page improvements feature</span></span>

<span data-ttu-id="4cad7-157">Antes de poder usar la característica *Mejoras de la página de sugerencias de variantes*, esta debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="4cad7-157">Before you can use *Variant suggestions page improvements* feature, it must be turned on in your system.</span></span> <span data-ttu-id="4cad7-158">Los administradores pueden usar la configuración de [gestión de funciones](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="4cad7-158">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="4cad7-159">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="4cad7-159">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="4cad7-160">**Módulo:** *Gestión de información de productos*</span><span class="sxs-lookup"><span data-stu-id="4cad7-160">**Module:** *Product information management*</span></span>
- <span data-ttu-id="4cad7-161">**Nombre de función:** *Mejoras de la página de sugerencias de variantes*</span><span class="sxs-lookup"><span data-stu-id="4cad7-161">**Feature name:** *Variant suggestions page improvements*</span></span>

### <a name="work-with-the-improved-variant-suggestions"></a><span data-ttu-id="4cad7-162">Trabajar con las sugerencias de variantes mejoradas</span><span class="sxs-lookup"><span data-stu-id="4cad7-162">Work with the improved variant suggestions</span></span>

<span data-ttu-id="4cad7-163">Para generar sugerencias de variantes de producto cuando la función *Mejoras de la página de sugerencias de variantes* no está habilitada:</span><span class="sxs-lookup"><span data-stu-id="4cad7-163">To generate product variant suggestions when the *Variant suggestions page improvements* feature is enabled:</span></span>

1. <span data-ttu-id="4cad7-164">Abra o cree un producto maestro y agregue las dimensiones de producto requeridas, como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="4cad7-164">Open or create a product master and add the required product dimensions to it, as described in the previous section.</span></span>
1. <span data-ttu-id="4cad7-165">Con el nuevo producto maestro aún abierto, seleccione **Variantes del producto** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="4cad7-165">With the product master open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="4cad7-166">Seleccione **Sugerencias de variantes** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="4cad7-166">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="4cad7-167">Seleccione los valores que desee usar para cada una de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="4cad7-167">Select the values that you want to use for each of the dimensions.</span></span>
1. <span data-ttu-id="4cad7-168">En la barra de herramientas superior, seleccione **Sugerir**.</span><span class="sxs-lookup"><span data-stu-id="4cad7-168">On the top toolbar, select **Suggest**.</span></span>
1. <span data-ttu-id="4cad7-169">El sistema genera una lista con todas las combinaciones posibles de los tamaños y colores que haya seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4cad7-169">The system generates a list with all possible combinations of the sizes and colors you selected.</span></span> <span data-ttu-id="4cad7-170">En la ficha desplegable **Variantes sugeridas**, seleccione la casilla para cada combinación de dimensión de producto que desee utilizar, o seleccione **Seleccionar todo** en la barra de herramientas para seleccionarlos todos.</span><span class="sxs-lookup"><span data-stu-id="4cad7-170">On the **Suggested variants** FastTab, select the check box for each product dimension combination that you want to use, or select **Select all** on the toolbar to select all of them.</span></span>  
1. <span data-ttu-id="4cad7-171">Seleccione **Crear** para agregar las variantes al producto maestro actual.</span><span class="sxs-lookup"><span data-stu-id="4cad7-171">Select **Create** to add the variants to the current product master.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
