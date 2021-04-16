---
title: Función FA_BALANCE de ER
description: Este tema proporciona información general sobre cómo usar la función FA_BALANCE de informes electrónicos (ER).
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
ms.openlocfilehash: ec78b9c5bf800503023315eb893076486b0a1fb0
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744328"
---
# <a name="fa_balance-er-function"></a><span data-ttu-id="ad8b9-103">Función FA_BALANCE de ER</span><span class="sxs-lookup"><span data-stu-id="ad8b9-103">FA_BALANCE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad8b9-104">La función `FA_BALANCE` devuelve un valor *Contenedor (registro)* que consiste en datos para el saldo del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor, el año del informe y la fecha del informe.</span><span class="sxs-lookup"><span data-stu-id="ad8b9-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="ad8b9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad8b9-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="ad8b9-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ad8b9-106">Arguments</span></span>

<span data-ttu-id="ad8b9-107">`fixed asset code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ad8b9-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="ad8b9-108">Un valor *Cadena* que representa el código de un elemento de activo fijo para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="ad8b9-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="ad8b9-109">`value model code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ad8b9-109">`value model code`: *String*</span></span>

<span data-ttu-id="ad8b9-110">Un valor *Cadena* que representa el código de un modelo de valor para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="ad8b9-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="ad8b9-111">`reporting year`: *Valor de enumeración*</span><span class="sxs-lookup"><span data-stu-id="ad8b9-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="ad8b9-112">Un valor de enumeración de la enumeración de aplicaciones **AssetYear** que define un período para el cálculo del saldo.</span><span class="sxs-lookup"><span data-stu-id="ad8b9-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="ad8b9-113">`reporting date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="ad8b9-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="ad8b9-114">Un valor *Fecha* que define una fecha para el cálculo del saldo.</span><span class="sxs-lookup"><span data-stu-id="ad8b9-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="ad8b9-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ad8b9-115">Return values</span></span>

<span data-ttu-id="ad8b9-116">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="ad8b9-116">*Container (record)*</span></span>

<span data-ttu-id="ad8b9-117">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="ad8b9-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="ad8b9-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad8b9-118">Example</span></span>

<span data-ttu-id="ad8b9-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` devuelve el contenedor preparado de los datos de los saldos del activo fijo **COMP-000001** que tiene el modelo de valor **Actual** en la fecha de la sesión actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ad8b9-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ad8b9-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ad8b9-120">Additional resources</span></span>

[<span data-ttu-id="ad8b9-121">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="ad8b9-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]