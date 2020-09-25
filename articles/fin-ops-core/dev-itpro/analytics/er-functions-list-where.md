---
title: Función WHERE de ER
description: Este tema proporciona información general sobre cómo usar la función WHERE de informes electrónicos (ER).
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
ms.openlocfilehash: 94326986791c95eac7b0f5771f779014d865d3bb
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743451"
---
# <a name="where-er-function"></a><span data-ttu-id="ee15e-103">Función WHERE de ER</span><span class="sxs-lookup"><span data-stu-id="ee15e-103">WHERE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee15e-104">La función `WHERE` devuelve la lista especificada como un valor *Lista de registros* después de que se haya filtrado de acuerdo con la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="ee15e-104">The `WHERE` function returns the specified list as a *Record list* value after it has been filtered according to the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee15e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee15e-105">Syntax</span></span>

```vb
WHERE (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="ee15e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ee15e-106">Arguments</span></span>

<span data-ttu-id="ee15e-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ee15e-107">`list`: *Record list*</span></span>

<span data-ttu-id="ee15e-108">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="ee15e-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="ee15e-109">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="ee15e-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="ee15e-110">Una expresión condicional válida que se utiliza para filtrar registros de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="ee15e-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="ee15e-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ee15e-111">Return values</span></span>

<span data-ttu-id="ee15e-112">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ee15e-112">*Record list*</span></span>

<span data-ttu-id="ee15e-113">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="ee15e-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ee15e-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ee15e-114">Usage notes</span></span>

<span data-ttu-id="ee15e-115">Esta función difiere de la función [FILTER](er-functions-list-filter.md), ya que la condición especificada se aplica a cualquier origen de datos de Informes electrónicos (ER) del tipo *Lista de registros* que esté presente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="ee15e-115">This function differs from the [FILTER](er-functions-list-filter.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="ee15e-116">Si los argumentos configurados para esta función (`list` y `condition`) permiten que esta solicitud se traduzca para la llamada directa de SQL, aparecerá un mensaje de advertencia en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="ee15e-116">If the arguments that are configured for this function (`list` and `condition`) allow this request to be translated to the direct SQL call, a warning message is thrown at design time.</span></span> <span data-ttu-id="ee15e-117">Este mensaje informa al usuario que el rendimiento podría mejorar si la función [FILTER](er-functions-list-filter.md) se usa en lugar de `WHERE`.</span><span class="sxs-lookup"><span data-stu-id="ee15e-117">This message informs the user that performance might be improved if the [FILTER](er-functions-list-filter.md) function is used instead of `WHERE`.</span></span>

## <a name="example-1"></a><span data-ttu-id="ee15e-118">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ee15e-118">Example 1</span></span>

<span data-ttu-id="ee15e-119">Si **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `WHERE (Vendors, Vendors.VendGroup = "40")` devuelve una lista solo de proveedores que pertenece al grupo de proveedores 40.</span><span class="sxs-lookup"><span data-stu-id="ee15e-119">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `WHERE (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="ee15e-120">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="ee15e-120">Example 2</span></span>

<span data-ttu-id="ee15e-121">Si especifica el origen de datos **DS** para el tipo *Campo calculado* y este contiene la expresión `SPLIT ("A|B|C", "|")`, la expresión `WHERE( DS, DS.Value = "B")` devuelve una lista de solo un registro que contiene el texto **"B"** en el campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="ee15e-121">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A|B|C", "|")`, the expression `WHERE( DS, DS.Value = "B")` returns a list of only one record that contains the text **"B"** in the **Value** field.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee15e-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ee15e-122">Additional resources</span></span>

[<span data-ttu-id="ee15e-123">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="ee15e-123">List functions</span></span>](er-functions-category-list.md)
