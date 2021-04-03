---
title: Función SUMIFS ER
description: Este tema proporciona información general sobre cómo usar la función SUMIFS de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff5ad3371a6e18ca1a3ee855e3b35f51f7513ef0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564768"
---
# <a name="sumifs-er-function"></a><span data-ttu-id="dfe15-103">Función SUMIFS ER</span><span class="sxs-lookup"><span data-stu-id="dfe15-103">SUMIFS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dfe15-104">La función `SUMIFS` devuelve un valor *Real* que representa la suma de valores que fueron devueltos por las vinculaciones de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="dfe15-104">The `SUMIFS` function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="dfe15-105">Cada condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="dfe15-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="dfe15-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dfe15-106">Syntax</span></span>

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="dfe15-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dfe15-107">Arguments</span></span>

<span data-ttu-id="dfe15-108">`key name for summing`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dfe15-108">`key name for summing`: *String*</span></span>

<span data-ttu-id="dfe15-109">Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** del componente de formato de informe electrónico (ER) para el cual el valor del enlace debe utilizarse para fines de suma.</span><span class="sxs-lookup"><span data-stu-id="dfe15-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of the Electronic reporting (ER) format component for which the value of the binding must be used for summing purposes.</span></span>

<span data-ttu-id="dfe15-110">La propiedad **Nombre de clave de datos recopilados** se puede configurar para un componente **Numérico** o un componente **Cadena** de un formato ER que reside bajo el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="dfe15-110">The **Collected data key name** property can be configured for either a **Numeric** component or a **String** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="dfe15-111">`condition 1 range`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dfe15-111">`condition 1 range`: *String*</span></span>

<span data-ttu-id="dfe15-112">Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="dfe15-112">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="dfe15-113">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dfe15-113">This argument is mandatory.</span></span>

<span data-ttu-id="dfe15-114">La propiedad **Nombre de clave de datos recopilados** se puede configurar para un componente **Secuencia** o un componente **Elemento XML** de un formato ER que reside bajo el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="dfe15-114">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="dfe15-115">`condition 1 value`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dfe15-115">`condition 1 value`: *String*</span></span>

<span data-ttu-id="dfe15-116">Un valor que devuelve la expresión que se ha configurado en la propiedad **Valor de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="dfe15-116">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="dfe15-117">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dfe15-117">This argument is mandatory.</span></span>

<span data-ttu-id="dfe15-118">La propiedad **Valor de clave de datos recopilados** se puede configurar para un componente **Secuencia** o un componente **Elemento XML** de un formato ER que reside bajo el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="dfe15-118">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="dfe15-119">`condition N range`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dfe15-119">`condition N range`: *String*</span></span>

<span data-ttu-id="dfe15-120">Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="dfe15-120">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="dfe15-121">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="dfe15-121">These additional arguments are optional.</span></span>

<span data-ttu-id="dfe15-122">La propiedad **Nombre de clave de datos recopilados** se puede configurar para un componente **Secuencia** o un componente **Elemento XML** de un formato ER que reside bajo el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="dfe15-122">The **Collected data key name** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="dfe15-123">`condition N value`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dfe15-123">`condition N value`: *String*</span></span>

<span data-ttu-id="dfe15-124">Un valor que devuelve la expresión que se ha configurado en la propiedad **Valor de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="dfe15-124">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="dfe15-125">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="dfe15-125">These additional arguments are optional.</span></span>

<span data-ttu-id="dfe15-126">La propiedad **Valor de clave de datos recopilados** se puede configurar para un componente **Secuencia** o un componente **Elemento XML** de un formato ER que reside bajo el componente **Común\\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="dfe15-126">The **Collected data key value** property can be configured for either a **Sequence** component or an **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="return-values"></a><span data-ttu-id="dfe15-127">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dfe15-127">Return values</span></span>

<span data-ttu-id="dfe15-128">*Real*</span><span class="sxs-lookup"><span data-stu-id="dfe15-128">*Real*</span></span>

<span data-ttu-id="dfe15-129">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="dfe15-129">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="dfe15-130">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="dfe15-130">Usage notes</span></span>

<span data-ttu-id="dfe15-131">Esta función devuelve un valor **0** (cero) cuando la opción **Recopilar detalles de salida** del componente actual **Común \\Archivo** está desactivado.</span><span class="sxs-lookup"><span data-stu-id="dfe15-131">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="dfe15-132">En los argumentos `condition range`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="dfe15-132">In the `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="dfe15-133">En los argumentos `condition value`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="dfe15-133">In the `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="dfe15-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dfe15-134">Example</span></span>

<span data-ttu-id="dfe15-135">Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.</span><span class="sxs-lookup"><span data-stu-id="dfe15-135">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dfe15-136">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dfe15-136">Additional resources</span></span>

[<span data-ttu-id="dfe15-137">Funciones de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="dfe15-137">Data collection functions</span></span>](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]