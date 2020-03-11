---
title: Función LISTOFFIELDS de ER
description: En este tema se proporciona información sobre cómo usar la función LISTOFFIELDS de informes electrónicos (ER).
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
ms.openlocfilehash: 0d51b59c437bd216c6d229546136bb604239fa92
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042007"
---
# <span data-ttu-id="e0463-103"><a name="LISTOFFIELDS">Función LISTOFFIELDS de ER</a></span><span class="sxs-lookup"><span data-stu-id="e0463-103"><a name="LISTOFFIELDS">LISTOFFIELDS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0463-104">La función `LISTOFFIELDS` devuelve un valor *Lista de registros* que se crea en función de la estructura del argumento especificado del tipo *Enumeración* o *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="e0463-104">The `LISTOFFIELDS` function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="e0463-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="e0463-105">Syntax 1</span></span>

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a><span data-ttu-id="e0463-106">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="e0463-106">Syntax 2</span></span>

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a><span data-ttu-id="e0463-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e0463-107">Arguments</span></span>

<span data-ttu-id="e0463-108">`path`: referencia de origen de datos</span><span class="sxs-lookup"><span data-stu-id="e0463-108">`path`: Data source reference</span></span>

<span data-ttu-id="e0463-109">La ruta de referencia válida de un origen de datos de uno de los siguientes tipos de datos:</span><span class="sxs-lookup"><span data-stu-id="e0463-109">The valid reference path of a data source of one of the following data types:</span></span>

- <span data-ttu-id="e0463-110">Enumeración de modelo</span><span class="sxs-lookup"><span data-stu-id="e0463-110">Model enumeration</span></span>
- <span data-ttu-id="e0463-111">Enumeración de formato</span><span class="sxs-lookup"><span data-stu-id="e0463-111">Format enumeration</span></span>
- <span data-ttu-id="e0463-112">Enumeración de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e0463-112">Application enumeration</span></span>
- <span data-ttu-id="e0463-113">Contenedor (registro)</span><span class="sxs-lookup"><span data-stu-id="e0463-113">Container (record)</span></span>

<span data-ttu-id="e0463-114">`language`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="e0463-114">`language`: *String*</span></span>

<span data-ttu-id="e0463-115">Texto que representa un código de idioma.</span><span class="sxs-lookup"><span data-stu-id="e0463-115">Text that represents a language code.</span></span>

## <a name="return-values"></a><span data-ttu-id="e0463-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e0463-116">Return values</span></span>

<span data-ttu-id="e0463-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="e0463-117">*Record list*</span></span>

<span data-ttu-id="e0463-118">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="e0463-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e0463-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="e0463-119">Usage notes</span></span>

<span data-ttu-id="e0463-120">La lista que se crea consta de registros con los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="e0463-120">The list that is created consists of records that have the following fields:</span></span>

- <span data-ttu-id="e0463-121">**Nombre** (tipo de datos *Cadena*)</span><span class="sxs-lookup"><span data-stu-id="e0463-121">**Name** (*String* data type)</span></span>
- <span data-ttu-id="e0463-122">**Etiqueta** (tipo de datos *Cadena*)</span><span class="sxs-lookup"><span data-stu-id="e0463-122">**Label** (*String* data type)</span></span>
- <span data-ttu-id="e0463-123">**Descripción** (tipo de datos *Cadena*)</span><span class="sxs-lookup"><span data-stu-id="e0463-123">**Description** (*String* data type)</span></span>
- <span data-ttu-id="e0463-124">**IsTranslated** (tipo de datos *Booleano*)</span><span class="sxs-lookup"><span data-stu-id="e0463-124">**IsTranslated** (*Boolean* data type)</span></span>

<span data-ttu-id="e0463-125">Si el argumento `path` se refiere a una fuente de datos del tipo *Contenedor (registro)*, para cada campo del registro contenedor referenciado, se agrega un nuevo registro a la lista que se crea.</span><span class="sxs-lookup"><span data-stu-id="e0463-125">If the `path` argument refers to a data source of the *Container (Record)* type, for every field of the referenced container record, a new record is added to the list that is created.</span></span> <span data-ttu-id="e0463-126">Para cada registro que se crea, el campo **Nombre** devuelve el nombre del campo del registro de contenedor referenciado para el que se creó el registro actual.</span><span class="sxs-lookup"><span data-stu-id="e0463-126">For every record that is created, the **Name** field returns the name of the field of the referenced container record that the current record was created for.</span></span>

<span data-ttu-id="e0463-127">Si el argumento `path` se refiere a un origen de datos de los tipos *Enumeración*, para cada valor de enumeración de la enumeración referenciada, se agrega un nuevo registro a la lista que se crea.</span><span class="sxs-lookup"><span data-stu-id="e0463-127">If the `path` argument refers to a data source of one of the *Enumeration* types, for every enumeration value of the referenced enumeration, a new record is added to the list that is created.</span></span> <span data-ttu-id="e0463-128">Para cada registro que se crea, el campo **Nombre** devuelve el valor de la enumeración referenciada para el registro actual para el que se ha creado, el campo **Descripción** devuelve la descripción de esa enumeración, y el campo **Etiqueta** devuelve la etiqueta de esa enumeración.</span><span class="sxs-lookup"><span data-stu-id="e0463-128">For every record that is created, the **Name** field returns the value of the referenced enumeration that the current record was created for, the **Description** field returns the description of that enumeration, and the **Label** field returns the label of that enumeration.</span></span>

<span data-ttu-id="e0463-129">En tiempo de ejecución, cuando se usa la sintaxis 1, los campos **Etiqueta** y **Descripción** deben devolver valores de devolución que se basan en la configuración de idioma del formato de informe electrónico (ER) que se está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="e0463-129">At runtime, when syntax 1 is used, the **Label** and **Description** fields must return values that are based on the language settings of the Electronic reporting (ER) format that is running:</span></span>

- <span data-ttu-id="e0463-130">Si las etiquetas y descripciones para el idioma solicitado están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en ese idioma y el campo **IsTranslated** devuelve **True**.</span><span class="sxs-lookup"><span data-stu-id="e0463-130">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="e0463-131">Si las etiquetas y las descripciones para el idioma solicitado no están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en el idioma predeterminado **EN-US** y el campo **IsTranslated** devuelve **False**.</span><span class="sxs-lookup"><span data-stu-id="e0463-131">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the default **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

<span data-ttu-id="e0463-132">En tiempo de ejecución, cuando se usa la sintaxis 2, los campos **Etiqueta** y **Descripción** deben devolver valores de devolución que se basan en el idioma que se define como el segundo argumento de la función llamada:</span><span class="sxs-lookup"><span data-stu-id="e0463-132">At runtime, when syntax 2 is used, the **Label** and **Description** fields must return values that are based on the language that is defined as the second argument of the called function:</span></span>

- <span data-ttu-id="e0463-133">Si las etiquetas y descripciones para el idioma solicitado están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en ese idioma y el campo **IsTranslated** devuelve **True**.</span><span class="sxs-lookup"><span data-stu-id="e0463-133">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="e0463-134">Si las etiquetas y las descripciones para el idioma solicitado no están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en el idioma **EN-US** y el campo **IsTranslated** devuelve **False**.</span><span class="sxs-lookup"><span data-stu-id="e0463-134">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

## <a name="example-1"></a><span data-ttu-id="e0463-135">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e0463-135">Example 1</span></span>

<span data-ttu-id="e0463-136">En la siguiente ilustración, se introduce una enumeración en un modelo de datos de ER.</span><span class="sxs-lookup"><span data-stu-id="e0463-136">In the following illustration, an enumeration is introduced in an ER data model.</span></span>

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

<span data-ttu-id="e0463-137">La siguiente ilustración muestra estos detalles:</span><span class="sxs-lookup"><span data-stu-id="e0463-137">The following illustration shows these details:</span></span>

- <span data-ttu-id="e0463-138">La enumeración del modelo se inserta en un informe como origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e0463-138">The model enumeration is inserted into a report as a data source.</span></span>
- <span data-ttu-id="e0463-139">Una expresión del ER utiliza la enumeración de modelo como un parámetro de la función `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="e0463-139">An ER expression uses the model enumeration as a parameter of the `LISTOFFIELDS` function.</span></span>
- <span data-ttu-id="e0463-140">Un origen de datos del tipo *Lista de registro* se inserta en un informe mediante la expresión de ER que se crea.</span><span class="sxs-lookup"><span data-stu-id="e0463-140">A data source of the *Record list* type is inserted into a report by using the ER expression that is created.</span></span>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

<span data-ttu-id="e0463-141">El siguiente ejemplo muestra los elementos del formato de ER que están enlazados al origen de datos del tipo *Lista de registro* creado mediante la función de `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="e0463-141">The following example shows the ER format elements that are bound to the data source of the *Record list* type that was created by using the `LISTOFFIELDS` function.</span></span>

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

<span data-ttu-id="e0463-142">La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.</span><span class="sxs-lookup"><span data-stu-id="e0463-142">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> <span data-ttu-id="e0463-143">Basado en la configuración de idioma de los elementos del formato del **ARCHIVO** principal y de la **CARPETA**, el texto traducido para las etiquetas y las descripciones se introduce en la salida del formato de ER.</span><span class="sxs-lookup"><span data-stu-id="e0463-143">Based on the language settings of the parent **FILE** and **FOLDER** format elements, translated text for labels and descriptions is entered in the output of the ER format.</span></span>

## <a name="example-2"></a><span data-ttu-id="e0463-144">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="e0463-144">Example 2</span></span>

<span data-ttu-id="e0463-145">Por ejemplo, utiliza el tipo de origen de datos *Campo calculado* para configurar los orígenes de datos **enumType\_de** y **enumType\_deCH** para la enumeración del modelo de datos **enumType**.</span><span class="sxs-lookup"><span data-stu-id="e0463-145">You use the *Calculated field* data source type to configure **enumType\_de** and **enumType\_deCH** data sources for the **enumType** data model enumeration:</span></span>

- <span data-ttu-id="e0463-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span><span class="sxs-lookup"><span data-stu-id="e0463-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span></span>
- <span data-ttu-id="e0463-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span><span class="sxs-lookup"><span data-stu-id="e0463-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span></span>

<span data-ttu-id="e0463-148">En este caso, puede usar la siguiente expresión para obtener la etiqueta del valor de enumeración en alemán suizo, si esta traducción está disponible.</span><span class="sxs-lookup"><span data-stu-id="e0463-148">In this case, you can use the following expression to get the label of the enumeration value in Swiss German, if that translation is available.</span></span> <span data-ttu-id="e0463-149">Si la traducción alemana suiza no está disponible, la etiqueta se encuentra en alemán.</span><span class="sxs-lookup"><span data-stu-id="e0463-149">If the Swiss German translation isn't available, the label is in German.</span></span>

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a><span data-ttu-id="e0463-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0463-150">Additional resources</span></span>

[<span data-ttu-id="e0463-151">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="e0463-151">List functions</span></span>](er-functions-category-list.md)
