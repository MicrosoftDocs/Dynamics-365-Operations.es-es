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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2ee153c1dde99810a78ed15c7505fa705088797
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745450"
---
# <a name="today-er-function"></a><span data-ttu-id="c60ef-103">Función TODAY ER</span><span class="sxs-lookup"><span data-stu-id="c60ef-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c60ef-104">La función `TODAY` devuelve un valor *Fecha* que representa la fecha actual del servidor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c60ef-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="c60ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c60ef-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="c60ef-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c60ef-106">Return values</span></span>

<span data-ttu-id="c60ef-107">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="c60ef-107">*Date*</span></span>

<span data-ttu-id="c60ef-108">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="c60ef-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="c60ef-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c60ef-109">Example</span></span>

<span data-ttu-id="c60ef-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` devuelve la fecha del servidor actual, 24 de diciembre de 2015, como la cadena **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="c60ef-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c60ef-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c60ef-111">Additional resources</span></span>

[<span data-ttu-id="c60ef-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="c60ef-112">Date and time functions</span></span>](er-functions-category-datetime.md)
