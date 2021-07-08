---
title: Editor de fórmulas avanzadas de informes electrónicos
description: Este tema describe cómo se puede usar el editor avanzado de fórmulas para configurar expresiones en la asignación de modelos y los componentes de formato de informes electrónicos (ER).
author: NickSelin
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: f7f80928e1d3f5d4892f72d4bd2fd09b70a26c1f
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270716"
---
# <a name="electronic-reporting-advanced-formula-editor"></a><span data-ttu-id="3382b-103">Editor de fórmulas avanzadas de informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="3382b-103">Electronic reporting advanced formula editor</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3382b-104">Además del [editor de fórmulas ](general-electronic-reporting-formula-designer.md) de [informes electrónicos ](general-electronic-reporting.md), puede usar el editor avanzado de fórmulas de informes electrónicos para mejorar la experiencia de configurar expresiones de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="3382b-104">In addition to the [Electronic reporting](general-electronic-reporting.md) [formula editor](general-electronic-reporting-formula-designer.md), you can use the advanced Electronic reporting formula editor to improve the experience of configuring Electronic reporting (ER) expressions.</span></span> <span data-ttu-id="3382b-105">El editor avanzado está basado en el navegador y funciona con el [editor Monaco](https://microsoft.github.io/monaco-editor).</span><span class="sxs-lookup"><span data-stu-id="3382b-105">The advanced editor is browser-based and powered by the [Monaco editor](https://microsoft.github.io/monaco-editor).</span></span> <span data-ttu-id="3382b-106">Las características avanzadas más utilizadas del editor se describen en este tema:</span><span class="sxs-lookup"><span data-stu-id="3382b-106">The most commonly used advanced editor features are described in this topic:</span></span>

- [<span data-ttu-id="3382b-107">Autoformato de código</span><span class="sxs-lookup"><span data-stu-id="3382b-107">Code autoformatting</span></span>](#Autoformatting)
- [<span data-ttu-id="3382b-108">IntelliSense</span><span class="sxs-lookup"><span data-stu-id="3382b-108">IntelliSense</span></span>](#IntelliSense)
- [<span data-ttu-id="3382b-109">Finalización del código</span><span class="sxs-lookup"><span data-stu-id="3382b-109">Code completion</span></span>](#CodeCompletion)
- [<span data-ttu-id="3382b-110">Navegación por el código</span><span class="sxs-lookup"><span data-stu-id="3382b-110">Code navigation</span></span>](#CodeNavigation)
- [<span data-ttu-id="3382b-111">Estructuración del código</span><span class="sxs-lookup"><span data-stu-id="3382b-111">Code structuring</span></span>](#CodeStructuring)
- [<span data-ttu-id="3382b-112">Buscar y reemplazar</span><span class="sxs-lookup"><span data-stu-id="3382b-112">Find and replace</span></span>](#FindAndReplace)
- [<span data-ttu-id="3382b-113">Pegado de datos</span><span class="sxs-lookup"><span data-stu-id="3382b-113">Data pasting</span></span>](#DataPasting)
- [<span data-ttu-id="3382b-114">Colorización de sintaxis</span><span class="sxs-lookup"><span data-stu-id="3382b-114">Syntax colorization</span></span>](#SyntaxColorization)

## <a name=""></a><span data-ttu-id="3382b-115"><a name="ActivateAdvEditor">Activar el editor avanzado de fórmulas</a></span><span class="sxs-lookup"><span data-stu-id="3382b-115"><a name="ActivateAdvEditor">Activate the advanced formula editor</a></span></span>

<span data-ttu-id="3382b-116">Complete los siguientes pasos para comenzar a usar el editor de fórmulas avanzado en su instancia de Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="3382b-116">Complete the following steps to start using the advanced formula editor in your instance of Microsoft Dynamics 365 Finance.</span></span>

1.  <span data-ttu-id="3382b-117">Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="3382b-117">Go to **Organization administration** \> **Electronic reporting** \> **Configurations**.</span></span>
2.  <span data-ttu-id="3382b-118">En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="3382b-118">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
3.  <span data-ttu-id="3382b-119">En el cuadro de diálogo **Parámetros del usuario**, en la sección **Seguimiento de ejecución**, establezca el parámetro **Habilitar editor avanzado de fórmulas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="3382b-119">In the **User parameters** dialog box, in the **Execution tracing** section, set the **Enable advanced formula editor** parameter to **Yes**.</span></span>

<span data-ttu-id="3382b-120">[![Cuadro de diálogo de parámetros de usuario, parámetro Habilitar editor de fórmulas avanzado resaltado](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span><span class="sxs-lookup"><span data-stu-id="3382b-120">[![User parameters dialog box, Enable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)</span></span>

> [!NOTE]
> <span data-ttu-id="3382b-121">Tenga en cuenta que este parámetro es específico del usuario y específico de la compañía.</span><span class="sxs-lookup"><span data-stu-id="3382b-121">Be aware that this parameter is user specific and company specific.</span></span>

<span data-ttu-id="3382b-122">Comenzando en Microsoft Dynamics 365 Finance versión 10.0.19, puede controlar qué editor de fórmulas ER se ofrece de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3382b-122">Starting in Microsoft Dynamics 365 Finance version 10.0.19, you can control what ER formula editor is offered by default.</span></span> <span data-ttu-id="3382b-123">Complete los siguientes pasos para habilitar el editor de fórmulas avanzado para todos los usuarios y empresas de la instancia de Finance actual.</span><span class="sxs-lookup"><span data-stu-id="3382b-123">Complete the following steps to enable the advanced formula editor for all users and companies of the current Finance instance.</span></span>

1.  <span data-ttu-id="3382b-124">Abra el espacio de trabajo **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="3382b-124">Open the **Feature management** workspace.</span></span>
2.  <span data-ttu-id="3382b-125">Busque y seleccione la función **Configure el editor de fórmulas avanzado de ER como el predeterminado para todos los usuarios** en la lista y luego seleccione **Habilitado ahora**.</span><span class="sxs-lookup"><span data-stu-id="3382b-125">Find and select the feature **Set the ER advanced formula editor as the default one for all users** in the list, and then select **Enable now**.</span></span>
3.  <span data-ttu-id="3382b-126">Vaya a **Administración de la organización** > **Informes electrónicos** > **Configuraciones**.</span><span class="sxs-lookup"><span data-stu-id="3382b-126">Go to **Organization administration** > **Electronic reporting** > **Configurations**.</span></span>
4.  <span data-ttu-id="3382b-127">En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.</span><span class="sxs-lookup"><span data-stu-id="3382b-127">On the **Configurations** page, on the Action Pane, on the **Configurations** tab, in the **Advanced settings** group, select **User parameters**.</span></span>
5.  <span data-ttu-id="3382b-128">En el cuadro de diálogo **Parámetros de usuario**, busque el parámetro **Deshabilitar el editor de fórmulas avanzado** y verifique que esté configurado en **No**.</span><span class="sxs-lookup"><span data-stu-id="3382b-128">In the **User parameters** dialog box, find the **Disable advanced formula editor** parameter and verify that it is set to **No**.</span></span>

<span data-ttu-id="3382b-129">[![Cuadro de diálogo de parámetros de usuario, parámetro Deshabilitar editor de fórmulas avanzado resaltado](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span><span class="sxs-lookup"><span data-stu-id="3382b-129">[![User parameters dialog box, Disable advanced formula editor parameter highlighted](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)</span></span>

> [!NOTE]
> <span data-ttu-id="3382b-130">Los valores de los parámetros **Habilitar el editor de fórmulas avanzado** y **Deshabilitar el editor de fórmulas avanzado** se mantienen separados para cada usuario y se ofrecen en el cuadro de diálogo **Parámetros de usuario** en función del estado de la función **Configure el editor de fórmulas avanzado de ER como el predeterminado para todos los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="3382b-130">The values of the parameters **Enable advanced formula editor** and **Disable advanced formula editor** are kept separate for each user and offered on the **User parameters** dialog box depending on the status of the **Set the ER advanced formula editor as the default one for all users** feature.</span></span>

## <a name=""></a><span data-ttu-id="3382b-131"><a name="Autoformatting">Autoformato de código</a></span><span class="sxs-lookup"><span data-stu-id="3382b-131"><a name="Autoformatting">Code autoformatting</a></span></span>

<span data-ttu-id="3382b-132">Cuando escribe una expresión compleja que consta de varias filas de código, se aplica automáticamente sangría a una nueva línea introducida en función de la sangría de la fila anterior.</span><span class="sxs-lookup"><span data-stu-id="3382b-132">When you write a complex expression that consists of multiple rows of code, the indentation of a new entered line will be automatic based on the indentation of the previous row.</span></span> <span data-ttu-id="3382b-133">Puede seleccionar líneas y cambiar la sangría introduciendo **Tabulador** o **Mayús+Tabulador**.</span><span class="sxs-lookup"><span data-stu-id="3382b-133">You can select lines and change their indentation by typing **Tab** or **Shift+Tab**.</span></span>

<span data-ttu-id="3382b-134">[![GIF del editor de fórmulas ER que muestra la selección de líneas y el cambio de la sangría](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span><span class="sxs-lookup"><span data-stu-id="3382b-134">[![ER formula editor gif showing selecting lines and changing the indentation](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)</span></span>

<span data-ttu-id="3382b-135">El formato automático permite mantener toda la expresión bien formateada para facilitar el mantenimiento y simplificar la comprensión de la lógica configurada.</span><span class="sxs-lookup"><span data-stu-id="3382b-135">Autoformatting allows you to keep the entire expression well formatted to make further maintenance easier and to simplify understanding of the configured logic.</span></span>

## <a name=""></a><span data-ttu-id="3382b-136"><a name="IntelliSense">IntelliSense</a></span><span class="sxs-lookup"><span data-stu-id="3382b-136"><a name="IntelliSense">IntelliSense</a></span></span>

<span data-ttu-id="3382b-137">El editor proporciona finalización de palabras para ayudarle a escribir expresiones más rápido y evitar errores tipográficos.</span><span class="sxs-lookup"><span data-stu-id="3382b-137">The editor provides word completion to help you write expression faster and avoid typos.</span></span> <span data-ttu-id="3382b-138">Cuando comienza a agregar texto nuevo, el editor ofrece automáticamente una lista de funciones compatibles con las funciones de ER que contienen los caracteres que ha introducido.</span><span class="sxs-lookup"><span data-stu-id="3382b-138">When you start adding new text, the editor automatically offers a list of functions supported in ER functions that contain the characters you have entered.</span></span> <span data-ttu-id="3382b-139">También puede activar IntelliSense en cualquier lugar de una expresión configurada escribiendo **Ctrl+espacio**.</span><span class="sxs-lookup"><span data-stu-id="3382b-139">You can also trigger IntelliSense in any place of a configured expression by typing **Ctrl+Space**.</span></span>

<span data-ttu-id="3382b-140">[![GIF del editor de fórmulas de ER que muestra la activación de IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span><span class="sxs-lookup"><span data-stu-id="3382b-140">[![ER formula editor gif showing triggering IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)</span></span>

## <a name=""></a><span data-ttu-id="3382b-141"><a name="CodeCompletion">Finalización del código</a></span><span class="sxs-lookup"><span data-stu-id="3382b-141"><a name="CodeCompletion">Code completion</a></span></span>

<span data-ttu-id="3382b-142">El editor proporciona automáticamente la finalización del código mediante:</span><span class="sxs-lookup"><span data-stu-id="3382b-142">The editor automatically provides code completion by:</span></span>

- <span data-ttu-id="3382b-143">Inserción de un corchete de cierre cuando se introduce un corchete de apertura, manteniendo el cursor dentro de los corchetes.</span><span class="sxs-lookup"><span data-stu-id="3382b-143">Inserting a closing bracket when an opening  bracket is entered, keeping the cursor inside the brackets.</span></span>
- <span data-ttu-id="3382b-144">Inserción del segundo signo de comillas cuando se ingresa el primero, manteniendo el cursor dentro de las comillas.</span><span class="sxs-lookup"><span data-stu-id="3382b-144">Inserting the second quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>
- <span data-ttu-id="3382b-145">Inserción del segundo símbolo de comillas dobles cuando se ingresa el primero, manteniendo el cursor dentro de las comillas.</span><span class="sxs-lookup"><span data-stu-id="3382b-145">Inserting the second double quotation symbol when the first one is entered, keeping the cursor inside the quotations.</span></span>

<span data-ttu-id="3382b-146">[![GIF del editor de fórmulas ER que muestra el editor que proporciona automáticamente la finalización del código](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span><span class="sxs-lookup"><span data-stu-id="3382b-146">[![ER formula editor gif showing the editor automatically providing code completion](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)</span></span>

<span data-ttu-id="3382b-147">Cuando señala el paréntesis escrito, el segundo paréntesis de este par se resalta automáticamente para mostrar la construcción que admiten.</span><span class="sxs-lookup"><span data-stu-id="3382b-147">When you point to the typed bracket, the second bracket of this pair is automatically highlighted to show the construct that they support.</span></span>

## <a name=""></a><span data-ttu-id="3382b-148"><a name="CodeNavigation">Navegación por el código</a></span><span class="sxs-lookup"><span data-stu-id="3382b-148"><a name="CodeNavigation">Code navigation</a></span></span>

<span data-ttu-id="3382b-149">Puede localizar los símbolos o las líneas requeridos en su expresión escribiendo el comando **Ir a** usando la paleta de comandos o el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="3382b-149">You can locate required symbols or lines in your expression by typing the **Go to** command using the command palette or the context menu.</span></span>

<span data-ttu-id="3382b-150">Por ejemplo, para saltar a la línea **8**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3382b-150">For example, to jump to line **8**, do the following:</span></span>

- <span data-ttu-id="3382b-151">Pulse **Ctrl+G**, ingrese el valor **8** y luego presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="3382b-151">Press **Ctrl+G**, enter the value **8**, and then press **Enter**.</span></span>

  <span data-ttu-id="3382b-152">– O bien –</span><span class="sxs-lookup"><span data-stu-id="3382b-152">-or-</span></span>

- <span data-ttu-id="3382b-153">Pulse **F1**, escriba **G**, seleccione **Ir a línea**, ingrese el valor **8** y pulse **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="3382b-153">Press **F1**, type **G**, select **Go to line**, enter the value **8**, and the press **Enter**.</span></span>

<span data-ttu-id="3382b-154">[![GIF del editor de fórmulas de ER que muestra cómo ubicar partes de una expresión usando la paleta de comandos](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span><span class="sxs-lookup"><span data-stu-id="3382b-154">[![ER formula editor gif showing how to locate parts of an expression using the command palette](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)</span></span>

## <a name=""></a><span data-ttu-id="3382b-155"><a name="CodeStructuring">Estructuración del código</a></span><span class="sxs-lookup"><span data-stu-id="3382b-155"><a name="CodeStructuring">Code structuring</a></span></span>

<span data-ttu-id="3382b-156">El código para algunas funciones, como [IF](er-functions-logical-if.md) o [CASE](er-functions-logical-case.md), se estructura automáticamente.</span><span class="sxs-lookup"><span data-stu-id="3382b-156">The code for some functions, such as [IF](er-functions-logical-if.md) or [CASE](er-functions-logical-case.md), is automatically structured.</span></span> <span data-ttu-id="3382b-157">Puede expandir y contraer cualquiera o todas las regiones plegables del código para reducir la parte editable de una expresión y centrarse solo en el fragmento de código que requiere su atención.</span><span class="sxs-lookup"><span data-stu-id="3382b-157">You can expand and collapse any or all of the folding regions of this code to reduce the editable part of an expression in order to focus on only  thepiece of code that requires your attention.</span></span> <span data-ttu-id="3382b-158">Los comandos de alternar plegar/desplegar se usan para eso.</span><span class="sxs-lookup"><span data-stu-id="3382b-158">The toggle fold/unfold commands can be used for that.</span></span>

<span data-ttu-id="3382b-159">Por ejemplo, para plegar todas las regiones, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3382b-159">For example, to fold all regions, do the following:</span></span>

- <span data-ttu-id="3382b-160">Pulse **Ctrl+K**</span><span class="sxs-lookup"><span data-stu-id="3382b-160">Press **Ctrl+K**</span></span>

  <span data-ttu-id="3382b-161">– O bien –</span><span class="sxs-lookup"><span data-stu-id="3382b-161">-or-</span></span>

- <span data-ttu-id="3382b-162">Pulse **F1**, **FO**, seleccione **Plegar todo** y luego presione **Entrar**</span><span class="sxs-lookup"><span data-stu-id="3382b-162">Press **F1**, press **FO**, select **Fold all**, and then press **Enter**</span></span>

<span data-ttu-id="3382b-163">Para desplegar todas las regiones, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3382b-163">To unfold all regions, do the following:</span></span>

- <span data-ttu-id="3382b-164">Pulse **Ctrl+J**</span><span class="sxs-lookup"><span data-stu-id="3382b-164">Press **Ctrl+J**</span></span>

  <span data-ttu-id="3382b-165">– O bien –</span><span class="sxs-lookup"><span data-stu-id="3382b-165">-or-</span></span>
  
- <span data-ttu-id="3382b-166">Pulse **F1**, escriba **UN**, seleccione **Desplegar todo** y luego presione **Entrar**</span><span class="sxs-lookup"><span data-stu-id="3382b-166">Press **F1**, type **UN**, select **Unfold all**, and then press **Enter**</span></span>

<span data-ttu-id="3382b-167">[![GIF del editor de fórmulas de ER que muestra el código desplegado](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span><span class="sxs-lookup"><span data-stu-id="3382b-167">[![ER formula editor gif showing code being unfolded](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)</span></span>

## <a name=""></a><span data-ttu-id="3382b-168"><a name="FindAndReplace">Buscar y reemplazar</a></span><span class="sxs-lookup"><span data-stu-id="3382b-168"><a name="FindAndReplace">Find and replace</a></span></span>

<span data-ttu-id="3382b-169">Para buscar ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3382b-169">To find occurrences of certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="3382b-170">Pulse **Ctrl+F** y luego presione **F3** para encontrar la próxima aparición del texto seleccionado, o presione **Mayús+F3** para encontrar la ocurrencia anterior.</span><span class="sxs-lookup"><span data-stu-id="3382b-170">Press **Ctrl+F** and then press **F3** to find the next occurrence of the selected text, or press **Shift+F3** to find the previous occurrence.</span></span>

  <span data-ttu-id="3382b-171">– O bien –</span><span class="sxs-lookup"><span data-stu-id="3382b-171">-or-</span></span>
  
- <span data-ttu-id="3382b-172">Pulse **F1**, escriba **F** y luego seleccione la opción requerida para encontrar el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3382b-172">Press **F1**, type **F**, and then select the required option to find the selected text.</span></span>

<span data-ttu-id="3382b-173">Para reemplazar ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3382b-173">To replace occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="3382b-174">Pulse **Ctrl+H**.</span><span class="sxs-lookup"><span data-stu-id="3382b-174">Press **Ctrl+H**.</span></span> <span data-ttu-id="3382b-175">Introduzca el texto alternativo y seleccione la opción de reemplazo para reemplazar el texto seleccionado o todas las apariciones de este texto en la expresión actual.</span><span class="sxs-lookup"><span data-stu-id="3382b-175">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

  <span data-ttu-id="3382b-176">– O bien –</span><span class="sxs-lookup"><span data-stu-id="3382b-176">-or-</span></span>
  
- <span data-ttu-id="3382b-177">Pulse **F1**, escriba **R** y luego seleccione la opción requerida para reemplazar el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3382b-177">Press **F1**, type **R**, and then select the required option to replace the selected text.</span></span> <span data-ttu-id="3382b-178">Introduzca el texto alternativo y seleccione la opción de reemplazo para reemplazar el texto seleccionado o todas las apariciones de este texto en la expresión actual.</span><span class="sxs-lookup"><span data-stu-id="3382b-178">Enter the alternative text and select the replacement option to replace either the selected text or all occurrences of this text in the current expression.</span></span>

<span data-ttu-id="3382b-179">Para cambiar todas las ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3382b-179">To change all occurrences of a certain text, select the text in your expression, and do the following:</span></span>

- <span data-ttu-id="3382b-180">Pulse **Ctrl+F2** y luego introduzca el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="3382b-180">Press **Ctrl+F2** and then enter the alternative text.</span></span>

  <span data-ttu-id="3382b-181">– O bien –</span><span class="sxs-lookup"><span data-stu-id="3382b-181">-or-</span></span>
  
- <span data-ttu-id="3382b-182">Pulse **F1**, escriba **C** y luego seleccione la opción requerida para cambiar el texto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3382b-182">Press **F1**, type **C**, and then select the required option to change the selected text.</span></span> <span data-ttu-id="3382b-183">Introduzca el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="3382b-183">Enter the alternative text.</span></span>

<span data-ttu-id="3382b-184">[![GIF del editor de fórmulas de ER que muestra buscar y reemplazar](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span><span class="sxs-lookup"><span data-stu-id="3382b-184">[![ER formula editor gif showing find and replace](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)</span></span>

## <a name=""></a><span data-ttu-id="3382b-185"><a name="DataPasting">Fuentes de datos y pegado de funciones</a></span><span class="sxs-lookup"><span data-stu-id="3382b-185"><a name="DataPasting">Data sources and functions pasting</a></span></span>

<span data-ttu-id="3382b-186">Puede elegir **Agregar origen de datos**, que pega a la expresión actual el origen de datos seleccionado actualmente en el panel izquierdo **Origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="3382b-186">You can select **Add data source**, which pastes to the current expression a data source that is currently selected on the **Data source** left panel.</span></span> <span data-ttu-id="3382b-187">De manera similar, puede elegir **Agregar función**, que pega en la expresión actual la función seleccionada actualmente en el panel derecho **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="3382b-187">Simlilarly, you can select **Add function**, which pastes to the current expression a function that is currently selected on the **Functions** right panel.</span></span> <span data-ttu-id="3382b-188">Si usa el editor de fórmulas ER, una función seleccionada o un origen de datos seleccionado siempre se pegará al final de la expresión configurada.</span><span class="sxs-lookup"><span data-stu-id="3382b-188">If you use the ER formula editor, a selected function or a selected data source will always be pasted to the end of the configured expression.</span></span> <span data-ttu-id="3382b-189">Si usa el editor avanzado de fórmulas ER, una función seleccionada o un origen de datos seleccionado se puede pegar en cualquier parte de la expresión configurada.</span><span class="sxs-lookup"><span data-stu-id="3382b-189">When you use the advanced ER formula editor, a selected function or a selected data source can be pasted to any part of the configured expression.</span></span> <span data-ttu-id="3382b-190">Deberá usar el cursor para especificar dónde desea pegar los datos.</span><span class="sxs-lookup"><span data-stu-id="3382b-190">You will need to use the cursor to specify where you want to paste the data.</span></span>

<span data-ttu-id="3382b-191">[![GIF del editor de fórmulas de ER que muestra cómo agregar una fuente de datos y pegar una función](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span><span class="sxs-lookup"><span data-stu-id="3382b-191">[![ER formula editor gif showing adding a data source and pasting a function](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)</span></span>

## <a name=""></a><span data-ttu-id="3382b-192"><a name="SyntaxColorization">Colorización de sintaxis</a></span><span class="sxs-lookup"><span data-stu-id="3382b-192"><a name="SyntaxColorization">Syntax colorization</a></span></span>

<span data-ttu-id="3382b-193">Actualmente, se utilizan diferentes colores para resaltar las siguientes partes de las expresiones:</span><span class="sxs-lookup"><span data-stu-id="3382b-193">Currently, different colors are used to highlight the following parts of expressions:</span></span>

- <span data-ttu-id="3382b-194">El texto entre corchetes dobles que puede representar un id. de etiqueta de una constante de texto.</span><span class="sxs-lookup"><span data-stu-id="3382b-194">The text in double brackets that can represent a label ID of a text constant.</span></span>

<span data-ttu-id="3382b-195">[![Editor de fórmulas ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span><span class="sxs-lookup"><span data-stu-id="3382b-195">[![ER formula editor](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)</span></span>

## <a name="limitations"></a><span data-ttu-id="3382b-196">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="3382b-196">Limitations</span></span>

<span data-ttu-id="3382b-197">El editor actualmente es compatible con los siguientes navegadores web:</span><span class="sxs-lookup"><span data-stu-id="3382b-197">The editor is currently supported in the following web browsers:</span></span>

- <span data-ttu-id="3382b-198">Chrome</span><span class="sxs-lookup"><span data-stu-id="3382b-198">Chrome</span></span>
- <span data-ttu-id="3382b-199">Borde</span><span class="sxs-lookup"><span data-stu-id="3382b-199">Edge</span></span>
- <span data-ttu-id="3382b-200">Firefox</span><span class="sxs-lookup"><span data-stu-id="3382b-200">Firefox</span></span>
- <span data-ttu-id="3382b-201">Opera</span><span class="sxs-lookup"><span data-stu-id="3382b-201">Opera</span></span>
- <span data-ttu-id="3382b-202">Safari</span><span class="sxs-lookup"><span data-stu-id="3382b-202">Safari</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3382b-203">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="3382b-203">Additional resources</span></span>

- [<span data-ttu-id="3382b-204">Visión general de los informes electrónicos (ER)</span><span class="sxs-lookup"><span data-stu-id="3382b-204">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="3382b-205">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="3382b-205">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)
- [<span data-ttu-id="3382b-206">Editor Monaco</span><span class="sxs-lookup"><span data-stu-id="3382b-206">Monaco editor</span></span>](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
