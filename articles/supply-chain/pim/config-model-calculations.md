---
title: Cálculos de modelo de configuración de producto
description: En este tema se describe cómo crear cálculos para los atributos en un modelo de configuración de producto
author: t-benebo
ms.date: 03/18/2021
ms.topic: article
ms.search.form: PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-03-18
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf6264f060d33575740ad38e7a65158baba296b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829627"
---
# <a name="product-configuration-model-calculations"></a><span data-ttu-id="52ea2-103">Cálculos de modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="52ea2-103">Product configuration model calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52ea2-104">En este tema se describe cómo crear cálculos para los atributos en un modelo de configuración de producto.</span><span class="sxs-lookup"><span data-stu-id="52ea2-104">This topic describes how to create calculations for attributes in a product configuration model.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52ea2-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="52ea2-105">Prerequisites</span></span>

<span data-ttu-id="52ea2-106">Los cálculos se usan en un modelo de configuración de productos para calcular los valores de configuración de un producto.</span><span class="sxs-lookup"><span data-stu-id="52ea2-106">Calculations are used in a product configuration model to calculate the configuration values for a product.</span></span> <span data-ttu-id="52ea2-107">Antes de que pueda comenzar a configurar los cálculos, debe existir el modelo de configuración del producto relacionado.</span><span class="sxs-lookup"><span data-stu-id="52ea2-107">Before you can start to set up calculations, the related product configuration model must exist.</span></span> <span data-ttu-id="52ea2-108">Para obtener una descripción general del proceso de configuración de los modelos de configuración y las tareas relacionadas, consulte [Configurar un modelo de configuración de producto](set-up-maintain-product-configuration-model.md).</span><span class="sxs-lookup"><span data-stu-id="52ea2-108">For an overview of the setup process for configuration models and the related tasks, see [Set up a product configuration model](set-up-maintain-product-configuration-model.md).</span></span>

## <a name="create-a-calculation"></a><span data-ttu-id="52ea2-109">Crear un cálculo</span><span class="sxs-lookup"><span data-stu-id="52ea2-109">Create a calculation</span></span>

<span data-ttu-id="52ea2-110">Un cálculo consta de una expresión y un atributo de destino.</span><span class="sxs-lookup"><span data-stu-id="52ea2-110">A calculation consists of an expression and a target attribute.</span></span> <span data-ttu-id="52ea2-111">Para obtener más información, consulte [Preguntas frecuentes sobre los cálculos de modelos de configuración de productos](calculate-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="52ea2-111">For more information, see [Calculations for product configuration models FAQ](calculate-product-configuration-models.md).</span></span>

<span data-ttu-id="52ea2-112">Para crear un cálculo para un modelo de producto existente, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="52ea2-112">To create a calculation for an existing product model, follow these steps.</span></span>

1. <span data-ttu-id="52ea2-113">Vaya a **Gestión de información de productos \> Común \> Modelos de configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="52ea2-113">Go to **Product information management \> Common \> Product configuration models**.</span></span>
1. <span data-ttu-id="52ea2-114">Abra un modelo de configuración de productos y seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="52ea2-114">Open a product configuration model, and then select **Edit**.</span></span>
1. <span data-ttu-id="52ea2-115">En la ficha desplegable **Cálculos**, seleccione **Agregar** para agregar un cálculo y luego establezca los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="52ea2-115">On the **Calculations** FastTab, select **Add** to add a calculation, and then set the following fields:</span></span>

    - <span data-ttu-id="52ea2-116">**Nombre**: escriba un nombre para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="52ea2-116">**Name** – Enter a name for the calculation.</span></span>
    - <span data-ttu-id="52ea2-117">**Descripción**: escriba una descripción del cálculo.</span><span class="sxs-lookup"><span data-stu-id="52ea2-117">**Description** – Enter a description of the calculation.</span></span>
    - <span data-ttu-id="52ea2-118">**Atributo de destino**: seleccione el atributo para el que está haciendo el cálculo.</span><span class="sxs-lookup"><span data-stu-id="52ea2-118">**Target attribute** – Select the attribute that you're making the calculation for.</span></span>

1. <span data-ttu-id="52ea2-119">Seleccione **Editar expresión**.</span><span class="sxs-lookup"><span data-stu-id="52ea2-119">Select **Edit expression**.</span></span>
1. <span data-ttu-id="52ea2-120">En el cuadro de diálogo **Ingrese un cálculo**, agregue los atributos, operadores y valores necesarios a la expresión.</span><span class="sxs-lookup"><span data-stu-id="52ea2-120">In the **Enter a calculation** dialog box, add the required attributes, operators, and values to the expression.</span></span> <span data-ttu-id="52ea2-121">Para obtener más información sobre cómo trabajar con estos elementos, consulte [Restricciones de expresión o restricciones de tabla en modelos de configuración de producto](expression-constraints-table-constraints-product-configuration-models.md).</span><span class="sxs-lookup"><span data-stu-id="52ea2-121">For more information about how to work with these elements, see [Expression constraints and table constraints in product configuration models](expression-constraints-table-constraints-product-configuration-models.md).</span></span>
1. <span data-ttu-id="52ea2-122">Cuando su expresión esté lista, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52ea2-122">When your expression is ready, select **OK**.</span></span>

## <a name="calculation-examples"></a><span data-ttu-id="52ea2-123">Ejemplos de cálculo</span><span class="sxs-lookup"><span data-stu-id="52ea2-123">Calculation examples</span></span>

<span data-ttu-id="52ea2-124">Esta sección proporciona algunos ejemplos que muestran cómo funcionan los cálculos.</span><span class="sxs-lookup"><span data-stu-id="52ea2-124">This section provides a few examples that show how calculations work.</span></span>

### <a name="example-1"></a><span data-ttu-id="52ea2-125">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="52ea2-125">Example 1</span></span>

<span data-ttu-id="52ea2-126">El atributo objetivo es booleano y el cálculo usa la siguiente expresión condicional:</span><span class="sxs-lookup"><span data-stu-id="52ea2-126">The target attribute is Boolean, and the calculation uses the following conditional expression:</span></span>

`If[(decimalAttribute1 / decimalAttribute2) < 1, True, False]`

<span data-ttu-id="52ea2-127">Esta expresión devuelve un valor de *True* al atributo de destino si `decimalAttribute2` es mayor o igual que `decimalAttribute1`.</span><span class="sxs-lookup"><span data-stu-id="52ea2-127">This expression returns a value of *True* to the target attribute if `decimalAttribute2` is greater than or equal to `decimalAttribute1`.</span></span> <span data-ttu-id="52ea2-128">De lo contrario, la expresión devuelve un valor *False*.</span><span class="sxs-lookup"><span data-stu-id="52ea2-128">Otherwise, it returns a value of *False*.</span></span>

### <a name="example-2"></a><span data-ttu-id="52ea2-129">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="52ea2-129">Example 2</span></span>

<span data-ttu-id="52ea2-130">Este ejemplo usa el atributo de texto `textFixedList` como atributo de destino.</span><span class="sxs-lookup"><span data-stu-id="52ea2-130">This example uses the text attribute `textFixedList` as the target attribute.</span></span> <span data-ttu-id="52ea2-131">Este atributo contiene la siguiente lista fija.</span><span class="sxs-lookup"><span data-stu-id="52ea2-131">This attribute contains the following fixed list.</span></span>

| <span data-ttu-id="52ea2-132">Valor</span><span class="sxs-lookup"><span data-stu-id="52ea2-132">Value</span></span> | <span data-ttu-id="52ea2-133">Valor del solucionador</span><span class="sxs-lookup"><span data-stu-id="52ea2-133">Solver value</span></span> |
|---|---|
| <span data-ttu-id="52ea2-134">C</span><span class="sxs-lookup"><span data-stu-id="52ea2-134">A</span></span> | <span data-ttu-id="52ea2-135">1a</span><span class="sxs-lookup"><span data-stu-id="52ea2-135">1a</span></span> |
| <span data-ttu-id="52ea2-136">mil millones</span><span class="sxs-lookup"><span data-stu-id="52ea2-136">B</span></span> | <span data-ttu-id="52ea2-137">2b</span><span class="sxs-lookup"><span data-stu-id="52ea2-137">2b</span></span> |
| <span data-ttu-id="52ea2-138">C</span><span class="sxs-lookup"><span data-stu-id="52ea2-138">C</span></span> | <span data-ttu-id="52ea2-139">2c</span><span class="sxs-lookup"><span data-stu-id="52ea2-139">2c</span></span> |

<span data-ttu-id="52ea2-140">La siguiente captura de pantalla muestra cómo podría verse la configuración de este atributo en su sistema.</span><span class="sxs-lookup"><span data-stu-id="52ea2-140">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="52ea2-141">![Configuración de tipo de atributo, por ejemplo 2](media/model-calculations-example2.png "Configuración de tipo de atributo, por ejemplo 2")</span><span class="sxs-lookup"><span data-stu-id="52ea2-141">![Attribute type settings for example 2](media/model-calculations-example2.png "Attribute type settings for example 2")</span></span>

<span data-ttu-id="52ea2-142">El atributo se utiliza en la siguiente declaración condicional:</span><span class="sxs-lookup"><span data-stu-id="52ea2-142">The attribute is used in the following conditional statement:</span></span>

`If[integerAttribute < 150, 0, 2]`

<span data-ttu-id="52ea2-143">Si `integerAttribute` es menor que 150, esta declaración devuelve el valor de texto del primer registro en la lista fija, *A*. De lo contrario, devuelve el valor de texto del tercer registro en la lista fija, *C*.</span><span class="sxs-lookup"><span data-stu-id="52ea2-143">If `integerAttribute` is less than 150, this statement returns the text value of the first record in the fixed list, *A*. Otherwise, it returns the text value of the third record in the fixed list, *C*.</span></span>

> [!NOTE]
> <span data-ttu-id="52ea2-144">La lista fija es equivalente a una enumeración basada en cero (enum), y se accede a sus valores mediante el valor entero apropiado.</span><span class="sxs-lookup"><span data-stu-id="52ea2-144">The fixed list is equivalent to a zero-based enumeration (enum), and its values are accessed by the appropriate integer value.</span></span> <span data-ttu-id="52ea2-145">Por lo tanto, el primer valor de lista fijo (*A*) coincide con *0*, el segundo valor (*B*) coincide con *1*, y el tercer valor (*C*) coincide con *2*.</span><span class="sxs-lookup"><span data-stu-id="52ea2-145">Therefore, the first fixed list value (*A*) is matched to *0*, the second value (*B*) is matched to *1*, and the third value (*C*) is matched to *2*.</span></span>

### <a name="example-3"></a><span data-ttu-id="52ea2-146">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="52ea2-146">Example 3</span></span>

<span data-ttu-id="52ea2-147">Este ejemplo usa el atributo de destino `textFixedList` del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="52ea2-147">This example uses the `textFixedList` target attribute from the previous example.</span></span> <span data-ttu-id="52ea2-148">También usa otro atributo de texto, `textAttribute`, que contiene la siguiente lista fija.</span><span class="sxs-lookup"><span data-stu-id="52ea2-148">It also uses another text attribute, `textAttribute`, that contains the following fixed list.</span></span>

| <span data-ttu-id="52ea2-149">Valor</span><span class="sxs-lookup"><span data-stu-id="52ea2-149">Value</span></span> | <span data-ttu-id="52ea2-150">Valor del solucionador</span><span class="sxs-lookup"><span data-stu-id="52ea2-150">Solver value</span></span> |
|---|---|
| <span data-ttu-id="52ea2-151">AA</span><span class="sxs-lookup"><span data-stu-id="52ea2-151">AA</span></span> | <span data-ttu-id="52ea2-152">1aa</span><span class="sxs-lookup"><span data-stu-id="52ea2-152">1aa</span></span> |
| <span data-ttu-id="52ea2-153">BB</span><span class="sxs-lookup"><span data-stu-id="52ea2-153">BB</span></span> | <span data-ttu-id="52ea2-154">2bb</span><span class="sxs-lookup"><span data-stu-id="52ea2-154">2bb</span></span> |

<span data-ttu-id="52ea2-155">La siguiente captura de pantalla muestra cómo podría verse la configuración de este atributo en su sistema.</span><span class="sxs-lookup"><span data-stu-id="52ea2-155">The following screenshot shows how the settings for this attribute might look in your system.</span></span>

<span data-ttu-id="52ea2-156">![Configuración de tipo de atributo, por ejemplo 3](media/model-calculations-example3.png "Configuración de tipo de atributo, por ejemplo 3")</span><span class="sxs-lookup"><span data-stu-id="52ea2-156">![Attribute type settings for example 3](media/model-calculations-example3.png "Attribute type settings for example 3")</span></span>

<span data-ttu-id="52ea2-157">El valor del atributo `textFixedList` se calcula utilizando la siguiente declaración condicional:</span><span class="sxs-lookup"><span data-stu-id="52ea2-157">The value for the `textFixedList` attribute is calculated by using the following conditional statement:</span></span>

`If[textAttribute == "1aa", 0, 2]`

<span data-ttu-id="52ea2-158">Si el valor `textAttribute` tiene un valor de resolución que es igual a *1aa*, esta expresión devuelve el valor de texto del primer registro en la lista fija, `textFixedList`, *A*. De lo contrario, devuelve el valor de texto del tercer registro en la lista fija `textFixedList`, *C*.</span><span class="sxs-lookup"><span data-stu-id="52ea2-158">If the `textAttribute` value has a solver value that equals *1aa*, this expression returns the text value of the first record in the `textFixedList` fixed list, *A*. Otherwise, it returns the text value of the third record in the `textFixedList` fixed list, *C*.</span></span>

> [!NOTE]
> - <span data-ttu-id="52ea2-159">La declaración condicional debe utilizar el valor solucionador del atributo.</span><span class="sxs-lookup"><span data-stu-id="52ea2-159">The conditional statement must use the solver value of the attribute.</span></span>
> - <span data-ttu-id="52ea2-160">En los cálculos solo se pueden utilizar atributos de texto de lista fija.</span><span class="sxs-lookup"><span data-stu-id="52ea2-160">Only fixed-list text attributes can be used in calculations.</span></span>

## <a name="see-also"></a><span data-ttu-id="52ea2-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="52ea2-161">See also</span></span>

- [<span data-ttu-id="52ea2-162">Preguntas más frecuentes sobre cálculos para modelos de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="52ea2-162">Calculations for product configuration models FAQ</span></span>](calculate-product-configuration-models.md)
- [<span data-ttu-id="52ea2-163">Agregar una restricción de expresión a un modelo de configuración de producto</span><span class="sxs-lookup"><span data-stu-id="52ea2-163">Add an expression constraint to a product configuration model</span></span>](tasks/add-expression-constraint-product-configuration-model.md)
- [<span data-ttu-id="52ea2-164">Visión general de los modelos de configuración de productos</span><span class="sxs-lookup"><span data-stu-id="52ea2-164">Product configuration models overview</span></span>](product-configuration-models.md)
