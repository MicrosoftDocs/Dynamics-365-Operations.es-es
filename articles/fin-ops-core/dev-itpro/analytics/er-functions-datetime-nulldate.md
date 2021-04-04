---
title: Función ER NULLDATE
description: Este tema proporciona información general sobre cómo usar la función NULLDATE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 79d37247653aa297fdee2c770180916b9a9a5fc5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563471"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="4d64b-103">Función ER NULLDATE</span><span class="sxs-lookup"><span data-stu-id="4d64b-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4d64b-104">La función `NULLDATE` devuelve un valor *Fecha* que representa la fecha **nula** (1 de enero de 1900).</span><span class="sxs-lookup"><span data-stu-id="4d64b-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="4d64b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d64b-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="4d64b-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4d64b-106">Return values</span></span>

<span data-ttu-id="4d64b-107">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="4d64b-107">*Date*</span></span>

<span data-ttu-id="4d64b-108">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="4d64b-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="4d64b-109">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="4d64b-109">Example 1</span></span>

<span data-ttu-id="4d64b-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` devuelve la fecha **nulo**, 1 de enero de 1900, como **"1900-01-01"**, según el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="4d64b-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="4d64b-111">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="4d64b-111">Example 2</span></span>

<span data-ttu-id="4d64b-112">La expresión `IF( Invoice.DocumentDate = NULLDATE(), true, false)` devuelve **Cierto** cuando el valor del campo **Fecha del documento** es igual a la fecha **nulo**.</span><span class="sxs-lookup"><span data-stu-id="4d64b-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="4d64b-113">En este ejemplo, **Factura** es un origen de datos de informe electrónico (ER) del tipo **Registros Finance/Tabla** y hace referencia a la tabla CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="4d64b-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4d64b-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4d64b-114">Additional resources</span></span>

[<span data-ttu-id="4d64b-115">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="4d64b-115">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]