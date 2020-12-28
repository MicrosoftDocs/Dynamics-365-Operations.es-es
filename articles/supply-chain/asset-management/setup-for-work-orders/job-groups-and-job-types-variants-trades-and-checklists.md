---
title: Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento
description: En este tema se describen las categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetJobTypeDefaultForecast, EntAssetJobTrade, EntAssetJobTypeDefaultCopy, EntAssetChecklistVariableValueLookup, EntAssetChecklistTemplateCreate, EntAssetJobVariant, EntAssetJobTypeDefaultReference, EntAssetJobTypeDefaultChecklist, EntAssetJobTypeDefault, EntAssetJobType, EntAssetJobTypeDefaultChecklistCopy, EntAssetChecklistTemplate, EntAssetJobTypeDefaultDescription, EntAssetJobTypeLookup, EntAssetJobTypeDefaultToolCopy, EntAssetJobTypePreviewPart, EntAssetJobTypeDefaultTool, EntAssetJobTypeDefaultForecastCopy, EntAssetChecklistTemplateLookup, EntAssetJobGroup, EntAssetChecklistVariable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8bf7c53a6150a2beeca5c6e9b5ab4ea98584158d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436835"
---
# <a name="maintenance-job-type-categories-and-maintenance-job-types-maintenance-job-type-variants-maintenance-job-trades-and-maintenance-checklists"></a>Categorías del tipo de trabajo de mantenimiento y tipos de trabajo de mantenimiento, variantes del tipo de trabajo de mantenimiento, comercios de trabajo de mantenimiento y listas de comprobación de mantenimiento

[!include [banner](../../includes/banner.md)]

 

Se adjunta un tipo de activo a cada activo. Los tipos de activo definen los tipos de trabajo de mantenimiento (y por lo tanto, los trabajos de mantenimiento) que se pueden realizar en los activos. Cuando crea una orden de trabajo, debe seleccionar un tipo de trabajo de mantenimiento. Puede seleccionar solo los tipos de trabajo de mantenimiento relacionadas con la configuración del tipo de activo que se usa para el activo.

Para una visión general gráfica de los activos y los tipos de trabajo de mantenimiento, y su conexión con las órdenes de trabajo, consulte [Ubicaciones técnicas y activos](../overview/functional-locations-and-objects.md).

Las variantes de tipo de trabajo de mantenimiento se pueden configurar en un tipo de trabajo de mantenimiento. Las variantes del tipo de trabajo de mantenimiento definen las variaciones de un tipo de trabajo, como los tamaños (pequeño, medio o grande), los períodos (semanal, cada dos semanas, mensual o cada tres meses) y las configuraciones (bajo estándar, flexible o alto rendimiento).

Las operaciones comerciales de trabajos de mantenimiento proporcionan información sobre los sectores profesionales como el de mecánica, eléctrico e hidráulico. Los requisitos de competencia se pueden establecer en un comercio de trabajo de mantenimiento. Todos los comercios de trabajos de mantenimiento se pueden usar en relación con todos los tipos de trabajo de mantenimiento. La selección de una variante del tipo de trabajo de mantenimiento o comercio del trabajo de mantenimiento en una orden de trabajo es opcional.

Para cada tipo de trabajo de mantenimiento, se pueden crear variaciones de la configuración del tipo de trabajo de mantenimiento. Por ejemplo, si tiene un tipo de trabajo de mantenimiento que se denomina **Servicio**, puede crear las variaciones siguientes para ese tipo de trabajo de mantenimiento: **Camiones a 30 000 km**, **Coches a 30 000 km** y **Furgonetas a 30 000 km**.

Las categorías del tipo de trabajo de mantenimiento se utilizan para obtener un grupo de tipos de trabajo de mantenimiento para propósitos de visión general. Entre los ejemplos de categorías de tipo de trabajo de mantenimiento, se incluyen **Calibración**, **Inspección**, **Revisión** e **Instrumentación**.

Las plantillas de la lista de comprobación de mantenimiento y las variables de la lista de comprobación de mantenimiento se utilizan para configurar las listas de comprobación de mantenimiento. Las listas de comprobación de mantenimiento se configuran en tipos de trabajo de mantenimiento y se usan en órdenes de trabajo.

Primero debe configurar las categorías de tipo de trabajo de mantenimiento, las variaciones de tipos de trabajo de mantenimiento y los comercios de trabajo de mantenimiento. A continuación, cree los tipos de trabajo de mantenimiento. Finalmente, en la página **Valores predeterminados de tipos de trabajo de mantenimiento**, cree todas las variaciones de tipos de trabajo de mantenimiento necesarias para su equipo. En esa página, también puede configurar previsiones, listas de comprobación de mantenimiento y las herramientas para una combinación de tipos de trabajo de mantenimiento.

> [!NOTE]
> Un tipo de trabajo de mantenimiento se puede relacionar con solo una categoría de tipo de trabajo de mantenimiento.

## <a name="create-a-maintenance-job-type-category"></a>Crear una categoría de tipo de trabajo de mantenimiento

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajos** \> **Categorías de tipo de trabajo de mantenimiento**.
2. Seleccione **Nuevo**.
3. En el campo **Categoría de tipo de trabajo de mantenimiento** , especifique un identificador para la categoría el tipo de trabajo de mantenimiento.
4. Escriba un nombre en el campo **Nombre**.

    Después de relacionar categorías del tipo de trabajo de mantenimiento con los tipos de trabajo de mantenimiento, el campo **Tipos de trabajo** muestra el número de tipos de trabajo de mantenimiento relacionados con esta categoría del tipo de trabajo de mantenimiento.

![Página de categorías de tipo de trabajo de mantenimiento](media/01-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type-variant"></a>Crear una variante de tipo de trabajo de mantenimiento

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajos** \> **Variantes de tipo de trabajo de mantenimiento**.
2. Seleccione **Nuevo**.
3. En el campo **Variante de tipo de trabajo de mantenimiento**, especifique un identificador para la variante de tipo de trabajo de mantenimiento.
4. En el campo **Descripción**, escriba una descripción.
5. En la ficha desplegable **Tipos de trabajo de mantenimiento**, seleccione **Agregar** para agregar un tipo de trabajo de mantenimiento.
6. En el campo **Tipo de trabajo de mantenimiento**, seleccione el tipo de trabajo de mantenimiento.
7. Repita los pasos del 5 al 6 para agregar más tipos de trabajo de mantenimiento a la variante de tipo de trabajo de mantenimiento.

    En la ficha desplegable **Detalles**, el campo **Tipos de trabajo** muestra el número de tipos de trabajo de mantenimiento que se han agregado a esta variante del tipo de trabajo de mantenimiento.

![Página de variantes de tipo de trabajo de mantenimiento](media/02-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-trade"></a>Crear un comercio de trabajo de mantenimiento

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajos** \> **Comercio de trabajo de mantenimiento**.
2. Seleccione **Nuevo**.
3. En el campo **Comercio**, especifique un identificador para el comercio del trabajo de mantenimiento.
4. En el campo **Descripción**, escriba una descripción.
5. En la ficha desplegable **Aptitudes**, seleccione **Agregar** para agregar una nueva aptitud que debe estar relacionada con el comercio del trabajo de mantenimiento.
6. En el campo **Aptitud**, seleccione la aptitud.
7. En el campo **Nivel**, seleccione el nivel de aptitud.
8. Repita los pasos del 5 al 7 para agregar más aptitudes al comercio del trabajo de mantenimiento.

    En la ficha desplegable **Detalles**, el campo **Aptitudes** muestra el número de aptitudes que se han agregado a este comercio del trabajo de mantenimiento.

9. En el ficha desplegable **Certificados**, seleccione **Agregar** para agregar un certificado para el comercio del trabajo de mantenimiento.
10. En el campo **Tipo de certificado**, seleccione el certificado.
11. Repita los pasos del 9 al 10 para agregar más certificados al comercio del trabajo de mantenimiento.

    En la ficha desplegable **Detalles**, el campo **Certificados** muestra el número de certificados que se han agregado a este comercio del trabajo de mantenimiento.

![Página de comercio de trabajo de mantenimiento](media/03-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-variable"></a>Crear una variable de la lista de comprobación de mantenimiento

Al crear las líneas de lista de comprobación de mantenimiento en el valor predeterminado del tipo de trabajo de mantenimiento, debe seleccionar un tipo de la lista de comprobación de mantenimiento. **Variable** es un tipo de la lista de comprobación de mantenimiento. Se usa para definir un posible resultado en un intervalo en una línea de la lista de comprobación de mantenimiento relacionada con una línea de orden de trabajo. Una variable le permite crear un conjunto de resultados predefinidos sin tener que crear una medida precisa.

**Ejemplo 1:** Puede medir el nivel de aceite definiendo tres valores: **Nivel demasiado alto**, **Nivel demasiado bajo** y **Nivel dentro del intervalo**. Por cada valor, defina si el resultado del valor es **Apto**, **No apto** o **Ninguno**.

**Ejemplo 2:** Realiza una inspección visual de un elemento del equipo para evaluar el desgaste y uso.

1. Seleccione **Administración de activos** \> **Configuración** \> **Listas de comprobación de mantenimiento** \> **Variables de listas de comprobación de mantenimiento**.
2. Seleccione **Nuevo**.
3. En el campo **Variable**, especifique un identificador para la variable de la lista de comprobación mantenimiento.
4. Escriba un nombre en el campo **Nombre**.
5. En la ficha desplegable **General** , seleccione **Agregar** para agregar una línea para una variable.

    Se especifica automáticamente un número de línea secuencia en el campo **Número de línea**. Una vez agregar todas las líneas, puede cambiar los números de línea como sea necesario. Al seleccionar la línea y luego pulsar la tecla **Flecha abajo**, el siguiente número de la secuencia se especifica automáticamente en la siguiente línea.

6. En el campo **Valor**, especifique una descripción para el valor.
7. En el campo **Resultado**, seleccione un resultado para la línea.

![Página de variables de lista de comprobación de mantenimiento](media/04-setup-for-work-orders.png)

## <a name="create-a-maintenance-checklist-template"></a>Crear una plantilla de la lista de comprobación de mantenimiento

Las plantillas de la lista de comprobación de mantenimiento se pueden usar como un conjunto común de tareas que un trabajador debe realizar para completar una orden de trabajo correctamente. Se hace referencia a las plantillas desde las líneas de la lista de comprobación de mantenimiento en el valor predeterminado del tipo de trabajo de mantenimiento. Las plantillas pueden hacer referencia en múltiples líneas de valor predeterminado del tipo de trabajo de mantenimiento. Por lo tanto, puede volver a usar con facilidad un conjunto de tareas comunes de la lista de comprobación de mantenimiento. Entre los ejemplos de plantillas de lista de comprobación de mantenimiento se incluyen instrucciones de seguridad general y una lista de los artículos y condiciones que se deben comprobar en una bomba específica o modelos similares de banda transportadora.

1. Seleccione **Administración de activos** \> **Configuración** \> **Listas de comprobación de mantenimiento** \> **Plantillas de listas de comprobación de mantenimiento**.
2. Seleccione **Nuevo**.

    Un identificador de plantilla se especifica automáticamente en el campo **Plantilla de lista de comprobación de mantenimiento** .

3. En el campo **Nombre**, escriba un nombre para la plantilla de lista de comprobación de mantenimiento.
4. En la ficha desplegable **Líneas de la lista de comprobación de mantenimiento**, seleccione **Agregar** para agregar una línea de plantilla.

    Se especifica automáticamente un número de línea secuencia en el campo **Número de línea**. Una vez agregar todas las líneas, puede cambiar los números de línea como sea necesario. Al seleccionar la línea y luego pulsar la tecla **Flecha abajo**, el siguiente número de la secuencia se especifica automáticamente en la siguiente línea.

5. En el campo **Tipo**, seleccione un tipo para la línea de la lista de comprobación de mantenimiento. Para cada tipo de lista de comprobación de mantenimiento, la ficha desplegable **Detalles de línea** muestra los campos relacionados. Los siguientes valores están disponibles:

    - **Texto**: la línea tiene texto que describe qué hacer. Utilice este tipo de lista de comprobación de mantenimiento si quiere que un trabajador compruebe o inspeccione algo, pero sin esperar resultados específicos (medibles). Tras seleccionar este tipo, especifique un nombre o un encabezado en el campo **Nombre**. En el campo **Instrucciones**, escriba una descripción de qué se debe hacer. Si el paso es obligatorio para la lista de comprobación de mantenimiento, establezca la opción **Obligatorio** en **Sí**.
    - **Encabezado**: la línea se utiliza como encabezado para agrupar las líneas de la lista de comprobación de mantenimiento que aparecen debajo de esta. Este tipo es útil si tiene varias líneas de la lista de comprobación de mantenimiento que se pueden dividir en áreas específicas. Los encabezados proporcionan una visión general para el trabajador que completará una lista de comprobación de mantenimiento con varias líneas de la lista de comprobación de mantenimiento. Tras seleccionar este tipo, especifique un nombre descriptivo en el campo **Nombre**.
    - **Plantilla**: la línea se utiliza para crear una referencia a una plantilla existente. Tras seleccionar este tipo, especifique un nombre para la plantilla en el campo **Nombre**. En el campo **Plantilla**, seleccione la plantilla.
    - **Variable**: la línea se utiliza para definir un posible resultado en un intervalo. Para obtener información sobre cómo configurar variables de la lista de comprobación de mantenimiento, vea la sección [Crear una variable de lista de comprobación de mantenimiento](#create-a-maintenance-checklist-variable). Tras seleccionar este tipo, especifique un nombre descriptivo para la variable en el campo **Nombre**. En el campo **Variable**, seleccione la variable. En el campo **Instrucciones**, escriba una descripción de qué se debe hacer. Si el paso es obligatorio para la lista de comprobación de mantenimiento, establezca la opción **Obligatorio** en **Sí**.
    - **Medida**: la línea se usa para registrar una medida concreta. Puede configurar la medida que debe estar relacionada con un contador predefinido. Tras seleccionar este tipo, especifique un nombre para la plantilla en el campo **Nombre**. Si este paso es obligatorio para la lista de comprobación de mantenimiento, establezca la opción **Obligatorio** en **Sí**. Si desea usar la línea de medida como registro de contador, seleccione el contador en el campo **Contador**. El campo **Unidad** relacionado se actualiza automáticamente. Si ha seleccionado un contador, seleccione el método de actualización en el campo **Valor**. En los campos **Valor mínimo** y **Valor máximo**, especifique el intervalo permitido del valor. En el campo **Instrucciones**, escriba una descripción de qué se debe hacer.

        > [!NOTE]
        > Las líneas del tipo **Medida** que no tenga una configuración de contador se trata como un registro independiente de medidas independiente para el que no hay seguimiento automático en Administración de activos. Del mismo modo, si el tipo de contador seleccionado no está presente en el activo relacionado con la orden de trabajo, la tarea de la lista de comprobación de mantenimiento se trata como una medida independiente. El valor del contador se puede cambiar varias veces. No se registra hasta que el [estado del ciclo de vida de la orden de trabajo](work-order-lifecycle-states.md) se cambie a un estado donde la opción **Procesar lista de comprobación de mantenimiento** esté establecida en **Sí**.

    En la ficha desplegable **Detalles**, el campo **Comprobaciones** muestra el número total de líneas de lista de comprobación en la plantilla. Este número incluye las líneas anidadas en cualquier plantilla existente a la que haya hecho referencia en la plantilla.

![Página de plantillas de lista de comprobación de mantenimiento](media/05-setup-for-work-orders.png)

## <a name="create-a-maintenance-job-type"></a>Crear un tipo de trabajo de mantenimiento

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajos** \> **Tipos de trabajo de mantenimiento**.
2. Seleccione **Nuevo**.
3. En el campo **Tipo de trabajo de mantenimiento** , especifique un identificador para el tipo de trabajo de mantenimiento.
4. Escriba un nombre en el campo **Nombre**.

    La ficha desplegable **Detalles** muestra una visión general del número de variantes del tipo de trabajo de mantenimiento, las aptitudes, los certificados, los trabajos posteriores y los tipos de activo que se han creado en este tipo de trabajo de mantenimiento. El campo **Líneas de instalación** muestra el número de líneas predeterminadas del tipo de trabajo de mantenimiento que se han configurado en este tipo de trabajo de mantenimiento. El campo **Activos** muestra el número de activos que están activos y que usan actualmente este tipo de trabajo de mantenimiento.

5. En la ficha desplegable **General**, en el campo **Categoría de tipo de trabajo de mantenimiento**, seleccione una categoría de tipo de trabajo de mantenimiento.
6. Establezca la opción **Actividades de tiempo de inactividad por mantenimiento** en **Sí** si el tipo de trabajo por mantenimiento requiere una parada por mantenimiento del equipo antes de que el trabajo pueda realizarse.
7. En la ficha desplegable **Descripción**, escriba una descripción del tipo de trabajo de mantenimiento.
8. En la ficha desplegable **Variantes del tipo de trabajo de mantenimiento**, puede agregar variantes al tipo de trabajo de mantenimiento.
9. En las fichas desplegable **Aptitudes necesarias** y **Certificados necesarios**, puede agregar aptitudes y certificar requisitos al tipo de trabajo de mantenimiento.
10. Si un tipo de trabajo de trabajo de mantenimiento específico se debe realizar a continuación, agréguelo a la ficha desplegable **Trabajos posteriores**. También puede configurar una variante y comercio del tipo de trabajo de mantenimiento que estén relacionados con el tipo de trabajo de mantenimiento. Si el trabajo posterior comienza un número específico de días antes o después de que el trabajo que usa este tipo de trabajo de mantenimiento haya comenzado, especifique el número de días en el campo **Retraso por días**. Los números positivos representan días después de que empiece el trabajo relacionado y los números negativos representan los días antes del inicio programado del trabajo relacionado. Por ejemplo, si especifica **5**, el trabajo posterior comenzará cinco días después del inicio del trabajo que está relacionado con el tipo del trabajo de mantenimiento. Si especifica **-3**, el trabajo posterior comenzará tres días antes del inicio programado del trabajo que está relacionado con el tipo del trabajo de mantenimiento.

    > [!NOTE]
    > Si agrega más de una línea del tipo de trabajo de mantenimiento, la secuencia de las líneas indica el orden en que se deben ejecutar. La secuencia comienza en la parte superior de la lista.

11. En la ficha desplegable **Tipos de activo**, puede agregar tipos de activo al tipo de trabajo de mantenimiento.

![Página de tipos de trabajo de mantenimiento](media/06-setup-for-work-orders.png)

## <a name="create-maintenance-job-type-default-lines-and-related-forecasts-maintenance-checklists-tools-description-and-attachments"></a>Crear líneas predeterminadas del tipo de trabajo de mantenimiento y previsiones relacionadas, listas de comprobación de mantenimiento, herramientas, descripciones y datos adjuntos

1. Seleccione **Administración de activos** \> **Configuración** \> **Trabajos** \> **Valores predeterminados del tipo de trabajo de mantenimiento**.

    O bien

    Seleccione **Administración de activos** \> **Configuración** \> **Trabajos** \> **Tipos de trabajo de mantenimiento**, seleccione un tipo de trabajo de mantenimiento y, a continuación, seleccione **Valores predeterminados del tipo de trabajo de mantenimiento**.

2. Seleccione **Nuevo**.
3. En los campos **Ubicación técnica**, **Tipo de activo**, **Fabricante**, **Modelo** y **Activo**, seleccione valores apropiados, en función de lo específico que debe ser el valor predeterminado del tipo de trabajo de mantenimiento.
4. En el campo **Tipo de trabajo de mantenimiento**, seleccione un tipo de trabajo de mantenimiento si no se hubiera seleccionado automáticamente.
5. En los campos **Variante del tipo de trabajo de mantenimiento** y **Comercio**, seleccione un tipo de trabajo de mantenimiento y un comercio de trabajo de mantenimiento según necesite.
6. Seleccionar **Previsión**.
7. En la página **Previsión de valor predeterminado del tipo de trabajo de mantenimiento**, puede hacer previsiones sobre las horas, los artículos y los gastos. En las fichas relevantes, seleccione **Agregar**, y realice las selecciones para crear las previsiones necesarias para el tipo de trabajo de mantenimiento.
8. En la pestaña **Previsión de artículos**, puede seleccionar las dimensiones del inventario que deben mostrarse en la línea de artículo. Seleccione **Inventario** \> **Dimensiones**, seleccione las dimensiones que se mostrarán, establezca la opción **Guardar configuración** en **Sí** y, a continuación, seleccione **Aceptar**.
9. En la pestaña **Previsión de artículos**, seleccione **Dónde se usó el artículo** para obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos en relación con los activos, los valores predeterminados del tipo de trabajo de mantenimiento, las piezas de repuesto y las órdenes de trabajo. 

    La ficha desplegable **Totales de previsión de mantenimiento** muestra una visión general de los totales de previsión. Esta visión general incluye el número total de las horas y las líneas de previsión que se han creado.

    > [!NOTE]
    > Para copiar la configuración de la previsión desde otro tipo de trabajo de mantenimiento, seleccione **Copiar previsión**, y seleccione el tipo de trabajo de mantenimiento desde donde copiar la configuración.

11. Seleccione **Guardar** para guardar los cambios.
12. Cierre la página **Previsión del valor predeterminado del tipo de trabajo de mantenimiento** para volver a la página **Valores predeterminados del tipo de trabajo de mantenimiento**.
13. Seleccione **Lista de comprobación de mantenimiento**.
14. En la página **Lista de comprobación de los valores predeterminados del tipo de trabajo de mantenimiento**, puede agregar líneas de la lista de comprobación de mantenimiento al valor predeterminado del tipo de trabajo de mantenimiento seleccionado. En la ficha desplegable **Líneas de comprobación de mantenimiento**, seleccione **Nuevo** para agregar una línea de lista de comprobación de mantenimiento.

    Los números de línea se introducen automáticamente en el campo **Número de línea** para indicar la secuencia de las líneas de la lista de comprobación de mantenimiento. Puede editar los números de línea como lo necesite. Después de crear la primera línea de la lista de comprobación de mantenimiento, selecciónela y, a continuación, presione la tecla **Flecha abajo** para agregar una línea por debajo de ella. De manera alternativa, puede seleccionar una línea de la lista de comprobación de mantenimiento y después seleccionar **Nuevo**. En este caso, se agrega una nueva línea sobre la línea seleccionada de la lista de comprobación de mantenimiento.

15. En el campo **Tipo**, seleccione el tipo de línea y, a continuación, agregue la información relacionada con el tipo de la lista de comprobación de mantenimiento. Para obtener una descripción de los tipos disponibles y los campos relacionados, consulte la sección [Crear una plantilla de lista de comprobación de mantenimiento](#create-a-maintenance-checklist-template).

    > [!NOTE]
    > Para copiar la configuración de la lista de comprobación de mantenimiento desde otro tipo de trabajo de mantenimiento, seleccione **Copiar lista de comprobación de mantenimiento**, y seleccione el tipo de trabajo de mantenimiento desde donde copiar la configuración.
    >
    > Puede crear fácilmente una plantilla a partir de una lista de comprobación de mantenimiento existente. A continuación puede volver a usar la plantilla en múltiples listas de comprobación de mantenimiento. La nueva plantilla será una copia exacta de la lista de comprobación de mantenimiento. Seleccione **Crear plantilla** y escriba un nombre para la plantilla. Para sustituir la lista de comprobación existente con una sola línea que haga referencia a la plantilla nueva, establezca la opción **Reemplazar** en **Sí**. Puede ver el contenido de la plantilla en la página de detalles **Plantillas de lista de comprobación de mantenimiento**.

16. Seleccione **Guardar** para guardar los cambios.
17. Vuelva a la página **Valores predeterminados del tipo de trabajo de mantenimiento**.
18. Seleccione **Herramientas**.
19. En la página **Herramientas predeterminadas del tipo de trabajo de mantenimiento**, puede agregar las herramientas (recursos) que se deben usar para el tipo de trabajo de mantenimiento. Seleccione **Nuevo** y, después, seleccione la herramienta en el campo **Recursos**.

    > [!NOTE]
    > Para copiar la configuración de la herramienta desde otro tipo de trabajo de mantenimiento, seleccione **Copiar herramientas**, y seleccione el tipo de trabajo de mantenimiento desde donde copiar la configuración.

20. Seleccione **Guardar** para guardar los cambios.
21. Vuelva a la página **Valores predeterminados del tipo de trabajo de mantenimiento**.
22. Seleccionar **Descripción del trabajo**.
23. En la página **Descripción del trabajo**, seleccione **Editar** y, después, agregue una descripción que esté relacionada con el valor predeterminado del tipo de trabajo de mantenimiento seleccionado, como sea necesario.
24. Seleccione **Guardar** para guardar la descripción.

    Si agrega una descripción del trabajo aquí, anula la descripción que se configura para el tipo de trabajo de mantenimiento en la página **Tipos de trabajo de mantenimiento**. Si no agrega una descripción del trabajo aquí, se utiliza cualquier descripción que se haya configurado para el tipo de trabajo de mantenimiento. Las descripciones se transfieren automáticamente a las órdenes de trabajo que usan el tipo de trabajo de mantenimiento o valor predeterminado del tipo de trabajo de mantenimiento.

25. Vuelva a la página **Valores predeterminados del tipo de trabajo de mantenimiento**.
26. Para configurar los datos adjuntos en una línea predeterminada de tipo de trabajo de mantenimiento, seleccionada, seleccione **Adjuntar documentos**. Los datos adjuntos que se configuran en una línea predeterminada de tipo de trabajo de mantenimiento se incluyen automáticamente en las líneas de orden de trabajo que usan esa línea predeterminada de tipo de trabajo de mantenimiento.
27. Seleccione **Nuevo** y, después, seleccione un tipo de documento.
28. Cargue el documento o el archivo.
29. Establezca los campos en la página **Archivos adjuntos**. La configuración de los archivos adjuntos usa la funcionalidad de configuración de documentos estándar.
30. Seleccione **Guardar** para el archivo adjunto.

    > [!NOTE]
    > Los datos adjuntos en una línea predeterminada del tipo de trabajo de mantenimiento se imprimen a la vez con un informe de órdenes de trabajo solo si los tipos de documento de los archivos adjuntos se seleccionan en la pestaña **Tipos de documento** de la página **Parámetros de administración de activos** (**Administración de activos** \> **Configuración** \> **Parámetros de administración de activos**). Los ejemplos de archivos adjuntos incluyen instrucciones que explican cómo completar un trabajo específico o una lista de comprobación de mantenimiento predefinida (si no utiliza la funcionalidad de lista de comprobación de mantenimiento para las líneas predeterminadas de tipo de trabajo de mantenimiento).

    En la página **Valores predeterminados del tipo de trabajo de mantenimiento**, cada línea muestra el número de horas previstas, así como el número de líneas que se han creado para los artículos, los gastos, las listas de comprobación de mantenimiento y las herramientas. El campo **Activos** muestra el número de activos que están relacionados con la línea predeterminada del tipo de trabajo de mantenimiento.

31. Para copiar un valor predeterminado del tipo de trabajo de mantenimiento a otro valor predeterminado del tipo de trabajo de mantenimiento, seleccione la línea predeterminada del tipo de trabajo de mantenimiento para copiar a otra configuración, seleccione **Copiar configuración** y seleccione el valor predeterminado del tipo de trabajo de mantenimiento para copiar.
32. Para ver una lista de los activos, los planes de mantenimiento o las rondas de mantenimiento que actualmente usan una línea predeterminada de tipo de trabajo de mantenimiento, selecciónela y, a continuación, seleccione **Utilizado por**.

![Página de tipos predeterminados de trabajo de mantenimiento](media/07-setup-for-work-orders.png)

Cuando el sistema selecciona el valor predeterminado disponible del tipo de trabajo de mantenimiento que se debería usarse en una línea de orden de trabajo, la selección se basa en el activo y en la configuración del tipo activo relacionado. Administración de activos revisa todos los registros de tipo predeterminado de trabajo de mantenimiento relacionados con el tipo de trabajo de mantenimiento que se asocia al tipo de activo para el que hay que comprobar si hay coincidencias posibles. Comprueba siempre primero la combinación más específica. Es decir para encontrar la combinación más específica, Administración de activos primero busca una posible coincidencia para el campo **Comercio**. Si no se encuentra ninguna coincidencia, comprueba si hay una coincidencia para el campo **Variante de tipo de trabajo de mantenimiento**. Si no se encuentra coincidencias, busca una coincidencia para el campo **Tipo de trabajo de mantenimiento**, etc. (**Comercio**, luego **Variante del tipo de trabajo de mantenimiento**, luego **Tipo de trabajo de mantenimiento**, luego **Activo**, luego **Modelo** y después **Fabricante** y, a continuación **Tipo de activo**). Si no se encuentra ninguna coincidencia, se utiliza el registro predeterminado donde solo se ha seleccionado el tipo de trabajo de mantenimiento.

Un identificador de la actividad de proyecto se relaciona automáticamente con cada línea predeterminada del tipo de trabajo de mantenimiento que cree. La actividad del proyecto se crea en el proyecto de previsión que se selecciona en el campo **Proyecto de previsión de mantenimiento** en la pestaña **Activos** de la página **Parámetros de administración de activos**. El propósito de la actividad de proyecto es gestionar previsiones de horas, artículos, gastos y en relación con las órdenes de trabajo. Las previsiones del tipo de trabajo de mantenimiento se transfieren automáticamente a la línea de orden de trabajo y se copian del proyecto de la previsión al proyecto de la orden de trabajo que se crea para la línea de orden de trabajo. El propósito de la actividad de proyecto es gestionar previsiones en relación con las órdenes de trabajo.

Puede configurar un trabajo por lotes para actualizar referencias predeterminadas del tipo de trabajo de mantenimiento en intervalos regulares o puede ejecutar manualmente el trabajo. Para crear un trabajo por lotes o ejecutar una actualización manual, seleccione **Administración de activos** \> **Periódico** \> **Mantenimiento preventivo** \> **Actualizar referencias predeterminadas del tipo de trabajo de mantenimiento**.

## <a name="overview-of-maintenance-job-types-that-are-related-to-assets"></a>Visión general de los tipos de trabajo de mantenimiento relacionadas con los activos

Una vez creadas las combinaciones necesarias predeterminadas de tipo de trabajo de mantenimiento, puede usar la página **Todos los activos** para obtener una visión general del valor predeterminado actual del tipo de trabajo de mantenimiento relacionado con un activo específico. La visión general muestra todas las combinaciones predeterminadas del tipo de trabajo de mantenimiento que se pueden utilizar en el tipo de activo seleccionado para el activo. Estas combinaciones incluyen combinaciones que tienen variaciones de variantes del tipo de trabajo de mantenimiento y comercios de trabajo de mantenimiento.

1. Seleccione **Administración de activos** \> **Común** \> **Activos** \> **Todos los activos** o **Activos activos**.
2. En la lista, seleccione el activo para obtener una visión general de las combinaciones de tipos de trabajo de mantenimiento.
3. En el panel de acciones, en la ficha **General** del grupo **Información relacionada**, seleccione **Tipos de trabajo de mantenimiento**.

    El panel izquierdo de la página **Tipos de trabajo de mantenimiento del activo** muestra una lista de todas las combinaciones de tipos de trabajo de mantenimiento relacionados con el activo seleccionado.

4. Seleccione una combinación de tipos de trabajo de mantenimiento para ver la configuración relacionada para la listas de comprobación de mantenimiento, las previsiones y las herramientas. La sección **Detalles** en la pestaña desplegable **Valores predeterminados del tipo de trabajo de mantenimiento** muestra el número de listas de comprobación de mantenimiento, las horas previstas, los artículos, etc., relacionados con el tipo de combinación de tipos de trabajo de mantenimiento seleccionado.
5. Para ver los detalles para el tipo de trabajo de mantenimiento seleccionado, seleccione **Tipos de trabajo de mantenimiento**.

![Página de tipos de activos de trabajo de mantenimiento](media/08-setup-for-work-orders.png)

## <a name="automatic-update-of-maintenance-job-type-forecasts"></a>Actualización automática de las previsiones de tipos de trabajo de mantenimiento

En Administración de activos, puede actualizar automáticamente los cambios en las previsiones de tipos de trabajo de mantenimiento en lo que respecta a costes por hora, costes de artículo y gastos, que se han actualizado en otros módulos. De esta manera, ayuda a garantizar que las previsiones de tipos de trabajo de mantenimiento usen siempre los últimos precios de coste.

1. Seleccione **Administración de activos** \> **Periódico** \> **Previsión** \> **Actualizar previsión de tipos de trabajo de mantenimiento**.
2. En el cuadro de diálogo **Actualizar previsión de tipos de trabajo de mantenimiento**, en la ficha desplegable **Registros que incluir**, puede agregar las selecciones para los tipos de trabajo de mantenimiento específicos según sea necesario. Seleccione **Filtrar** y, después, seleccione **Seleccionar** para hacer selecciones.
3. En la pestaña desplegable **Ejecutar en segundo plano**, puede configurar la actualización automática como un trabajo por lotes según sea necesario.
4. Seleccione **Aceptar** para iniciar la actualización de la previsión.
