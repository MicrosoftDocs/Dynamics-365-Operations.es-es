---
title: Función LIST de ER
description: Este tema proporciona información general sobre cómo usar la función LIST de informes electrónicos (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 50cb8858301c030df07ad4af9fe2a9513f41fead
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750421"
---
# <a name="list-er-function"></a><span data-ttu-id="7db39-103">Función LIST de ER</span><span class="sxs-lookup"><span data-stu-id="7db39-103">LIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7db39-104">La función `LIST` devuelve un valor *Lista de registros* nuevo que consiste en una lista de registros nueva creada a partir de los argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="7db39-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="7db39-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7db39-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="7db39-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7db39-106">Arguments</span></span>

<span data-ttu-id="7db39-107">`record 1`: *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="7db39-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="7db39-108">Una referencia a un origen de datos de tipo de datos *Registro*.</span><span class="sxs-lookup"><span data-stu-id="7db39-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="7db39-109">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="7db39-109">This argument is required.</span></span>

<span data-ttu-id="7db39-110">`record N`: *Contenedor (registro)*</span><span class="sxs-lookup"><span data-stu-id="7db39-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="7db39-111">Una referencia a un origen de datos de tipo de datos *Registro*.</span><span class="sxs-lookup"><span data-stu-id="7db39-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="7db39-112">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="7db39-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="7db39-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7db39-113">Return values</span></span>

<span data-ttu-id="7db39-114">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="7db39-114">*Record list*</span></span>

<span data-ttu-id="7db39-115">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="7db39-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7db39-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="7db39-116">Usage notes</span></span>

<span data-ttu-id="7db39-117">La estructura de la lista que se crea contiene solo los campos que se presentan en la estructura de cada registro que se menciona en los argumentos.</span><span class="sxs-lookup"><span data-stu-id="7db39-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="7db39-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7db39-118">Example</span></span>

<span data-ttu-id="7db39-119">Especifica el origen de datos **Registro 1** del tipo *Contenedor*.</span><span class="sxs-lookup"><span data-stu-id="7db39-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="7db39-120">Esta fuente de datos contiene los siguientes campos anidados del *Campo calculado*:</span><span class="sxs-lookup"><span data-stu-id="7db39-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="7db39-121">**Código:** este campo contiene una expresión que devuelve un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="7db39-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="7db39-122">**Importe:** este campo contiene una expresión que devuelve un valor de tipo *Real*.</span><span class="sxs-lookup"><span data-stu-id="7db39-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="7db39-123">Después, especifica el origen de datos **Registro 2** del tipo *Contenedor*.</span><span class="sxs-lookup"><span data-stu-id="7db39-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="7db39-124">Esta fuente de datos contiene los siguientes campos anidados del *Campo calculado*:</span><span class="sxs-lookup"><span data-stu-id="7db39-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="7db39-125">**Importe:** este campo contiene una expresión que devuelve un valor de tipo *Real*.</span><span class="sxs-lookup"><span data-stu-id="7db39-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="7db39-126">**IsValid:** este campo contiene una expresión que devuelve un valor de tipo *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="7db39-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="7db39-127">En este caso, la expresión `LIST('Record 1', 'Record 2')` devuelve una nueva lista que contiene dos registros.</span><span class="sxs-lookup"><span data-stu-id="7db39-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="7db39-128">La estructura de esta lista consta de un solo campo **Importe** del tipo *Real*, porque este campo es el único campo que se presenta en cada argumento de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="7db39-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7db39-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7db39-129">Additional resources</span></span>

[<span data-ttu-id="7db39-130">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="7db39-130">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]