---
title: Función FIRST de ER
description: Este tema proporciona información general sobre cómo usar la función FIRST de informes electrónicos (ER).
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
ms.openlocfilehash: 3ed0e0aaf29e2a67a4842d71121f1adc24f524f7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745234"
---
# <a name="first-er-function"></a><span data-ttu-id="c802a-103">Función FIRST de ER</span><span class="sxs-lookup"><span data-stu-id="c802a-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c802a-104">La función `FIRST` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si esa lista no está vacía.</span><span class="sxs-lookup"><span data-stu-id="c802a-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="c802a-105">Si la lista está vacía, esta función genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="c802a-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="c802a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c802a-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="c802a-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c802a-107">Arguments</span></span>

<span data-ttu-id="c802a-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="c802a-108">`list`: *Record list*</span></span>

<span data-ttu-id="c802a-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="c802a-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c802a-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c802a-110">Return values</span></span>

<span data-ttu-id="c802a-111">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="c802a-111">*Container (record)*</span></span>

<span data-ttu-id="c802a-112">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="c802a-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="c802a-113">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="c802a-113">Example 1</span></span>

<span data-ttu-id="c802a-114">La expresión `FIRST(SPLIT("ABC",1)).Value` devuelve el valor del texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="c802a-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="c802a-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="c802a-115">Example 2</span></span>

<span data-ttu-id="c802a-116">La expresión `FIRST(SPLIT("",1)).Value` lanza una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c802a-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c802a-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c802a-117">Additional resources</span></span>

[<span data-ttu-id="c802a-118">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="c802a-118">List functions</span></span>](er-functions-category-list.md)
