---
title: Función FA_BALANCE de ER
description: Este tema proporciona información general sobre cómo usar la función FA_BALANCE de informes electrónicos (ER).
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
ms.openlocfilehash: 76a087157ae53e2c571654ade7383d7bd7a005c3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041455"
---
# <span data-ttu-id="ca540-103"><a name="FA_BALANCE">Función FA_BALANCE de ER</a></span><span class="sxs-lookup"><span data-stu-id="ca540-103"><a name="FA_BALANCE">FA_BALANCE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ca540-104">La función `FA_BALANCE` devuelve un valor *Contenedor (registro)* que consiste en datos para el saldo del activo fijo para el elemento del activo fijo especificado, el código del modelo de valor, el año del informe y la fecha del informe.</span><span class="sxs-lookup"><span data-stu-id="ca540-104">The `FA_BALANCE` function returns a *Container (record)* value that consists of data for the fixed asset balance for the specified fixed asset item, value model code, reporting year, and reporting date.</span></span>

## <a name="syntax"></a><span data-ttu-id="ca540-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca540-105">Syntax</span></span>

```vb
FA_BALANCE (fixed asset code, value model code, reporting year, reporting date)
```

## <a name="arguments"></a><span data-ttu-id="ca540-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ca540-106">Arguments</span></span>

<span data-ttu-id="ca540-107">`fixed asset code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ca540-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="ca540-108">Un valor *Cadena* que representa el código de un elemento de activo fijo para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="ca540-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="ca540-109">`value model code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ca540-109">`value model code`: *String*</span></span>

<span data-ttu-id="ca540-110">Un valor *Cadena* que representa el código de un modelo de valor para el que se calcula el saldo.</span><span class="sxs-lookup"><span data-stu-id="ca540-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="ca540-111">`reporting year`: *Valor de enumeración*</span><span class="sxs-lookup"><span data-stu-id="ca540-111">`reporting year`: *Enumeration value*</span></span>

<span data-ttu-id="ca540-112">Un valor de enumeración de la enumeración de aplicaciones **AssetYear** que define un período para el cálculo del saldo.</span><span class="sxs-lookup"><span data-stu-id="ca540-112">An enumeration value of the **AssetYear** application enumeration that defines a period for the balance calculation.</span></span>

<span data-ttu-id="ca540-113">`reporting date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="ca540-113">`reporting date`: *Date*</span></span>

<span data-ttu-id="ca540-114">Un valor *Fecha* que define una fecha para el cálculo del saldo.</span><span class="sxs-lookup"><span data-stu-id="ca540-114">A *Date* value that defines a date for the balance calculation.</span></span>

## <a name="return-values"></a><span data-ttu-id="ca540-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ca540-115">Return values</span></span>

<span data-ttu-id="ca540-116">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="ca540-116">*Container (record)*</span></span>

<span data-ttu-id="ca540-117">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="ca540-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="ca540-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ca540-118">Example</span></span>

<span data-ttu-id="ca540-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` devuelve el contenedor preparado de los datos de los saldos del activo fijo **COMP-000001** que tiene el modelo de valor **Actual** en la fecha de la sesión actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ca540-119">`FA_ BALANCE ("COMP-000001", "Current", AxEnumAssetYear.ThisYear, SESSIONTODAY ())` returns the data container of balances for fixed asset **COMP-000001** that has been prepared for the **Current** value model on the current application session date.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca540-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ca540-120">Additional resources</span></span>

[<span data-ttu-id="ca540-121">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="ca540-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
