---
title: Función de ER ENDSWITH
description: En este tema se proporciona información sobre cómo usar la función ENDSWITH de informes electrónicos (ER).
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: bdd2f364e2d0b80d3df20592ec827dcabf99a06c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745410"
---
# <a name="endswith-er-function"></a><span data-ttu-id="32058-103">Función de ER ENDSWITH</span><span class="sxs-lookup"><span data-stu-id="32058-103">ENDSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="32058-104">La función `ENDSWITH` determina si la entrada especificada termina con el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="32058-104">The `ENDSWITH` function determines whether the specified input ends with the specified text.</span></span> <span data-ttu-id="32058-105">Devuelve un valor *Booleano* **VERDADERO** si la entrada especificada termina con el texto especificado.</span><span class="sxs-lookup"><span data-stu-id="32058-105">It returns a *Boolean* value of **TRUE** if the specified input ends with the specified text.</span></span> <span data-ttu-id="32058-106">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="32058-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="32058-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="32058-107">Syntax</span></span>

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a><span data-ttu-id="32058-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="32058-108">Arguments</span></span>

<span data-ttu-id="32058-109">`input`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="32058-109">`input`: *String*</span></span>

<span data-ttu-id="32058-110">La ruta válida de un elemento de una fuente de datos del tipo *Cadena* o una constante de cadena, cuyo valor podría terminar con el segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="32058-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might end with the second argument.</span></span>

<span data-ttu-id="32058-111">`start text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="32058-111">`start text`: *String*</span></span>

<span data-ttu-id="32058-112">La ruta válida de un elemento de un origen de datos del tipo de datos *Cadena* o una constante de cadena, cuyo valor podría estar al final del segundo argumento.</span><span class="sxs-lookup"><span data-stu-id="32058-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the end of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="32058-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="32058-113">Return values</span></span>

<span data-ttu-id="32058-114">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="32058-114">*Boolean*</span></span>

<span data-ttu-id="32058-115">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="32058-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="32058-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="32058-116">Usage notes</span></span>

<span data-ttu-id="32058-117">Esta función se puede utilizar para especificar una expresión de condición de la función [FILTRAR](er-functions-list-filter.md) solo cuando la asignación relevante está configurada en [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acceder a [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="32058-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="32058-118">De lo contrario, se lanza una excepción en el momento de diseño.</span><span class="sxs-lookup"><span data-stu-id="32058-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="32058-119">El mensaje que recibe recomienda que utilice la función [DONDE](er-functions-list-where.md) en lugar de la función `FILTER`.</span><span class="sxs-lookup"><span data-stu-id="32058-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="32058-120">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="32058-120">Example 1</span></span>

<span data-ttu-id="32058-121">La expresion `ENDSWITH ("abc", "d")` devuelve **FALSO**, mientras que la expresión `ENDSWITH ("abc", "C")` devuelve **VERDADERO**.</span><span class="sxs-lookup"><span data-stu-id="32058-121">The expression `ENDSWITH ("abc", "d")` returns **FALSE**, whereas the expression `ENDSWITH ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="32058-122">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="32058-122">Example 2</span></span>

<span data-ttu-id="32058-123">La expresion `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` devuelve **VERDADERO** si el valor del campo **Dirección** del origen de datos **modelo** termina con la cadena **USA**.</span><span class="sxs-lookup"><span data-stu-id="32058-123">The expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returns **TRUE** if the value of the **Address** field of the **model** data source ends with the string **USA**.</span></span> <span data-ttu-id="32058-124">En caso contrario, devuelve **FALSO**.</span><span class="sxs-lookup"><span data-stu-id="32058-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="32058-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="32058-125">Additional resources</span></span>

[<span data-ttu-id="32058-126">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="32058-126">Logical functions</span></span>](er-functions-category-logical.md)
