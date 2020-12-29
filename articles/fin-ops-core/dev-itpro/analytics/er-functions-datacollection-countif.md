---
title: Función COUNTIF ER
description: Este tema proporciona información general sobre cómo usar la función COUNTIF de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 3f1429ad98f9d4fdab992c2011c6518734484a84
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681193"
---
# <a name="countif-er-function"></a><span data-ttu-id="5ddbd-103">Función COUNTIF ER</span><span class="sxs-lookup"><span data-stu-id="5ddbd-103">COUNTIF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ddbd-104">La función `COUNTIF` devuelve un valor *Entero* que representa el número de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-104">The `COUNTIF` function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="5ddbd-105">La condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-105">The condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ddbd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ddbd-106">Syntax</span></span>

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a><span data-ttu-id="5ddbd-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5ddbd-107">Arguments</span></span>

<span data-ttu-id="5ddbd-108">`condition range`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="5ddbd-108">`condition range`: *String*</span></span>

<span data-ttu-id="5ddbd-109">Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** de un componente de formato de informe electrónico (ER).</span><span class="sxs-lookup"><span data-stu-id="5ddbd-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span>

<span data-ttu-id="5ddbd-110">`condition value`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="5ddbd-110">`condition value`: *String*</span></span>

<span data-ttu-id="5ddbd-111">Un valor que devuelve la expresión que se ha configurado en la propiedad **Valor de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-111">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span>

## <a name="return-values"></a><span data-ttu-id="5ddbd-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5ddbd-112">Return values</span></span>

<span data-ttu-id="5ddbd-113">*Entero*</span><span class="sxs-lookup"><span data-stu-id="5ddbd-113">*Integer*</span></span>

<span data-ttu-id="5ddbd-114">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5ddbd-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5ddbd-115">Usage notes</span></span>

<span data-ttu-id="5ddbd-116">Las propiedades **Nombre de clave de datos recopilados** y **Valor de clave de datos recopilados** se pueden configurar para el componente **Secuencia** o el componente **Elemento XML** de un formato ER que reside bajo el componente **Común \\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-116">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="5ddbd-117">Esta función devuelve un valor **0** (cero) cuando la opción **Recopilar detalles de salida** del componente actual **Común \\Archivo** está desactivado.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-117">This function returns a **0** (zero) value when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="5ddbd-118">En el argumento `condition range`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-118">In the `condition range` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="5ddbd-119">En el argumento `condition value`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-119">In the `condition value` argument, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="5ddbd-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5ddbd-120">Example</span></span>

<span data-ttu-id="5ddbd-121">Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.</span><span class="sxs-lookup"><span data-stu-id="5ddbd-121">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ddbd-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5ddbd-122">Additional resources</span></span>

[<span data-ttu-id="5ddbd-123">Funciones de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="5ddbd-123">Data collection functions</span></span>](er-functions-category-data-collection.md)
