---
title: Función TABLENAME2ID de ER
description: Este tema proporciona información general sobre cómo usar la función TABLENAME2ID de informes electrónicos (ER).
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
ms.openlocfilehash: d9f9e38f46df8a93b5cb16b8d0d5e5afbff8558a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744008"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="09a05-103">Función TABLENAME2ID de ER</span><span class="sxs-lookup"><span data-stu-id="09a05-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="09a05-104">La función `TABLENAME2ID` devuelve una representación numérica del id. de tabla para el nombre de tabla especificado como un valor de tipo *Entero*.</span><span class="sxs-lookup"><span data-stu-id="09a05-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="09a05-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09a05-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="09a05-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="09a05-106">Arguments</span></span>

<span data-ttu-id="09a05-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="09a05-107">`text`: *String*</span></span>

<span data-ttu-id="09a05-108">Un valor de texto que representa un nombre de tabla válido.</span><span class="sxs-lookup"><span data-stu-id="09a05-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="09a05-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="09a05-109">Return values</span></span>

<span data-ttu-id="09a05-110">*Entero*</span><span class="sxs-lookup"><span data-stu-id="09a05-110">*Integer*</span></span>

<span data-ttu-id="09a05-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="09a05-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="09a05-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="09a05-112">Usage notes</span></span>

<span data-ttu-id="09a05-113">La ejecución de esta función puede tener diferentes resultados en diferentes instancias de Microsoft Dynamics 365 Finance, aunque se utilice el mismo nombre de empresa.</span><span class="sxs-lookup"><span data-stu-id="09a05-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="09a05-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="09a05-114">Example</span></span>

<span data-ttu-id="09a05-115">`TABLENAME2ID ("Intrastat")` devuelve **1510**.</span><span class="sxs-lookup"><span data-stu-id="09a05-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="09a05-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="09a05-116">Additional resources</span></span>

[<span data-ttu-id="09a05-117">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="09a05-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
