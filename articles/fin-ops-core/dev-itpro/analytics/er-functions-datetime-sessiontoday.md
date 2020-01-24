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
ms.openlocfilehash: bcfb36d6e3fb8475546f7cfb420c4aca848ac896
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917474"
---
# <span data-ttu-id="ede14-103"><a name="SESSIONTODAY">Función SESSIONTODAY ER</a></span><span class="sxs-lookup"><span data-stu-id="ede14-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ede14-104">La función `SESSIONTODAY` devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ede14-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="ede14-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ede14-105">Syntax</span></span>

```
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="ede14-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ede14-106">Return values</span></span>

<span data-ttu-id="ede14-107">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="ede14-107">*Date*</span></span>

<span data-ttu-id="ede14-108">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="ede14-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="ede14-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ede14-109">Example</span></span>

<span data-ttu-id="ede14-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="ede14-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ede14-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ede14-111">Additional resources</span></span>

[<span data-ttu-id="ede14-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="ede14-112">Date and time functions</span></span>](er-functions-category-datetime.md)
