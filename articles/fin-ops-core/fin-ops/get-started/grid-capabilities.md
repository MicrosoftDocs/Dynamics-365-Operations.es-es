---
title: Funcionalidad de cuadrícula
description: Este tema describe varias características potentes del control de cuadrícula. La nueva característica de cuadrícula debe estar habilitada para tener acceso a estas capacidades.
author: jasongre
manager: AnnBe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: fb30cdded33f90bb472c8abdb70875077b1dd985
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693783"
---
# <a name="grid-capabilities"></a>Funcionalidad de cuadrícula

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El nuevo control de cuadrícula proporciona una serie de capacidades útiles y potentes que se pueden utilizar para mejorar la productividad del usuario, construir vistas más interesantes de sus datos y obtener información significativa sobre sus datos. Este artículo cubrirá las siguientes capacidades: 

-  Cálculo de los totales
-  Escribir por delante del sistema
-  Evaluar expresiones matemáticas 
-  Agrupar datos tabulares (habilitado por separado usando la característica **(Versión preliminar) Agrupación en cuadrículas**)
-  Columnas del sistema ancladas

## <a name="calculating-totals"></a>Cálculo de los totales
En las aplicaciones de Finance and Operations, los usuarios tienen la capacidad de ver los totales en la parte inferior de las columnas numéricas en las cuadrículas. Estos totales se muestran en una sección de pie de página en la parte inferior de la cuadrícula. 

### <a name="showing-the-grid-footer"></a>Mostrar el pie de página de la cuadrícula
Hay un área de pie de página en la parte inferior de cada cuadrícula tabular en las aplicaciones Finance and Operations. El pie de página puede mostrar información valiosa relacionada con los datos que aparecen en la cuadrícula. Algunos ejemplos de esta información son:

- El número de filas seleccionadas en la tabla (cuando se selecciona más de un registro)
- Totales generales en la parte inferior de las columnas numéricas configuradas
- El número de filas del conjunto de datos 

Este pie de página está oculto de forma predeterminada pero se puede activar fácilmente. Para mostrar el pie de página de una cuadrícula, haga clic con el botón derecho en el encabezado de una columna en la cuadrícula y seleccione la opción **Mostrar pie de página**. Una vez que el pie de página se ha activado para una cuadrícula en particular, esa configuración se recordará hasta que el usuario opte por ocultar el pie de página, lo que se puede hacer haciendo clic derecho en el encabezado de una columna y seleccionando **Ocultar pie de página**.  Tenga en cuenta que se espera que la acción **Mostrar pie de página/Ocultar pie de página** se reubique en una actualización futura. 

### <a name="specifying-columns-with-totals"></a>Especificar columnas con totales
Actualmente, no se configurarán columnas para mostrar totales por defecto. En cambio, esto se considera una actividad de configuración única, similar a ajustar el ancho de las columnas en las cuadrículas. Una vez que especifique que desea ver los totales de una columna, esa configuración se recordará la próxima vez que visite la página.  

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

Si el cálculo tarda demasiado, puede cancelar la operación seleccionando el botón **Cancelar**. Sin embargo, a veces, el conjunto de datos será demasiado grande para calcular los totales (un límite impuesto por su organización) y, en su lugar, se le notificará para que filtre más sus datos.

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
Los usuarios siempre han podido exportar datos de cuadrículas en aplicaciones de Finance and Operations a Excel utilizando el mecanismo **Exportar a Excel**. Sin embargo, la capacidad de introducir datos por delante del sistema permite que la nueva cuadrícula admita copiar tablas de Excel y pegarlas directamente en cuadrículas en las aplicaciones de Finance and Operations. La celda de la cuadrícula desde la que se inicia la operación de pegado determina dónde comienza a pegarse la tabla copiada. El contenido de la cuadrícula se sobrescribe con el contenido de la tabla copiada, excepto en dos casos:

- Si el número de columnas en la tabla copiada excede el número de columnas que permanecen en la cuadrícula, comenzando desde la ubicación de pegado, se notifica al usuario de que se han ignorado las columnas adicionales. 
- Si el número de filas en la tabla copiada excede el número de filas en la cuadrícula, comenzando desde la ubicación de pegado, el contenido pegado sobrescribe las celdas existentes y las filas adicionales de la tabla copiada se insertan como nuevas filas en la parte inferior de la cuadrícula. 

## <a name="evaluating-math-expressions"></a>Evaluar expresiones matemáticas
Como un refuerzo de productividad, los usuarios pueden introducir fórmulas matemáticas en celdas numéricas en una cuadrícula. No tienen que hacer el cálculo en una aplicación fuera del sistema. Por ejemplo, si introduce **= 15\*4** y después pulsa la tecla **Tab** para salir del campo, el sistema evaluará la expresión y guardará un valor de **60** para el campo.

Para que el sistema reconozca un valor como una expresión, comience el valor con un signo igual (**=**). Para obtener más información sobre los operadores y la sintaxis compatibles, consulte [Símbolos matemáticos admitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="grouping-tabular-data"></a>Agrupación de datos tabulares
Los usuarios comerciales a menudo necesitan realizar análisis de datos ad-hoc. Si bien esto se puede hacer exportando datos a Microsoft Excel y usando tablas dinámicas, la característica **Agrupación en cuadrículas**, que está disponible de modo general en la versión 10.0.16/Platform update 40 y que depende de la característica de control de cuadrículas nuevas, permite a los usuarios organizar sus datos de manera interesante dentro de las aplicaciones de Finance and Operations. Dado que esta característica extiende la característica **Totales**, **Agrupamiento** también permite obtener información significativa sobre los datos al proporcionar subtotales a nivel de grupo.

Para usar esta característica, haga clic con el botón derecho en la columna que desea agrupar y seleccione **Agrupar por esta columna**. Esta acción ordenará los datos por la columna seleccionada, agregará un nuevo **Agrupar por** columna al principio de la cuadrícula e insertará "filas de encabezado" al comienzo de cada grupo. Estas filas de encabezado proporcionan la siguiente información sobre cada grupo: 
-  Valor de datos para el grupo 
-  Nombre de columna (esta información es especialmente útil cuando tenga múltiples niveles de agrupación)  
-  Número de filas de datos en este grupo
-  Subtotales para cualquier columna configurada para mostrar totales

Con [Vistas guardadas](saved-views.md) habilitado, esta agrupación se puede guardar mediante personalización como parte de una vista para un acceso rápido la próxima vez que visite la página.  

### <a name="multiple-levels-of-grouping"></a>Múltiples niveles de agrupación
Una vez que haya agrupado los datos en una sola columna, puede agrupar los datos en una columna diferente seleccionando **Agrupar por esta columna** en la columna deseada. Este proceso se puede repetir hasta que tenga 5 niveles anidados de agrupación, que es la profundidad máxima admitida. En este punto, ya no podrá agrupar por columnas adicionales.  

En cualquier momento, puede eliminar la agrupación en cualquier columna haciendo clic derecho en esa columna y seleccionando **Desagrupar**. También puede eliminar la agrupación de todas las columnas seleccionando **Opciones de cuadrícula** y después **Desagrupar todo**.   

Tenga en cuenta que antes de la versión 10.0.16 / Platform update 40, solo se admitía un nivel de agrupación. En estas versiones, si los datos están agrupados y selecciona **Agrupar por esta columna** para una columna diferente, se reemplaza la agrupación original.  


### <a name="expanding-and-collapsing-groups"></a>Expandir y contraer grupos
La agrupación inicial de datos tendrá todos los grupos expandidos. Puede crear vistas resumidas de los datos contrayendo grupos individuales, o puede usar la expansión y contracción de grupos para ayudar a navegar a través de los datos. Para expandir o contraer un grupo, seleccione el botón de chevron (>) en la fila de encabezado del grupo correspondiente. Tenga en cuenta que el estado expandir/contraer de grupos individuales **no** está guardado en la personalización.

### <a name="selecting-and-unselecting-rows-at-the-group-level"></a>Seleccionar y anular la selección de filas a nivel de grupo
De la misma manera que puede seleccionar (o anular la selección) todas las filas de la cuadrícula seleccionando la casilla de verificación en la parte superior de la primera columna de la cuadrícula, también puede seleccionar rápidamente (o anular la selección) todas las filas de un grupo seleccionando la casilla de verificación en la fila de encabezado de grupo correspondiente. La casilla de verificación en la fila del encabezado del grupo siempre reflejará el estado de selección actual de las filas de ese grupo, independientemente de si todas las filas están seleccionadas, no hay filas seleccionadas o solo algunas filas están seleccionadas.

### <a name="hiding-column-names"></a>Ocultar nombres de columnas
Al agrupar datos, el comportamiento predeterminado es mostrar el nombre de la columna en la fila del encabezado del grupo. A partir de la versión 10.0.14/Platform update 38, puede optar por suprimir el nombre de la columna en las filas de encabezado de grupo seleccionando **Opciones de cuadrícula** > **Ocultar el nombre de la columna del grupo**.

## <a name="pinned-system-columns"></a>Columnas del sistema ancladas
La columna de selección de fila y la columna de estado de fila de la nueva cuadrícula están ancladas o congeladas en la parte más a la izquierda de la cuadrícula. Por lo tanto, cuando estas columnas se incluyen en una cuadrícula, siempre estarán visibles para el usuario, independientemente de la posición de desplazamiento horizontal en la cuadrícula.   

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>¿Cómo habilito el nuevo control de cuadrícula en mi entorno? 

**10.0.9/Platform update 33 y posterior**

La característica **Nuevo control de cuadrícula** está disponible directamente en la administración de características de cualquier entorno. Al igual que otras características de vista previa pública, la habilitación de esta característica en producción está sujeta a [Acuerdo de términos de uso complementarios](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8/Platform update 32 y 10.0.7/Platform update 31**

La característica **Nuevo control de cuadrícula** se puede habilitar en entornos de Nivel 1 (desarrollo/prueba) y Nivel 2 (espacio aislado) para proporcionar pruebas adicionales y cambios de diseño siguiendo los pasos que se describen a continuación.

1.  **Habilite el tramo**: ejecute la instrucción SQL siguiente: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Restablecer IIS** para vaciar la memoria caché estática de la distribución de paquetes piloto. 

3.  **Encontrar la característica**: vaya al espacio de trabajo **Administración de características**. Si **Nuevo control de cuadrícula** no aparece en la lista de todas las características, seleccione **Buscar actualizaciones**.   

4.  **Habilitar la característica**: encuentre la característica **Nuevo control de cuadrícula** en la lista de características y seleccione **Habilitar ahora** en el panel de detalles. Tenga en cuenta que se requiere una actualización del navegador. 

Todas las sesiones de usuario posteriores comenzarán con el nuevo control de cuadrícula habilitado.

## <a name="developer-opting-out-individual-pages-from-using-the-new-grid"></a>[Desarrollador] Desactivar páginas individuales para que no usen la nueva cuadrícula 
Si su organización detecta una página que tiene problemas al utilizar la nueva cuadrícula, hay una API disponible a partir de la versión 10.0.13/Platform update 37 para permitir que un formulario individual use el control de cuadrícula heredado al mismo tiempo que permite que el resto del sistema utilice el nuevo control de cuadrícula. Para excluir una página individual de la nueva cuadrícula, agregue la siguiente publicación de llamada `super()` en el método `run()` del formulario.

 ```this.forceLegacyGrid();```

Esta API se aplicará hasta la versión de octubre de 2021, cuando el nuevo control de cuadrícula se vuelva obligatorio. Si algún problema requiere el uso de esta API, notifíqueselo a Microsoft.

## <a name="developer-size-to-available-width-columns"></a>[Desarrollador] Columnas de tamaño hasta el ancho disponible
Si un desarrollador establece la propiedad **WidthMode** en **SizeToAvailable** para las columnas que hay dentro de la nueva cuadrícula, esas columnas tendrán inicialmente el mismo ancho que tendrían si la propiedad estuviera establecida en **SizeToContent**. Sin embargo, se estiran para utilizar el ancho adicional disponible en la cuadrícula. Si la propiedad se establece en **SizeToAvailable** para varias columnas, todas esas columnas compartirán el ancho adicional disponible en la cuadrícula. Sin embargo, si un usuario cambia manualmente el tamaño de una de esas columnas, la columna se volverá estática. Permanecerá en ese ancho y ya no se estirará para ocupar el ancho de cuadrícula adicional disponible.  

## <a name="known-issues"></a>Problemas conocidos
Esta sección mantiene una lista de problemas conocidos para el nuevo control de cuadrícula mientras la característica está en un estado de vista previa.  

### <a name="open-issues"></a>Problemas abiertos
-  Después de habilitar la característica **Nuevo control de cuadrícula**, algunas páginas continuarán utilizando el control de cuadrícula existente. Esto ocurrirá en las siguientes situaciones:  
    -  Existe una lista de tarjetas en la página que se representa en varias columnas.
    -  Existe una lista de tarjetas agrupadas en la página.
    -  Una columna de cuadrícula con un control extensible sin reacción.

    Cuando un usuario encuentra por primera vez una de estas situaciones, aparecerá un mensaje sobre la actualización de la página. Después de que aparezca este mensaje, la página continuará utilizando la cuadrícula existente para todos los usuarios hasta la próxima actualización de la versión del producto. Se considerará una mejor administración de estos escenarios, para que se pueda utilizar la nueva cuadrícula, en una actualización futura.    
    
-  [KB 4582758] Los registros aparecen borrosos cuando cambia el zoom de 100 a cualquier otro porcentaje
    
### <a name="fixed-as-part-of-10015"></a>Corregido como parte de 10.0.15    

-  [KB 4582723] Las opciones de visualización no se muestran cuando se realizan más adelante en el ciclo de vida del formulario

### <a name="fixed-as-part-of-10014"></a>Corregido como parte de 10.0.14

-  (Actualización de calidad) [KB 4584752] Error de cliente inesperado con la página de propuestas de factura del proyecto

### <a name="fixed-as-part-of-10013"></a>Corregido como parte de 10.0.13

-  (Actualización de calidad) [KB 4583880] Regression Suite Automation Tool (RSAT) las pruebas fallan en la acción OpenLookup con "No se puede leer la propiedad RowIndex de undefined"
-  (Actualización de calidad) [KB 4583847] Error de cliente inesperado al navegar por las búsquedas 
-  (Actualización de calidad) [Error 471777] No se pueden seleccionar campos en una cuadrícula para editar o crear una aplicación móvil
-  [Error 474851] Los hipervínculos en los controles del grupo de referencia no funcionan 
-  [Error 474848] Las vistas previas mejoradas con cuadrículas no se muestran
-  [KB 4582726] No se respeta la propiedad RotateSign  
-  [Error 470173] Las casillas de verificación en filas inactivas se alternan cuando se hace clic en el espacio en blanco en la celda
-  [Error 474848] Las vistas previas mejoradas con cuadrículas no se muestran
-  [Error 474851] Los hipervínculos en los controles del grupo de referencia no funcionan 
-  [Error 471777] No se pueden seleccionar campos en una cuadrícula para editar o crear una aplicación móvil
-  [KB 4569441] Problemas con la representación de listas de tarjetas de varias columnas, información sobre herramientas en imágenes y opciones de visualización en algunos campos
-  [KB 4575279] No todas las filas marcadas se eliminan en el diario general
-  [KB 4575233] Las opciones de visualización no se restauran después de pasar a otra fila
-  [Error 477884] Las búsquedas devuelven un valor / registro incorrecto si se activa un nuevo control de cuadrícula
-  [KB 4571095] La publicación del recibo del producto se produce al presionar accidentalmente Entrar (administración correcta de la acción predeterminada de una página)
-  [KB 4575437] Las búsquedas con controles editables se cierran inesperadamente
-  [KB 4569418] Línea duplicada creada en el formulario de programación de entrega
-  [KB 4575435] La vista previa mejorada a veces persiste incluso cuando el puntero del mouse no está cerca del campo
-  [KB 4575434] La búsqueda no se filtra cuando el campo se ha modificado
-  [KB 4575430] Los valores en los campos de contraseña no están enmascarados en la cuadrícula
-  [KB 4569438] "El procesamiento se ha detenido debido a un problema de validación" aparece después de marcar líneas mientras se liquidan las transacciones del proveedor
-  [KB 4569434] La actualización del formulario de entidades jurídicas da como resultado menos registros
-  [KB 4575297] El foco sigue moviéndose al panel del registrador de tareas al editar y tabular a través de una cuadrícula
-  [KB 4566773] Las transacciones de corrección no se muestran como negativas en la consulta de transacciones de comprobantes 
-  [KB 4575288] El foco se restablece a la fila activa al seleccionar el borde entre filas en una lista simple
-  [KB 4575287] El foco no vuelve a la primera columna cuando se usa la flecha hacia abajo para crear una nueva fila en los diarios
-  [KB 4564819] No se pueden eliminar líneas en una factura de texto libre (porque el origen de datos ChangeGroupMode = ImplicitInnerOuter)
-  [KB 4563317] La información sobre herramientas o las vistas previas mejoradas no se muestran para las imágenes

### <a name="fixed-as-part-of-10012"></a>Corregido como parte de 10.0.12

- [KB 4558545] Los controles de tabla no actualizan el contenido de los elementos mostrados.
- [KB 4558570] Los elementos aún se muestran en la página una vez que se ha eliminado el registro.
- [KB 4558572] No se aplica el estilo asociado con el Panel de lista **ExtendedStyle**.
- [KB 4558573] Los errores de validación no se pueden corregir cuando el cambio requerido está fuera de la cuadrícula.
- [KB 4558584] Los números negativos no se representan correctamente.
- [KB 4560726] Se produce un "error inesperado del cliente" después de que el intercambio entre listas se realiza mediante un control de Vista de lista.
- [KB 4562141] Los índices de cuadrícula se desactivan después de agregar un nuevo registro.
- [KB 4562151] Las opciones del grabador de tareas **Validar** y **Copiar** no están disponibles para los controles de fecha/número. 
- [KB 4562153] Las casillas de selección múltiple no están visibles en las cuadrículas de listas/tarjetas.
- [KB 4562646] En ocasiones, no puede hacer clic fuera de la cuadrícula después de seleccionar varias filas en la cuadrícula.
- [KB 4562647] El foco se restablece al primer control en el cuadro de diálogo **Publicar** después de agregar una nueva fila en la cuadrícula de roles de seguridad.
- [KB 4563310] La vista previa mejorada no se cierra después de cambiar una fila.
- [KB 4563313] Se produce un "error inesperado del cliente" en Internet Explorer cuando se selecciona un valor en una búsqueda.
- [KB 4564557] Las búsquedas y los menús desplegables no se abrirán en Internet Explorer
- [KB 4563324] La navegación no funciona después de abierto el espacio de trabajo **Gestión de personal**.

### <a name="fixed-as-part-of-10011"></a>Corregido como parte de 10.0.11

- [Problema 432458] Las líneas vacías o duplicadas se muestran al comienzo de algunas colecciones secundarias.
- [KB 4549711] Las líneas de una propuesta de pago no se pueden eliminar correctamente después de habilitar el nuevo control de cuadrícula.
- [KB 4558374] No se pueden crear registros que requieran un cuadro de diálogo selector polimórfico.
- [KB 4558375] El texto de ayuda no se muestra en las columnas de la nueva cuadrícula.
- [KB 4558376] Las cuadrículas del panel de lista no se representan a la altura correcta en Internet Explorer.
- [KB 4558377] Las columnas de cuadro combinado que tienen el ancho **SizeToAvailable** no se representan en algunas páginas.
- [KB 4558378] La obtención de detalles a veces abre el registro incorrecto.
- [KB 4558379] Se produce un error cuando se abren búsquedas donde **ReplaceOnLookup**=**No**.
- [KB 4558380] El espacio disponible en la cuadrícula no se llena inmediatamente después de que se contrae parte de la página.
- [KB 4558381] Los números negativos no se representan correctamente/Los usuarios a veces se bloquean después de encontrar problemas de validación.
- [KB 4558382] Se producen errores inesperados del cliente.
- [KB 4558383] Los controles fuera de la cuadrícula no se actualizan después de eliminar el último registro.
- [KB 4558587] Los grupos de referencia que tienen cuadros combinados para los campos de reemplazo no muestran valores.
- [KB 4562143] Los campos no se actualizan después de un cambio de fila/El procesamiento de cuadrícula se atasca después de la eliminación de filas.
- [KB 4562645] Se produce una excepción cuando se abre una búsqueda mientras se ejecutan las pruebas de Regression Suite Automation Tool (RSAT).

### <a name="fixed-as-part-of-10010"></a>Corregido como parte de 10.0.10

- [Problema 414301] Algunos datos de líneas anteriores desaparecen cuando se crean nuevas líneas.
- [Error 417044] No hay un mensaje de cuadrícula vacío para las cuadrículas de estilo de lista.
- [KB 4539058] Algunas cuadrículas (generalmente en fichas desplegables) a veces no se representan (pero se mostrarán si se aleja la imagen).
- [KB 4549734] Las filas activas no se tratan como marcadas si la columna de marcado está oculta.
- [KB 4549796] Los valores no se pueden editar en una cuadrícula cuando está en modo de vista.
- [KB 4558367] La selección de texto es inconsistente cuando se cambian las filas.
- [KB 4558368] La selección múltiple con el teclado está permitida en escenarios de selección única.
- [KB 4558369] Las imágenes de estado desaparecen en la cuadrícula jerárquica.
- [KB 4558370] Una fila nueva no se desplaza hasta la vista.
- [KB 4558372] La nueva cuadrícula se bloquea en el modo de procesamiento si el número de columnas en el contenido que se pega excede el número de columnas restantes en la cuadrícula.
- [KB 4562631] Los valores de tiempo no tienen el formato correcto.

### <a name="quality-update-for-1009platform-update-33"></a>Actualización de calidad para 10.0.9/Actualización de plataforma 33

- [KB 4550367] Los valores de tiempo no tienen el formato correcto.
