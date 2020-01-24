---
title: Función NOW ER
description: Este tema proporciona información general sobre cómo usar la función NOW de informes electrónicos (ER).
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
ms.openlocfilehash: cffb23afa4cb347d2840b099b0b49a71150d87d8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917566"
---
# <span data-ttu-id="ecd1b-103"><a name="NOW">Función NOW ER</a></span><span class="sxs-lookup"><span data-stu-id="ecd1b-103"><a name="NOW">NOW ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ecd1b-104">La función `NOW` devuelve un valor *Fecha y hora* que representa la fecha y hora actuales del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ecd1b-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="ecd1b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecd1b-105">Syntax</span></span>

```
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="ecd1b-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ecd1b-106">Return values</span></span>

<span data-ttu-id="ecd1b-107">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="ecd1b-107">*DateTime*</span></span>

<span data-ttu-id="ecd1b-108">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="ecd1b-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="ecd1b-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ecd1b-109">Example</span></span>

<span data-ttu-id="ecd1b-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` devuelve la fecha/hora del servidor actual, 24 de diciembre de 2015, como **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="ecd1b-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ecd1b-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ecd1b-111">Additional resources</span></span>

[<span data-ttu-id="ecd1b-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="ecd1b-112">Date and time functions</span></span>](er-functions-category-datetime.md)