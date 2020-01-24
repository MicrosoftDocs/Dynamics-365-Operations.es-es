---
title: Función REVERSE de ER
description: Este tema proporciona información general sobre cómo usar la función REVERSE de informes electrónicos (ER).
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
ms.openlocfilehash: 3343ad788cef29a79f9b110bf29809cd5f0e5c63
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917244"
---
# <span data-ttu-id="a5ee0-103"><a name="REVERSE">Función REVERSE de ER</a></span><span class="sxs-lookup"><span data-stu-id="a5ee0-103"><a name="REVERSE">REVERSE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5ee0-104">La función `REVERSE` devuelve la lista especificada como un valor *Lista de registros* en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="a5ee0-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5ee0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a5ee0-105">Syntax</span></span>

```
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="a5ee0-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a5ee0-106">Arguments</span></span>

<span data-ttu-id="a5ee0-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a5ee0-107">`list`: *Record list*</span></span>

<span data-ttu-id="a5ee0-108">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="a5ee0-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a5ee0-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a5ee0-109">Return values</span></span>

<span data-ttu-id="a5ee0-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a5ee0-110">*Record list*</span></span>

<span data-ttu-id="a5ee0-111">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="a5ee0-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="a5ee0-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a5ee0-112">Example 1</span></span>

<span data-ttu-id="a5ee0-113">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("C|B|A", "|")`, la expresión `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` devuelve el valor de texto **"C"**.</span><span class="sxs-lookup"><span data-stu-id="a5ee0-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a5ee0-114">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a5ee0-114">Example 2</span></span>

<span data-ttu-id="a5ee0-115">Cuando **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` devuelva la lista de proveedores que se clasifica por nombre en orden descendente.</span><span class="sxs-lookup"><span data-stu-id="a5ee0-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5ee0-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a5ee0-116">Additional resources</span></span>

[<span data-ttu-id="a5ee0-117">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="a5ee0-117">List functions</span></span>](er-functions-category-list.md)
