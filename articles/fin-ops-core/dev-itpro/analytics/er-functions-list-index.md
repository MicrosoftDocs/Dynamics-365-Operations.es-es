---
title: Función INDEX de ER
description: Este tema proporciona información general sobre cómo usar la función INDEX de informes electrónicos (ER).
author: NickSelin
ms.date: 05/20/2021
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
ms.openlocfilehash: 5a0fdb8958670efe8e2a37cee183bf836fa6c7e8
ms.sourcegitcommit: 047b0503868cc7d7b21868e24405d76af35db747
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2021
ms.locfileid: "6087760"
---
# <a name="index-er-function"></a><span data-ttu-id="54479-103">Función INDEX de ER</span><span class="sxs-lookup"><span data-stu-id="54479-103">INDEX ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="54479-104">La función `INDEX` devuelve un valor *Contenedor (registro)* que se selecciona utilizando el índice numérico especificado en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="54479-104">The `INDEX` function returns a *Container (record)* value that is selected by using the specified numeric index in the specified list.</span></span> <span data-ttu-id="54479-105">Si el índice está fuera del intervalo para los registros de la lista, se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="54479-105">If the index is out of range for the records in the specified list, an exception is thrown.</span></span>

## <a name="syntax"></a><span data-ttu-id="54479-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54479-106">Syntax</span></span>

```vb
INDEX (list, index)
```

## <a name="arguments"></a><span data-ttu-id="54479-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="54479-107">Arguments</span></span>

<span data-ttu-id="54479-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="54479-108">`list`: *Record list*</span></span>

<span data-ttu-id="54479-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="54479-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="54479-110">`index`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="54479-110">`index`: *Integer*</span></span>

<span data-ttu-id="54479-111">Un índice numérico que indica la posición del registro deseado en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="54479-111">A numeric index that indicates the position of the desired record in the specified list.</span></span>

> [!NOTE]
> <span data-ttu-id="54479-112">Debido a que la numeración basada en uno se usa para esta función, especifique el valor **1** para devolver el primer registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="54479-112">Because one-based numbering is used for this function, specify the value **1** to return the first record of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="54479-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="54479-113">Return values</span></span>

<span data-ttu-id="54479-114">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="54479-114">*Container (record)*</span></span>

<span data-ttu-id="54479-115">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="54479-115">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="54479-116">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="54479-116">Example 1</span></span>

<span data-ttu-id="54479-117">Si especifica el origen de datos **DS** para el tipo *Campo calculado* y este contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `DS.Value` devuelve el valor de texto **"B"** para el segundo registro de esta lista de registros.</span><span class="sxs-lookup"><span data-stu-id="54479-117">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `DS.Value` returns the text value **"B"** for the second record of this record list.</span></span> <span data-ttu-id="54479-118">La expresión `INDEX (SPLIT ("A|B|C", "|"), 2).Value` también devuelve el valor del texto **"B"**.</span><span class="sxs-lookup"><span data-stu-id="54479-118">The expression `INDEX (SPLIT ("A|B|C", "|"), 2).Value` also returns the text value **"B"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="54479-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="54479-119">Example 2</span></span>

<span data-ttu-id="54479-120">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `INDEX (SPLIT ("A|B|C", "|"), 4).Value` lanza una excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="54479-120">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `INDEX (SPLIT ("A|B|C", "|"), 4).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="54479-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="54479-121">Additional resources</span></span>

[<span data-ttu-id="54479-122">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="54479-122">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
