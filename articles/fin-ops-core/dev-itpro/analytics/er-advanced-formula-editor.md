---
title: Editor de fórmulas avanzadas de informes electrónicos
description: Este tema describe cómo se puede usar el editor avanzado de fórmulas para configurar expresiones en la asignación de modelos y los componentes de formato de informes electrónicos (ER).
author: NickSelin
manager: AnnBe
ms.date: 01/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: d183f77da1dda0c4f04e4e48ab3db0133f494a55
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015378"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="b76a1-103">Editor de fórmulas avanzadas de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="b76a1-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="b76a1-104">Además del [editor de fórmulas ](general-electronic-reporting-formula-designer.md) de [informes electrónicos ](general-electronic-reporting.md), puede usar el editor avanzado de fórmulas de informes electrónicos para mejorar la experiencia de configurar expresiones de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="b76a1-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="b76a1-105">El editor avanzado está basado en el navegador y funciona con el [editor Monaco](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="b76a1-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="b76a1-106">Las características avanzadas más utilizadas del editor se describen en este tema:</span><span class="sxs-lookup"><span data-stu-id="b76a1-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="b76a1-107">Autoformato de código</span><span class="sxs-lookup"><span data-stu-id="b76a1-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="b76a1-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="b76a1-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="b76a1-109">Finalización del código</span><span class="sxs-lookup"><span data-stu-id="b76a1-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="b76a1-110">Navegación por el código</span><span class="sxs-lookup"><span data-stu-id="b76a1-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="b76a1-111">Estructuración del código</span><span class="sxs-lookup"><span data-stu-id="b76a1-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="b76a1-112">Buscar y reemplazar</span><span class="sxs-lookup"><span data-stu-id="b76a1-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="b76a1-113">Pegado de datos</span><span class="sxs-lookup"><span data-stu-id="b76a1-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="b76a1-114">Colorización de sintaxis</span><span class="sxs-lookup"><span data-stu-id="b76a1-114">Syntax colorization</span></span>](#SyntaxColorization)

## <span data-ttu-id="b76a1-115"><a name="ActivateAdvEditor">Activar el editor avanzado de fórmulas</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="b76a1-116">Complete los siguientes pasos para comenzar a usar el editor de fórmulas avanzado en su instancia de Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="b76a1-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="b76a1-117">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="b76a1-118">En la página  **Configuraciones**, en el panel de acciones, en la pestaña  **Configuraciones**, en el grupo  **Configuración avanzada**, seleccione  **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="b76a1-119">En el cuadro de diálogo **Parámetros del usuario**, en la sección **Seguimiento de ejecución**, establezca el parámetro **Habilitar editor avanzado de fórmulas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="b76a1-120">[![Página de configuraciones de ER](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="b76a1-120">[![ER configurations page](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="b76a1-121">Tenga en cuenta que este parámetro es específico del usuario y específico de la compañía.</span><span class="sxs-lookup"><span data-stu-id="b76a1-121">Be aware that this parameter is user specific and company specific.</span></span>

## <span data-ttu-id="b76a1-122"><a name="Autoformatting">Autoformato de código</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-122"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="b76a1-123">Cuando escribe una expresión compleja que consta de varias filas de código, se aplica automáticamente sangría a una nueva línea introducida en función de la sangría de la fila anterior.</span><span class="sxs-lookup"><span data-stu-id="b76a1-123">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="b76a1-124">Puede seleccionar líneas y cambiar la sangría introduciendo **Tabulador** o **Mayús+Tabulador**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-124">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="b76a1-125">[![Editor de fórmulas ER](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="b76a1-125">[![ER formula editor](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="b76a1-126">El formato automático permite mantener toda la expresión bien formateada para facilitar el mantenimiento y simplificar la comprensión de la lógica configurada.</span><span class="sxs-lookup"><span data-stu-id="b76a1-126">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <span data-ttu-id="b76a1-127"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-127"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="b76a1-128">El editor proporciona finalización de palabras para ayudarle a escribir expresiones más rápido y evitar errores tipográficos.</span><span class="sxs-lookup"><span data-stu-id="b76a1-128">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="b76a1-129">Cuando comienza a agregar texto nuevo, el editor ofrece automáticamente una lista de funciones compatibles con las funciones de ER que contienen los caracteres que ha introducido.</span><span class="sxs-lookup"><span data-stu-id="b76a1-129">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="b76a1-130">También puede activar IntelliSense en cualquier lugar de una expresión configurada escribiendo **Ctrl+espacio**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-130">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="b76a1-131">[![Editor de fórmulas ER](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="b76a1-131">[![ER formula editor](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <span data-ttu-id="b76a1-132"><a name="CodeCompletion">Finalización del código</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-132"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="b76a1-133">El editor proporciona automáticamente la finalización del código mediante:</span><span class="sxs-lookup"><span data-stu-id="b76a1-133">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="b76a1-134">Inserción de un corchete de cierre cuando se introduce un corchete de apertura, manteniendo el cursor dentro de los corchetes.</span><span class="sxs-lookup"><span data-stu-id="b76a1-134">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="b76a1-135">Inserción del segundo signo de comillas cuando se ingresa el primero, manteniendo el cursor dentro de las comillas.</span><span class="sxs-lookup"><span data-stu-id="b76a1-135">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="b76a1-136">Inserción del segundo símbolo de comillas dobles cuando se ingresa el primero, manteniendo el cursor dentro de las comillas.</span><span class="sxs-lookup"><span data-stu-id="b76a1-136">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="b76a1-137">[![Editor de fórmulas ER](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="b76a1-137">[![ER formula editor](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="b76a1-138">Cuando señala el paréntesis escrito, el segundo paréntesis de este par se resalta automáticamente para mostrar la construcción que admiten.</span><span class="sxs-lookup"><span data-stu-id="b76a1-138">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <span data-ttu-id="b76a1-139"><a name="CodeNavigation">Navegación por el código</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-139"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="b76a1-140">Puede localizar los símbolos o las líneas requeridos en su expresión escribiendo el comando **Ir a** usando la paleta de comandos o el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="b76a1-140">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="b76a1-141">Por ejemplo, para saltar a la línea **8**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b76a1-141">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="b76a1-142">Pulse **Ctrl+G**, ingrese el valor **8** y luego presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-142">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="b76a1-143">– O bien –</span><span class="sxs-lookup"><span data-stu-id="b76a1-143">-or-</span></span>

- <span data-ttu-id="b76a1-144">Pulse **F1**, escriba **G**, seleccione **Ir a línea**, ingrese el valor **8** y pulse **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-144">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="b76a1-145">[![Editor de fórmulas ER](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="b76a1-145">[![ER formula editor](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <span data-ttu-id="b76a1-146"><a name="CodeStructuring">Estructuración del código</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-146"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="b76a1-147">El código para algunas funciones, como [IF](er-functions-logical-if.md) o [CASE](er-functions-logical-case.md), se estructura automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b76a1-147">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="b76a1-148">Puede expandir y contraer cualquiera o todas las regiones plegables del código para reducir la parte editable de una expresión y centrarse solo en el fragmento de código que requiere su atención.</span><span class="sxs-lookup"><span data-stu-id="b76a1-148">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="b76a1-149">Los comandos de alternar plegar/desplegar se usan para eso.</span><span class="sxs-lookup"><span data-stu-id="b76a1-149">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="b76a1-150">Por ejemplo, para plegar todas las regiones, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b76a1-150">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="b76a1-151">Pulse **Ctrl+K**</span><span class="sxs-lookup"><span data-stu-id="b76a1-151">Press **Ctrl+K**</span></span>

  <span data-ttu-id="b76a1-152">– O bien –</span><span class="sxs-lookup"><span data-stu-id="b76a1-152">-or-</span></span>

- <span data-ttu-id="b76a1-153">Pulse **F1**, **FO**, seleccione **Plegar todo** y luego presione **Entrar**</span><span class="sxs-lookup"><span data-stu-id="b76a1-153">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="b76a1-154">Para desplegar todas las regiones, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b76a1-154">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="b76a1-155">Pulse **Ctrl+J**</span><span class="sxs-lookup"><span data-stu-id="b76a1-155">Press **Ctrl+J**</span></span>

  <span data-ttu-id="b76a1-156">– O bien –</span><span class="sxs-lookup"><span data-stu-id="b76a1-156">-or-</span></span>
  
- <span data-ttu-id="b76a1-157">Pulse **F1**, escriba **UN**, seleccione **Desplegar todo** y luego presione **Entrar**</span><span class="sxs-lookup"><span data-stu-id="b76a1-157">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="b76a1-158">[![Editor de fórmulas ER](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="b76a1-158">[![ER formula editor](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <span data-ttu-id="b76a1-159"><a name="FindAndReplace">Buscar y reemplazar</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-159"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="b76a1-160">Para buscar ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b76a1-160">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b76a1-161">Pulse **Ctrl+F** y luego presione **F3** para encontrar la próxima aparición del texto seleccionado, o presione **Mayús+F3** para encontrar la ocurrencia anterior.</span><span class="sxs-lookup"><span data-stu-id="b76a1-161">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="b76a1-162">– O bien –</span><span class="sxs-lookup"><span data-stu-id="b76a1-162">-or-</span></span>
  
- <span data-ttu-id="b76a1-163">Pulse **F1**, escriba **F** y luego seleccione la opción requerida para encontrar el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b76a1-163">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="b76a1-164">Para reemplazar ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b76a1-164">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b76a1-165">Pulse **Ctrl+H**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-165">Press **Ctrl+H**.</span></span> <span data-ttu-id="b76a1-166">Introduzca el texto alternativo y seleccione la opción de reemplazo para reemplazar el texto seleccionado o todas las apariciones de este texto en la expresión actual.</span><span class="sxs-lookup"><span data-stu-id="b76a1-166">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="b76a1-167">– O bien –</span><span class="sxs-lookup"><span data-stu-id="b76a1-167">-or-</span></span>
  
- <span data-ttu-id="b76a1-168">Pulse **F1**, escriba **R** y luego seleccione la opción requerida para reemplazar el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b76a1-168">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="b76a1-169">Introduzca el texto alternativo y seleccione la opción de reemplazo para reemplazar el texto seleccionado o todas las apariciones de este texto en la expresión actual.</span><span class="sxs-lookup"><span data-stu-id="b76a1-169">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="b76a1-170">Para cambiar todas las ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b76a1-170">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="b76a1-171">Pulse **Ctrl+F2** y luego introduzca el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="b76a1-171">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="b76a1-172">– O bien –</span><span class="sxs-lookup"><span data-stu-id="b76a1-172">-or-</span></span>
  
- <span data-ttu-id="b76a1-173">Pulse **F1**, escriba **C** y luego seleccione la opción requerida para cambiar el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b76a1-173">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="b76a1-174">Introduzca el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="b76a1-174">Enter the alternative text.</span></span>

<span data-ttu-id="b76a1-175">[![Editor de fórmulas ER](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="b76a1-175">[![ER formula editor](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <span data-ttu-id="b76a1-176"><a name="DataPasting">Fuentes de datos y pegado de funciones</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-176"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="b76a1-177">Puede elegir **Agregar origen de datos**, que pega a la expresión actual el origen de datos seleccionado actualmente en el panel izquierdo **Origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-177">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="b76a1-178">De manera similar, puede elegir **Agregar función**, que pega en la expresión actual la función seleccionada actualmente en el panel derecho **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="b76a1-178">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="b76a1-179">Si usa el editor de fórmulas ER, una función seleccionada o un origen de datos seleccionado siempre se pegará al final de la expresión configurada.</span><span class="sxs-lookup"><span data-stu-id="b76a1-179">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="b76a1-180">Si usa el editor avanzado de fórmulas ER, una función seleccionada o un origen de datos seleccionado se puede pegar en cualquier parte de la expresión configurada.</span><span class="sxs-lookup"><span data-stu-id="b76a1-180">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="b76a1-181">Deberá usar el cursor para especificar dónde desea pegar los datos.</span><span class="sxs-lookup"><span data-stu-id="b76a1-181">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="b76a1-182">[![Editor de fórmulas ER](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="b76a1-182">[![ER formula editor](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <span data-ttu-id="b76a1-183"><a name="SyntaxColorization">Colorización de sintaxis</a></span><span class="sxs-lookup"><span data-stu-id="b76a1-183"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="b76a1-184">Actualmente, se utilizan diferentes colores para resaltar las siguientes partes de las expresiones:</span><span class="sxs-lookup"><span data-stu-id="b76a1-184">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="b76a1-185">El texto entre corchetes dobles que puede representar un id. de etiqueta de una constante de texto.</span><span class="sxs-lookup"><span data-stu-id="b76a1-185">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="b76a1-186">[![Editor de fórmulas ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="b76a1-186">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b76a1-187">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b76a1-187">Additional resources</span></span>

- [<span data-ttu-id="b76a1-188">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="b76a1-188">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="b76a1-189">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="b76a1-189">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="b76a1-190">Editor Monaco</span><span class="sxs-lookup"><span data-stu-id="b76a1-190">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)
