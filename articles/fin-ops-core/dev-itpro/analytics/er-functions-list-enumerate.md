---
title: Función ENUMERATE de ER
description: Este tema proporciona información general sobre cómo usar la función ENUMERATE de informes electrónicos (ER).
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
ms.openlocfilehash: d34904571ee6de8b36a0840a9470f16858489163
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042156"
---
# <span data-ttu-id="ee59c-103"><a name="ENUMERATE">Función de ENUMERATE de ER</a></span><span class="sxs-lookup"><span data-stu-id="ee59c-103"><a name="ENUMERATE">ENUMERATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee59c-104">La función `ENUMERATE` devuelve un valor *Lista de registros* nuevo que consiste en registros enumerados de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="ee59c-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee59c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee59c-105">Syntax</span></span>

```vb
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="ee59c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ee59c-106">Arguments</span></span>

<span data-ttu-id="ee59c-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ee59c-107">`list`: *Record list*</span></span>

<span data-ttu-id="ee59c-108">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="ee59c-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ee59c-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ee59c-109">Return values</span></span>

<span data-ttu-id="ee59c-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ee59c-110">*Record list*</span></span>

<span data-ttu-id="ee59c-111">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="ee59c-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ee59c-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ee59c-112">Usage notes</span></span>

<span data-ttu-id="ee59c-113">La lista de registros enumerados que se devuelve expone los siguientes elementos adicionales:</span><span class="sxs-lookup"><span data-stu-id="ee59c-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="ee59c-114">El registro de campos (componente **Valor**)</span><span class="sxs-lookup"><span data-stu-id="ee59c-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="ee59c-115">El índice de registros actual (componente **Número**)</span><span class="sxs-lookup"><span data-stu-id="ee59c-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="ee59c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ee59c-116">Example</span></span>

<span data-ttu-id="ee59c-117">En la ilustración siguiente, un origen de datos **Enumerado** se crea como una lista enumerada de registros de proveedor desde el origen de los datos **Proveedores** que hace referencia a la tabla VendTable.</span><span class="sxs-lookup"><span data-stu-id="ee59c-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="ee59c-118">La ilustración siguiente muestra el formato de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="ee59c-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="ee59c-119">En este formato, se crean vínculos de datos para generar una salida en formato XML.</span><span class="sxs-lookup"><span data-stu-id="ee59c-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="ee59c-120">Esta salida presenta proveedores individuales como nodos enumerados.</span><span class="sxs-lookup"><span data-stu-id="ee59c-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="ee59c-121">La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.</span><span class="sxs-lookup"><span data-stu-id="ee59c-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="ee59c-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ee59c-122">Additional resources</span></span>

[<span data-ttu-id="ee59c-123">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="ee59c-123">List functions</span></span>](er-functions-category-list.md)
