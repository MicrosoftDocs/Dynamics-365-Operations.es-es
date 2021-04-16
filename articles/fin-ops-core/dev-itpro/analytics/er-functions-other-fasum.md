---
title: Función FA_SUM de ER
description: Este tema proporciona información general sobre cómo usar la función FA_SUM de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: d6f380e384e591e7417cfa40c73f9be6575fb0f6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744304"
---
# <a name="fa_sum-er-function"></a><span data-ttu-id="2c912-103">Función FA_SUM de ER</span><span class="sxs-lookup"><span data-stu-id="2c912-103">FA_SUM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c912-104">La función `FA_SUM` devuelve un valor *Contenedor (registro)* que consiste en datos para las cantidades del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor y un período de fechas.</span><span class="sxs-lookup"><span data-stu-id="2c912-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="2c912-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c912-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="2c912-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2c912-106">Arguments</span></span>

<span data-ttu-id="2c912-107">`fixed asset code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="2c912-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="2c912-108">Un valor *Cadena* que representa el código de un elemento de activo fijo para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="2c912-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="2c912-109">`value model code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="2c912-109">`value model code`: *String*</span></span>

<span data-ttu-id="2c912-110">Un valor *Cadena* que representa el código de un modelo de valor para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="2c912-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="2c912-111">`start date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="2c912-111">`start date`: *Date*</span></span>

<span data-ttu-id="2c912-112">Un valor *Fecha* que representa la fecha de inicio de un período para el que se calculan los importes de los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="2c912-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="2c912-113">`end date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="2c912-113">`end date`: *Date*</span></span>

<span data-ttu-id="2c912-114">Un valor *Fecha* que representa la fecha final de un período para el que se calculan los importes de los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="2c912-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="2c912-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="2c912-115">Return values</span></span>

<span data-ttu-id="2c912-116">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="2c912-116">*Container (record)*</span></span>

<span data-ttu-id="2c912-117">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="2c912-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="2c912-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2c912-118">Example</span></span>

<span data-ttu-id="2c912-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` devuelve el contenedor de datos para activos fijos **COMP-000001** que se ha preparado para el modelo de valor **Actual** y por un período desde **Fecha1** a **Fecha2**.</span><span class="sxs-lookup"><span data-stu-id="2c912-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c912-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2c912-120">Additional resources</span></span>

[<span data-ttu-id="2c912-121">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="2c912-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]