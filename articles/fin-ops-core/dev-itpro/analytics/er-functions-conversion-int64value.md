---
title: Función INT64VALUE ER
description: Este tema proporciona información general sobre cómo usar la función INT64VALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 89a26e867579bcb34a9bae33fa0b98e1ecfe9995
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755405"
---
# <a name="int64value-er-function"></a><span data-ttu-id="2910a-103">Función INT64VALUE ER</span><span class="sxs-lookup"><span data-stu-id="2910a-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2910a-104">La función `INT64VALUE` devuelve un valor *Int64* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="2910a-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="2910a-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="2910a-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="2910a-106">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="2910a-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="2910a-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2910a-107">Arguments</span></span>

<span data-ttu-id="2910a-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="2910a-108">`text`: *String*</span></span>

<span data-ttu-id="2910a-109">Un valor de texto que debe convertirse en un número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="2910a-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="2910a-110">`number`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="2910a-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="2910a-111">Un valor numérico *Real* o *Entero* que debe convertirse en un número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="2910a-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="2910a-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="2910a-112">Return values</span></span>

<span data-ttu-id="2910a-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="2910a-113">*Int64*</span></span>

<span data-ttu-id="2910a-114">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="2910a-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2910a-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="2910a-115">Usage notes</span></span>

<span data-ttu-id="2910a-116">Se trunca cualquier posición decimal.</span><span class="sxs-lookup"><span data-stu-id="2910a-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="2910a-117">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="2910a-117">Example 1</span></span>

<span data-ttu-id="2910a-118">`INT64VALUE ("22565422744")` devuelve el valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="2910a-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="2910a-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="2910a-119">Example 2</span></span>

<span data-ttu-id="2910a-120">`INT64VALUE ( VALUE("22565422744.77"))` devuelve el valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="2910a-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2910a-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2910a-121">Additional resources</span></span>

[<span data-ttu-id="2910a-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="2910a-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]