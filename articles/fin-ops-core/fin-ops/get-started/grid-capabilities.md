---
title: Funcionalidad de cuadrícula
description: Este tema describe varias características potentes del control de cuadrícula. La nueva función de cuadrícula debe estar habilitada para tener acceso a estas capacidades.
author: jasongre
manager: AnnBe
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DefaultDashboard
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: fd45f71fc15e467c461433682310ab7b7cc0158a
ms.sourcegitcommit: 0d7b700950b1f95dc030ceab5bbdfd4fe1f79ace
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "3284413"
---
# <a name="grid-capabilities"></a>Funcionalidad de cuadrícula

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

El nuevo control de cuadrícula proporciona una serie de capacidades útiles y potentes que se pueden utilizar para mejorar la productividad del usuario, construir vistas más interesantes de sus datos y obtener información significativa sobre sus datos. Este artículo cubrirá las siguientes capacidades: 

-  Cálculo de los totales
-  Agrupar datos
-  Escribir por delante del sistema
-  Evaluar expresiones matemáticas 

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

## <a name="grouping-data"></a>Agrupar datos
Los usuarios comerciales a menudo necesitan realizar análisis de datos ad-hoc. Si bien esto se puede hacer exportando datos a Microsoft Excel y usando tablas dinámicas, la funcionalidad de **Agrupamiento** en cuadrículas tabulares permite a los usuarios organizar sus datos de manera interesante dentro de las aplicaciones de Finance and Operations. Como esta característica extiende la característica **Totales**, **Agrupamiento** también permite obtener información significativa sobre los datos al proporcionar subtotales a nivel de grupo.

Para usar esta función, haga clic con el botón derecho en la columna por la que desea agrupar y seleccione **Agrupar por esta columna**. Esta acción ordenará los datos por la columna seleccionada, agregará un nuevo Grupo por columna al principio de la cuadrícula e insertará "filas de encabezado" al comienzo de cada grupo. Estas filas de encabezado proporcionan la siguiente información sobre cada grupo: 
-  Valor de datos para el grupo 
-  Etiqueta de columna (esta información será especialmente útil después de que se admitan múltiples niveles de agrupación).
-  Número de filas de datos en este grupo
-  Subtotales para cualquier columna configurada para mostrar totales

Con [Vistas guardadas](saved-views.md) habilitado, esta agrupación se puede guardar mediante personalización como parte de una vista para un acceso rápido la próxima vez que visite la página.  

Si selecciona **Agrupar por esta columna** para una columna diferente, la agrupación original será reemplazada, porque solo un nivel de agrupación es compatible con la versión 10.0.9 / Platform update 33.

Para deshacer la agrupación en una cuadrícula, haga clic derecho en la columna de agrupación y seleccione **Desagrupar**.  

## <a name="typing-ahead-of-the-system"></a>Escribir por delante del sistema
En muchos escenarios comerciales, la capacidad de ingresar datos rápidamente en el sistema es muy importante. Antes de que se introdujera el nuevo control de cuadrícula, los usuarios podían cambiar los datos solo en la fila actual. Antes de que pudieran crear una nueva fila o cambiar a una fila diferente, debían esperar a que el sistema validara con éxito los cambios. En un intento por reducir la cantidad de tiempo que los usuarios esperan a que se completen estas validaciones y para mejorar la productividad del usuario, la nueva cuadrícula ajusta estas validaciones para que sean asíncronas. Por lo tanto, el usuario puede moverse a otras filas para realizar cambios mientras las validaciones de fila anteriores están pendientes. 

Para admitir este nuevo comportamiento, se ha agregado una nueva columna para el estado de la fila en la parte superior de la cuadrícula cuando la cuadrícula está en modo de edición. Esta columna indica uno de los siguientes estados:

- **En blanco**: ninguna imagen de estado indica que la fila ha sido guardada con éxito por el sistema.
- **Procesamiento pendiente**: este estado indica que los cambios en la fila aún no han sido guardados por el servidor, pero están en una cola de cambios que deben procesarse. Antes de tomar medidas fuera de la cuadrícula, debe esperar a que se procesen todos los cambios pendientes. Además, el texto en estas filas está en cursiva para indicar el estado no guardado de las filas. 
- **Advertencia de validación**: este estado indica que el sistema no puede guardar los cambios en la fila debido a algún problema de validación. En la cuadrícula anterior, ¿se veía obligado a volver a la fila para solucionar el problema de inmediato? Sin embargo, en la nueva cuadrícula, se le notifica que se encontró un problema de validación, pero puede decidir cuándo desea solucionarlo. Cuando esté listo para solucionar el problema, puede mover manualmente el foco de nuevo a la fila. Alternativamente, puede seleccionar la acción **Solucionar este problema**. Esta acción mueve inmediatamente el foco a la fila que tiene el problema y le permite realizar modificaciones dentro o fuera de la cuadrícula. Tenga en cuenta que el procesamiento de las filas pendientes posteriores se detiene hasta que se resuelve esta advertencia de validación. 
- **Pausado**: este estado indica que el procesamiento por parte del servidor está en pausa porque la validación de la fila activó un cuadro de diálogo emergente que requiere la intervención del usuario. Debido a que el usuario podría estar ingresando datos en alguna otra fila, el cuadro de diálogo emergente no se presenta de inmediato a ese usuario. En cambio, se presentará cuando el usuario elija reanudar el procesamiento. Este estado va acompañado de una notificación que informa al usuario sobre la situación. La notificación incluye una acción **Reanudar procesamiento** que activa el cuadro de diálogo emergente.  
    
Cuando los usuarios ingresan datos con antelación al lugar donde el servidor está procesando, pueden esperar algunas degradaciones en la experiencia de entrada de datos, como la falta de búsquedas, la validación de nivel de control y la entrada de valores predeterminados. Se recomienda a los usuarios que necesitan una lista desplegable para encontrar un valor que esperen a que el servidor se ponga al día con la fila actual. La validación de nivel de control y la entrada de valores predeterminados también ocurrirán cuando el servidor procese esa fila.   

### <a name="pasting-from-excel"></a>Pegar desde Excel
Los usuarios siempre han podido exportar datos de cuadrículas en aplicaciones de Finance and Operations a Excel utilizando el mecanismo **Exportar a Excel**. Sin embargo, la capacidad de ingresar datos por delante del sistema permite que la nueva cuadrícula admita copiar tablas de Excel y pegarlas directamente en cuadrículas en las aplicaciones de Finance and Operations. La celda de la cuadrícula desde la que se inicia la operación de pegado determina dónde comienza a pegarse la tabla copiada. El contenido de la cuadrícula se sobrescribe con el contenido de la tabla copiada, excepto en dos casos:

- Si el número de columnas en la tabla copiada excede el número de columnas que permanecen en la cuadrícula, comenzando desde la ubicación de pegado, se notifica al usuario de que se han ignorado las columnas adicionales. 
- Si el número de filas en la tabla copiada excede el número de filas en la cuadrícula, comenzando desde la ubicación de pegado, el contenido pegado sobrescribe las celdas existentes y las filas adicionales de la tabla copiada se insertan como nuevas filas en la parte inferior de la cuadrícula. 

## <a name="evaluating-math-expressions"></a>Evaluar expresiones matemáticas
Como un refuerzo de productividad, los usuarios pueden introducir fórmulas matemáticas en celdas numéricas en una cuadrícula. No tienen que hacer el cálculo en una aplicación fuera del sistema. Por ejemplo, si introduce **= 15\*4** y después pulsa la tecla **Tab** para salir del campo, el sistema evaluará la expresión y guardará un valor de **60** para el campo.

Para que el sistema reconozca un valor como una expresión, comience el valor con un signo igual (**=**). Para obtener más información sobre los operadores y la sintaxis compatibles, vea [Símbolos matemáticos admitidos](http://bugwheels94.github.io/math-expression-evaluator/#supported-maths-symbols).

## <a name="frequently-asked-questions"></a>Preguntas frecuentes
### <a name="how-do-i-enable-the-new-grid-control-in-my-environment"></a>¿Cómo habilito el nuevo control de cuadrícula en mi entorno? 

**10.0.9 / Platform update 33 y posteriores** La característica **Nuevo control de cuadrícula** está disponible directamente en Administración de características en cualquier entorno. Al igual que otras características de vista previa pública, la habilitación de esta característica en producción está sujeta a [Acuerdo de términos de uso complementarios](https://go.microsoft.com/fwlink/?linkid=2105274).  

**10.0.8 / Platform update 32 y 10.0.7 / Platform update 31** La característica **Nuevo control de cuadrícula** se puede habilitar en entornos de Nivel 1 (desarrollo/prueba) y Nivel 2 (espacio aislado) para proporcionar pruebas adicionales y cambios de diseño siguiendo los pasos siguientes.

1.  **Habilite el tramo**: ejecute la instrucción SQL siguiente: 

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, enabled, FLIGHTSERVICEID, PARTITION) VALUES('CLIReactGridEnableFeature', 1, 0, 5637144576);`

2. **Restablecer IIS** para vaciar la memoria caché estática de la distribución de paquetes piloto. 

3.  **Encontrar la característica**: vaya al espacio de trabajo **Administración de características**. Si **Nuevo control de cuadrícula** no aparece en la lista de todas las funciones, seleccione **Buscar actualizaciones**.   

4.  **Habilitar la característica**: encuentre la característica **Nuevo control de cuadrícula** en la lista de características y seleccione **Habilitar ahora** en el panel de detalles. Tenga en cuenta que se requiere una actualización del navegador. 

Todas las sesiones de usuario posteriores comenzarán con el nuevo control de cuadrícula habilitado.

## <a name="known-issues"></a>Problemas conocidos
Esta sección mantiene una lista de problemas conocidos para el nuevo control de cuadrícula mientras la función está en un estado de vista previa.  

### <a name="open-issues"></a>Problemas abiertos

- Las listas de tarjetas que se representaban como columnas múltiples ahora se representan como una sola columna.
- Las listas agrupadas no se representan como grupos o en columnas separadas.
- La información sobre herramientas no se muestra para las imágenes.
- La visualización de líneas de cuadrícula no funciona para todos los tipos de campo.
- De forma intermitente, no puede hacer clic fuera de la cuadrícula después de seleccionar varias filas.
- Las opciones del Grabador de tareas **Validar** y **Copiar** no están disponibles para los controles de fecha/número.

### <a name="fixed-as-part-of-10012"></a>Corregido como parte de 10.0.12

> [!Note]
> Se proporciona la siguiente información para que pueda planificar en consecuencia. Para obtener más información acerca la programación de lanzamiento de la versión 10.0.12 objetivo, consulte [Disponibilidad de actualización del servicio](../../fin-ops/get-started/public-preview-releases.md).

- [Problema 429126] Los controles fuera de la cuadrícula no se actualizan después de eliminar el último registro.
- [Problema 430575] Los controles de tabla no actualizan el contenido de los elementos mostrados.
- [KB 4558570] Los elementos aún se muestran en la página una vez que se ha eliminado el registro.
- [KB 4558584] Los números negativos no se representan correctamente.
- [KB 4558575] Los campos no se actualizan después de un cambio de fila/El procesamiento de cuadrícula se atasca después de la eliminación de filas.
- [Problema 436980] No se aplica el estilo asociado con el Panel de lista **ExtendedStyle**.
- [KB 4558573] Los errores de validación no se pueden corregir cuando el cambio requerido está fuera de la cuadrícula.
    
### <a name="quality-update-for-10011"></a>Actualización de calidad para 10.0.11

- [KB 4558381] Los números negativos no se representan correctamente/Los usuarios a veces se bloquean después de encontrar problemas de validación.

### <a name="fixed-as-part-of-10011"></a>Corregido como parte de 10.0.11

- [KB 4558374] No se pueden crear registros que requieran un cuadro de diálogo selector polimórfico.
- [KB 4558382] Se producen errores inesperados del cliente.
- [KB 4558375] El texto de ayuda no se muestra en las columnas de la nueva cuadrícula.
- [KB 4558376] Las cuadrículas del panel de lista no se representan a la altura correcta en Internet Explorer.
- [KB 4558377] Las columnas de cuadro combinado que tienen el ancho **SizeToAvailable** no se representan en algunas páginas.
- [KB 4549711] Las líneas de una propuesta de pago no se pueden eliminar correctamente después de habilitar el nuevo control de cuadrícula.
- [KB 4558378] La obtención de detalles a veces abre el registro incorrecto.
- [KB 4558379] Se produce un error cuando se abren búsquedas donde **ReplaceOnLookup**=**No**.
- [KB 4558380] El espacio disponible en la cuadrícula no se llena inmediatamente después de que se contrae parte de la página.
- [Problema 432458] Las líneas vacías o duplicadas se muestran al comienzo de algunas colecciones secundarias.
- [KB 4558587] Los grupos de referencia que tienen cuadros combinados para los campos de reemplazo no muestran valores.

### <a name="fixed-as-part-of-10010"></a>Corregido como parte de 10.0.10

- [Problema 414301] Algunos datos de líneas anteriores desaparecen cuando se crean nuevas líneas.
- [KB 4550367] Los valores de tiempo no tienen el formato correcto.
- [KB 4549734] Las filas activas no se tratan como marcadas si la columna de marcado está oculta.
- [Error 417044] No hay un mensaje de cuadrícula vacío para las cuadrículas de estilo de lista.
- [KB 4558367] La selección de texto es inconsistente cuando se cambian las filas.
- [KB 4558372] La nueva cuadrícula se bloquea en el modo de procesamiento si el número de columnas en el contenido que se pega excede el número de columnas restantes en la cuadrícula.
- [KB 4558368] La selección múltiple con el teclado está permitida en escenarios de selección única.
- [KB 4539058] Algunas cuadrículas (generalmente en fichas desplegables) a veces no se representan (pero se mostrarán si se aleja la imagen).
- [KB 4558369] Las imágenes de estado desaparecen en la cuadrícula jerárquica.
- [KB 4558370] Una fila nueva no se desplaza hasta la vista.
- [KB 4549796] Los valores no se pueden editar en una cuadrícula cuando está en modo de vista.

### <a name="quality-update-for-1009platform-update-33"></a>Actualización de calidad para 10.0.9/Actualización de plataforma 33

- [KB 4550367] Los valores de tiempo no tienen el formato correcto.
