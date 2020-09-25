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
ms.openlocfilehash: 33ccf358dc5355cd00d5ff41ebd8148a334cba38
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743864"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="c4695-103">Función GETENUMVALUEBYNAME de ER</span><span class="sxs-lookup"><span data-stu-id="c4695-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4695-104">La función `GETENUMVALUEBYNAME` busca un valor específico de tipo *Enum* en el origen de datos de enumeración especificado utilizando el nombre de enumeración especificado como un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="c4695-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="c4695-105">Si el valor *Enum* se encuentra, la función lo devuelve.</span><span class="sxs-lookup"><span data-stu-id="c4695-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="c4695-106">De lo contrario, la función devuelve el valor de enumeración **nulo**.</span><span class="sxs-lookup"><span data-stu-id="c4695-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c4695-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c4695-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="c4695-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c4695-108">Arguments</span></span>

<span data-ttu-id="c4695-109">`enumeration data source path`: *Enumeración*</span><span class="sxs-lookup"><span data-stu-id="c4695-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="c4695-110">La ruta válida de un origen de datos de uno de los siguientes tipos de enumeración:</span><span class="sxs-lookup"><span data-stu-id="c4695-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="c4695-111">Enumeración de modelo de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="c4695-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="c4695-112">Enumeración de formato de ER</span><span class="sxs-lookup"><span data-stu-id="c4695-112">ER format enumeration</span></span>
- <span data-ttu-id="c4695-113">Enumeración de Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="c4695-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="c4695-114">`enumeration value text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c4695-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="c4695-115">Un valor de cadena que representa el nombre de un valor de enumeración único.</span><span class="sxs-lookup"><span data-stu-id="c4695-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="c4695-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c4695-116">Return values</span></span>

<span data-ttu-id="c4695-117">*Enum* anulable</span><span class="sxs-lookup"><span data-stu-id="c4695-117">Nullable *Enum*</span></span>

<span data-ttu-id="c4695-118">El valor de enumeración resultante.</span><span class="sxs-lookup"><span data-stu-id="c4695-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c4695-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="c4695-119">Usage notes</span></span>

<span data-ttu-id="c4695-120">No se produce ninguna excepción si no se encuentra un valor de tipo *Enum* con el nombre del valor de enumeración especificado como un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="c4695-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example"></a><span data-ttu-id="c4695-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4695-121">Example</span></span>

<span data-ttu-id="c4695-122">En la siguiente ilustración, la enumeración **ReportDirection** se introduce en un modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="c4695-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="c4695-123">Tenga en cuenta que se definen etiquetas para los valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="c4695-123">Notice that labels are defined for the enumeration values.</span></span>

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="c4695-124">La siguiente ilustración muestra estos detalles:</span><span class="sxs-lookup"><span data-stu-id="c4695-124">The following illustration shows these details:</span></span>

- <span data-ttu-id="c4695-125">El origen de datos **$Direction** se configura en un informe de ER.</span><span class="sxs-lookup"><span data-stu-id="c4695-125">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="c4695-126">Este origen de datos se configura en función de la enumeración del modelo **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="c4695-126">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="c4695-127">La expresión `$IsArrivals` está diseñada para usar el origen de datos **$Direction** basado en la enumeración del modelo como un parámetro de esta función.</span><span class="sxs-lookup"><span data-stu-id="c4695-127">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="c4695-128">El valor de esta expresión de comparación es **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="c4695-128">The value of this comparison expression is **TRUE**.</span></span>

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a><span data-ttu-id="c4695-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c4695-129">Additional resources</span></span>

[<span data-ttu-id="c4695-130">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="c4695-130">Text functions</span></span>](er-functions-category-text.md)
