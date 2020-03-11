---
title: Función DATETODATETIME ER
description: Este tema proporciona información general sobre cómo usar la función DATETODATETIME de informes electrónicos (ER).
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
ms.openlocfilehash: 961ccd18e70d4f9851027492366a7d9408a668c5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042421"
---
# <span data-ttu-id="b33c6-103"><a name="DATETODATETIME">Función DATETODATETIME ER</a></span><span class="sxs-lookup"><span data-stu-id="b33c6-103"><a name="DATETODATETIME">DATETODATETIME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b33c6-104">La función `DATETODATETIME` devuelve un valor *Fecha y hora* que se convierte de un determinado valor de datos a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="b33c6-104">The `DATETODATETIME` function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="b33c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b33c6-105">Syntax</span></span>

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a><span data-ttu-id="b33c6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b33c6-106">Arguments</span></span>

<span data-ttu-id="b33c6-107">`date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="b33c6-107">`date`: *Date*</span></span>

<span data-ttu-id="b33c6-108">Un valor de fecha / hora que representa la fecha a convertir.</span><span class="sxs-lookup"><span data-stu-id="b33c6-108">A date value that represents the date to convert.</span></span>

## <a name="return-values"></a><span data-ttu-id="b33c6-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b33c6-109">Return values</span></span>

<span data-ttu-id="b33c6-110">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="b33c6-110">*DateTime*</span></span>

<span data-ttu-id="b33c6-111">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="b33c6-111">The resulting date/time value.</span></span>

## <a name="example-1"></a><span data-ttu-id="b33c6-112">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="b33c6-112">Example 1</span></span>

<span data-ttu-id="b33c6-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` devuelve la fecha de la sesión actual de Microsoft Dynamics 365 Finance, 24 de diciembre de 2015, como **12/24 / 2015 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="b33c6-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` returns the date of the current Microsoft Dynamics 365 Finance session, December 24, 2015, as **12/24/2015 12:00:00 AM**.</span></span> <span data-ttu-id="b33c6-114">En este ejemplo, **CompInfo** es un origen de datos de informe electrónico (ER) del tipo **Finance and Operations/Tabla** y hace referencia a la tabla CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="b33c6-114">In this example, **CompInfo** is an Electronic reporting (ER) data source of the **Finance and Operations/Table** type, and it refers to the CompanyInfo table.</span></span>

## <a name="example-2"></a><span data-ttu-id="b33c6-115">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="b33c6-115">Example 2</span></span>

<span data-ttu-id="b33c6-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` devuelve el valor de fecha / hora **11/12 / 2019 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="b33c6-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returns the date/time value **11/12/2019 12:00:00 AM**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b33c6-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b33c6-117">Additional resources</span></span>

[<span data-ttu-id="b33c6-118">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="b33c6-118">Date and time functions</span></span>](er-functions-category-datetime.md)
