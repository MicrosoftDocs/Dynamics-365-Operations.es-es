---
title: Función SESSIONNOW ER
description: En este tema se proporciona información sobre cómo usar la función SESSIONNOW de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 5489fab61791654c2e583fc11b27aba09fb90c86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042306"
---
# <span data-ttu-id="1621f-103"><a name="">Función SESSIONNOW ER</a></span><span class="sxs-lookup"><span data-stu-id="1621f-103"><a name="">SESSIONNOW ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1621f-104">La función `SESSIONNOW` devuelve un valor *Fecha y hora* que representa la fecha y hora actuales de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1621f-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="1621f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1621f-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="1621f-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1621f-106">Return values</span></span>

<span data-ttu-id="1621f-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="1621f-107">*DateTime*</span></span>

<span data-ttu-id="1621f-108">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="1621f-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="1621f-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1621f-109">Example</span></span>

<span data-ttu-id="1621f-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` devuelve la fecha/hora de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24.12.2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="1621f-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1621f-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1621f-111">Additional resources</span></span>

[<span data-ttu-id="1621f-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="1621f-112">Date and time functions</span></span>](er-functions-category-datetime.md)
