---
title: Función FIRSTORNULL de ER
description: En este tema se explica cómo usar la función FIRSTORNULL de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: 1ccc094fc468470ffc857c729b6d8402796785d7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753225"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="f33d1-103">Función FIRSTORNULL de ER</span><span class="sxs-lookup"><span data-stu-id="f33d1-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f33d1-104">La función `FIRSTORNULL` devuelve el primer registro de la lista especificada como un valor *Contenedor (registro)*, si ese registro no está vacío.</span><span class="sxs-lookup"><span data-stu-id="f33d1-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="f33d1-105">Si el registro está vacío, esta función devuelve un valor nulo *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="f33d1-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="f33d1-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f33d1-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="f33d1-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f33d1-107">Arguments</span></span>

<span data-ttu-id="f33d1-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="f33d1-108">`list`: *Record list*</span></span>

<span data-ttu-id="f33d1-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="f33d1-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="f33d1-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f33d1-110">Return values</span></span>

<span data-ttu-id="f33d1-111">*Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="f33d1-111">*Container (record)*</span></span>

<span data-ttu-id="f33d1-112">El valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="f33d1-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="f33d1-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f33d1-113">Example</span></span>

<span data-ttu-id="f33d1-114">La expresión `FIRSTORNULL(SPLIT("",1)).Value` devuelve una cadena vacía (**""**).</span><span class="sxs-lookup"><span data-stu-id="f33d1-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f33d1-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f33d1-115">Additional resources</span></span>

[<span data-ttu-id="f33d1-116">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="f33d1-116">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]