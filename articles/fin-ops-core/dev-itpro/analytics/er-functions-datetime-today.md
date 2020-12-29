---
title: Función TODAY ER
description: Este tema proporciona información general sobre cómo usar la función TODAY de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a93a9171456fb69e16c8104b0afb9ad485311b1a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683804"
---
# <a name="today-er-function"></a><span data-ttu-id="5b6fe-103">Función TODAY ER</span><span class="sxs-lookup"><span data-stu-id="5b6fe-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5b6fe-104">La función `TODAY` devuelve un valor *Fecha* que representa la fecha actual del servidor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b6fe-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b6fe-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5b6fe-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="5b6fe-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5b6fe-106">Return values</span></span>

<span data-ttu-id="5b6fe-107">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="5b6fe-107">*Date*</span></span>

<span data-ttu-id="5b6fe-108">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="5b6fe-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="5b6fe-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5b6fe-109">Example</span></span>

<span data-ttu-id="5b6fe-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` devuelve la fecha del servidor actual, 24 de diciembre de 2015, como la cadena **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="5b6fe-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b6fe-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5b6fe-111">Additional resources</span></span>

[<span data-ttu-id="5b6fe-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="5b6fe-112">Date and time functions</span></span>](er-functions-category-datetime.md)
