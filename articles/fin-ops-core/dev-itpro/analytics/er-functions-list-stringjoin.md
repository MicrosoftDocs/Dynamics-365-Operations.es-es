---
title: Función STRINGJOIN de ER
description: En este tema se proporciona información sobre cómo usar la función STRINGJOIN de informes electrónicos (ER).
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
ms.openlocfilehash: 10a98e98d913b0b4fe36690f7effd5d8d9a3faf4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041800"
---
# <span data-ttu-id="d2b1c-103"><a name="STRINGJOIN">Función STRINGJOIN de ER</a></span><span class="sxs-lookup"><span data-stu-id="d2b1c-103"><a name="STRINGJOIN">STRINGJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d2b1c-104">La función `STRINGJOIN` devuelve una valor *Cadena* que consta de valores concatenados del campo especificado de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="d2b1c-105">Los valores pueden estar separados por el delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="d2b1c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2b1c-106">Syntax</span></span>

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="d2b1c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d2b1c-107">Arguments</span></span>

<span data-ttu-id="d2b1c-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="d2b1c-108">`list`: *Record list*</span></span>

<span data-ttu-id="d2b1c-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="d2b1c-110">`field`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="d2b1c-110">`field`: *Field*</span></span>

<span data-ttu-id="d2b1c-111">La ruta válida de un campo del tipo de datos *Cadena* en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="d2b1c-112">`delimiter`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d2b1c-112">`delimiter`: *String*</span></span>

<span data-ttu-id="d2b1c-113">Un delimitador que se utiliza para separar subcadenas.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="d2b1c-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d2b1c-114">Return values</span></span>

<span data-ttu-id="d2b1c-115">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="d2b1c-115">*String*</span></span>

<span data-ttu-id="d2b1c-116">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d2b1c-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d2b1c-117">Example</span></span>

<span data-ttu-id="d2b1c-118">Si introduce `SPLIT("abc" , 1)` como fuente de datos **DS**, la expresión `STRINGJOIN (DS, DS.Value, "-")` devuelve **"a-b-c"**.</span><span class="sxs-lookup"><span data-stu-id="d2b1c-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d2b1c-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d2b1c-119">Additional resources</span></span>

[<span data-ttu-id="d2b1c-120">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="d2b1c-120">List functions</span></span>](er-functions-category-list.md)
