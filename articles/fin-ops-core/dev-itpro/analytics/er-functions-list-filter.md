---
title: Función FILTER de ER
description: Este tema proporciona información general sobre cómo usar la función FILTER de informes electrónicos (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: aa8c0b4601db625d442dd545151968f38bd58cf1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746612"
---
# <a name="filter-er-function"></a><span data-ttu-id="75586-103">Función FILTER de ER</span><span class="sxs-lookup"><span data-stu-id="75586-103">FILTER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75586-104">La función `FILTER` devuelve la lista especificada como un valor *Lista de registros* después de que se haya cambiado la consulta para que filtre por la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="75586-104">The `FILTER` function returns the specified list as a *Record list* value after the query has been changed so that it filters for the specified condition.</span></span>

## <a name="syntax"></a><span data-ttu-id="75586-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75586-105">Syntax</span></span>

```vb
FILTER (list, condition)
```

## <a name="arguments"></a><span data-ttu-id="75586-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="75586-106">Arguments</span></span>

<span data-ttu-id="75586-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="75586-107">`list`: *Record list*</span></span>

<span data-ttu-id="75586-108">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="75586-108">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="75586-109">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="75586-109">`condition`: *Boolean*</span></span>

<span data-ttu-id="75586-110">Una expresión condicional válida que se utiliza para filtrar registros de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="75586-110">A valid conditional expression that is used to filter records of the specified list.</span></span>

## <a name="return-values"></a><span data-ttu-id="75586-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="75586-111">Return values</span></span>

<span data-ttu-id="75586-112">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="75586-112">*Record list*</span></span>

<span data-ttu-id="75586-113">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="75586-113">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="75586-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="75586-114">Usage notes</span></span>

<span data-ttu-id="75586-115">Esta función difiere de la función [DONDE](er-functions-list-where.md), ya que la condición especificada se aplica a cualquier origen de datos de Informes electrónicos (ER) del tipo *Registros de la tabla* a nivel de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="75586-115">This function differs from the [WHERE](er-functions-list-where.md) function, because the specified condition is applied to any Electronic reporting (ER) data source of the *Table records* type at the database level.</span></span> <span data-ttu-id="75586-116">La lista y la condición se pueden definir mediante tablas y relaciones.</span><span class="sxs-lookup"><span data-stu-id="75586-116">The list and condition can be defined by using tables and relations.</span></span>

<span data-ttu-id="75586-117">Si uno o ambos argumentos configurados para esta función (`list` y `condition`) no permite que esta solicitud se traduzca para la llamada directa de SQL, se produce una excepción en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="75586-117">If one or both arguments that are configured for this function (`list` and `condition`) don't allow this request to be translated to the direct SQL call, an exception is thrown at design time.</span></span> <span data-ttu-id="75586-118">Esta excepción informa al usuario que `list` o `condition` no se pueden usar para consultar la base de datos.</span><span class="sxs-lookup"><span data-stu-id="75586-118">This exception informs the user that either `list` or `condition` can't be used to query the database.</span></span>

## <a name="example-1"></a><span data-ttu-id="75586-119">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="75586-119">Example 1</span></span>

<span data-ttu-id="75586-120">Si **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `FILTER (Vendors, Vendors.VendGroup = "40")` devuelve una lista solo de proveedores que pertenece al grupo de proveedores 40.</span><span class="sxs-lookup"><span data-stu-id="75586-120">If **Vendor** is configured as an ER data source that refers to the VendTable table, the expression `FILTER (Vendors, Vendors.VendGroup = "40")` returns a list of only vendors that belong to vendor group 40.</span></span>

## <a name="example-2"></a><span data-ttu-id="75586-121">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="75586-121">Example 2</span></span>

<span data-ttu-id="75586-122">Si **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, y **si parmVendorBankGroup** que está configurado como un origen de datos de ER que devuelve un valor del tipo de datos *Cadena*, la expresión `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` devuelve una lista solo de cuentas de proveedores que pertenecen a un grupo bancario específico.</span><span class="sxs-lookup"><span data-stu-id="75586-122">If **Vendor** is configured as an ER data source that refers to the VendTable table, and if **parmVendorBankGroup** is configured as an ER data source that returns a value of the *String* data type, the expression `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` returns a list of only vendor accounts that belong to a specific bank group.</span></span>

## <a name="example-3"></a><span data-ttu-id="75586-123">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="75586-123">Example 3</span></span>

<span data-ttu-id="75586-124">Especifica un origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("A,B,C", ",")`.</span><span class="sxs-lookup"><span data-stu-id="75586-124">You enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("A,B,C", ",")`.</span></span> <span data-ttu-id="75586-125">Luego especifica otra expresión, `FILTER( DS, DS.Value = "B")`.</span><span class="sxs-lookup"><span data-stu-id="75586-125">You then enter another expression, `FILTER( DS, DS.Value = "B")`.</span></span> <span data-ttu-id="75586-126">Cuando intenta guardar esta expresión en el diseñador de fórmulas de ER, se produce la siguiente excepción: "Error de validación: la expresión de lista de la función FILTER no es consultable".</span><span class="sxs-lookup"><span data-stu-id="75586-126">When you try to save this expression in the ER formula designer, the following exception is thrown: "Validation error: The list expression of FILTER function is not queryable."</span></span>

## <a name="additional-resources"></a><span data-ttu-id="75586-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="75586-127">Additional resources</span></span>

[<span data-ttu-id="75586-128">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="75586-128">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]