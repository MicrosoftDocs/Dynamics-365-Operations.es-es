---
title: Función NUMSEQVALUE ER
description: En este tema se proporciona información sobre cómo usar la función NUMSEQVALUE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: d68784524a5639d8d447daa2cda940680d795542
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915841"
---
# <span data-ttu-id="8e32b-103"><a name="NUMSEQVALUE">Función NUMSEQVALUE de ER</a></span><span class="sxs-lookup"><span data-stu-id="8e32b-103"><a name="NUMSEQVALUE">NUMSEQVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e32b-104">La función `NUMSEQVALUE` devuelve un valor de tipo *Cadena* que representa el nuevo valor generado de una secuencia numérica, basado en la secuencia numérica especificada, el ámbito y el id. de ámbito.</span><span class="sxs-lookup"><span data-stu-id="8e32b-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="8e32b-105">El id. de ámbito es igual al código de empresa suministrado por el contexto en el que se ejecuta el formato de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="8e32b-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="8e32b-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="8e32b-106">Syntax 1</span></span>

```
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="8e32b-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="8e32b-107">Syntax 2</span></span>

```
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="8e32b-108">Sintaxis 3</span><span class="sxs-lookup"><span data-stu-id="8e32b-108">Syntax 3</span></span>

```
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="8e32b-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8e32b-109">Arguments</span></span>

<span data-ttu-id="8e32b-110">`number sequence code`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="8e32b-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="8e32b-111">Un valor de texto que representa el código de la secuencia numérica en la que se requiere un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8e32b-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="8e32b-112">`number sequence record ID`: *Int64*</span><span class="sxs-lookup"><span data-stu-id="8e32b-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="8e32b-113">Un valor de tipo *Int64* que representa el id. de registro de un registro de la tabla NumberSequenceTable que contiene la definición de la secuencia numérica en la que se requiere un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8e32b-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="8e32b-114">`scope type`: *Valor de enumeración*</span><span class="sxs-lookup"><span data-stu-id="8e32b-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="8e32b-115">Un valor de enumeración de **ERExpressionNumberSequenceScopeType** que define el ámbito de la secuencia numérica en la que se requiere un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="8e32b-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="8e32b-116">Los tipos de ámbito disponibles son **Compartido**, **Entidad jurídica** y **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="8e32b-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="8e32b-117">`scope ID`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="8e32b-117">`scope ID`: *String*</span></span>

<span data-ttu-id="8e32b-118">Valor de tipo *Cadena* que identifica el ámbito en función del tipo de ámbito especificado.</span><span class="sxs-lookup"><span data-stu-id="8e32b-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="8e32b-119">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8e32b-119">Return values</span></span>

<span data-ttu-id="8e32b-120">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="8e32b-120">*String*</span></span>

<span data-ttu-id="8e32b-121">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="8e32b-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8e32b-122">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="8e32b-122">Usage notes</span></span>

<span data-ttu-id="8e32b-123">Para el ámbito de tipo **Compartido**, especifique una cadena vacía como identificador de ámbito.</span><span class="sxs-lookup"><span data-stu-id="8e32b-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="8e32b-124">Para los ámbitos de tipo **Empresa** y **Entidad jurídica**, especifique el código de empresa como identificador de ámbito.</span><span class="sxs-lookup"><span data-stu-id="8e32b-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="8e32b-125">Si especifica una cadena vacía como el identificador de ámbito para estos tipos de ámbito, se usa el código de la empresa actual.</span><span class="sxs-lookup"><span data-stu-id="8e32b-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="8e32b-126">Cuando se utiliza la sintaxis 1, se solicita la secuencia numérica para el tipo de ámbito **Empresa** y el el código de empresa lo suministra el contexto en el que se ejecuta el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8e32b-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="8e32b-127">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="8e32b-127">Example 1</span></span>

<span data-ttu-id="8e32b-128">En su formato de ER, usted define el origen de datos **AskNumSeq** del tipo *Parámetro de entrada del usuario*.</span><span class="sxs-lookup"><span data-stu-id="8e32b-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="8e32b-129">Este origen de datos hace referencia a la tipo de datos extendido (EDT) **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="8e32b-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="8e32b-130">A continuación, define el origen de datos **NumSeq** del tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="8e32b-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="8e32b-131">Este origen de datos contiene la expresión `NUMSEQVALUE (AskNumSeq)`.</span><span class="sxs-lookup"><span data-stu-id="8e32b-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="8e32b-132">Cuando se llama al origen de datos **NumSeq**, devuelve el nuevo valor generado de la secuencia numérica que se especificó en tiempo de ejecución al introducir su código en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="8e32b-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="8e32b-133">Se solicita la secuencia numérica para el ámbito de tipo **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="8e32b-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="8e32b-134">El código de empresa lo suministra el contexto en el que se ejecuta el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8e32b-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="8e32b-135">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="8e32b-135">Example 2</span></span>

<span data-ttu-id="8e32b-136">Los siguientes orígenes de datos se definen en la asignación del modelo:</span><span class="sxs-lookup"><span data-stu-id="8e32b-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="8e32b-137">El origen de datos **LedgerParms** del tipo *Tabla*.</span><span class="sxs-lookup"><span data-stu-id="8e32b-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="8e32b-138">Este origen de datos hace referencia a la tabla LedgerParameters.</span><span class="sxs-lookup"><span data-stu-id="8e32b-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="8e32b-139">El origen de datos **NumSeq** del tipo de datos *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="8e32b-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="8e32b-140">Este origen de datos contiene la expresión `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span><span class="sxs-lookup"><span data-stu-id="8e32b-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="8e32b-141">Cuando se llama al origen de datos **NumSeq**, devuelve el nuevo valor generado a partir de la secuencia numérica que se ha configurado en los parámetros de contabilidad general para la empresa que proporciona el contexto donde se ejecuta el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8e32b-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="8e32b-142">Esta secuencia numérica identifica de forma exclusiva los diarios y actúa como número de lote que vincula las transacciones.</span><span class="sxs-lookup"><span data-stu-id="8e32b-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="8e32b-143">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="8e32b-143">Example 3</span></span>

<span data-ttu-id="8e32b-144">Los siguientes orígenes de datos se definen en la asignación del modelo:</span><span class="sxs-lookup"><span data-stu-id="8e32b-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="8e32b-145">El origen de datos **enumScope** del tipo *enumeración* de Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="8e32b-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="8e32b-146">Este origen de datos hace referencia a la enumeración **ERExpressionNumberSequenceScopeType**.</span><span class="sxs-lookup"><span data-stu-id="8e32b-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="8e32b-147">El origen de datos **NumSeq** del tipo de datos *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="8e32b-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="8e32b-148">Este origen de datos contiene la expresión `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span><span class="sxs-lookup"><span data-stu-id="8e32b-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="8e32b-149">Cuando se llama al origen de datos **NumSeq**, devuelve el nuevo valor generado a partir de la secuencia numérica **Gene\_1** que se ha configurado para la empresa que proporciona el contexto donde se ejecuta el formato de ER.</span><span class="sxs-lookup"><span data-stu-id="8e32b-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8e32b-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8e32b-150">Additional resources</span></span>

[<span data-ttu-id="8e32b-151">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="8e32b-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
