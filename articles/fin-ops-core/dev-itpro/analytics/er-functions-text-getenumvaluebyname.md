---
title: Función GETENUMVALUEBYNAME de ER
description: Este tema proporciona información general sobre cómo usar la función GETENUMVALUEBYNAME de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 09/23/2020
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
ms.openlocfilehash: 722ea8ea233d617b0584e21e98073428f16c0801
ms.sourcegitcommit: ad5b7676fc1213316e478afcffbfaee7d813f3bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "3885236"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="c11dc-103">Función GETENUMVALUEBYNAME de ER</span><span class="sxs-lookup"><span data-stu-id="c11dc-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c11dc-104">La función `GETENUMVALUEBYNAME` busca un valor específico de tipo *Enum* en el origen de datos de enumeración especificado utilizando el nombre de enumeración especificado como un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="c11dc-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="c11dc-105">Si el valor *Enum* se encuentra, la función lo devuelve.</span><span class="sxs-lookup"><span data-stu-id="c11dc-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="c11dc-106">De lo contrario, la función devuelve el valor de enumeración **nulo**.</span><span class="sxs-lookup"><span data-stu-id="c11dc-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="c11dc-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c11dc-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="c11dc-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c11dc-108">Arguments</span></span>

<span data-ttu-id="c11dc-109">`enumeration data source path`: *Enumeración*</span><span class="sxs-lookup"><span data-stu-id="c11dc-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="c11dc-110">La ruta válida de un origen de datos de uno de los siguientes tipos de enumeración:</span><span class="sxs-lookup"><span data-stu-id="c11dc-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="c11dc-111">Enumeración de modelo de informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="c11dc-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="c11dc-112">Enumeración de formato de ER</span><span class="sxs-lookup"><span data-stu-id="c11dc-112">ER format enumeration</span></span>
- <span data-ttu-id="c11dc-113">Enumeración de Microsoft Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="c11dc-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="c11dc-114">`enumeration value text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c11dc-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="c11dc-115">Un valor de cadena que representa el nombre de un valor de enumeración único.</span><span class="sxs-lookup"><span data-stu-id="c11dc-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="c11dc-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c11dc-116">Return values</span></span>

<span data-ttu-id="c11dc-117">*Enum* anulable</span><span class="sxs-lookup"><span data-stu-id="c11dc-117">Nullable *Enum*</span></span>

<span data-ttu-id="c11dc-118">El valor de enumeración resultante.</span><span class="sxs-lookup"><span data-stu-id="c11dc-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c11dc-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="c11dc-119">Usage notes</span></span>

<span data-ttu-id="c11dc-120">No se produce ninguna excepción si no se encuentra un valor de tipo *Enum* con el nombre del valor de enumeración especificado como un valor de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="c11dc-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="c11dc-121">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="c11dc-121">Example 1</span></span>

<span data-ttu-id="c11dc-122">En la siguiente ilustración, la enumeración **ReportDirection** se introduce en un modelo de datos.</span><span class="sxs-lookup"><span data-stu-id="c11dc-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="c11dc-123">Tenga en cuenta que se definen etiquetas para los valores de enumeración.</span><span class="sxs-lookup"><span data-stu-id="c11dc-123">Notice that labels are defined for the enumeration values.</span></span>

![Valores disponibles para una enumeración de modelo de datos](./media/ER-data-model-enumeration-values.PNG)

<span data-ttu-id="c11dc-125">La siguiente ilustración muestra estos detalles:</span><span class="sxs-lookup"><span data-stu-id="c11dc-125">The following illustration shows these details:</span></span>

- <span data-ttu-id="c11dc-126">El origen de datos **$Direction** se configura en un informe de ER.</span><span class="sxs-lookup"><span data-stu-id="c11dc-126">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="c11dc-127">Este origen de datos se configura en función de la enumeración del modelo **ReportDirection**.</span><span class="sxs-lookup"><span data-stu-id="c11dc-127">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="c11dc-128">La expresión `$IsArrivals` está diseñada para usar el origen de datos **$Direction** basado en la enumeración del modelo como un parámetro de esta función.</span><span class="sxs-lookup"><span data-stu-id="c11dc-128">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="c11dc-129">El valor de esta expresión de comparación es **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="c11dc-129">The value of this comparison expression is **TRUE**.</span></span>

![Ejemplo de enumeración de modelo de datos](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a><span data-ttu-id="c11dc-131">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="c11dc-131">Example 2</span></span>

<span data-ttu-id="c11dc-132">Las funciones `GETENUMVALUEBYNAME` y [`LISTOFFIELDS`](er-functions-list-listoffields.md) permiten obtener valores y etiquetas de enumeraciones compatibles como valores de texto.</span><span class="sxs-lookup"><span data-stu-id="c11dc-132">The `GETENUMVALUEBYNAME` and [`LISTOFFIELDS`](er-functions-list-listoffields.md) functions let you fetch values and labels of supported enumerations as text values.</span></span> <span data-ttu-id="c11dc-133">(Las enumeraciones admitidas son enumeraciones de aplicaciones, enumeraciones de modelos de datos y enumeraciones de formato).</span><span class="sxs-lookup"><span data-stu-id="c11dc-133">(The supported enumerations are application enumerations, data model enumerations, and format enumerations.)</span></span>

<span data-ttu-id="c11dc-134">En la siguiente ilustración, el origen de datos **TransType** se introduce en una asignación de modelos.</span><span class="sxs-lookup"><span data-stu-id="c11dc-134">In the following illustration, the **TransType** data source is introduced in a model mapping.</span></span> <span data-ttu-id="c11dc-135">Este origen de datos hace referencia a la enumeración de aplicación **LedgerTransType**.</span><span class="sxs-lookup"><span data-stu-id="c11dc-135">This data source refers to the **LedgerTransType** application enumeration.</span></span>

![Fuente de datos de un mapeo de modelo que se refiere a una enumeración de aplicaciones](./media/er-functions-text-getenumvaluebyname-example2-1.png)

<span data-ttu-id="c11dc-137">En la siguiente ilustración se muestra el origen de datos **TransTypeList** que se configura en una asignación de modelos.</span><span class="sxs-lookup"><span data-stu-id="c11dc-137">The following illustration shows the **TransTypeList** data source that is configured in a model mapping.</span></span> <span data-ttu-id="c11dc-138">Este origen de datos se configura en función de la enumeración de aplicación **TransType**.</span><span class="sxs-lookup"><span data-stu-id="c11dc-138">This data source is configured based on the **TransType** application enumeration.</span></span> <span data-ttu-id="c11dc-139">La función `LISTOFFIELDS` se utiliza para devolver todos los valores de enumeración como una lista de registros que contienen campos.</span><span class="sxs-lookup"><span data-stu-id="c11dc-139">The `LISTOFFIELDS` function is used to return all enumeration values as a list of records that contain fields.</span></span> <span data-ttu-id="c11dc-140">De esta manera, se exponen los detalles de cada valor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="c11dc-140">In this way, the details of every enumeration value are exposed.</span></span>

> [!NOTE]
> <span data-ttu-id="c11dc-141">El campo **EnumValue** está configurado para el origen de datos **TransTypeList** mediante la expresión `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`.</span><span class="sxs-lookup"><span data-stu-id="c11dc-141">The **EnumValue** field is configured for the **TransTypeList** data source by using the `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` expression.</span></span> <span data-ttu-id="c11dc-142">Este campo devuelve un valor de enumeración para cada registro de esta lista.</span><span class="sxs-lookup"><span data-stu-id="c11dc-142">This field returns an enumeration value for every record in this list.</span></span>

![Fuente de datos de un mapeo de modelo que devuelve todos los valores de enumeración de una enumeración seleccionada como una lista de registros](./media/er-functions-text-getenumvaluebyname-example2-2.png)

<span data-ttu-id="c11dc-144">En la siguiente ilustración se muestra el origen de datos **VendTrans** que se configura en una asignación de modelos.</span><span class="sxs-lookup"><span data-stu-id="c11dc-144">The following illustration shows the **VendTrans** data source that is configured in a model mapping.</span></span> <span data-ttu-id="c11dc-145">Esta fuente de datos devuelve registros de transacciones de proveedores de la tabla de aplicación **VendTrans**.</span><span class="sxs-lookup"><span data-stu-id="c11dc-145">This data source returns vendor transaction records from the **VendTrans** application table.</span></span> <span data-ttu-id="c11dc-146">El tipo de libro mayor de cada transacción se define por el valor del campo **TransType**.</span><span class="sxs-lookup"><span data-stu-id="c11dc-146">The ledger type of every transaction is defined by the value of the **TransType** field.</span></span>

> [!NOTE]
> <span data-ttu-id="c11dc-147">El campo **TransTypeTitle** está configurado para el origen de datos **VendTrans** mediante la expresión `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`.</span><span class="sxs-lookup"><span data-stu-id="c11dc-147">The **TransTypeTitle** field is configured for the **VendTrans** data source by using the `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` expression.</span></span> <span data-ttu-id="c11dc-148">Este campo devuelve la etiqueta de un valor de enumeración de la transacción actual como texto, si este valor de enumeración está disponible.</span><span class="sxs-lookup"><span data-stu-id="c11dc-148">This field returns the label of an enumeration value of the current transaction as text, if this enumeration value is available.</span></span> <span data-ttu-id="c11dc-149">En caso contrario, devuelve un valor de cadena en blanco.</span><span class="sxs-lookup"><span data-stu-id="c11dc-149">Otherwise, it returns a blank string value.</span></span>
>
> <span data-ttu-id="c11dc-150">El campo **TransTypeTitle** está vinculado al campo **LedgerType** de un modelo de datos que permite que esta información se utilice en todos los formatos ER que utilizan el modelo de datos como fuente de datos.</span><span class="sxs-lookup"><span data-stu-id="c11dc-150">The **TransTypeTitle** field is bound to the **LedgerType** field of a data model that enables this information to be used in every ER format that uses the data model as a source of data.</span></span>

![Fuente de datos de un mapeo de modelo que devuelve transacciones de proveedores](./media/er-functions-text-getenumvaluebyname-example2-3.png)

<span data-ttu-id="c11dc-152">La siguiente ilustración muestra cómo puede utilizar el [depurador de fuente de datos](er-debug-data-sources.md) para probar el mapeo del modelo configurado.</span><span class="sxs-lookup"><span data-stu-id="c11dc-152">The following illustration shows how you can use the [data source debugger](er-debug-data-sources.md) to test the configured model mapping.</span></span>

![Usar el depurador de la fuente de datos para probar el mapeo del modelo configurado](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

<span data-ttu-id="c11dc-154">El campo **LedgerType** de un modelo de datos expone las etiquetas de tipos de transacciones como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="c11dc-154">The **LedgerType** field of a data model exposes labels of transaction types as expected.</span></span>

<span data-ttu-id="c11dc-155">Si planea utilizar este enfoque para una gran cantidad de datos transaccionales, debe considerar el rendimiento de la ejecución.</span><span class="sxs-lookup"><span data-stu-id="c11dc-155">If you plan to use this approach for a large amount of transactional data, you must consider execution performance.</span></span> <span data-ttu-id="c11dc-156">Para obtener más información, vea [Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="c11dc-156">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c11dc-157">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c11dc-157">Additional resources</span></span>

[<span data-ttu-id="c11dc-158">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="c11dc-158">Text functions</span></span>](er-functions-category-text.md)

[<span data-ttu-id="c11dc-159">Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento</span><span class="sxs-lookup"><span data-stu-id="c11dc-159">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)

[<span data-ttu-id="c11dc-160">Función LISTOFFIELDS de ER</span><span class="sxs-lookup"><span data-stu-id="c11dc-160">LISTOFFIELDS ER function</span></span>](er-functions-list-listoffields.md)

[<span data-ttu-id="c11dc-161">Función FIRSTORNULL de ER</span><span class="sxs-lookup"><span data-stu-id="c11dc-161">FIRSTORNULL ER function</span></span>](er-functions-list-firstornull.md)

[<span data-ttu-id="c11dc-162">Función WHERE de ER</span><span class="sxs-lookup"><span data-stu-id="c11dc-162">WHERE ER function</span></span>](er-functions-list-where.md)
