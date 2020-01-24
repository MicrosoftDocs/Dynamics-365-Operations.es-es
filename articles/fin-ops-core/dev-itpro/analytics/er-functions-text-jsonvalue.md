---
title: Función JSONVALUE de ER
description: Este tema proporciona información general sobre cómo usar la función JSONVALUE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: d8209f8ce9d244ab7c82f897e4f59283e94e0522
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915680"
---
# <span data-ttu-id="0b21e-103"><a name="JSONVALUE">Función JSONVALUE de ER</a></span><span class="sxs-lookup"><span data-stu-id="0b21e-103"><a name="JSONVALUE">JSONVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b21e-104">La función `JSONVALUE` analiza los datos en formato JavaScript Object Notation (JSON) a los que se accede por la ruta especificada y extrae un valor escalar que se basa en el id. especificado.</span><span class="sxs-lookup"><span data-stu-id="0b21e-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="0b21e-105">Luego devuelve el valor escalar extraído como valor *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="0b21e-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b21e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b21e-106">Syntax</span></span>

```
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="0b21e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0b21e-107">Arguments</span></span>

<span data-ttu-id="0b21e-108">`input`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="0b21e-108">`input`: *String*</span></span>

<span data-ttu-id="0b21e-109">La ruta válida de un origen de datos de tipo *Cadena* que contiene datos JSON.</span><span class="sxs-lookup"><span data-stu-id="0b21e-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="0b21e-110">`path`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="0b21e-110">`path`: *String*</span></span>

<span data-ttu-id="0b21e-111">El identificador de un valor escalar de datos JSON.</span><span class="sxs-lookup"><span data-stu-id="0b21e-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="0b21e-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0b21e-112">Return values</span></span>

<span data-ttu-id="0b21e-113">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="0b21e-113">*String*</span></span>

<span data-ttu-id="0b21e-114">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="0b21e-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="0b21e-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0b21e-115">Example</span></span>

<span data-ttu-id="0b21e-116">El origen de datos **JsonField** contiene los siguientes datos en formato JSON: **{BuildNumber:7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="0b21e-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="0b21e-117">En este caso, la expresión `JSONVALUE (JsonField, "BuildNumber")` devuelve el siguiente valor de tipo *Cadena*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="0b21e-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0b21e-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0b21e-118">Additional resources</span></span>

[<span data-ttu-id="0b21e-119">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="0b21e-119">Text functions</span></span>](er-functions-category-text.md)
