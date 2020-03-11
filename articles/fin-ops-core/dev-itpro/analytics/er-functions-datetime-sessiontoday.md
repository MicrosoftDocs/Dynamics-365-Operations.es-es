---
title: Función SESSIONTODAY ER
description: En este tema se proporciona información sobre cómo usar la función SESSIONTODAY de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 483ff46a27068bc2d70c80a848f0329861c914b3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042283"
---
# <span data-ttu-id="2039c-103"><a name="SESSIONTODAY">Función SESSIONTODAY ER</a></span><span class="sxs-lookup"><span data-stu-id="2039c-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2039c-104">La función `SESSIONTODAY` devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2039c-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="2039c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2039c-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="2039c-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="2039c-106">Return values</span></span>

<span data-ttu-id="2039c-107">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="2039c-107">*Date*</span></span>

<span data-ttu-id="2039c-108">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="2039c-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="2039c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2039c-109">Example</span></span>

<span data-ttu-id="2039c-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="2039c-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2039c-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2039c-111">Additional resources</span></span>

[<span data-ttu-id="2039c-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="2039c-112">Date and time functions</span></span>](er-functions-category-datetime.md)
