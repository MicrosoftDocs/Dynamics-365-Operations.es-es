---
title: Función LEN de ER
description: Este tema proporciona información general sobre cómo usar la función LEN de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: fce4b5311d84364310b76545a775f1cc8db2fd70
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569977"
---
# <a name="len-er-function"></a><span data-ttu-id="b402e-103">Función LEN de ER</span><span class="sxs-lookup"><span data-stu-id="b402e-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b402e-104">La función `LEN` devuelve un valor de tipo *Entero* que representa el número de caracteres de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="b402e-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="b402e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b402e-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="b402e-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b402e-106">Arguments</span></span>

<span data-ttu-id="b402e-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="b402e-107">`text`: *String*</span></span>

<span data-ttu-id="b402e-108">Valor de tipo *Cadena* que especifica el texto.</span><span class="sxs-lookup"><span data-stu-id="b402e-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="b402e-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b402e-109">Return values</span></span>

<span data-ttu-id="b402e-110">*Entero*</span><span class="sxs-lookup"><span data-stu-id="b402e-110">*Integer*</span></span>

<span data-ttu-id="b402e-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="b402e-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="b402e-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b402e-112">Example</span></span>

<span data-ttu-id="b402e-113">`LEN ("Sample")` devuelve **6**.</span><span class="sxs-lookup"><span data-stu-id="b402e-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b402e-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b402e-114">Additional resources</span></span>

[<span data-ttu-id="b402e-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="b402e-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]