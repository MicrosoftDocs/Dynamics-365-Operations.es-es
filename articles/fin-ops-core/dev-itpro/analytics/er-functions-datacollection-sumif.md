---
title: Función SUMIF ER
description: Este tema proporciona información general sobre cómo usar la función SUMIF de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 04/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 174ac28ee2b726ec7fb2ff6d3dda45906c56af65
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745618"
---
# <a name="sumif-er-function"></a><span data-ttu-id="21531-103">Función SUMIF ER</span><span class="sxs-lookup"><span data-stu-id="21531-103">SUMIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21531-104">La función `SUMIF` devuelve un valor *Real* que representa la suma de valores que fueron devueltos por las vinculaciones de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="21531-104">The `SUMIF` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="21531-105">La condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="21531-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="21531-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21531-106">Syntax</span></span>

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="21531-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="21531-107">Arguments</span></span>

<span data-ttu-id="21531-108">`key name for summing`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="21531-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="21531-109">Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** del componente de formato de informe electrónico (ER) para el cual el valor del enlace debe utilizarse para fines de suma.</span><span class="sxs-lookup"><span data-stu-id="21531-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="21531-110">La propiedad **Valor de clave de datos recopilados** se puede configurar para un componente **Secuencia** o un componente **Elemento XML** de un formato ER que reside bajo el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="21531-110">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="21531-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="21531-111">Return values</span></span>

<span data-ttu-id="21531-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="21531-112">*Real*</span></span>

<span data-ttu-id="21531-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="21531-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="21531-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="21531-114">Usage notes</span></span>

<span data-ttu-id="21531-115">Esta función devuelve un valor **0** (cero) cuando la opción **Recopilar detalles de salida** del componente actual **Común\\Archivo** está desactivado.</span><span class="sxs-lookup"><span data-stu-id="21531-115">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="21531-116">En el argumento `condition range`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="21531-116">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="21531-117">En el argumento `condition value`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="21531-117">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="21531-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21531-118">Example</span></span>

<span data-ttu-id="21531-119">Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.</span><span class="sxs-lookup"><span data-stu-id="21531-119">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

<span data-ttu-id="21531-120">Para obtener más información y ejemplos sobre el uso de esta función, consulte [Aplazar la ejecución de elementos de secuencia en formatos ER](er-defer-sequence-element.md#Example) y [Aplazar la ejecución de elementos XML en formatos ER](er-defer-xml-element.md#Example).</span><span class="sxs-lookup"><span data-stu-id="21531-120">For more information and examples about using this function, see [Defer the execution of sequence elements in ER formats](er-defer-sequence-element.md#Example) and [Defer the execution of XML elements in ER formats](er-defer-xml-element.md#Example).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21531-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="21531-121">Additional resources</span></span>

[<span data-ttu-id="21531-122">Funciones de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="21531-122">Data collection functions</span></span>](er-functions-category-data-collection.md)
