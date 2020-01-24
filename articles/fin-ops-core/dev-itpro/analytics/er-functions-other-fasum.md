---
title: Función FA_SUM de ER
description: Este tema proporciona información general sobre cómo usar la función FA_SUM de informes electrónicos (ER).
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
ms.openlocfilehash: 32eb07689598a3b6c852f272b480106670b88cd0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916991"
---
# <span data-ttu-id="ec9ac-103"><a name="FA_SUM">Función FA_SUM de ER</a></span><span class="sxs-lookup"><span data-stu-id="ec9ac-103"><a name="FA_SUM">FA_SUM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ec9ac-104">La función `FA_SUM` devuelve un valor *Contenedor (registro)* que consiste en datos para las cantidades del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor y un período de fechas.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="ec9ac-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec9ac-105">Syntax</span></span>

```
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="ec9ac-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ec9ac-106">Arguments</span></span>

<span data-ttu-id="ec9ac-107">`fixed asset code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ec9ac-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="ec9ac-108">Un valor *Cadena* que representa el código de un elemento de activo fijo para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="ec9ac-109">`value model code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ec9ac-109">`value model code`: *String*</span></span>

<span data-ttu-id="ec9ac-110">Un valor *Cadena* que representa el código de un modelo de valor para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="ec9ac-111">`start date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="ec9ac-111">`start date`: *Date*</span></span>

<span data-ttu-id="ec9ac-112">Un valor *Fecha* que representa la fecha de inicio de un período para el que se calculan los importes de los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="ec9ac-113">`end date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="ec9ac-113">`end date`: *Date*</span></span>

<span data-ttu-id="ec9ac-114">Un valor *Fecha* que representa la fecha final de un período para el que se calculan los importes de los activos fijos.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="ec9ac-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ec9ac-115">Return values</span></span>

<span data-ttu-id="ec9ac-116">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="ec9ac-116">*Container (record)*</span></span>

<span data-ttu-id="ec9ac-117">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="ec9ac-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec9ac-118">Example</span></span>

<span data-ttu-id="ec9ac-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` devuelve el contenedor de datos para activos fijos **COMP-000001** que se ha preparado para el modelo de valor **Actual** y por un período desde **Fecha1** a **Fecha2**.</span><span class="sxs-lookup"><span data-stu-id="ec9ac-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ec9ac-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ec9ac-120">Additional resources</span></span>

[<span data-ttu-id="ec9ac-121">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="ec9ac-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
