---
title: Función ER de COLLECTEDLIST
description: Este tema proporciona información general sobre cómo usar la función COLLECTEDLIST de informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a66ba364a7d06cd5ac03b57f07e2c5d4eb7a46d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042605"
---
# <span data-ttu-id="29e26-103"><a name="COLLECTEDLIST">Función ER de COLLECTEDLIST</a></span><span class="sxs-lookup"><span data-stu-id="29e26-103"><a name="COLLECTEDLIST">COLLECTEDLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="29e26-104">La función `COLLECTEDLIST` devuelve un valor *Lista de registros* que contiene la lista de valores que fueron devueltos por la propiedad **Valor de clave de datos recopilados** de elementos de formato y recopilada cuando los elementos de formato se utilizaron para generar documentos salientes durante la ejecución del formato y eso satisface las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="29e26-104">The `COLLECTEDLIST` function a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate outbound documents during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="29e26-105">Cada condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="29e26-105">Each condition consists of a key range and a key value.</span></span>

## <a name="syntax"></a><span data-ttu-id="29e26-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29e26-106">Syntax</span></span>

```vb
COLLECTEDLIST (condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a><span data-ttu-id="29e26-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="29e26-107">Arguments</span></span>

<span data-ttu-id="29e26-108">`condition 1 range`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="29e26-108">`condition 1 range`: *String*</span></span>

<span data-ttu-id="29e26-109">Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** de un componente de formato de informe electrónico (ER).</span><span class="sxs-lookup"><span data-stu-id="29e26-109">A value that is returned by the expression that has been configured in the **Collected data key name** property of an Electronic reporting (ER) format component.</span></span> <span data-ttu-id="29e26-110">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="29e26-110">This argument is mandatory.</span></span>

<span data-ttu-id="29e26-111">`condition 1 value`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="29e26-111">`condition 1 value`: *String*</span></span>

<span data-ttu-id="29e26-112">Un valor que devuelve la expresión que se ha configurado en la propiedad **Valor de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="29e26-112">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="29e26-113">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="29e26-113">This argument is mandatory.</span></span>

<span data-ttu-id="29e26-114">`condition N range`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="29e26-114">`condition N range`: *String*</span></span>

<span data-ttu-id="29e26-115">Un valor que devuelve la expresión que se ha configurado en la propiedad **Nombre de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="29e26-115">A value that is returned by the expression that has been configured in the **Collected data key name** property of an ER format component.</span></span> <span data-ttu-id="29e26-116">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="29e26-116">These additional arguments are optional.</span></span>

<span data-ttu-id="29e26-117">`condition N value`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="29e26-117">`condition N value`: *String*</span></span>

<span data-ttu-id="29e26-118">Un valor que devuelve la expresión que se ha configurado en la propiedad **Valor de clave de datos recopilados** de un componente de formato de ER.</span><span class="sxs-lookup"><span data-stu-id="29e26-118">A value that is returned by the expression that has been configured in the **Collected data key value** property of an ER format component.</span></span> <span data-ttu-id="29e26-119">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="29e26-119">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="29e26-120">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="29e26-120">Return values</span></span>

<span data-ttu-id="29e26-121">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="29e26-121">*Record list*</span></span>

<span data-ttu-id="29e26-122">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="29e26-122">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="29e26-123">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="29e26-123">Usage notes</span></span>

<span data-ttu-id="29e26-124">Las propiedades **Nombre de clave de datos recopilados** y **Valor de clave de datos recopilados** se pueden configurar para el componente **Secuencia** o el componente **Elemento XML** de un formato ER que reside bajo el componente **Común \\Archivo** donde la opción **Recopilar detalles de salida** está activada.</span><span class="sxs-lookup"><span data-stu-id="29e26-124">The **Collected data key name** and **Collected data key value** properties can be configured for either the **Sequence** component or the **XML Element** component of an ER format that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

<span data-ttu-id="29e26-125">Esta función devuelve una lista vacía cuando la opción **Recopilar detalles de salida** del componente actual **Común\\Archivo** está desactivado.</span><span class="sxs-lookup"><span data-stu-id="29e26-125">This function returns an empty list when the **Collect output details** option of the current **Common\\File** component is turned off.</span></span>

<span data-ttu-id="29e26-126">En los argumentos `condition range`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="29e26-126">In `condition range` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

<span data-ttu-id="29e26-127">En los argumentos `condition value`, el carácter comodín **"\*"** se puede usar para representar cualquier carácter múltiple.</span><span class="sxs-lookup"><span data-stu-id="29e26-127">In `condition value` arguments, the wildcard character **"\*"** can be used to represent any multiple characters.</span></span>

## <a name="example"></a><span data-ttu-id="29e26-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29e26-128">Example</span></span>

<span data-ttu-id="29e26-129">Para obtener más información sobre cómo usar esta función, consulte la guía de tareas de los [datos de uso de ER del formato generados para contar y calcular](tasks/er-format-counting-summing-1.md), que forma parte del proceso empresarial de **Adquirir/desarrollar los componentes de servicio/solución de IT**.</span><span class="sxs-lookup"><span data-stu-id="29e26-129">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="29e26-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="29e26-130">Additional resources</span></span>

[<span data-ttu-id="29e26-131">Funciones de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="29e26-131">Data collection functions</span></span>](er-functions-category-data-collection.md)
