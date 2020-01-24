---
title: Función LIST de ER
description: Este tema proporciona información general sobre cómo usar la función LIST de informes electrónicos (ER).
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
ms.openlocfilehash: 6848fe535a6a588eaf06f96e93f28db9ef304940
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917290"
---
# <span data-ttu-id="49273-103"><a name="LIST">Función LIST de ER</a></span><span class="sxs-lookup"><span data-stu-id="49273-103"><a name="LIST">LIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49273-104">La función `LIST` devuelve un valor *Lista de registros* nuevo que consiste en una lista de registros nueva creada a partir de los argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="49273-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="49273-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="49273-105">Syntax</span></span>

```
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="49273-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="49273-106">Arguments</span></span>

<span data-ttu-id="49273-107">`record 1`: *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="49273-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="49273-108">Una referencia a un origen de datos de tipo de datos *Registro*.</span><span class="sxs-lookup"><span data-stu-id="49273-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="49273-109">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="49273-109">This argument is required.</span></span>

<span data-ttu-id="49273-110">`record N`: *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="49273-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="49273-111">Una referencia a un origen de datos de tipo de datos *Registro*.</span><span class="sxs-lookup"><span data-stu-id="49273-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="49273-112">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="49273-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="49273-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="49273-113">Return values</span></span>

<span data-ttu-id="49273-114">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="49273-114">*Record list*</span></span>

<span data-ttu-id="49273-115">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="49273-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="49273-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="49273-116">Usage notes</span></span>

<span data-ttu-id="49273-117">La estructura de la lista que se crea contiene solo los campos que se presentan en la estructura de cada registro que se menciona en los argumentos.</span><span class="sxs-lookup"><span data-stu-id="49273-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="49273-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="49273-118">Example</span></span>

<span data-ttu-id="49273-119">Especifica el origen de datos **Registro 1** del tipo *Contenedor*.</span><span class="sxs-lookup"><span data-stu-id="49273-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="49273-120">Esta fuente de datos contiene los siguientes campos anidados del *Campo calculado*:</span><span class="sxs-lookup"><span data-stu-id="49273-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="49273-121">**Código:** este campo contiene una expresión que devuelve un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="49273-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="49273-122">**Importe:** este campo contiene una expresión que devuelve un valor de tipo *Real*.</span><span class="sxs-lookup"><span data-stu-id="49273-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="49273-123">Después, especifica el origen de datos **Registro 2** del tipo *Contenedor*.</span><span class="sxs-lookup"><span data-stu-id="49273-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="49273-124">Esta fuente de datos contiene los siguientes campos anidados del *Campo calculado*:</span><span class="sxs-lookup"><span data-stu-id="49273-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="49273-125">**Importe:** este campo contiene una expresión que devuelve un valor de tipo *Real*.</span><span class="sxs-lookup"><span data-stu-id="49273-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="49273-126">**IsValid:** este campo contiene una expresión que devuelve un valor de tipo *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="49273-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="49273-127">En este caso, la expresión `LIST('Record 1', 'Record 2')` devuelve una nueva lista que contiene dos registros.</span><span class="sxs-lookup"><span data-stu-id="49273-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="49273-128">La estructura de esta lista consta de un solo campo **Importe** del tipo *Real*, porque este campo es el único campo que se presenta en cada argumento de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="49273-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="49273-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="49273-129">Additional resources</span></span>

[<span data-ttu-id="49273-130">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="49273-130">List functions</span></span>](er-functions-category-list.md)