---
title: Función IF de ER
description: Este tema proporciona información general sobre cómo usar la función IF de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: b29302ffe534f2439519e57c6a6b8c94c1df8d62
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917152"
---
# <span data-ttu-id="98a80-103"><a name="IF">Función IF de ER</a></span><span class="sxs-lookup"><span data-stu-id="98a80-103"><a name="IF">IF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="98a80-104">La función `IF` devuelve el primer valor especificado si se cumple la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="98a80-104">The `IF` function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="98a80-105">De lo contrario, devuelve el segundo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="98a80-105">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="98a80-106">El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos.</span><span class="sxs-lookup"><span data-stu-id="98a80-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="98a80-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98a80-107">Syntax</span></span>

```
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a><span data-ttu-id="98a80-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="98a80-108">Arguments</span></span>

<span data-ttu-id="98a80-109">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="98a80-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="98a80-110">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="98a80-110">A valid conditional expression that must be tested.</span></span>

<span data-ttu-id="98a80-111">`first value`: *Cualquiera de los tipos de datos admitidos*</span><span class="sxs-lookup"><span data-stu-id="98a80-111">`first value`: *Any of the supported data types*</span></span>

<span data-ttu-id="98a80-112">El resultado que se devuelve si se cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="98a80-112">The result that is returned if the condition is met.</span></span>

<span data-ttu-id="98a80-113">`second value`: *Cualquiera de los tipos de datos admitidos*</span><span class="sxs-lookup"><span data-stu-id="98a80-113">`second value`: *Any of the supported data types*</span></span>

<span data-ttu-id="98a80-114">El resultado que se devuelve si no se cumple la condición.</span><span class="sxs-lookup"><span data-stu-id="98a80-114">The result that is returned if the condition isn't met.</span></span>

## <a name="return-values"></a><span data-ttu-id="98a80-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="98a80-115">Return values</span></span>

<span data-ttu-id="98a80-116">*Cualquiera de los tipos de datos admitidos*</span><span class="sxs-lookup"><span data-stu-id="98a80-116">*Any of the supported data types*</span></span>

<span data-ttu-id="98a80-117">El valor resultante de cualquiera de los tipos de datos admitidos.</span><span class="sxs-lookup"><span data-stu-id="98a80-117">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="98a80-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="98a80-118">Usage notes</span></span>

<span data-ttu-id="98a80-119">Los argumentos `first value` y `second value` deben especificarse utilizando el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="98a80-119">The `first value` and `second value` arguments must be specified by using the same data type.</span></span> <span data-ttu-id="98a80-120">Se produce una excepción en tiempo de diseño si los tipos de datos de los valores configurados no coinciden.</span><span class="sxs-lookup"><span data-stu-id="98a80-120">An exception is thrown at design time if the data types of the configured values don't match.</span></span>

<span data-ttu-id="98a80-121">Si el primer valor y el segundo valor son valores del tipo de datos *Contenedor (registro)* o *Lista de registros*, el resultado solo tiene los campos que existen en ambos valores.</span><span class="sxs-lookup"><span data-stu-id="98a80-121">If the first value and the second value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="98a80-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98a80-122">Example</span></span>

<span data-ttu-id="98a80-123">`IF (1=2, "condition is met", "condition is not met")` devuelve la cadena **"no se cumple la condición"**.</span><span class="sxs-lookup"><span data-stu-id="98a80-123">`IF (1=2, "condition is met", "condition is not met")` returns the string **"condition is not met"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98a80-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="98a80-124">Additional resources</span></span>

[<span data-ttu-id="98a80-125">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="98a80-125">Logical functions</span></span>](er-functions-category-logical.md)
