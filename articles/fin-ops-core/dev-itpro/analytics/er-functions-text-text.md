---
title: Función TEXT de ER
description: Este tema proporciona información general sobre cómo usar la función TEXT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: c26d0c4c8c6290bd2dbb10a288bbd59941a8d98e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915565"
---
# <span data-ttu-id="2e460-103"><a name="TEXT">Función TEXT de ER</a></span><span class="sxs-lookup"><span data-stu-id="2e460-103"><a name="TEXT">TEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e460-104">La función `TEXT` devuelve el número especificado como un valor de tipo *Cadena* después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2e460-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e460-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e460-105">Syntax</span></span>

```
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="2e460-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2e460-106">Arguments</span></span>

<span data-ttu-id="2e460-107">`number`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="2e460-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="2e460-108">Un valor numérico que debe convertirse en una cadena de texto.</span><span class="sxs-lookup"><span data-stu-id="2e460-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="2e460-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="2e460-109">Return values</span></span>

<span data-ttu-id="2e460-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="2e460-110">*String*</span></span>

<span data-ttu-id="2e460-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="2e460-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2e460-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="2e460-112">Usage notes</span></span>

<span data-ttu-id="2e460-113">Para los valores del tipo *Real*, la conversión de la cadena está limitada a dos posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="2e460-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="2e460-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e460-114">Example</span></span>

<span data-ttu-id="2e460-115">Si se define la configuración regional del servidor de la instancia de Microsoft Dynamics 365 Finance como **EN-US**, `TEXT (NOW ())` devuelve la fecha de la sesión de Finance actual, el 17 de diciembre de 2015, como la cadena de texto **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="2e460-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="2e460-116">`TEXT (1/3)` devuelve **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="2e460-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2e460-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2e460-117">Additional resources</span></span>

[<span data-ttu-id="2e460-118">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="2e460-118">Text functions</span></span>](er-functions-category-text.md)
