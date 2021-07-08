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
# <a name="electronic-reporting-advanced-formula-editor"></a>Editor de fórmulas avanzadas de informes electrónicos

[!include [banner](../includes/banner.md)]

Además del [editor de fórmulas ](general-electronic-reporting-formula-designer.md) de [informes electrónicos ](general-electronic-reporting.md), puede usar el editor avanzado de fórmulas de informes electrónicos para mejorar la experiencia de configurar expresiones de informes electrónicos (ER). El editor avanzado está basado en el navegador y funciona con el [editor Monaco](https://microsoft.github.io/monaco-editor). Las características avanzadas más utilizadas del editor se describen en este tema:

- [Autoformato de código](#Autoformatting)
- [IntelliSense](#IntelliSense)
- [Finalización del código](#CodeCompletion)
- [Navegación por el código](#CodeNavigation)
- [Estructuración del código](#CodeStructuring)
- [Buscar y reemplazar](#FindAndReplace)
- [Pegado de datos](#DataPasting)
- [Colorización de sintaxis](#SyntaxColorization)

## <a name=""></a><a name="ActivateAdvEditor">Activar el editor avanzado de fórmulas</a>

Complete los siguientes pasos para comenzar a usar el editor de fórmulas avanzado en su instancia de Microsoft Dynamics 365 Finance.

1.  Vaya a **Administración de la organización** \> **Informes electrónicos** \> **Configuraciones**.
2.  En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
3.  En el cuadro de diálogo **Parámetros del usuario**, en la sección **Seguimiento de ejecución**, establezca el parámetro **Habilitar editor avanzado de fórmulas** en **Sí**.

[![Cuadro de diálogo de parámetros de usuario, parámetro Habilitar editor de fórmulas avanzado resaltado](./media/ER-AdvEditor-Activate.png)](./media/ER-AdvEditor-Activate.png)

> [!NOTE]
> Tenga en cuenta que este parámetro es específico del usuario y específico de la compañía.

Comenzando en Microsoft Dynamics 365 Finance versión 10.0.19, puede controlar qué editor de fórmulas ER se ofrece de forma predeterminada. Complete los siguientes pasos para habilitar el editor de fórmulas avanzado para todos los usuarios y empresas de la instancia de Finance actual.

1.  Abra el espacio de trabajo **Administración de características**.
2.  Busque y seleccione la función **Configure el editor de fórmulas avanzado de ER como el predeterminado para todos los usuarios** en la lista y luego seleccione **Habilitado ahora**.
3.  Vaya a **Administración de la organización** > **Informes electrónicos** > **Configuraciones**.
4.  En la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
5.  En el cuadro de diálogo **Parámetros de usuario**, busque el parámetro **Deshabilitar el editor de fórmulas avanzado** y verifique que esté configurado en **No**.

[![Cuadro de diálogo de parámetros de usuario, parámetro Deshabilitar editor de fórmulas avanzado resaltado](./media/ER-AdvEditor-Activate2.png)](./media/ER-AdvEditor-Activate2.png)

> [!NOTE]
> Los valores de los parámetros **Habilitar el editor de fórmulas avanzado** y **Deshabilitar el editor de fórmulas avanzado** se mantienen separados para cada usuario y se ofrecen en el cuadro de diálogo **Parámetros de usuario** en función del estado de la función **Configure el editor de fórmulas avanzado de ER como el predeterminado para todos los usuarios**.

## <a name=""></a><a name="Autoformatting">Autoformato de código</a>

Cuando escribe una expresión compleja que consta de varias filas de código, se aplica automáticamente sangría a una nueva línea introducida en función de la sangría de la fila anterior. Puede seleccionar líneas y cambiar la sangría introduciendo **Tabulador** o **Mayús+Tabulador**.

[![GIF del editor de fórmulas ER que muestra la selección de líneas y el cambio de la sangría](./media/ER-AdvEditor-Indentation.gif)](./media/ER-AdvEditor-Indentation.gif)

El formato automático permite mantener toda la expresión bien formateada para facilitar el mantenimiento y simplificar la comprensión de la lógica configurada.

## <a name=""></a><a name="IntelliSense">IntelliSense</a>

El editor proporciona finalización de palabras para ayudarle a escribir expresiones más rápido y evitar errores tipográficos. Cuando comienza a agregar texto nuevo, el editor ofrece automáticamente una lista de funciones compatibles con las funciones de ER que contienen los caracteres que ha introducido. También puede activar IntelliSense en cualquier lugar de una expresión configurada escribiendo **Ctrl+espacio**.

[![GIF del editor de fórmulas de ER que muestra la activación de IntelliSense](./media/ER-AdvEditor-Intelisense.gif)](./media/ER-AdvEditor-Intelisense.gif)

## <a name=""></a><a name="CodeCompletion">Finalización del código</a>

El editor proporciona automáticamente la finalización del código mediante:

- Inserción de un corchete de cierre cuando se introduce un corchete de apertura, manteniendo el cursor dentro de los corchetes.
- Inserción del segundo signo de comillas cuando se ingresa el primero, manteniendo el cursor dentro de las comillas.
- Inserción del segundo símbolo de comillas dobles cuando se ingresa el primero, manteniendo el cursor dentro de las comillas.

[![GIF del editor de fórmulas ER que muestra el editor que proporciona automáticamente la finalización del código](./media/ER-AdvEditor-CodeCompletion.gif)](./media/ER-AdvEditor-CodeCompletion.gif)

Cuando señala el paréntesis escrito, el segundo paréntesis de este par se resalta automáticamente para mostrar la construcción que admiten.

## <a name=""></a><a name="CodeNavigation">Navegación por el código</a>

Puede localizar los símbolos o las líneas requeridos en su expresión escribiendo el comando **Ir a** usando la paleta de comandos o el menú contextual.

Por ejemplo, para saltar a la línea **8**, haga lo siguiente:

- Pulse **Ctrl+G**, ingrese el valor **8** y luego presione **Entrar**.

  – O bien –

- Pulse **F1**, escriba **G**, seleccione **Ir a línea**, ingrese el valor **8** y pulse **Entrar**.

[![GIF del editor de fórmulas de ER que muestra cómo ubicar partes de una expresión usando la paleta de comandos](./media/ER-AdvEditor-Goto.gif)](./media/ER-AdvEditor-Goto.gif)

## <a name=""></a><a name="CodeStructuring">Estructuración del código</a>

El código para algunas funciones, como [IF](er-functions-logical-if.md) o [CASE](er-functions-logical-case.md), se estructura automáticamente. Puede expandir y contraer cualquiera o todas las regiones plegables del código para reducir la parte editable de una expresión y centrarse solo en el fragmento de código que requiere su atención. Los comandos de alternar plegar/desplegar se usan para eso.

Por ejemplo, para plegar todas las regiones, haga lo siguiente:

- Pulse **Ctrl+K**

  – O bien –

- Pulse **F1**, **FO**, seleccione **Plegar todo** y luego presione **Entrar**

Para desplegar todas las regiones, haga lo siguiente:

- Pulse **Ctrl+J**

  – O bien –
  
- Pulse **F1**, escriba **UN**, seleccione **Desplegar todo** y luego presione **Entrar**

[![GIF del editor de fórmulas de ER que muestra el código desplegado](./media/ER-AdvEditor-ToggleFold.gif)](./media/ER-AdvEditor-ToggleFold.gif)

## <a name=""></a><a name="FindAndReplace">Buscar y reemplazar</a>

Para buscar ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:

- Pulse **Ctrl+F** y luego presione **F3** para encontrar la próxima aparición del texto seleccionado, o presione **Mayús+F3** para encontrar la ocurrencia anterior.

  – O bien –
  
- Pulse **F1**, escriba **F** y luego seleccione la opción requerida para encontrar el texto seleccionado.

Para reemplazar ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:

- Pulse **Ctrl+H**. Introduzca el texto alternativo y seleccione la opción de reemplazo para reemplazar el texto seleccionado o todas las apariciones de este texto en la expresión actual.

  – O bien –
  
- Pulse **F1**, escriba **R** y luego seleccione la opción requerida para reemplazar el texto seleccionado. Introduzca el texto alternativo y seleccione la opción de reemplazo para reemplazar el texto seleccionado o todas las apariciones de este texto en la expresión actual.

Para cambiar todas las ocurrencias de cierto texto, seleccione el texto en la expresión y haga lo siguiente:

- Pulse **Ctrl+F2** y luego introduzca el texto alternativo.

  – O bien –
  
- Pulse **F1**, escriba **C** y luego seleccione la opción requerida para cambiar el texto seleccionado. Introduzca el texto alternativo.

[![GIF del editor de fórmulas de ER que muestra buscar y reemplazar](./media/ER-AdvEditor-Find.gif)](./media/ER-AdvEditor-Find.gif)

## <a name=""></a><a name="DataPasting">Fuentes de datos y pegado de funciones</a>

Puede elegir **Agregar origen de datos**, que pega a la expresión actual el origen de datos seleccionado actualmente en el panel izquierdo **Origen de datos**. De manera similar, puede elegir **Agregar función**, que pega en la expresión actual la función seleccionada actualmente en el panel derecho **Funciones**. Si usa el editor de fórmulas ER, una función seleccionada o un origen de datos seleccionado siempre se pegará al final de la expresión configurada. Si usa el editor avanzado de fórmulas ER, una función seleccionada o un origen de datos seleccionado se puede pegar en cualquier parte de la expresión configurada. Deberá usar el cursor para especificar dónde desea pegar los datos.

[![GIF del editor de fórmulas de ER que muestra cómo agregar una fuente de datos y pegar una función](./media/ER-AdvEditor-PasteValue.gif)](./media/ER-AdvEditor-PasteValue.gif)

## <a name=""></a><a name="SyntaxColorization">Colorización de sintaxis</a>

Actualmente, se utilizan diferentes colores para resaltar las siguientes partes de las expresiones:

- El texto entre corchetes dobles que puede representar un id. de etiqueta de una constante de texto.

[![Editor de fórmulas ER](./media/ER-AdvEditor-SyntaxColorization.png)](./media/ER-AdvEditor-SyntaxColorization.png)

## <a name="limitations"></a>Limitaciones

El editor actualmente es compatible con los siguientes navegadores web:

- Chrome
- Borde
- Firefox
- Opera
- Safari

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos (ER)](general-electronic-reporting.md)
- [Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)
- [Editor Monaco](https://microsoft.github.io/monaco-editor)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
