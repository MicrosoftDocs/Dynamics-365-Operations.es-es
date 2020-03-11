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
ms.openlocfilehash: 45e95751e3adfe6aa208daaba774a349216e1f1f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042076"
---
# <span data-ttu-id="9abce-103"><a name="INDEX">Función INDEX de ER</a></span><span class="sxs-lookup"><span data-stu-id="9abce-103"><a name="INDEX">INDEX ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9abce-104">La función `INDEX` devuelve un valor *Contenedor (registro)* que se selecciona utilizando el índice numérico especificado en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="9abce-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="9abce-105">Si el índice está fuera del intervalo para los registros de la lista, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="9abce-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="9abce-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9abce-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="9abce-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9abce-107">Arguments</span></span>

<span data-ttu-id="9abce-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="9abce-108">`list`: *Record list*</span></span>

<span data-ttu-id="9abce-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="9abce-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="9abce-110">`index`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="9abce-110">`index`: *Integer*</span></span>

<span data-ttu-id="9abce-111">Un índice numérico que indica la posición del registro deseado en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="9abce-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="9abce-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9abce-112">Return values</span></span>

<span data-ttu-id="9abce-113">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="9abce-113">*Container (record)*</span></span>

<span data-ttu-id="9abce-114">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="9abce-114">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="9abce-115">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="9abce-115">Example 1</span></span>

<span data-ttu-id="9abce-116">Si especifica el origen de datos **DS** para el tipo *Campo calculado* y este contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `DS.Value` devuelve el valor de texto **"B"** para el segundo registro de esta lista de registros.</span><span class="sxs-lookup"><span data-stu-id="9abce-116">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="9abce-117">La expresión `INDEX (SPLIT ("A|B|C", "|"), 2).Value` también devuelve el valor del texto **"B"**.</span><span class="sxs-lookup"><span data-stu-id="9abce-117">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="9abce-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="9abce-118">Example 2</span></span>

<span data-ttu-id="9abce-119">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `INDEX (SPLIT ("A|B|C", "|"), 4).Value` lanza una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9abce-119">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9abce-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9abce-120">Additional resources</span></span>

[<span data-ttu-id="9abce-121">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="9abce-121">List functions</span></span>](er-functions-category-list.md)
