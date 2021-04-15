---
title: Lista de funciones ER en la categoría de contenedor
description: Este tema proporciona información sobre las funciones de contenedor que son compatibles con los informes electrónicos (ER).
author: NickSelin
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 95f207538ea4f0f7df775bf28d0dcf6529d1a91c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753249"
---
# <a name="list-of-er-functions-in-the-container-category"></a><span data-ttu-id="d0f5f-103">Lista de funciones ER en la categoría de contenedor</span><span class="sxs-lookup"><span data-stu-id="d0f5f-103">List of ER functions in the container category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d0f5f-104">Las [funciones](er-formula-language.md#functions) de contenedor de [informes electrónicos (ER)](general-electronic-reporting.md) se pueden usar para llevar a cabo operaciones que utilizan orígenes de datos del tipo de datos *Contenedor*.</span><span class="sxs-lookup"><span data-stu-id="d0f5f-104">[Electronic reporting (ER)](general-electronic-reporting.md) container [functions](er-formula-language.md#functions) can be used to perform operations that involve data sources of the *Container* data type.</span></span> <span data-ttu-id="d0f5f-105">Estas operaciones ocurren cuando los datos de procesamiento representan una colección de datos binarios en formato de objeto grande binario (BLOB).</span><span class="sxs-lookup"><span data-stu-id="d0f5f-105">These operations occur when the processing data represents a collection of binary data in binary large object (BLOB) format.</span></span> <span data-ttu-id="d0f5f-106">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="d0f5f-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="d0f5f-107">Lista de funciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="d0f5f-107">List of supported functions</span></span>

| <span data-ttu-id="d0f5f-108">Función</span><span class="sxs-lookup"><span data-stu-id="d0f5f-108">Function</span></span> | <span data-ttu-id="d0f5f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0f5f-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="d0f5f-110">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="d0f5f-110">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="d0f5f-111">Esta función devuelve un valor de *Contenedor* que consta de contenido binario que se descodifica a partir de la cadena ASCII especificada que representa un grupo Base64 de esquemas de codificación de binario a texto.</span><span class="sxs-lookup"><span data-stu-id="d0f5f-111">This function returns a *Container* value that consists of binary content that is decoded from the specified ASCII string that represents a Base64 group of binary-to-text encoding schemes.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="d0f5f-112">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d0f5f-112">Additional resources</span></span>

[<span data-ttu-id="d0f5f-113">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="d0f5f-113">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="d0f5f-114">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="d0f5f-114">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="d0f5f-115">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="d0f5f-115">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]