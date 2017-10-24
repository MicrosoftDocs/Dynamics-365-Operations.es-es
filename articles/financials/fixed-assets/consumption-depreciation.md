---
title: "Depreciación de consumo"
description: "Este artículo le ofrece una visión general del método de depreciación Consumo."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13751
ms.assetid: d25a681f-49a5-4bfc-aa76-1c6373e35dd8
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c48877058edf8251ef6eb5dd63d7eecd1866f33
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="consumption-depreciation"></a><span data-ttu-id="3c746-103">Depreciación de consumo</span><span class="sxs-lookup"><span data-stu-id="3c746-103">Consumption depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="3c746-104">Este artículo le ofrece una visión general del método de depreciación Consumo.</span><span class="sxs-lookup"><span data-stu-id="3c746-104">This article gives an overview of the Consumption method of depreciation.</span></span>

<span data-ttu-id="3c746-105">Si configura un perfil de depreciación para activos fijos y selecciona **Consumo** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos se asignan a este perfil de depreciación según su uso.</span><span class="sxs-lookup"><span data-stu-id="3c746-105">If you set up a depreciation profile for fixed assets and select **Consumption** in the **Method** field on the **Depreciation profiles** page, fixed assets are assigned to the depreciation profile based on their usage.</span></span> <span data-ttu-id="3c746-106">No tiene que configurar porcentajes e intervalos en la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="3c746-106">You don't have to set up percentages and intervals on the **Depreciation profiles** page.</span></span> <span data-ttu-id="3c746-107">Una vez creado el perfil de depreciación que utiliza el método Consumo, puede configurar el método de varias formas.</span><span class="sxs-lookup"><span data-stu-id="3c746-107">After you create a depreciation profile that uses the Consumption method, you can set up the method in various ways.</span></span>

## <a name="set-up-and-use-consumption-depreciation"></a><span data-ttu-id="3c746-108">Configuración y uso de la depreciación de consumo</span><span class="sxs-lookup"><span data-stu-id="3c746-108">Set up and use consumption depreciation</span></span>
1.  <span data-ttu-id="3c746-109">En la página **Métodos de depreciación**, cree el perfil de depreciación.</span><span class="sxs-lookup"><span data-stu-id="3c746-109">On the **Depreciation profiles** page, create the depreciation profile.</span></span> <span data-ttu-id="3c746-110">Para los cálculos de consumo, el perfil de depreciación debe tener un identificador y un nombre, y **Consumo** debe estar seleccionado en el campo **Método**.</span><span class="sxs-lookup"><span data-stu-id="3c746-110">For consumption calculations, the depreciation profile must have an ID and a name, and **Consumption** must be selected in the **Method** field.</span></span>
2.  <span data-ttu-id="3c746-111">En la página **Factores de consumo**, configure factores de consumo.</span><span class="sxs-lookup"><span data-stu-id="3c746-111">On the **Consumption factors** page, set up consumption factors.</span></span> <span data-ttu-id="3c746-112">Cada factor de consumo debe tener un identificador y un nombre, y un factor de consumo que se especifique como una cantidad o un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="3c746-112">Each consumption factor must have an ID and a name, and a consumption factor that is specified as either a quantity or a percentage.</span></span>
3.  <span data-ttu-id="3c746-113">En la página **Unidades de consumo**, configure unidades de consumo.</span><span class="sxs-lookup"><span data-stu-id="3c746-113">On the **Consumption units** page, set up consumption units.</span></span> <span data-ttu-id="3c746-114">Cada unidad de consumo debe tener un identificador y un nombre.</span><span class="sxs-lookup"><span data-stu-id="3c746-114">Each consumption unit must have an ID and a name.</span></span> <span data-ttu-id="3c746-115">Las unidades de depreciación se usan para calcular la depreciación del consumo en la página **Depreciación de consumo**.</span><span class="sxs-lookup"><span data-stu-id="3c746-115">Depreciation units are used to calculate consumption depreciation on the **Consumption depreciation** page.</span></span> <span data-ttu-id="3c746-116">Algunos ejemplos de unidades son kilómetro (km), kilogramo (kg) y hora.</span><span class="sxs-lookup"><span data-stu-id="3c746-116">Examples of units are kilometer (km), kilogram (kg), and hour.</span></span>
4.  <span data-ttu-id="3c746-117">En la página **Activos fijos**, configure activos fijos individuales.</span><span class="sxs-lookup"><span data-stu-id="3c746-117">On the **Fixed assets** page, set up individual fixed assets.</span></span> <span data-ttu-id="3c746-118">Para cada activo fijo, seleccione los modelos de valor y los libros amortización que tengan perfiles de depreciación.</span><span class="sxs-lookup"><span data-stu-id="3c746-118">For each fixed asset, select value models and depreciation books that have depreciation profiles.</span></span> <span data-ttu-id="3c746-119">Debe configurar modelos de valor o libros de amortización para la depreciación de consumo, si cualquiera de sus activos fijos usan perfiles de depreciación que se basan en el método Consumo.</span><span class="sxs-lookup"><span data-stu-id="3c746-119">You must set up value models or depreciation books for consumption depreciation if any of your fixed assets use depreciation profiles that are based on the Consumption method.</span></span> <span data-ttu-id="3c746-120">Esta configuración se realiza en la ficha **Depreciación** de la página **Modelos de valor** o la ficha desplegable **General** de la página **Perfil de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="3c746-120">This setup is done either on the **Depreciation** tab of the **Value models** page or on the **General** FastTab of the **Depreciation profile** page.</span></span> <span data-ttu-id="3c746-121">Puede utilizar el mismo modelo de valor para varios activos fijos.</span><span class="sxs-lookup"><span data-stu-id="3c746-121">You can use the same value model for multiple fixed assets.</span></span> <span data-ttu-id="3c746-122">Los perfiles de depreciación son parte del modelo de valor o libro amortización que seleccione para cada activo fijo.</span><span class="sxs-lookup"><span data-stu-id="3c746-122">Depreciation profiles are part of the value model or depreciation book that you select for each fixed asset.</span></span> <span data-ttu-id="3c746-123">No puede agregar ni modificar perfiles de depreciación directamente en la página **Activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="3c746-123">You can't add or modify depreciation profiles directly on the **Fixed assets** page.</span></span> <span data-ttu-id="3c746-124">Puede modificar perfiles de depreciación solo en la página **Libros de amortización**.</span><span class="sxs-lookup"><span data-stu-id="3c746-124">You can modify depreciation profiles only on the **Depreciation books** page.</span></span>
5.  <span data-ttu-id="3c746-125">En la página **Modelos de valor** de la página **Libros de amortización**, en el grupo de campos **Depreciación de consumo**, especifique información en los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="3c746-125">On the **Value models** page or the **Depreciation books** page, in the **Consumption depreciation** field group, enter information in the following fields:</span></span>
    -   <span data-ttu-id="3c746-126">Factor de consumo</span><span class="sxs-lookup"><span data-stu-id="3c746-126">Consumption factor</span></span>
    -   <span data-ttu-id="3c746-127">Unidad</span><span class="sxs-lookup"><span data-stu-id="3c746-127">Unit</span></span>
    -   <span data-ttu-id="3c746-128">Depreciación de unidad</span><span class="sxs-lookup"><span data-stu-id="3c746-128">Unit depreciation</span></span>
    -   <span data-ttu-id="3c746-129">Consumo estimado</span><span class="sxs-lookup"><span data-stu-id="3c746-129">Estimated consumption</span></span>

    <span data-ttu-id="3c746-130">El campo**Consumo registrado** muestra la depreciación de consumo, en unidades, que ya se ha registrado para la combinación del activo fijo y del modelo de valor, o para el libro de depreciación.</span><span class="sxs-lookup"><span data-stu-id="3c746-130">The **Posted consumption** field shows the consumption depreciation, in units, that has already been posted either for the combination of the fixed asset and value model, or for the depreciation book.</span></span> <span data-ttu-id="3c746-131">No es posible actualizar manualmente el valor en este campo.</span><span class="sxs-lookup"><span data-stu-id="3c746-131">You can't manually update the value in this field.</span></span>

## <a name="examples"></a><span data-ttu-id="3c746-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c746-132">Examples</span></span>
### <a name="example-1"></a><span data-ttu-id="3c746-133">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="3c746-133">Example 1</span></span>

<span data-ttu-id="3c746-134">El siguiente factor de consumo se configura para el 31 de enero:</span><span class="sxs-lookup"><span data-stu-id="3c746-134">The following consumption factor is set up for January 31:</span></span>

-   <span data-ttu-id="3c746-135">La cantidad es 1.000.</span><span class="sxs-lookup"><span data-stu-id="3c746-135">The quantity is 1,000.</span></span>
-   <span data-ttu-id="3c746-136">El precio de depreciación de la unidad se especifica para el activo fijo es 1,5.</span><span class="sxs-lookup"><span data-stu-id="3c746-136">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>

<span data-ttu-id="3c746-137">La propuesta de depreciación el 31 de enero es la siguiente: Cantidad × Depreciación de unidad 1.000 x 1,5 = 1.500 Si el factor especificado para el activo fijo es un factor de porcentaje, la cantidad que se estima en el campo **Consumo estimado** para el modelo de valor del activo fijo se multiplica por el porcentaje que se configura para la fecha final seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3c746-137">The depreciation proposal on January 31 is as follows: Quantity × Unit depreciation 1,000 × 1.5 = 1,500 If the factor that is specified for the fixed asset is a percentage factor, the quantity that is estimated in the **Estimated consumption** field for the value model of the fixed asset is multiplied by the percentage that is set up for the selected end date.</span></span> <span data-ttu-id="3c746-138">La cantidad resultante se sugiere entonces como cantidad de depreciación para el período.</span><span class="sxs-lookup"><span data-stu-id="3c746-138">The resulting quantity is then suggested as the depreciation quantity for the period.</span></span>

### <a name="example-2"></a><span data-ttu-id="3c746-139">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="3c746-139">Example 2</span></span>

<span data-ttu-id="3c746-140">El siguiente factor de depreciación de consumo se configura para el 31 de enero.</span><span class="sxs-lookup"><span data-stu-id="3c746-140">The following factor for consumption depreciation is set up for January 31:</span></span>

-   <span data-ttu-id="3c746-141">El porcentaje es del 10%.</span><span class="sxs-lookup"><span data-stu-id="3c746-141">The percentage is 10 percent.</span></span>
-   <span data-ttu-id="3c746-142">El precio de depreciación de la unidad se especifica para el activo fijo es 1,5.</span><span class="sxs-lookup"><span data-stu-id="3c746-142">The unit depreciation price that is specified for the fixed asset is 1.5.</span></span>
-   <span data-ttu-id="3c746-143">La cantidad estimada del activo fijo es 2.000.</span><span class="sxs-lookup"><span data-stu-id="3c746-143">The estimated quantity of the fixed asset is 2,000.</span></span>

<span data-ttu-id="3c746-144">La propuesta de depreciación el 31 de enero es la siguiente: Cantidad estimada × Porcentaje x Unidad de depreciación 2.000 x ,10 × de 1,5 = 300</span><span class="sxs-lookup"><span data-stu-id="3c746-144">The depreciation proposal on January 31 is as follows: Estimated quantity × Percentage × Unit depreciation 2,000 × .10 × 1.5 = 300</span></span>




