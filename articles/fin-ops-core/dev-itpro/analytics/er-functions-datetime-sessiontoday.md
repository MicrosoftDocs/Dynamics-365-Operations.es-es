---
title: Función SESSIONTODAY ER
description: En este tema se proporciona información sobre cómo usar la función SESSIONTODAY de informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 6d0fcbbf1a1fb0809e3f76161314f38bcd8a74aa
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746781"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="da94a-103">Función SESSIONTODAY ER</span><span class="sxs-lookup"><span data-stu-id="da94a-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="da94a-104">La función `SESSIONTODAY` devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da94a-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="da94a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da94a-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="da94a-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="da94a-106">Return values</span></span>

<span data-ttu-id="da94a-107">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="da94a-107">*Date*</span></span>

<span data-ttu-id="da94a-108">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="da94a-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="da94a-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da94a-109">Example</span></span>

<span data-ttu-id="da94a-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="da94a-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="da94a-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="da94a-111">Additional resources</span></span>

[<span data-ttu-id="da94a-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="da94a-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]