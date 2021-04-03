---
title: Función FIRSTORNULL de ER
description: En este tema se explica cómo usar la función FIRSTORNULL de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 53284333507ef1264d3eb66b0c7141eb69f32392
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564634"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="5799d-103">Función FIRSTORNULL de ER</span><span class="sxs-lookup"><span data-stu-id="5799d-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5799d-104">La función `FIRSTORNULL` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si ese registro no está vacío.</span><span class="sxs-lookup"><span data-stu-id="5799d-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="5799d-105">Si el registro está vacío, esta función devuelve un valor nulo *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="5799d-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5799d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5799d-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="5799d-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5799d-107">Arguments</span></span>

<span data-ttu-id="5799d-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="5799d-108">`list`: *Record list*</span></span>

<span data-ttu-id="5799d-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="5799d-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="5799d-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5799d-110">Return values</span></span>

<span data-ttu-id="5799d-111">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="5799d-111">*Container (record)*</span></span>

<span data-ttu-id="5799d-112">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="5799d-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="5799d-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5799d-113">Example</span></span>

<span data-ttu-id="5799d-114">La expresión `FIRSTORNULL(SPLIT("",1)).Value` devuelve una cadena vacía (**""**).</span><span class="sxs-lookup"><span data-stu-id="5799d-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5799d-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5799d-115">Additional resources</span></span>

[<span data-ttu-id="5799d-116">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="5799d-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]