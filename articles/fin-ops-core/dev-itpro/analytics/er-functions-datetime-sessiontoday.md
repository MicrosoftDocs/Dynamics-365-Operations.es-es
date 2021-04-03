---
title: Función SESSIONTODAY ER
description: En este tema se proporciona información sobre cómo usar la función SESSIONTODAY de informes electrónicos (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: e6ad28e642fcfae3cfa2692a4e41b99fae7fc9df
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561359"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="60ed3-103">Función SESSIONTODAY ER</span><span class="sxs-lookup"><span data-stu-id="60ed3-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="60ed3-104">La función `SESSIONTODAY` devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="60ed3-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="60ed3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="60ed3-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="60ed3-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="60ed3-106">Return values</span></span>

<span data-ttu-id="60ed3-107">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="60ed3-107">*Date*</span></span>

<span data-ttu-id="60ed3-108">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="60ed3-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="60ed3-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60ed3-109">Example</span></span>

<span data-ttu-id="60ed3-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="60ed3-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="60ed3-111">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="60ed3-111">Additional resources</span></span>

[<span data-ttu-id="60ed3-112">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="60ed3-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]