---
title: Crear variantes de productos predefinidas
description: Este procedimiento le guía por la creación de variantes de productos para un producto maestro mediante las combinaciones de dimensiones de productos.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d07a090dbd41eb17e8d604887435bbb8b07e8d9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966939"
---
# <a name="create-predefined-product-variants"></a><span data-ttu-id="77664-103">Crear variantes de productos predefinidas</span><span class="sxs-lookup"><span data-stu-id="77664-103">Create predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="77664-104">Este procedimiento le guía por la creación de variantes de productos para un producto maestro mediante las combinaciones de dimensiones de productos.</span><span class="sxs-lookup"><span data-stu-id="77664-104">This procedure walks through creating product variants for a product master using the combinations of product dimensions.</span></span> <span data-ttu-id="77664-105">La empresa de demostración utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="77664-105">The demo company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-master"></a><span data-ttu-id="77664-106">Crear un producto maestro</span><span class="sxs-lookup"><span data-stu-id="77664-106">Create a product master</span></span>
1. <span data-ttu-id="77664-107">Vaya a Gestión de información de productos > Productos > Productos maestros.</span><span class="sxs-lookup"><span data-stu-id="77664-107">Go to Product information management > Products > Product masters.</span></span>
2. <span data-ttu-id="77664-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="77664-108">Click New.</span></span>
3. <span data-ttu-id="77664-109">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-109">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="77664-110">Especificar un número de producto manualmente solo es obligatorio si no se ha establecido ninguna secuencia numérica para el campo del número de producto.</span><span class="sxs-lookup"><span data-stu-id="77664-110">Entering a product number manually is only required if no number sequence has been set for the product number field.</span></span> <span data-ttu-id="77664-111">En otras palabras, omita el paso si se ha establecido la secuencia numérica para el campo.</span><span class="sxs-lookup"><span data-stu-id="77664-111">In other words, skip the step if number sequence has been set for the field.</span></span>  
4. <span data-ttu-id="77664-112">En el campo Nombre de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-112">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="77664-113">En el campo Grupo de dimensiones de producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-113">In the Product dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="77664-114">Seleccione el grupo de dimensiones de producto SizeCol (tamaño y color).</span><span class="sxs-lookup"><span data-stu-id="77664-114">Select the product dimension group SizeCol (Size and Color).</span></span>  
6. <span data-ttu-id="77664-115">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="77664-115">Click OK.</span></span>

## <a name="add-product-dimensions"></a><span data-ttu-id="77664-116">Agregar dimensiones de productos</span><span class="sxs-lookup"><span data-stu-id="77664-116">Add product dimensions</span></span>
1. <span data-ttu-id="77664-117">Haga clic en Dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="77664-117">Click Product dimensions.</span></span>
    * <span data-ttu-id="77664-118">Este ejemplo muestra cómo especificar manualmente dimensiones de producto.</span><span class="sxs-lookup"><span data-stu-id="77664-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="77664-119">También puede elegir seleccionar un grupo de tamaños, colores o estilos que incluya los valores de dimensiones de productos que desea usar.</span><span class="sxs-lookup"><span data-stu-id="77664-119">You can also choose to select a size, color or style group that includes the product dimension values you want to use.</span></span>  
2. <span data-ttu-id="77664-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="77664-120">Click New.</span></span>
3. <span data-ttu-id="77664-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="77664-121">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="77664-122">En el campo Tamaño, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-122">In the Size field, enter or select a value.</span></span>
5. <span data-ttu-id="77664-123">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-123">In the Name field, type a value.</span></span>
6. <span data-ttu-id="77664-124">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="77664-124">Click New.</span></span>
7. <span data-ttu-id="77664-125">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="77664-125">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="77664-126">En el campo Tamaño, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-126">In the Size field, enter or select a value.</span></span>
9. <span data-ttu-id="77664-127">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-127">In the Name field, type a value.</span></span>
10. <span data-ttu-id="77664-128">Haga clic en la ficha Colores.</span><span class="sxs-lookup"><span data-stu-id="77664-128">Click the Colors tab.</span></span>
11. <span data-ttu-id="77664-129">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="77664-129">Click New.</span></span>
12. <span data-ttu-id="77664-130">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="77664-130">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="77664-131">En el campo Color, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-131">In the Color field, enter or select a value.</span></span>
14. <span data-ttu-id="77664-132">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-132">In the Name field, type a value.</span></span>
15. <span data-ttu-id="77664-133">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="77664-133">Click New.</span></span>
16. <span data-ttu-id="77664-134">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="77664-134">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="77664-135">En el campo Color, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-135">In the Color field, enter or select a value.</span></span>
18. <span data-ttu-id="77664-136">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="77664-136">In the Name field, type a value.</span></span>
19. <span data-ttu-id="77664-137">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="77664-137">Click Save.</span></span>
20. <span data-ttu-id="77664-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="77664-138">Close the page.</span></span>

## <a name="generate-product-variants"></a><span data-ttu-id="77664-139">Generar variantes de productos</span><span class="sxs-lookup"><span data-stu-id="77664-139">Generate product variants</span></span>
1. <span data-ttu-id="77664-140">Haga clic en Variantes del producto.</span><span class="sxs-lookup"><span data-stu-id="77664-140">Click Product variants.</span></span>
2. <span data-ttu-id="77664-141">Haga clic en Sugerencias de variantes.</span><span class="sxs-lookup"><span data-stu-id="77664-141">Click Variant suggestions.</span></span>
3. <span data-ttu-id="77664-142">Haga clic en Seleccionar todo.</span><span class="sxs-lookup"><span data-stu-id="77664-142">Click Select all.</span></span>
    * <span data-ttu-id="77664-143">En este ejemplo, se seleccionan todas las variantes posibles.</span><span class="sxs-lookup"><span data-stu-id="77664-143">In this example, all possible variants are selected.</span></span> <span data-ttu-id="77664-144">Si solo se usará un subconjunto de las combinaciones de dimensiones de productos posibles para crear variantes, puede seleccionar las entradas individuales.</span><span class="sxs-lookup"><span data-stu-id="77664-144">If only a subset of the possible product dimension combinations will be used to create variants, you can select the individual entries.</span></span>  
4. <span data-ttu-id="77664-145">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="77664-145">Click Create.</span></span>
    * <span data-ttu-id="77664-146">Puede generar descripciones para todas sus variantes en función de la combinación de los valores de dimensiones de productos.</span><span class="sxs-lookup"><span data-stu-id="77664-146">You can generate descriptions for all your variants based on the combination of product dimension values.</span></span> <span data-ttu-id="77664-147">Las descripciones son opcionales.</span><span class="sxs-lookup"><span data-stu-id="77664-147">The descriptions are optional.</span></span>  
5. <span data-ttu-id="77664-148">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="77664-148">Click Save.</span></span>

