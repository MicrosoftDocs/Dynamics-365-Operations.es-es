---
title: Función FORMAT de ER
description: En este tema se proporciona información sobre cómo usar la función FORMAT de informes electrónicos (ER).
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
ms.openlocfilehash: 6ee53ef3c1a8820f75580e2f9fbd48575d6a828f
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746471"
---
# <a name="format-er-function"></a><span data-ttu-id="fc43d-103">Función FORMAT de ER</span><span class="sxs-lookup"><span data-stu-id="fc43d-103">FORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fc43d-104">La función `FORMAT` devuelve la cadena especificada como un valor de tipo *Cadena* tras aplicar formato sustituyendo cualquier instancia de **%N** por el argumento *N*-ésimo.</span><span class="sxs-lookup"><span data-stu-id="fc43d-104">The `FORMAT` function returns the specified string as a *String* value after it has been formatted by substituting any occurrences of **%N** with the *N* th argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc43d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc43d-105">Syntax</span></span>

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a><span data-ttu-id="fc43d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fc43d-106">Arguments</span></span>

<span data-ttu-id="fc43d-107">`string`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="fc43d-107">`string`: *String*</span></span>

<span data-ttu-id="fc43d-108">Hay que aplicar formato a una referencia a un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="fc43d-108">A reference to a data source of the *String* type that must be formatted.</span></span> <span data-ttu-id="fc43d-109">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc43d-109">This argument is required.</span></span>

<span data-ttu-id="fc43d-110">`argument 1`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="fc43d-110">`argument 1`: *String*</span></span>

<span data-ttu-id="fc43d-111">El primer argumento, que se utiliza para reemplazar instancias de **%1**.</span><span class="sxs-lookup"><span data-stu-id="fc43d-111">The first argument, which is used to replace occurrences of **%1**.</span></span> <span data-ttu-id="fc43d-112">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fc43d-112">This argument is required.</span></span>

<span data-ttu-id="fc43d-113">`argument N`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="fc43d-113">`argument N`: *String*</span></span>

<span data-ttu-id="fc43d-114">El *N*-ésimo argumento, que se utiliza para reemplazar instancias de **%2**, **%3**, etc.</span><span class="sxs-lookup"><span data-stu-id="fc43d-114">The *N* th argument, which is used to replace occurrences of **%2**, **%3**, and so on.</span></span> <span data-ttu-id="fc43d-115">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="fc43d-115">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="fc43d-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="fc43d-116">Return values</span></span>

<span data-ttu-id="fc43d-117">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="fc43d-117">*String*</span></span>

<span data-ttu-id="fc43d-118">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="fc43d-118">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fc43d-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="fc43d-119">Usage notes</span></span>

<span data-ttu-id="fc43d-120">Si no se proporciona un argumento para un parámetro, el parámetro se devuelve como **“%N”** en la cadena.</span><span class="sxs-lookup"><span data-stu-id="fc43d-120">If an argument isn't provided for a parameter, the parameter is returned as **"%N"** in the string.</span></span> <span data-ttu-id="fc43d-121">Para valores del tipo *Real*, la conversión de cadena predetermina está limitada a dos posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="fc43d-121">For values of the *Real* type, the default string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="fc43d-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc43d-122">Example</span></span>

<span data-ttu-id="fc43d-123">En la siguiente ilustración, el origen de datos **PaymentModel** devuelve una lista de registros de cliente mediante el componente **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="fc43d-123">In the following illustration, the **PaymentModel** data source returns a list of customer records by using the **Customer** component.</span></span> <span data-ttu-id="fc43d-124">Devuelve el valor de la fecha de procesamiento a través del campo **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="fc43d-124">It returns the processing date value by using the **ProcessingDate** field.</span></span>

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

<span data-ttu-id="fc43d-125">En el formato de informes electrónicos (ER) diseñado para generar un archivo electrónico para los clientes seleccionados, **PaymentModel** se selecciona como origen de datos y controla el flujo de proceso.</span><span class="sxs-lookup"><span data-stu-id="fc43d-125">In the Electronic reporting (ER) format that is designed to generate an electronic file for selected customers, **PaymentModel** is selected as a data source, and it controls the process flow.</span></span> <span data-ttu-id="fc43d-126">Si un cliente está detenido para la fecha de procesamiento del informe, se genera una excepción para notificárselo al usuario.</span><span class="sxs-lookup"><span data-stu-id="fc43d-126">If a selected customer is stopped for the date when the report is processed, an exception is thrown to notify the user.</span></span> <span data-ttu-id="fc43d-127">La fórmula que está diseñada para este tipo de control de proceso puede usar los recursos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fc43d-127">The formula that is designed for this type of processing control can use the following resources:</span></span>

- <span data-ttu-id="fc43d-128">Etiqueta SYS70894, que tiene el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="fc43d-128">Label SYS70894, which has the following text:</span></span>

    - <span data-ttu-id="fc43d-129">**Para el idioma EN-US:** “No hay nada que imprimir”</span><span class="sxs-lookup"><span data-stu-id="fc43d-129">**For the EN-US language:** "Nothing to print"</span></span>
    - <span data-ttu-id="fc43d-130">**Para el idioma DE:** "Nichts zu drucken"</span><span class="sxs-lookup"><span data-stu-id="fc43d-130">**For the DE language:** "Nichts zu drucken"</span></span>

- <span data-ttu-id="fc43d-131">Etiqueta SYS18389, que tiene el siguiente texto:</span><span class="sxs-lookup"><span data-stu-id="fc43d-131">Label SYS18389, which has the following text:</span></span>

    - <span data-ttu-id="fc43d-132">**Para el idioma EN-US:** "Customer %1 is stopped for %2."</span><span class="sxs-lookup"><span data-stu-id="fc43d-132">**For the EN-US language:** "Customer %1 is stopped for %2."</span></span>
    - <span data-ttu-id="fc43d-133">**Para el idioma DE:** "Debitor '%1' wird für %2 gesperrt."</span><span class="sxs-lookup"><span data-stu-id="fc43d-133">**For the DE language:** "Debitor '%1' wird für %2 gesperrt."</span></span>

<span data-ttu-id="fc43d-134">Esta es la expresión que se puede diseñar.</span><span class="sxs-lookup"><span data-stu-id="fc43d-134">Here is the expression that can be designed.</span></span>

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

<span data-ttu-id="fc43d-135">Si se procesa un informe para el cliente **Litware Retail** el 17 de diciembre de 2015, en la cultura **EN-US** y el idioma **EN-US**, esta fórmula devuelve el siguiente texto, que puede presentarse al usuario como mensaje de excepción:</span><span class="sxs-lookup"><span data-stu-id="fc43d-135">If a report is processed for the **Litware Retail** customer on December 17, 2015, in the **EN-US** culture and the **EN-US** language, this formula returns the following text, which can be presented to the user as an exception message:</span></span>

<span data-ttu-id="fc43d-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span><span class="sxs-lookup"><span data-stu-id="fc43d-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span></span>

<span data-ttu-id="fc43d-137">Si el mismo informe se procesa para el cliente **Litware Retail** el 17 de diciembre de 2015, en la cultura **DE** y el idioma **DE**, la fórmula devuelve el siguiente texto, que usa un formato de fecha diferente:</span><span class="sxs-lookup"><span data-stu-id="fc43d-137">If the same report is processed for the **Litware Retail** customer on December 17, 2015, in the **DE** culture and the **DE** language, the formula returns the following text, which uses a different date format:</span></span>

<span data-ttu-id="fc43d-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span><span class="sxs-lookup"><span data-stu-id="fc43d-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span></span>

>[!NOTE]
> <span data-ttu-id="fc43d-139">La sintaxis siguiente se aplica en las fórmulas de ER para las etiquetas:</span><span class="sxs-lookup"><span data-stu-id="fc43d-139">The following syntax is applied in ER formulas for labels:</span></span>
>
> - <span data-ttu-id="fc43d-140">**Para las etiquetas de recursos de la aplicación de Microsoft Dynamics 365 Finance:** **\@X**, donde **X** es el id. de etiqueta en el árbol de objetos de aplicación (AOT)</span><span class="sxs-lookup"><span data-stu-id="fc43d-140">**For labels from resources in the Microsoft Dynamics 365 Finance app:** **\@X**, where **X** is the label ID in the Application Object Tree (AOT)</span></span>
> - <span data-ttu-id="fc43d-141">**Para las etiquetas que se encuentran en las configuraciones de ER:** **@"GER_LABEL:X**, donde **X** es el id. de etiqueta de la configuración de ER</span><span class="sxs-lookup"><span data-stu-id="fc43d-141">**For labels that reside in ER configurations:** **@"GER_LABEL:X"**, where **X** is the label ID in the ER configuration</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc43d-142">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fc43d-142">Additional resources</span></span>

[<span data-ttu-id="fc43d-143">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="fc43d-143">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]