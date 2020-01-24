---
title: Lista de funciones ER en la categoría de recopilación de datos
description: Este tema proporciona información sobre las funciones de recopilación de datos que son compatibles con los informes electrónicos (ER).
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
ms.openlocfilehash: b318945c9cd10b237843d26cfdc46fc08e84e268
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917819"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a><span data-ttu-id="9d633-103">Lista de funciones ER en la categoría de recopilación de datos</span><span class="sxs-lookup"><span data-stu-id="9d633-103">List of ER functions in the data collection category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d633-104">Las funciones de recopilación de datos de informes electrónicos (ER) se utilizan para contar y sumar en un formato ER que se está ejecutando, en función de los datos de la salida que ya se ha generado en formato **Texto** o **Xml**.</span><span class="sxs-lookup"><span data-stu-id="9d633-104">Electronic reporting (ER) data collection functions are used to do counting and summing in an ER format that is being run, based on data of the output that has already been generated in **Text** or **Xml** format.</span></span> <span data-ttu-id="9d633-105">Este enfoque se utiliza para ayudar a mejorar el rendimiento de un formato ER que se ejecuta, para ingresar valores de totales acumulados en documentos generados y para otros fines.</span><span class="sxs-lookup"><span data-stu-id="9d633-105">This approach is used to help improve performance of an ER format that is run, to enter values of running totals in generated documents, and for other purposes.</span></span> <span data-ttu-id="9d633-106">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="9d633-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="9d633-107">Lista de funciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="9d633-107">List of supported functions</span></span>

| <span data-ttu-id="9d633-108">Función</span><span class="sxs-lookup"><span data-stu-id="9d633-108">Function</span></span> | <span data-ttu-id="9d633-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d633-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="9d633-110">CollectedList</span><span class="sxs-lookup"><span data-stu-id="9d633-110">CollectedList</span></span>](er-functions-datacollection-collectedlist.md) | <span data-ttu-id="9d633-111">Esta función devuelve un valor *Lista de registros* que contiene la lista de valores que fueron devueltos por la propiedad **Valor de clave de datos recopilados** de elementos de formato y recopilada cuando los elementos de formato se utilizaron para generar un documento saliente durante la ejecución del formato, y eso satisface las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="9d633-111">This function returns a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="9d633-112">Cada condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="9d633-112">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="9d633-113">CountIF</span><span class="sxs-lookup"><span data-stu-id="9d633-113">CountIF</span></span>](er-functions-datacollection-countif.md) | <span data-ttu-id="9d633-114">Esta función devuelve un valor *Entero* que representa el número de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="9d633-114">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="9d633-115">La condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="9d633-115">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="9d633-116">CountIFs</span><span class="sxs-lookup"><span data-stu-id="9d633-116">CountIFs</span></span>](er-functions-datacollection-countifs.md) | <span data-ttu-id="9d633-117">Esta función devuelve un valor *Entero* que representa el número de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="9d633-117">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="9d633-118">Cada condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="9d633-118">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="9d633-119">FormatElementName</span><span class="sxs-lookup"><span data-stu-id="9d633-119">FormatElementName</span></span>](er-functions-datacollection-formatelementname.md) | <span data-ttu-id="9d633-120">Esta función devuelve un valor *Cadena* que representa el nombre del elemento del formato ER actual.</span><span class="sxs-lookup"><span data-stu-id="9d633-120">This function returns a *String* value that represents the name of the current ER format's element.</span></span> |
| [<span data-ttu-id="9d633-121">SumIF</span><span class="sxs-lookup"><span data-stu-id="9d633-121">SumIF</span></span>](er-functions-datacollection-sumif.md) | <span data-ttu-id="9d633-122">Esta función devuelve un valor *Real* que representa la suma de valores que fueron devueltos por las vinculaciones de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="9d633-122">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="9d633-123">La condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="9d633-123">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="9d633-124">SumIFs</span><span class="sxs-lookup"><span data-stu-id="9d633-124">SumIFs</span></span>](er-functions-datacollection-sumifs.md) | <span data-ttu-id="9d633-125">Esta función devuelve un valor *Real* que representa la suma de valores que fueron devueltos por las vinculaciones de elementos de formato que se recopiló cuando los elementos de formato se usaron para generar un documento saliente durante la ejecución del formato y que cumple las condiciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="9d633-125">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="9d633-126">Cada condición consta de un rango clave y un valor clave.</span><span class="sxs-lookup"><span data-stu-id="9d633-126">Each condition consists of a key range and a key value.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="9d633-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9d633-127">Additional resources</span></span>

[<span data-ttu-id="9d633-128">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="9d633-128">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="9d633-129">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="9d633-129">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="9d633-130">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="9d633-130">Electronic reporting formula language</span></span>](er-formula-language.md)
