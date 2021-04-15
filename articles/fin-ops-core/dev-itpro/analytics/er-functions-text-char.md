---
title: Función CHAR de ER
description: Este tema proporciona información general sobre cómo usar la función CHAR de informes electrónicos (ER).
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
ms.openlocfilehash: a621328817171be7df0622507c84f5c6f6fe90a1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746444"
---
# <a name="char-er-function"></a><span data-ttu-id="a92e8-103">Función CHAR de ER</span><span class="sxs-lookup"><span data-stu-id="a92e8-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a92e8-104">La función `CHAR` devuelve un valor de tipo *Cadena* que presenta un solo carácter al que hace referencia el código numérico de Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="a92e8-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="a92e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a92e8-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="a92e8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a92e8-106">Arguments</span></span>

<span data-ttu-id="a92e8-107">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="a92e8-107">`number`: *Integer*</span></span>

<span data-ttu-id="a92e8-108">Un número que corresponde a un único carácter.</span><span class="sxs-lookup"><span data-stu-id="a92e8-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="a92e8-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a92e8-109">Return values</span></span>

<span data-ttu-id="a92e8-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="a92e8-110">*String*</span></span>

<span data-ttu-id="a92e8-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="a92e8-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a92e8-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a92e8-112">Usage notes</span></span>

<span data-ttu-id="a92e8-113">La cadena que esta función devuelve depende de la codificación seleccionada en el elemento de formato **ARCHIVO** principal.</span><span class="sxs-lookup"><span data-stu-id="a92e8-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="a92e8-114">Para ver una de lista de codificaciones admitidas, consulte [Clase de codificación](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="a92e8-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="a92e8-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a92e8-115">Example</span></span>

<span data-ttu-id="a92e8-116">`CHAR (255)` devuelve **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="a92e8-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a92e8-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a92e8-117">Additional resources</span></span>

[<span data-ttu-id="a92e8-118">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="a92e8-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]