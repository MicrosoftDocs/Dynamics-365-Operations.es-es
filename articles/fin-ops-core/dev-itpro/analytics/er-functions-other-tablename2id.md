---
title: Función TABLENAME2ID de ER
description: Este tema proporciona información general sobre cómo usar la función TABLENAME2ID de informes electrónicos (ER).
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
ms.openlocfilehash: 0f94d00d9d40830d895e906ffbaa2a236f1efc43
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746564"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="a99d8-103">Función TABLENAME2ID de ER</span><span class="sxs-lookup"><span data-stu-id="a99d8-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a99d8-104">La función `TABLENAME2ID` devuelve una representación numérica del id. de tabla para el nombre de tabla especificado como un valor de tipo *Entero*.</span><span class="sxs-lookup"><span data-stu-id="a99d8-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="a99d8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a99d8-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="a99d8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a99d8-106">Arguments</span></span>

<span data-ttu-id="a99d8-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="a99d8-107">`text`: *String*</span></span>

<span data-ttu-id="a99d8-108">Un valor de texto que representa un nombre de tabla válido.</span><span class="sxs-lookup"><span data-stu-id="a99d8-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="a99d8-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a99d8-109">Return values</span></span>

<span data-ttu-id="a99d8-110">*Entero*</span><span class="sxs-lookup"><span data-stu-id="a99d8-110">*Integer*</span></span>

<span data-ttu-id="a99d8-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="a99d8-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a99d8-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a99d8-112">Usage notes</span></span>

<span data-ttu-id="a99d8-113">La ejecución de esta función puede tener diferentes resultados en diferentes instancias de Microsoft Dynamics 365 Finance, aunque se utilice el mismo nombre de empresa.</span><span class="sxs-lookup"><span data-stu-id="a99d8-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="a99d8-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a99d8-114">Example</span></span>

<span data-ttu-id="a99d8-115">`TABLENAME2ID ("Intrastat")` devuelve **1510**.</span><span class="sxs-lookup"><span data-stu-id="a99d8-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a99d8-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a99d8-116">Additional resources</span></span>

[<span data-ttu-id="a99d8-117">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="a99d8-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]