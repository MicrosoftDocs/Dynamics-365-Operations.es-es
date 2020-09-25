---
title: Función CONVERTCURRENCY de ER
description: En este tema se proporciona información sobre cómo usar la función CONVERTCURRENCY de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: ae6e0069c6e9227d4cf1045eeebbb825a2f943c3
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744320"
---
# <a name="convertcurrency-er-function"></a><span data-ttu-id="dc816-103">Función CONVERTCURRENCY de ER</span><span class="sxs-lookup"><span data-stu-id="dc816-103">CONVERTCURRENCY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc816-104">La función `CONVERTCURRENCY` devuelve un valor *Real* que representa el resultado de convertir el importe monetario especificado de la divisa de origen especificada a la divisa de destino especificada con la configuración de la empresa especificada en la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="dc816-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc816-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc816-105">Syntax</span></span>

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="dc816-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dc816-106">Arguments</span></span>

<span data-ttu-id="dc816-107">`amount`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="dc816-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="dc816-108">Un valor numérico que representa la cantidad monetaria que debe convertirse.</span><span class="sxs-lookup"><span data-stu-id="dc816-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="dc816-109">`source currency`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dc816-109">`source currency`: *String*</span></span>

<span data-ttu-id="dc816-110">El código de la divisa de origen.</span><span class="sxs-lookup"><span data-stu-id="dc816-110">The code of the source currency.</span></span>

<span data-ttu-id="dc816-111">`target currency`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dc816-111">`target currency`: *String*</span></span>

<span data-ttu-id="dc816-112">El código de divisa objetivo.</span><span class="sxs-lookup"><span data-stu-id="dc816-112">The code of the target currency.</span></span>

<span data-ttu-id="dc816-113">`date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="dc816-113">`date`: *Date*</span></span>

<span data-ttu-id="dc816-114">Un valor *Fecha* que representa la fecha que se utiliza para determinar el tipo de cambio para la conversión.</span><span class="sxs-lookup"><span data-stu-id="dc816-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="dc816-115">`company`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dc816-115">`company`: *String*</span></span>

<span data-ttu-id="dc816-116">Un valor *Cadena* que representa el código de una empresa que proporciona la configuración que se utiliza para la conversión.</span><span class="sxs-lookup"><span data-stu-id="dc816-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="dc816-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dc816-117">Return values</span></span>

<span data-ttu-id="dc816-118">*Real*</span><span class="sxs-lookup"><span data-stu-id="dc816-118">*Real*</span></span>

<span data-ttu-id="dc816-119">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="dc816-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="dc816-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc816-120">Example</span></span>

<span data-ttu-id="dc816-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` devuelve el equivalente de un euro en dólares estadounidenses en la fecha de la sesión actual, en función de la configuración para la empresa de **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="dc816-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dc816-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dc816-122">Additional resources</span></span>

[<span data-ttu-id="dc816-123">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="dc816-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
