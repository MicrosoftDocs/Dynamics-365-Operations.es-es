---
title: Función GETENUMVALUEBYNAME de ER
description: Este tema proporciona información general sobre cómo usar la función GETENUMVALUEBYNAME de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 4ded0c62b4556b21e731cd9b98db2863ec6ec442
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916853"
---
# <span data-ttu-id="9d27c-103"><a name="GETENUMVALUEBYNAME">Función GETENUMVALUEBYNAME de ER</a></span><span class="sxs-lookup"><span data-stu-id="9d27c-103"><a name="GETENUMVALUEBYNAME">GETENUMVALUEBYNAME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d27c-104">La función `GETENUMVALUEBYNAME` busca un valor específico de tipo *Enum* en el origen de datos de enumeración especificado utilizando el nombre de enumeración especificado como un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="9d27c-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="9d27c-105">Si el valor *Enum* se encuentra, la función lo devuelve.</span><span class="sxs-lookup"><span data-stu-id="9d27c-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="9d27c-106">De lo contrario, la función devuelve el valor de enumeración **nulo**.</span><span class="sxs-lookup"><span data-stu-id="9d27c-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d27c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d27c-107">Syntax</span></span>

```
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="9d27c-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9d27c-108">Arguments</span></span>

<span data-ttu-id="9d27c-109">`enumeration data source path`: *Enumeración*</span><span class="sxs-lookup"><span data-stu-id="9d27c-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="9d27c-110">La ruta válida de un origen de datos de uno de los siguientes tipos de enumeración:</span><span class="sxs-lookup"><span data-stu-id="9d27c-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="9d27c-111">Enumeración de modelo de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="9d27c-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="9d27c-112">Enumeración de formato de ER</span><span class="sxs-lookup"><span data-stu-id="9d27c-112">ER format enumeration</span></span>
- <span data-ttu-id="9d27c-113">Enumeración de Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="9d27c-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="9d27c-114">`enumeration value text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9d27c-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="9d27c-115">Un valor de cadena que representa el nombre de un valor de enumeración único.</span><span class="sxs-lookup"><span data-stu-id="9d27c-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="9d27c-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9d27c-116">Return values</span></span>

<span data-ttu-id="9d27c-117">*Enum* anulable</span><span class="sxs-lookup"><span data-stu-id="9d27c-117">Nullable *Enum*</span></span>

<span data-ttu-id="9d27c-118">El valor de enumeración resultante.</span><span class="sxs-lookup"><span data-stu-id="9d27c-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9d27c-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9d27c-119">Usage notes</span></span>

<span data-ttu-id="9d27c-120">No se produce ninguna excepción si no se encuentra un valor de tipo *Enum* con el nombre del valor de enumeración especificado como un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="9d27c-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="9d27c-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d27c-121">Example</span></span>

<span data-ttu-id="9d27c-122">En la siguiente ilustración, la enumeración **ReportDirection** se introduce en un modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="9d27c-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="9d27c-123">Tenga en cuenta que se definen etiquetas para los valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="9d27c-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="9d27c-124">La siguiente ilustración muestra estos detalles:</span><span class="sxs-lookup"><span data-stu-id="9d27c-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="9d27c-125">El origen de datos **$Direction** se configura en un informe de ER.</span><span class="sxs-lookup"><span data-stu-id="9d27c-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="9d27c-126">Este origen de datos se configura en función de la enumeración del modelo **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="9d27c-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="9d27c-127">La expresión `$IsArrivals` está diseñada para usar el origen de datos **$Direction** basado en la enumeración del modelo como un parámetro de esta función.</span><span class="sxs-lookup"><span data-stu-id="9d27c-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="9d27c-128">El valor de esta expresión de comparación es **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="9d27c-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="9d27c-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9d27c-129">Additional resources</span></span>

[<span data-ttu-id="9d27c-130">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="9d27c-130">Text functions</span></span>](er-functions-category-text.md)
