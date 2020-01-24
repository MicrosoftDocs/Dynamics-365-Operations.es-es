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
ms.openlocfilehash: 99d50313f8097d43b820ffc1c36eef0097e7ec55
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917198"
---
# <span data-ttu-id="6b670-103"><a name="STRINGJOIN">Función STRINGJOIN de ER</a></span><span class="sxs-lookup"><span data-stu-id="6b670-103"><a name="STRINGJOIN">STRINGJOIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b670-104">La función `STRINGJOIN` devuelve una valor *Cadena* que consta de valores concatenados del campo especificado de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="6b670-104">The `STRINGJOIN` function returns a *String* value that consists of concatenated values of the specified field from the specified list.</span></span> <span data-ttu-id="6b670-105">Los valores pueden estar separados por el delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="6b670-105">The values can be separated by the specified delimiter.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b670-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b670-106">Syntax</span></span>

```
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a><span data-ttu-id="6b670-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6b670-107">Arguments</span></span>

<span data-ttu-id="6b670-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="6b670-108">`list`: *Record list*</span></span>

<span data-ttu-id="6b670-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="6b670-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="6b670-110">`field`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="6b670-110">`field`: *Field*</span></span>

<span data-ttu-id="6b670-111">La ruta válida de un campo del tipo de datos *Cadena* en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="6b670-111">The valid path of a field of the *String* data type in the specified list.</span></span>

<span data-ttu-id="6b670-112">`delimiter`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="6b670-112">`delimiter`: *String*</span></span>

<span data-ttu-id="6b670-113">Un delimitador que se utiliza para separar subcadenas.</span><span class="sxs-lookup"><span data-stu-id="6b670-113">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="6b670-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="6b670-114">Return values</span></span>

<span data-ttu-id="6b670-115">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="6b670-115">*String*</span></span>

<span data-ttu-id="6b670-116">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="6b670-116">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6b670-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b670-117">Example</span></span>

<span data-ttu-id="6b670-118">Si introduce `SPLIT("abc" , 1)` como fuente de datos **DS**, la expresión `STRINGJOIN (DS, DS.Value, "-")` devuelve **"a-b-c"**.</span><span class="sxs-lookup"><span data-stu-id="6b670-118">If you enter `SPLIT("abc" , 1)` as data source **DS**, the expression `STRINGJOIN (DS, DS.Value, "-")` returns **"a-b-c"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b670-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6b670-119">Additional resources</span></span>

[<span data-ttu-id="6b670-120">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="6b670-120">List functions</span></span>](er-functions-category-list.md)
