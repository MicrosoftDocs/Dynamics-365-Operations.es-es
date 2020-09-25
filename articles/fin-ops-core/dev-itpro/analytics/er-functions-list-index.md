---
title: Función INDEX de ER
description: Este tema proporciona información general sobre cómo usar la función INDEX de informes electrónicos (ER).
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
ms.openlocfilehash: 051e22daa3fe2d6c328e36403201d940f724bd29
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745190"
---
# <a name="index-er-function"></a><span data-ttu-id="88ec8-103">Función INDEX de ER</span><span class="sxs-lookup"><span data-stu-id="88ec8-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88ec8-104">La función `INDEX` devuelve un valor *Contenedor (registro)* que se selecciona utilizando el índice numérico especificado en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="88ec8-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="88ec8-105">Si el índice está fuera del intervalo para los registros de la lista, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="88ec8-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="88ec8-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="88ec8-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="88ec8-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="88ec8-107">Arguments</span></span>

<span data-ttu-id="88ec8-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="88ec8-108">`list`: *Record list*</span></span>

<span data-ttu-id="88ec8-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="88ec8-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="88ec8-110">`index`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="88ec8-110">`index`: *Integer*</span></span>

<span data-ttu-id="88ec8-111">Un índice numérico que indica la posición del registro deseado en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="88ec8-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="88ec8-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="88ec8-112">Return values</span></span>

<span data-ttu-id="88ec8-113">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="88ec8-113">*Container (record)*</span></span>

<span data-ttu-id="88ec8-114">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="88ec8-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="88ec8-115">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="88ec8-115">Example 1</span></span>

<span data-ttu-id="88ec8-116">Si especifica el origen de datos **DS** para el tipo *Campo calculado* y este contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `DS.Value` devuelve el valor de texto **"B"** para el segundo registro de esta lista de registros.</span><span class="sxs-lookup"><span data-stu-id="88ec8-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="88ec8-117">La expresión `INDEX (SPLIT ("A|B|C", "|"), 2).Value` también devuelve el valor del texto **"B"**.</span><span class="sxs-lookup"><span data-stu-id="88ec8-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="88ec8-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="88ec8-118">Example 2</span></span>

<span data-ttu-id="88ec8-119">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `INDEX (SPLIT ("A|B|C", "|"), 4).Value` lanza una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="88ec8-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88ec8-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="88ec8-120">Additional resources</span></span>

[<span data-ttu-id="88ec8-121">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="88ec8-121">List functions</span></span>](er-functions-category-list.md)
