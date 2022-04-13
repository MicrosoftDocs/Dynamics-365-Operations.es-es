---
title: Funcionalidad de cuadrícula
description: Este tema describe varias características potentes del control de cuadrícula. Debe activar la nueva característica de cuadrícula para tener acceso a estas capacidades.
author: jasongre
ms.date: 03/21/2022
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
ms.openlocfilehash: 81577f54bd7fdc7d683c760dd4410f27da8ee1f0
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462803"
---
# <a name="grid-capabilities"></a>Funcionalidades de cuadrícula

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El nuevo control de cuadrícula proporciona varias capacidades útiles y potentes que puede utilizar para mejorar la productividad del usuario, construir vistas más interesantes de sus datos y obtener información significativa sobre sus datos. Este artículo cubrirá las siguientes capacidades: 

- Cálculo de los totales
- Escribir por delante del sistema
- Evaluar expresiones matemáticas 
- Agrupar datos tabulares (habilitado por separado usando la característica **Agrupación en cuadrículas**)
- Congelar columnas (habilitadas por separado mediante la característica **Congelación de columnas en rejillas**)
- Ancho de columna de ajuste automático
- Columnas extensibles

## <a name="calculating-totals"></a>Cálculo de los totales
En las aplicaciones de Finance and Operations, los usuarios tienen la capacidad de ver los totales en la parte inferior de las columnas numéricas en las cuadrículas. Una sección de pie de página en la parte inferior de la cuadrícula que muestra estos totales. 

### <a name="showing-the-grid-footer"></a>Mostrar el pie de página de la cuadrícula
Hay un área de pie de página en la parte inferior de cada cuadrícula tabular en las aplicaciones Finance and Operations. El pie de página puede mostrar información valiosa relacionada con los datos que aparecen en la cuadrícula. Algunos ejemplos de esta información son:

- El número de filas seleccionadas en la tabla (cuando selecciona más de un registro)
- Totales generales en la parte inferior de las columnas numéricas configuradas
- El número de filas del conjunto de datos 

Este pie de página está oculto de forma predeterminada, pero puede activarlo. Para mostrar el pie de página de una cuadrícula, seleccione el botón **Opciones de cuadrícula** en el encabezado de cuadrícula y seleccione la opción **Mostrar pie de página**. Después de activar el pie de página para una cuadrícula en particular, esa configuración se recordará hasta que el usuario decida ocultar el pie de página. Para ocultar el pie de página, seleccione **Ocultar pie de página** en el menú **Opciones de cuadrícula**.

### <a name="specifying-columns-with-totals"></a>Especificar columnas con totales
Actualmente, ninguna columna muestra los totales de forma predeterminada. En cambio, esto se considera una actividad de configuración única, similar a ajustar el ancho de las columnas en las cuadrículas. Una vez que especifique que desea ver los totales de una columna, esa configuración se recordará la próxima vez que visite la página.

Hay dos formas de configurar una columna para mostrar un total: 

- Haga clic con el botón derecho en la columna para la que quiere ver un total y después seleccione **Totalizar esta columna**. Esta acción hace que ocurran tres eventos:

    1. El pie de página se hace visible. 
    2. Se guardará su preferencia para ver un total en esta columna. 
    3. Se iniciará un cálculo de totales para esta columna y cualquier otra que haya configurado previamente para ver los totales. El tiempo que se requiere para mostrar un total depende del tamaño del conjunto de datos que está totalizando.

- Después de que el pie de página esté visible, seleccione **Mostrar total** en el área de pie de página en la parte inferior de la columna para la que desea ver un total. Si no hay columnas configuradas, el botón **Mostrar total** estará disponible para todas las columnas numéricas. 

    Una vez que haya al menos una columna configurada para los totales, los botones **Mostrar total** solo estarán disponibles al pasar el ratón o al enfocar. La acción de seleccionar **Mostrar total** solo guarda su preferencia para ver un total en esta columna, de modo que la preferencia se aplique durante futuras visitas a la página. En el pie de página, este estado se indica mediante un guión que aparece en la columna. (Alternativamente, si el conjunto de datos es lo suficientemente pequeño, se muestra un total de inmediato).

Si comete un error y ya no desea ver un total en una columna en particular, haga clic con el botón derecho en la columna y seleccione **Ocultar total** o seleccione el botón **Ocultar total** en el pie de página de esa columna. Esta preferencia también se guardará para futuras visitas a la página. 

### <a name="calculating-totals"></a>Cálculo de los totales
Cuando llega a una página con el pie de página visible y las columnas ya configuradas para los totales, los totales pueden mostrarse o no en el pie de página. El comportamiento depende del tamaño del conjunto de datos en la página. Si el conjunto de datos es lo suficientemente pequeño, los totales se mostrarán automáticamente, junto con el número de filas en el conjunto de datos. Si hay guiones en el pie de página debajo de las columnas que configuró para los totales, entonces el conjunto de datos es demasiado grande para que el sistema muestre los totales de inmediato, y se necesita una acción explícita para calcular los totales. Para hacer esto, haga clic en el botón **Calcular** en el pie de página, o haga clic con el botón derecho en una columna para la que desea un total y seleccione **Totalizar esta columna**.

Si el cálculo tarda demasiado en completarse, puede cancelar la operación seleccionando el botón **Cancelar**. A veces, el conjunto de datos será demasiado grande para calcular los totales (un límite impuesto por su organización) y, en su lugar, se le notificará para que filtre más sus datos. 

> [!NOTE]
> Las administraciones del sistema pueden modificar el límite del número de registros disponibles para el cálculo de totales ajustando el parámetro **Número máximo de registros locales para cada cuadrícula** en la página **Opciones de rendimiento del cliente**. El valor predeterminado es de 25 000 registros. Los administradores deben tener cuidado al ajustar este valor porque un valor demasiado grande puede agotar la memoria disponible en la máquina del usuario. La recomendación es no superar los 50 000 registros.   

Los totales se actualizarán automáticamente a medida que actualice, elimine o cree filas en el conjunto de datos.

## <a name="typing-ahead-of-the-system"></a>Escribir por delante del sistema
En muchos escenarios comerciales, la capacidad de introducir datos rápidamente en el sistema es muy importante. Antes de que se introdujera el nuevo control de cuadrícula, los usuarios podían cambiar los datos solo en la fila actual. Antes de que pudieran crear una nueva fila o cambiar a una fila diferente, debían esperar a que el sistema validara con éxito los cambios. En un intento por reducir la cantidad de tiempo que los usuarios esperan a que se completen estas validaciones y para mejorar la productividad del usuario, la nueva cuadrícula ajusta estas validaciones para que sean asíncronas. Por lo tanto, el usuario puede moverse a otras filas para realizar cambios mientras las validaciones de fila anteriores están pendientes. 

Para admitir este nuevo comportamiento, se ha agregado una nueva columna para el estado de fila a la derecha de la columna de selección de fila cuando la cuadrícula está en modo de edición. Esta columna indica uno de los siguientes estados:

- **En blanco**: ninguna imagen de estado indica que la fila ha sido guardada con éxito por el sistema.
- **Procesamiento pendiente**: este estado indica que los cambios en la fila aún no han sido guardados por el servidor, pero están en una cola de cambios que deben procesarse. Antes de tomar medidas fuera de la cuadrícula, debe esperar a que se procesen todos los cambios pendientes. Además, el texto en estas filas está en cursiva para indicar el estado no guardado de las filas. 
- **Estado no válido**: este estado indica que se activó alguna advertencia o mensaje durante el procesamiento de la fila, y podría haber evitado que el sistema guarde los cambios en esa fila. En la cuadrícula antigua, si la operación de guardado resultó incorrecta, se le hubiera obligado a volver a la fila para solucionar el problema de inmediato. Sin embargo, en la nueva cuadrícula, se le notifica que se encontró un problema de validación, pero puede decidir cuándo desea solucionarlo. Cuando esté listo para solucionar un problema, puede mover manualmente el foco de nuevo a la fila. Alternativamente, puede seleccionar la acción **Solucionar este problema**. Esta acción mueve inmediatamente el foco a la fila que tiene el problema y le permite realizar modificaciones dentro o fuera de la cuadrícula. Tenga en cuenta que el procesamiento de las filas pendientes posteriores se detiene hasta que se resuelve esta advertencia de validación. 
- **Pausado**: este estado indica que el procesamiento por parte del servidor está en pausa porque la validación de la fila activó un cuadro de diálogo emergente que requiere la intervención del usuario. Debido a que el usuario podría estar introduciendo datos en alguna otra fila, el cuadro de diálogo emergente no se presenta de inmediato a ese usuario. En cambio, se presentará cuando el usuario elija reanudar el procesamiento. Este estado va acompañado de una notificación que informa al usuario sobre la situación. La notificación incluye una acción **Reanudar procesamiento** que activa el cuadro de diálogo emergente.

Cuando los usuarios introducen datos con antelación al lugar donde el servidor está procesando, pueden esperar algunas degradaciones en la experiencia de entrada de datos, como la falta de búsquedas, la validación de nivel de control y la entrada de valores predeterminados. Se recomienda a los usuarios que necesitan una lista desplegable para encontrar un valor que esperen a que el servidor se ponga al día con la fila actual. La validación de nivel de control y la entrada de valores predeterminados también ocurrirán cuando el servidor procese esa fila.

### <a name="pasting-from-excel"></a>Pegar desde Excel
Los usuarios siempre han podido exportar datos de cuadrículas en aplicaciones de Finanzas y Operaciones a Microsoft Excel utilizando el mecanismo **Exportar a Excel**. Sin embargo, la capacidad de introducir datos por delante del sistema permite que la nueva cuadrícula admita copiar tablas de Excel y pegarlas directamente en cuadrículas en las aplicaciones de Finance and Operations. La celda de la cuadrícula desde la que se inicia la operación de pegado determina dónde comienza a pegarse la tabla copiada. El contenido de la cuadrícula se sobrescribe con el contenido de la tabla copiada, excepto en dos casos:

- Si el número de columnas en la tabla copiada excede el número de columnas que permanecen en la cuadrícula, comenzando desde la ubicación de pegado, se notifica al usuario de que se han ignorado las columnas adicionales. 
- Si el número de filas en la tabla copiada excede el número de filas en la cuadrícula, comenzando desde la ubicación de pegado, el contenido pegado sobrescribe las celdas existentes y las filas adicionales de la tabla copiada se insertan como nuevas filas en la parte inferior de la cuadrícula. 

## <a name="evaluating-math-expressions"></a>Evaluar expresiones matemáticas
Como un refuerzo de productividad, los usuarios pueden introducir fórmulas matemáticas en celdas numéricas en una cuadrícula. No tienen que hacer el cálculo en una aplicación fuera del sistema. Por ejemplo, si introduce **= 15\*4** y después pulsa la tecla **Tab** para salir del campo, el sistema evaluará la expresión y guardará un valor de **60** para el campo.

Para que el sistema reconozca un valor como una expresión, comience el valor con un signo igual (**=**). Para obtener más información sobre los operadores y la sintaxis compatibles, consulte [Símbolos matemáticos admitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Agrupación de datos tabulares
Los usuarios comerciales a menudo necesitan realizar análisis de datos ad-hoc. Si bien esto se puede hacer exportando datos a Microsoft Excel y usando tablas dinámicas, la característica **Agrupación en cuadrículas**, que depende de la característica de control de cuadrículas nuevas, permite a los usuarios organizar sus datos de manera interesante dentro de las aplicaciones de Finanzas y Operaciones. Dado que esta característica extiende la característica **Totales**, **Agrupamiento** también permite obtener información significativa sobre los datos al proporcionar subtotales a nivel de grupo.

Para usar esta característica, haga clic con el botón derecho en la columna que desea agrupar y seleccione **Agrupar por esta columna**. Esta acción ordenará los datos por la columna seleccionada, agregará un nuevo **Agrupar por** columna al principio de la cuadrícula e insertará "filas de encabezado" al comienzo de cada grupo. Estas filas de encabezado proporcionan la siguiente información sobre cada grupo:

- Valor de datos para el grupo 
- Nombre de columna (esta información es especialmente útil cuando tenga múltiples niveles de agrupación)
- Número de filas de datos en este grupo
- Subtotales para cualquier columna configurada para mostrar totales

Con [Vistas guardadas](saved-views.md) habilitado, esta agrupación se puede guardar mediante personalización como parte de una vista para un acceso rápido la próxima vez que visite la página.

### <a name="multiple-levels-of-grouping"></a>Múltiples niveles de agrupación
Una vez que haya agrupado los datos en una sola columna, puede agrupar los datos en una columna diferente seleccionando **Agrupar por esta columna** en la columna deseada. Este proceso se puede repetir hasta que tenga 5 niveles anidados de agrupación, que es la profundidad máxima admitida. En este punto, ya no podrá agrupar por columnas adicionales.

En cualquier momento, puede eliminar la agrupación en cualquier columna haciendo clic derecho en esa columna y seleccionando **Desagrupar**. También puede eliminar la agrupación de todas las columnas seleccionando **Opciones de cuadrícula** y después **Desagrupar todo**.

### <a name="sorting-grouped-data"></a>Ordenar datos agrupados
Después de agrupar datos por una o más columnas, puede cambiar la dirección de ordenación de cualquier columna de agrupación a través del encabezado de columna correspondiente. 

El comportamiento cuando ordena en columnas no agrupadas depende de la versión de su producto:

- En la versión 10.0.24 y anteriores, si ordena en una columna no agrupada, la agrupación se elimina de todas las columnas y los datos se ordenan en la columna seleccionada. 
- En la versión 10.0.25 y posteriores, si ordena en una columna no agrupada, la agrupación se mantiene intacta y los datos se ordenan dentro de cada grupo, según la columna seleccionada.

### <a name="expanding-and-collapsing-groups"></a>Expandir y contraer grupos
La agrupación inicial de datos tendrá todos los grupos expandidos. Puede crear vistas resumidas de los datos contrayendo grupos individuales, o puede usar la expansión y contracción de grupos para ayudar a navegar a través de los datos. Para expandir o contraer un grupo, seleccione el botón de chevron (>) en la fila de encabezado del grupo correspondiente. Tenga en cuenta que el estado expandir/contraer de grupos individuales **no** está guardado en la personalización.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Seleccionar y anular la selección de filas a nivel de grupo
De la misma manera que puede seleccionar (o anular la selección) todas las filas de la cuadrícula seleccionando la casilla de verificación en la parte superior de la primera columna de la cuadrícula, también puede seleccionar rápidamente (o anular la selección) todas las filas de un grupo seleccionando la casilla de verificación en la fila de encabezado de grupo correspondiente. La casilla de verificación en la fila del encabezado del grupo siempre reflejará el estado de selección actual de las filas de ese grupo, independientemente de si todas las filas están seleccionadas, no hay filas seleccionadas o solo algunas filas están seleccionadas.

### <a name="hiding-column-names"></a>Ocultar nombres de columnas
Al agrupar datos, el comportamiento predeterminado es mostrar el nombre de la columna en la fila del encabezado del grupo. Puede optar por suprimir el nombre de la columna en las filas de encabezado de grupo seleccionando **Opciones de cuadrícula** > **Ocultar el nombre de la columna del grupo**.

### <a name="grouping-on-date-and-time-columns"></a>Agrupación en columnas de fecha y hora
A partir de la versión 10.0.24, para los campos de fecha o fecha y hora, la opción se ha agregado al grupo por año, mes o día. El "valor" del grupo en la fila de encabezado correspondiente coincidirá con el formato de ese campo. Además, para los campos DateTime y Time, podrá agrupar por hora, minuto o segundo. 

## <a name="freezing-columns"></a>Columnas de congelación
Algunas columnas en una cuadrícula pueden ser lo suficientemente importantes para el contexto como para que no desee que se desplacen fuera de la vista. En su lugar, puede que desee que los valores de esas columnas estén siempre visibles. La característica **Congelar columnas en la cuadrícula** proporciona esta flexibilidad a los usuarios. 

Para congelar una columna, haga clic con el botón derecho en el encabezado de la columna y luego seleccione **Congelar columna**. La primera vez que completa este paso, la columna seleccionada se convierte en la primera columna y ya no se desplazará fuera de la vista. Cualquier columna posterior que congele se agregará a la derecha de la última columna congelada. Puede utilizar la función Mover estándar para reordenar las columnas inmovilizadas según sus necesidades. Sin embargo, las columnas congeladas no se pueden mover para que aparezcan entre el conjunto de columnas no congeladas. De igual modo, las columnas no congeladas no se pueden mover para que aparezcan entre el conjunto de columnas congeladas.

Para descongelar una columna, haga clic con el botón derecho en el encabezado de la columna congelada y luego seleccione **Descongelar columna**. 

Tenga en cuenta que las columnas de selección de fila y estado de fila en la nueva cuadrícula siempre están congeladas como las dos primeras columnas. Por lo tanto, cuando estas columnas se incluyen en una cuadrícula, siempre estarán visibles para los usuarios, independientemente de la posición de desplazamiento horizontal en la cuadrícula. Estas dos columnas no se pueden reordenar.

## <a name="autofit-column-width"></a>Ancho de columna de ajuste automático
Al igual que en Excel, los usuarios pueden forzar automáticamente el cambio de tamaño de una columna en función del contenido que se muestra actualmente en esa columna. Para hacer esto, haga doble clic en los controladores de tamaño en la columna, o colocando el foco en el encabezado de la columna y presionando **A** (para autoajuste). Esta funcionalidad está disponible a partir de la versión 10.0.23.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>¿Cómo habilito el nuevo control de cuadrícula en mi entorno? 

La característica **Nuevo control de cuadrícula** está disponible directamente en la administración de características de cualquier entorno. Después de habilitar la función en Administración de características, todas las sesiones de usuario posteriores utilizarán el nuevo control de cuadrículas. 

Esta característica está habilitada de forma predeterminada a partir de la versión 10.0.21 y se prevé que sea obligatoria en octubre de 2022.  

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Desarrollador] Desactivar páginas individuales para que no usen la nueva cuadrícula 
Si su organización detecta una página que tiene problemas al utilizar la nueva cuadrícula, hay una API disponible para permitir que un formulario individual use el control de cuadrícula heredado al mismo tiempo que permite que el resto del sistema utilice el nuevo control de cuadrícula. Para excluir una página individual de la nueva cuadrícula, agregue la siguiente publicación de llamada `super()` en el método `run()` del formulario.

```this.forceLegacyGrid();```

Se aplicará esta API hasta que el nuevo control de cuadrícula se vuelva obligatorio. Ese cambio está actualmente previsto para octubre de 2022. Si algún problema requiere el uso de esta API, notifíqueselo a Microsoft.

### <a name="forcing-a-page-to-use-the-new-grid-after-previously-opting-out-the-grid"></a>Forzar una página a usar la nueva cuadrícula después de haber optado previamente por no recibir la cuadrícula
Si ha optado por que una página individual no use la nueva cuadrícula, es posible que desee volver a habilitar la nueva cuadrícula después de que se hayan resuelto los problemas subyacentes. Para hacer esto, simplemente necesita eliminar la llamada a `forceLegacyGrid()`. El cambio no entrará en vigor hasta que ocurra una de las siguientes situaciones:

- **Reimplementación del entorno**: cuando un entorno se actualiza y se vuelve a implementar, la tabla que almacena las páginas que se excluyeron de la nueva cuadrícula (FormControlReactGridState) se borra automáticamente.
- **Borrado manual de la tabla**: para escenarios de desarrollo, deberá usar SQL para borrar la tabla FormControlReactGridState y luego reiniciar el AOS. Esta combinación de acciones restablecerá el almacenamiento en caché de las páginas que se excluyeron de la nueva cuadrícula.

## <a name="developer-opting-individual-grids-out-of-the-typing-ahead-of-the-system-capability"></a>[Desarrollador] Optar por cuadrículas individuales fuera de la capacidad de escribir antes de la capacidad del sistema
Han surgido algunos escenarios que no se prestan para trabajar bien con la capacidad *Escribir antes que el sistema* de la red. (Por ejemplo, algún código que se activa cuando se valida una fila hace que se active una búsqueda de fuentes de datos, y la investigación puede dañar ediciones no confirmadas en filas existentes). Si su organización descubre tal escenario, hay una API disponible que le permite a un el desarrollador excluye una cuadrícula individual de la validación de filas asíncrona y vuelve al comportamiento heredado.

Cuando la validación de filas asincrónicas está deshabilitada en una cuadrícula, los usuarios no pueden crear una nueva fila o moverse a una fila existente diferente en la cuadrícula mientras haya problemas de validación en la fila actual. Como efecto secundario de esta acción, las tablas no se pueden pegar desde Excel en cuadrículas de Finanzas y operaciones.

Para excluir una cuadrícula individual de una validación de filas asincrónica, agregue la siguiente llamada después de `super()` en el método `run()` del formulario.

```<gridControl>.allowPreemptiveClient(false);```

> [!NOTE]
> - Esta llamada debe invocarse solo en casos excepcionales y no debe ser la norma para todas las redes.
> - No recomendamos que alterne esta API en tiempo de ejecución después de que se cargue el formulario.

## <a name="developer-size-to-available-width-columns"></a>[Desarrollador] Columnas de tamaño hasta el ancho disponible
Si un desarrollador establece la propiedad **WidthMode** en **SizeToAvailable** para las columnas que hay dentro de la nueva cuadrícula, esas columnas tendrán inicialmente el mismo ancho que tendrían si la propiedad estuviera establecida en **SizeToContent**. Sin embargo, se estiran para utilizar el ancho adicional disponible en la cuadrícula. Si la propiedad se establece en **SizeToAvailable** para varias columnas, todas esas columnas compartirán el ancho adicional disponible en la cuadrícula. Sin embargo, si un usuario cambia manualmente el tamaño de una de esas columnas, la columna se volverá estática. Permanecerá en ese ancho y ya no se estirará para ocupar el ancho de cuadrícula adicional disponible.

## <a name="known-issues"></a>Problemas conocidos
Esta sección mantiene una lista de problemas conocidos para el nuevo control de cuadrícula.

### <a name="open-issues"></a>Problemas abiertos
- Después de habilitar la característica **Nuevo control de cuadrícula**, algunas páginas continuarán utilizando el control de cuadrícula existente. Esto ocurrirá en las siguientes situaciones:
 
    - Existe una lista de tarjetas en la página que se representa en varias columnas.
    - Existe una lista de tarjetas agrupadas en la página.
    - Una columna de cuadrícula con un control extensible sin reacción.

    Cuando un usuario encuentra por primera vez una de estas situaciones, aparecerá un mensaje sobre la actualización de la página. Después de que aparezca este mensaje, la página continuará utilizando la cuadrícula existente para todos los usuarios hasta la próxima actualización de la versión del producto. Se considerará una mejor administración de estos escenarios, para que se pueda utilizar la nueva cuadrícula, en una actualización futura.

- [KB 4582758] Los registros aparecen borrosos cuando cambia el zoom de 100 a cualquier otro porcentaje
- [KB 4592012] Error de cliente inesperado en IE11 al pegar varias líneas desde Excel

    Microsoft no busca una solución para este problema


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
