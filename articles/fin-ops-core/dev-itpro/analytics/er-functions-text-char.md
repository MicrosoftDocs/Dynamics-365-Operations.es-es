---
title: Función CHAR de ER
description: Este tema proporciona información general sobre cómo usar la función CHAR de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a9f0f70c250592bf74b1a1df823e66803e853a64
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683000"
---
# <a name="char-er-function"></a><span data-ttu-id="1ff25-103">Función CHAR de ER</span><span class="sxs-lookup"><span data-stu-id="1ff25-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ff25-104">La función `CHAR` devuelve un valor de tipo *Cadena* que presenta un solo carácter al que hace referencia el código numérico de Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="1ff25-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="1ff25-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ff25-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="1ff25-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1ff25-106">Arguments</span></span>

<span data-ttu-id="1ff25-107">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="1ff25-107">`number`: *Integer*</span></span>

<span data-ttu-id="1ff25-108">Un número que corresponde a un único carácter.</span><span class="sxs-lookup"><span data-stu-id="1ff25-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="1ff25-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1ff25-109">Return values</span></span>

<span data-ttu-id="1ff25-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="1ff25-110">*String*</span></span>

<span data-ttu-id="1ff25-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="1ff25-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1ff25-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="1ff25-112">Usage notes</span></span>

<span data-ttu-id="1ff25-113">La cadena que esta función devuelve depende de la codificación seleccionada en el elemento de formato **ARCHIVO** principal.</span><span class="sxs-lookup"><span data-stu-id="1ff25-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="1ff25-114">Para ver una de lista de codificaciones admitidas, consulte [Clase de codificación](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="1ff25-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="1ff25-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ff25-115">Example</span></span>

<span data-ttu-id="1ff25-116">`CHAR (255)` devuelve **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="1ff25-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1ff25-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1ff25-117">Additional resources</span></span>

[<span data-ttu-id="1ff25-118">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="1ff25-118">Text functions</span></span>](er-functions-category-text.md)
