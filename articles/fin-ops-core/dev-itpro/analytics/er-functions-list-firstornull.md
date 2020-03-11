---
title: Función FIRSTORNULL de ER
description: En este tema se explica cómo usar la función FIRSTORNULL de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042122"
---
# <span data-ttu-id="47720-103"><a name="FIRSTORNULL">Función FIRSTORNULL de ER</a></span><span class="sxs-lookup"><span data-stu-id="47720-103"><a name="FIRSTORNULL">FIRSTORNULL ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="47720-104">La función `FIRSTORNULL` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si ese registro no está vacío.</span><span class="sxs-lookup"><span data-stu-id="47720-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="47720-105">Si el registro está vacío, esta función devuelve un valor nulo *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="47720-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="47720-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47720-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="47720-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="47720-107">Arguments</span></span>

<span data-ttu-id="47720-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="47720-108">`list`: *Record list*</span></span>

<span data-ttu-id="47720-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="47720-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="47720-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="47720-110">Return values</span></span>

<span data-ttu-id="47720-111">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="47720-111">*Container (record)*</span></span>

<span data-ttu-id="47720-112">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="47720-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="47720-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47720-113">Example</span></span>

<span data-ttu-id="47720-114">La expresión `FIRSTORNULL(SPLIT("",1)).Value` devuelve una cadena vacía (**""**).</span><span class="sxs-lookup"><span data-stu-id="47720-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="47720-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="47720-115">Additional resources</span></span>

[<span data-ttu-id="47720-116">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="47720-116">List functions</span></span>](er-functions-category-list.md)
