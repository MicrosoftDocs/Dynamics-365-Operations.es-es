---
title: Funcionalidades de cuadrícula
description: Este artículo describe varias características potentes del control de cuadrícula. Debe activar la nueva característica de cuadrícula para tener acceso a estas capacidades.
author: jasongre
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: a8968a1263dfafd67b07b4beb78c51493e95756e
ms.sourcegitcommit: 47534a943f87a9931066e28f5d59323776e6ac65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2022
ms.locfileid: "9258959"
---
# <a name="grid-capabilities"></a>Funcionalidades de cuadrícula

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El nuevo control de cuadrícula proporciona varias capacidades útiles y potentes que puede utilizar para mejorar la productividad del usuario, construir vistas más interesantes de sus datos y obtener información significativa sobre sus datos. Este artículo cubrirá las siguientes capacidades: 

- Mostrar valores calculados 
- Escribir por delante del sistema
- Evaluar expresiones matemáticas 
- Agrupar datos tabulares (habilitado por separado usando la característica **Agrupación en cuadrículas**)
- Congelar columnas (habilitadas por separado mediante la característica **Congelación de columnas en rejillas**)
- Ancho de columna de ajuste automático
- Columnas extensibles

## <a name="showing-calculated-values"></a>Mostrar valores calculados
En las aplicaciones de finanzas y operaciones, los usuarios pueden ver un valor calculado para cada columna numérica en una cuadrícula. Una sección de pie de página en la parte inferior de la cuadrícula que muestra estos valores calculados.

[![Mostrar valores calculados en cuadrículas.](./media/grids-aggregation.png)](./media/grids-aggregation.png)

En las versiones anteriores a la 10.0.29, el total es el único valor calculado admitido. Sin embargo, a partir de la versión 10.0.29, después de habilitar la característica **Capacidades extendidas de agregación de cuadrículas**, los usuarios pueden seleccionar entre los siguientes cuatro valores calculados:

- Mínimo
- Máximo
- Total
- Promedio

Una sola columna puede mostrar solo un tipo de valor calculado. Sin embargo, cada columna de la cuadrícula se puede configurar para mostrar un tipo diferente de valor calculado.

### <a name="showing-the-grid-footer"></a>Mostrar el pie de página de la cuadrícula
Hay un área de pie de página en la parte inferior de cada cuadrícula tabular en las aplicaciones de finanzas y operaciones. El pie de página puede mostrar información valiosa relacionada con los datos que aparecen en la cuadrícula. Algunos ejemplos de esta información son:

- El número de filas seleccionadas en la tabla (cuando selecciona más de un registro)
- Los valores calculados en la parte inferior de las columnas numéricas configuradas (por ejemplo, totales generales)
- El número de filas del conjunto de datos 

Este pie de página está oculto de forma predeterminada, pero puede activarlo. Para mostrar el pie de página de una cuadrícula, seleccione el botón **Opciones de cuadrícula** en el encabezado de cuadrícula y seleccione la opción **Mostrar pie de página**. Después de activar el pie de página para una cuadrícula en particular, esa configuración se recordará hasta que el usuario decida ocultar el pie de página. Para ocultar el pie de página, seleccione **Ocultar pie de página** en el menú **Opciones de cuadrícula**.

### <a name="specifying-columns-with-calculated-values"></a>Especificación de columnas con valores calculados
Actualmente, ninguna columna muestra los valores calculados de forma predeterminada. En cambio, la configuración se considera una actividad de configuración única, como ajustar el ancho de las columnas en las cuadrículas. Una vez que especifique que desea ver un valor calculado para una columna, esa configuración se recordará la próxima vez que visite la página.

Hay dos formas de configurar una columna para mostrar un valor calculado:

- Seleccione y mantenga presionada (o haga clic con el botón derecho) en la columna para la que desea ver un valor calculado. Si la función **Capacidades extendidas de agregación de cuadrículas** está habilitada, seleccione **Ver totales de columna** y luego seleccione el valor calculado deseado. Si esa función no está habilitada, seleccione **Total de esta columna**. Esta acción hace que ocurran tres eventos:

    1. El pie de la cuadrícula se hace visible. 
    2. Se guarda su preferencia para ver un valor calculado para la columna. 
    3. Se iniciará un cálculo deseado para la columna y cualquier otra que haya configurado previamente para mostrar un valor calculado. El tiempo que se requiere para mostrar los valores calculados depende del tamaño del conjunto de datos.

- Después de que el pie de página esté visible, seleccione **Mostrar totales** (o **Seleccionar valor calculado** si la función **Capacidades extendidas de agregación de cuadrículas** está habilitada) en el área de pie de página en la parte inferior de la columna para la que desea ver un valor calculado. Si no hay columnas configuradas, ese botón estará disponible en el pie de página para todas las columnas numéricas.

    Después de configurar al menos una columna para mostrar un valor calculado, **Mostrar totales** (o **Seleccionar valor calculado**) estará disponible solo al pasar el mouse por encima o al enfocar. La acción de seleccionar el botón solo guarda su preferencia para ver un valor calculado en la columna, de modo que la preferencia se aplique durante futuras visitas a la página. En el pie de página, este estado se indica mediante un guión que aparece en la columna. (Tenga en cuenta que el valor calculado aparecerá inmediatamente si el conjunto de datos es lo suficientemente pequeño).

Si comete un error y ya no desea ver un valor calculado en una columna específica, seleccione y mantenga presionada (o haga clic con el botón derecho) en la columna y luego seleccione **Ocultar total** (o **Ver totales de columna \> Ninguna** si la función **Capacidades extendidas de agregación de cuadrículas** está habilitada). Alternativamente, seleccione **Ocultar total** (u **Ocultar valor calculado**) en el pie de página de esa columna. Esta preferencia también se guardará para futuras visitas a la página. 

### <a name="calculating-aggregate-values"></a>Cálculo de valores agregados
Cuando va a una página donde el pie de página está visible y las columnas ya están configuradas para mostrar valores calculados, es posible que esos valores no se muestren en el pie de página. El comportamiento depende del tamaño del conjunto de datos en la página. Si el conjunto de datos es lo suficientemente pequeño, los valores calculados se mostrarán automáticamente, junto con el número de filas en el conjunto de datos. Si hay guiones en el pie de página debajo de las columnas que configuró para los totales, entonces el conjunto de datos es demasiado grande para que el sistema muestre los valores calculados de inmediato. En este caso, se requiere una acción explícita para calcular los valores. Para calcular los valores, seleccione el botón **Calcular** en el pie de página. Alternativamente, seleccione y mantenga presionada (o haga clic con el botón derecho) la columna para la que desea ver el total y luego seleccione **Totalizar esta columna** (o **Ver totales de columna** y luego el valor calculado deseado si la función **Capacidades extendidas de agregación de cuadrículas** está habilitada).

Si el cálculo tarda demasiado en completarse, puede cancelar la operación en cualquier momento seleccionando **Cancelar**. A veces, el conjunto de datos será demasiado grande para calcular valores agregados (un límite impuesto por su organización). En este caso, se le notificará que filtre más sus datos.

> [!NOTE]
> Los administradores del sistema pueden modificar el límite del número de registros que están disponibles para el cálculo de agregados ajustando el parámetro **Número máximo de registros locales para cada cuadrícula** en la página **Opciones de rendimiento del cliente**. El valor predeterminado es de 25 000 registros. Los administradores deben tener cuidado cuando ajusten este valor, porque un valor demasiado grande puede agotar la memoria disponible en la máquina del usuario. Recomendamos qeu el valor no supere los 50 000 registros.

Los valores calculados se actualizarán automáticamente a medida que actualice, elimine o cree filas en el conjunto de datos.

## <a name="typing-ahead-of-the-system"></a>Escribir por delante del sistema
En muchos escenarios comerciales, la capacidad de introducir datos rápidamente en el sistema es muy importante. Antes de que se introdujera el nuevo control de cuadrícula, los usuarios podían cambiar los datos solo en la fila actual. Por lo tanto, después de realizar cambios en una fila, los usuarios no podían cambiar a una fila diferente ni crear una fila nueva hasta que el sistema validara correctamente los cambios en la fila actual y (en el caso de la creación de filas) ejecutara toda la lógica asociada. con la creación de una nueva fila. Para ayudar a reducir la cantidad de tiempo que los usuarios invierten esperando a que se completen estas operaciones y para ayudar a mejorar la productividad del usuario, la nueva cuadrícula ajusta estas acciones para que sean asíncronas. Los usuarios pueden crear nuevas filas o moverse a otras filas para realizar cambios mientras las validaciones de fila anteriores y la lógica de creación de filas están pendientes. 

[![Escribir por delante del sistema.](./media/gridFastEntry-07-25-2022.gif)](./media/gridFastEntry-07-25-2022.gif)

Para admitir este nuevo comportamiento, se ha agregado una nueva columna para el estado de fila a la derecha de la columna de selección de fila cuando la cuadrícula está en modo de edición. Esta columna indica uno de los siguientes estados:

- **En blanco**: ninguna imagen de estado indica que la fila ha sido guardada con éxito por el sistema.
- **Procesamiento pendiente**: este estado indica que los cambios en la fila aún no han sido guardados por el servidor, pero están en una cola de cambios que deben procesarse. Antes de tomar medidas fuera de la cuadrícula, debe esperar a que se procesen todos los cambios pendientes. Además, el texto en estas filas está en cursiva para indicar el estado no guardado de las filas. 
- **Estado no válido**: este estado indica que se activó alguna advertencia o mensaje durante el procesamiento de la fila, y podría haber evitado que el sistema guarde los cambios en esa fila. En la cuadrícula antigua, si la operación de guardado resultó incorrecta, se le hubiera obligado a volver a la fila para solucionar el problema de inmediato. Sin embargo, en la nueva cuadrícula, se le notifica que se encontró un problema de validación, pero puede decidir cuándo desea solucionarlo. Cuando esté listo para solucionar un problema, puede mover manualmente el foco de nuevo a la fila. Alternativamente, puede seleccionar la acción **Solucionar este problema**. Esta acción mueve inmediatamente el foco a la fila que tiene el problema y le permite realizar modificaciones dentro o fuera de la cuadrícula. Tenga en cuenta que el procesamiento de las filas pendientes posteriores se detiene hasta que se resuelve esta advertencia de validación. 
- **Pausado**: este estado indica que el procesamiento por parte del servidor está en pausa porque la validación de la fila activó un cuadro de diálogo emergente que requiere la intervención del usuario. Debido a que el usuario podría estar introduciendo datos en alguna otra fila, el cuadro de diálogo emergente no se presenta de inmediato a ese usuario. En cambio, se presentará cuando el usuario elija reanudar el procesamiento. Este estado va acompañado de una notificación que informa al usuario sobre la situación. La notificación incluye una acción **Reanudar procesamiento** que activa el cuadro de diálogo emergente.

### <a name="differences-when-entering-data-ahead-of-the-system"></a>Diferencias al ingresar datos antes del sistema
Cuando ingresa datos antes del lugar donde el sistema está procesando, puede esperar algunos cambios en la experiencia de ingreso de datos:

- Notará que no hay listas desplegables de búsqueda, los valores de campo no se validan después de pasar a una columna diferente en la misma fila y las columnas inicialmente no muestran valores predeterminados. Este comportamiento ocurre cuando crea o actualiza antes que el sistema. Sin embargo, después de que el sistema alcance el lugar donde está editando actualmente, se reanudará la experiencia estándar. Si realizó cambios en un campo que normalmente recibe un valor predeterminado, sus cambios anulan el valor del campo predeterminado cuando el servidor comienza a procesar la fila.
- Si crea una nueva fila utilizando la tecla **Flecha hacia abajo**, todas las columnas de la cuadrícula aparecerán como editables. De forma predeterminada, el foco se colocará en la primera columna de la nueva fila. Es posible que esta columna no sea la misma columna que recibió el enfoque inicial en la cuadrícula heredada o la misma columna que recibe el enfoque después de seleccionar un botón **Nuevo**. Su organización puede personalizar el sistema y cambiar la columna que recibe el enfoque inicial cuando se selecciona la tecla **Flecha hacia abajo**. Para obtener más información, consulte la sección [Especificar la columna que recibe el foco inicial cuando se crean nuevas filas usando la tecla de flecha hacia abajo](#developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key). Independientemente, puede usar la personalización para optimizar cada cuadrícula para la entrada de datos. Específicamente, puede reordenar los campos para que la primera columna sea la columna en la que desea comenzar a ingresar datos. También es posible que desee reordenar los campos en general para la entrada de datos, para reducir las tabulaciones y ocultar los campos que no son necesarios para la entrada de datos en esta vista en particular.

### <a name="pasting-from-excel"></a>Pegar desde Excel
Los usuarios siempre han podido exportar datos de cuadrículas en aplicaciones de finanzas y operaciones a Microsoft Excel utilizando el mecanismo **Exportar a Excel**. Sin embargo, la capacidad de introducir datos por delante del sistema permite que la nueva cuadrícula admita copiar tablas de Excel y pegarlas directamente en cuadrículas en las aplicaciones de finanzas y operaciones. La celda de la cuadrícula desde la que se inicia la operación de pegado determina dónde comienza a pegarse la tabla copiada. El contenido de la cuadrícula se sobrescribe con el contenido de la tabla copiada, excepto en dos casos:

- Si el número de columnas en la tabla copiada excede el número de columnas que permanecen en la cuadrícula, comenzando desde la ubicación de pegado, se notifica al usuario de que se han ignorado las columnas adicionales. 
- Si el número de filas en la tabla copiada excede el número de filas en la cuadrícula, comenzando desde la ubicación de pegado, el contenido pegado sobrescribe las celdas existentes y las filas adicionales de la tabla copiada se insertan como nuevas filas en la parte inferior de la cuadrícula. 

## <a name="evaluating-math-expressions"></a>Evaluar expresiones matemáticas
Como un refuerzo de productividad, los usuarios pueden introducir fórmulas matemáticas en celdas numéricas en una cuadrícula. No tienen que hacer el cálculo en una aplicación fuera del sistema. Por ejemplo, si introduce **= 15\*4** y después pulsa la tecla **Tab** para salir del campo, el sistema evaluará la expresión y guardará un valor de **60** para el campo.

[![Evaluar expresiones matemáticas.](./media/gridMathExpression-07-25-2022.gif)](./media/gridMathExpression-07-25-2022.gif)

Para que el sistema reconozca un valor como una expresión, comience el valor con un signo igual (**=**). Para obtener más información sobre los operadores y la sintaxis compatibles, consulte [Símbolos matemáticos admitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

A partir de la versión 10.0.29, la capacidad de evaluar expresiones matemáticas en controles numéricos se ha ampliado y ahora también está disponible fuera de la cuadrícula.

## <a name="grouping-tabular-data"></a>Agrupación de datos tabulares
Los usuarios comerciales a menudo tienen que realizar análisis de datos ad-hoc. Aunque este análisis se puede hacer exportando datos a Microsoft Excel y usando tablas dinámicas, la característica **Agrupación en cuadrículas**, que depende de la característica de control de cuadrículas nuevas, permite a los usuarios organizar sus datos de manera interesante dentro de las aplicaciones de finanzas y operaciones. Dado que esta característica extiende la característica **Valores calculados**, **Agrupamiento** permite obtener información significativa sobre los datos al proporcionar valores calculados (por ejemplo, subtotales) en el nivel de grupo.

[![Agrupación de datos en una cuadrícula.](./media/grids-groupingWithTotals.png)](./media/grids-groupingWithTotals.png)

Para usar esta característica, haga clic con el botón derecho en la columna que desea agrupar y seleccione **Agrupar por esta columna**. Esta acción ordenará los datos por la columna seleccionada, agregará un nuevo **Agrupar por** columna al principio de la cuadrícula e insertará "filas de encabezado" al comienzo de cada grupo. Estas filas de encabezado proporcionan la siguiente información sobre cada grupo:

- Valor de datos para el grupo 
- Nombre de columna (esta información es especialmente útil cuando tenga múltiples niveles de agrupación)
- Número de filas de datos en este grupo
- Valores calculados para cualquier columna configurada (por ejemplo, subtotales si la columna está configurada para mostrar un total)

Con [Vistas guardadas](saved-views.md) habilitado, puede guardar la agrupación como parte de una vista en páginas que permiten guardar consultas en vistas. Por ejemplo, aquellos con selectores de vista grandes. Consulte la sección [Cambiar entre vistas](saved-views.md#switching-between-views) para obtener más información. 

### <a name="multiple-levels-of-grouping"></a>Múltiples niveles de agrupación
Una vez que haya agrupado los datos en una sola columna, puede agrupar los datos en una columna diferente seleccionando **Agrupar por esta columna** en la columna deseada. Este proceso se puede repetir hasta que tenga 5 niveles anidados de agrupación, que es la profundidad máxima admitida. En este punto, ya no podrá agrupar por columnas adicionales.

En cualquier momento, puede eliminar la agrupación en cualquier columna haciendo clic derecho en esa columna y seleccionando **Desagrupar**. También puede eliminar la agrupación de todas las columnas seleccionando **Opciones de cuadrícula** y después **Desagrupar todo**.

### <a name="sorting-grouped-data"></a>Ordenar datos agrupados
Después de agrupar datos por una o más columnas, puede cambiar la dirección de ordenación de cualquier columna de agrupación a través del encabezado de columna correspondiente. 

Si ordena en una columna no agrupada, la agrupación permanece intacta. Los datos se ordenan dentro de cada grupo, según la columna seleccionada.

### <a name="expanding-and-collapsing-groups"></a>Expandir y contraer grupos
La agrupación inicial de datos tendrá todos los grupos expandidos. Puede crear vistas resumidas de los datos contrayendo grupos individuales, o puede usar la expansión y contracción de grupos para ayudar a navegar a través de los datos. Para expandir o contraer un grupo, seleccione el botón de chevron (>) en la fila de encabezado del grupo correspondiente. Tenga en cuenta que el estado expandir/contraer de grupos individuales **no** está guardado en la personalización.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Seleccionar y anular la selección de filas en el nivel de grupo
De la misma manera que puede seleccionar (o anular la selección) todas las filas de la cuadrícula seleccionando la casilla de verificación en la parte superior de la primera columna de la cuadrícula, también puede seleccionar rápidamente (o anular la selección) todas las filas de un grupo seleccionando la casilla de verificación en la fila de encabezado de grupo correspondiente. La casilla de verificación en la fila del encabezado del grupo siempre reflejará el estado de selección actual de las filas de ese grupo, independientemente de si todas las filas están seleccionadas, no hay filas seleccionadas o solo algunas filas están seleccionadas.

### <a name="hiding-column-names"></a>Ocultar nombres de columnas
Al agrupar datos, el comportamiento predeterminado es mostrar el nombre de la columna en la fila del encabezado del grupo. Puede optar por suprimir el nombre de la columna en las filas de encabezado de grupo seleccionando **Opciones de cuadrícula** > **Ocultar el nombre de la columna del grupo**.

### <a name="grouping-on-date-and-time-columns"></a>Agrupación en columnas de fecha y hora
Al agrupar por los campos fecha o fecha y hora, tiene la opción de agrupar por año, mes o día. El "valor" del grupo en la fila de encabezado correspondiente coincidirá con el formato de ese campo. Además, para los campos DateTime y Time, podrá agrupar por hora, minuto o segundo.

> [!IMPORTANT]
> Actualmente, los usuarios no pueden agregar una columna de agrupación después de agruparse en un segmento de una columna de fecha u hora.

## <a name="freezing-columns"></a>Columnas de congelación
Algunas columnas en una cuadrícula pueden ser lo suficientemente importantes para el contexto como para que no desee que se desplacen fuera de la vista. En su lugar, puede que desee que los valores de esas columnas estén siempre visibles. La característica **Congelar columnas en la cuadrícula** proporciona esta flexibilidad a los usuarios. 

[![Congelando columnas en una cuadrícula.](./media/gridFreezingColumns-07-25-2022.gif)](./media/gridFreezingColumns-07-25-2022.gif)

Para congelar una columna, haga clic con el botón derecho en el encabezado de la columna y luego seleccione **Congelar columna**. La primera vez que completa este paso, la columna seleccionada se convierte en la primera columna y ya no se desplazará fuera de la vista. Cualquier columna posterior que congele se agregará a la derecha de la última columna congelada. Puede utilizar la función Mover estándar para reordenar las columnas inmovilizadas según sus necesidades. Sin embargo, las columnas congeladas no se pueden mover para que aparezcan entre el conjunto de columnas no congeladas. De igual modo, las columnas no congeladas no se pueden mover para que aparezcan entre el conjunto de columnas congeladas.

Para descongelar una columna, haga clic con el botón derecho en el encabezado de la columna congelada y luego seleccione **Descongelar columna**. 

Tenga en cuenta que las columnas de selección de fila y estado de fila en la nueva cuadrícula siempre están congeladas como las dos primeras columnas. Por lo tanto, cuando estas columnas se incluyen en una cuadrícula, siempre estarán visibles para los usuarios, independientemente de la posición de desplazamiento horizontal en la cuadrícula. Estas dos columnas no se pueden reordenar.

## <a name="autofit-column-width"></a>Ancho de columna de ajuste automático
Como en Excel, los usuarios pueden forzar automáticamente el cambio de tamaño de una columna en función del contenido que se muestre actualmente en ella. Simplemente toque dos veces (o haga doble clic) los controladores de tamaño en la columna. Alternativamente, ponga el foco en el encabezado de la columna y luego seleccione la tecla **A** (para ajuste automático).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>¿Cómo habilito el nuevo control de cuadrícula en mi entorno? 

La característica **Nuevo control de cuadrícula** está disponible directamente en la administración de características de cualquier entorno. Después de habilitar la función en Administración de características, todas las sesiones de usuario posteriores utilizarán el nuevo control de cuadrículas. 

Esta característica comenzó a estar habilitada por defecto en la versión 10.0.21. Está previsto que sea obligatorio en octubre de 2022.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Desarrollador] Desactivar páginas individuales para que no usen la nueva cuadrícula 
Si su organización detecta una página que tiene problemas al utilizar la nueva cuadrícula, hay una API disponible para permitir que un formulario individual use el control de cuadrícula heredado al mismo tiempo que permite que el resto del sistema utilice el nuevo control de cuadrícula. Para excluir una página individual de la nueva cuadrícula, agregue la siguiente publicación de llamada `super()` en el método `run()` del formulario.

```this.forceLegacyGrid();```

Esta API eventualmente quedará obsoleta para permitir la eliminación del control de cuadrícula heredado. Sin embargo, permanecerá disponible durante al menos 12 meses después de que se anuncie su desuso. Si algún problema requiere el uso de esta API, notifíqueselo a Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forzar una página a usar la nueva cuadrícula después de haber optado previamente por no recibir la cuadrícula
Si ha optado por que una página individual no use la nueva cuadrícula, es posible que desee volver a habilitar la nueva cuadrícula después de que se hayan resuelto los problemas subyacentes. Para hacer esto, simplemente necesita eliminar la llamada a `forceLegacyGrid()`. El cambio no entrará en vigor hasta que ocurra una de las siguientes situaciones:

- **Reimplementación del entorno**: cuando un entorno se actualiza y se vuelve a implementar, la tabla que almacena las páginas que se excluyeron de la nueva cuadrícula (FormControlReactGridState) se borra automáticamente.
- **Borrado manual de la tabla**: para escenarios de desarrollo, deberá usar SQL para borrar la tabla FormControlReactGridState y luego reiniciar el AOS. Esta combinación de acciones restablecerá el almacenamiento en caché de las páginas que se excluyeron de la nueva cuadrícula.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Desarrollador] Optar por cuadrículas individuales fuera de la capacidad de escribir antes de la capacidad del sistema
Han surgido algunos escenarios que no se prestan para trabajar bien con la capacidad *Escribir antes que el sistema* de la red. (Por ejemplo, algún código que se activa cuando se valida una fila hace que se active una búsqueda de fuentes de datos, y la investigación puede dañar ediciones no confirmadas en filas existentes). Si su organización descubre tal escenario, hay una API disponible que le permite a un el desarrollador excluye una cuadrícula individual de la validación de filas asíncrona y vuelve al comportamiento heredado.

Cuando la validación de filas asincrónicas está deshabilitada en una cuadrícula, los usuarios no pueden crear una nueva fila o moverse a una fila existente diferente en la cuadrícula mientras haya problemas de validación en la fila actual. Como efecto secundario de esta acción, las tablas no se pueden pegar desde Excel en cuadrículas de finanzas y operaciones.

Para excluir una cuadrícula individual de una validación de filas asincrónica, agregue la siguiente llamada después de `super()` en el método `run()` del formulario.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Esta llamada debe invocarse solo en casos excepcionales y no debe ser la norma para todas las redes.
> - No recomendamos que alterne esta API en tiempo de ejecución después de que se cargue el formulario.

## <a name="developer-size-to-available-width-columns"></a>[Desarrollador] Columnas de tamaño hasta el ancho disponible
Si un desarrollador establece la propiedad **WidthMode** en **SizeToAvailable** para las columnas que hay dentro de la nueva cuadrícula, esas columnas tendrán inicialmente el mismo ancho que tendrían si la propiedad estuviera establecida en **SizeToContent**. Sin embargo, se estiran para utilizar el ancho adicional disponible en la cuadrícula. Si la propiedad se establece en **SizeToAvailable** para varias columnas, todas esas columnas compartirán el ancho adicional disponible en la cuadrícula. Sin embargo, si un usuario cambia manualmente el tamaño de una de esas columnas, la columna se volverá estática. Permanecerá en ese ancho y ya no se estirará para ocupar el ancho de cuadrícula adicional disponible.

## <a name="developer-specifying-the-column-that-receives-the-initial-focus-when-new-rows-are-created-by-using-the-down-arrow-key"></a>[Desarrollador] Especificar la columna que recibe el foco inicial cuando se crean nuevas filas usando la tecla de flecha hacia abajo
Como se discutió en la sección [Diferencias al ingresar datos antes del sistema](#differences-when-entering-data-ahead-of-the-system), si la capacidad "Escribiendo antes que el sistema" está habilitada, y un usuario crea una nueva fila usando la tecla **Flecha hacia abajo**, el comportamiento predeterminado es poner el foco en la primera columna de la nueva fila. Esta experiencia puede diferir de la experiencia en la cuadrícula heredada o cuando se selecciona el botón **Nuevo**.

Los usuarios y las organizaciones pueden crear vistas guardadas que están optimizadas para la entrada de datos. (Por ejemplo, puede reordenar las columnas para que la primera columna sea en la que desea comenzar a ingresar datos). Además, a partir de la versión 10.0.29, las organizaciones pueden ajustar este comportamiento mediante el método **selectedControlOnCreate()**. Este método permite a un desarrollador especificar la columna que debe recibir el foco inicial cuando se crea una nueva fila usando la tecla de **flecha hacia abajo**. Como entrada, esta API toma el ID de control que corresponde a la columna que debe recibir el foco inicial.

## <a name="known-issues"></a>Problemas conocidos
Esta sección mantiene una lista de problemas conocidos para el nuevo control de cuadrícula.

### <a name="open-issues"></a>Problemas abiertos
- Después de habilitar la característica **Nuevo control de cuadrícula**, algunas páginas continuarán utilizando el control de cuadrícula existente. Esto ocurrirá en las siguientes situaciones:
 
    - Existe una lista de tarjetas en la página que se representa en varias columnas.
    - Existe una lista de tarjetas agrupadas en la página.
    - Una columna de cuadrícula con un control extensible sin reacción.

    Cuando un usuario encuentra por primera vez una de estas situaciones, aparecerá un mensaje sobre la actualización de la página. Después de que aparezca este mensaje, la página continuará utilizando la cuadrícula existente para todos los usuarios hasta la próxima actualización de la versión del producto. Se considerará una mejor administración de estos escenarios, para que se pueda utilizar la nueva cuadrícula, en una actualización futura.

- [KB 4582758] Los registros aparecen borrosos cuando cambia el zoom de 100 a cualquier otro porcentaje

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

