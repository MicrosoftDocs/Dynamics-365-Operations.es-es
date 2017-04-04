---
title: "Espacio de trabajo de cierre del período financiero"
description: "Este artículo proporciona una visión general del espacio de trabajo de cierre del período financiero y la configuración asociada."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: ba0d709d123f56edb2a5287376c06c1f41181b1c
ms.lasthandoff: 03/31/2017


---

# <a name="financial-period-close-workspace"></a>Espacio de trabajo de cierre del período financiero

Este artículo proporciona una visión general del espacio de trabajo de cierre del período financiero y la configuración asociada.

Espacio de trabajo de cierre del período financiero

** Cerrar financiero del período ** el área de trabajo le permite realizar un seguimiento de sus procesos de cierre financieros a través de las empresas, las áreas, y las personas. En función de su vista ** cierre del período financiero ** del espacio de trabajo, verá de todas las tareas y estados de una programación cerrada, o sólo de las tareas que tiene asignados. 

Debe seleccionar una programación cerrada en la parte superior del espacio de trabajo. Todos los datos que se muestra en el área de trabajo continuación filtra por la programación cerrada seleccionado.

### <a name="summary-tiles"></a>Iconos de resumen

Los iconos de **Resumen** proporcionan una visión general del proceso y los indicadores le ayudan a controlar el proceso de cierre. Puede ver las tareas que son tareas vencidas, restantes del día actual, las tareas que están hoy debido pero está bloqueado debido a dependencias, y todas las tareas restantes del proceso. Esta información es para todas las empresas incluidas en la programación cerrada seleccionado.

### <a name="tasks-and-status-section"></a>Sección Tareas y estados

** En las tareas y estado ** la sección, analizar el estado de la programación cerrada total de varias maneras: estado de la empresa, estado por área, por estado y la persona responsable. Puede ver el estado de todas las tareas en la programación cerrada, sólo las tareas que son hoy, o debido las tareas vencidas cambiando el filtro en la parte superior de la lista de tarjeta. También puede seleccionar el filtro de la empresa para ver el estado para una empresa específica. Cada ficha del estado da un desglose por el porcentaje se ha completado y el número de tareas restante. Haga clic en la tarjeta o ** ver detalles ** la acción para filtrar la lista de tareas detallada por la tarjeta seleccionado. 

La última ficha es para la lista de tareas detallada. Esta lista muestra la lista de tareas y completa puede filtrar de modo que muestre solo a tareas que le interese. Puede filtrar la lista de tareas de varias maneras. Por ejemplo, puede filtrar por fecha de vencimiento de ésta, la empresa asociada, y el área asociada. También puede seleccionar para mostrar u ocultar tareas completadas en la lista de tareas. 

Se usan dos indicadores para las tareas:

-   Icono del signo de exclamación indica que la tarea es vencida. Para las tareas vencidas, la fecha de vencimiento también se resaltada en rojo.
-   Un icono de candado indica que la tarea depende de otras tareas que no se completen. Una tarea que es bloqueada por dependencias no se puede marcar como completado. Puede establecer las dependencias para una tarea mediante ** dependencia determinada ** la acción.

El nombre de tarea es un hipervínculo en Microsoft Dynamics 365 para la página de las operaciones u otra página web donde el usuario debe ir a completar el trabajo. Puede establecer este hipervínculo mediante ** vínculo de tarea ** campos al editar o crear una tarea. 

Puede vincular archivos, notas, imágenes, y las direcciones URL a una tarea mediante ** los datos adjuntos ** la acción. Por ejemplo, puede indicar los números de diarios que se utilizan como parte de una tarea, agregar comentarios acerca de una tarea específica, o adjuntar un archivo de informe impreso para una tarea. Un icono ** aparece en los datos adjuntos ** la columna para la tarea si el archivo adjunto presente. 

** Tarea ** completada la opción debe seleccionar manualmente después de que la tarea se haya completado. Cuando una tarea ha marcado, ** fecha completado ** el campo se actualiza automáticamente a la fecha y hora actual. Los indicadores de la dependencia también se actualizarán como corresponda.

## <a name="all-financial-period-close-tasks-list-page"></a>Página de lista Todas las tareas de cierre del período financiero
Puede ver toda la producción actual y tareas anteriores del cierre del período ** todas las tareas financieras de cierre del período ** de la página de lista. Esta página de lista se puede usar para el análisis del historial del proceso de cierre, ya que incluye información acerca de la fecha de vencimiento programada, la fecha de finalización real, y la persona que completó la tarea. Es fácil exportar la información de esta página de lista a Microsoft Excel para informar y auditoria.

## <a name="financial-period-close-configuration-page"></a>Página Configuración de cierre del período financiero
Para poder usar ** cierre del período financiero ** el área de trabajo, debe configurar el proceso en Microsoft Dynamics 365 para las operaciones mediante ** configuración financiera de cierre del período ** la página. Haga clic en (** contabilidad general ** &gt; ** Cierre el período ** &gt; ** configuración financiera de cierre del período **).

### <a name="resources"></a>Recursos

En ** los recursos ** la ficha, se define a las personas implicadas en los procesos de cierre. Cualquier empleado responsable de una tarea cerrada primero debe asignado aquí. También debe especificar la vista de empleado del espacio de trabajo. Están disponibles las siguientes opciones:

-   **Solo tareas asignadas**: el usuario verá solo las tareas que tiene asignadas.
-   **Todos los estados y tareas**: el usuario verá todas las tareas de cierre y los estados del proceso general.

Los usuarios que tienen permisos para ver solo sus tareas asignadas no podrán agregar tareas a la lista de tareas, editar tareas o quitar tareas de la lista de tareas.

### <a name="task-areas"></a>Áreas de tareas

Las áreas de tareas se usan para agrupar las tareas de cierre en áreas lógicas de propiedad dentro de su organización. Por ejemplo, Proveedores, Clientes o Contabilidad general se pueden usar como áreas de tareas.

### <a name="calendars"></a>Calendarios

Crear y editar calendarios cerrados financieros usando la ficha de los calendarios.  Aquí es donde se definirá los días laborables para los procesos de cierre, y se usará para programar tareas cerradas.  Crear un calendario nuevo, e indique los días laborables que se utilizarán para la programación de tarea.  Es la mejor crear un calendario para el período largo de tiempo, como un año o varios años, ya que se puede editar después de su creación.  Después de crear el calendario, haga clic en el botón Editar para actualizar el calendario en días específicos, como festivos.  Las siguientes tareas de cierre se programarán los días en que el valor del control se establece para abrir.  Si las siguientes tareas de cierre son Programación en un día concreto, ese día debe tener el valor del control establecido a cerrado.

### <a name="templates"></a>Plantillas

Use una plantilla cercana financiera para definir todas las tareas que forman parte de un proceso de cierre. Una tarea cerrada es un esfuerzo de trabajo periódico que se asigna al usuario para completar como parte de cada proceso de cierre. En la plantilla, una fecha de vencimiento relativa debe definirse para cada tarea cerrada. La fecha de vencimiento relativa es el número de días antes o después de la fecha final del período definido que la tarea se vencimiento de cada período. Un tiempo debido también se asigna a cada tarea. El tiempo a vencer se establece al contexto de su zona horaria y se convierte a la zona horaria para cada usuario. 

Es posible asignar una tarea en la plantilla a una o más empresas donde se aplica esa tarea. Si se asignan otra persona para completar ese esfuerzo de trabajo en cada empresa, es posible que la encuentre útil crear las varias tareas para el mismo esfuerzo del trabajo. Cree una tarea para cada empresa. 

** Vínculo de la tarea ** el elemento de menú está asociado al esfuerzo de trabajo de la tarea y se puede usar para ir directamente a la página asociada del vínculo de la tarea en el área de trabajo. Por ejemplo, una tarea cerradas de ejecutar el proceso de revalorización de divisa para los proveedores se puede vincular al asociado ** revalorización de divisa extranjera ** páginas correspondientes en Microsoft Dynamics 365 para las operaciones. También puede vincular a una dirección URL externa. 

> Esta [! Sugerencia] si desea vincular un informe específico del generador de administración totales en una tarea financiera de cierre del período, puede utilizar la dirección URL de informe. Para tener acceso a la dirección URL de informe, abra el informe en el diseñador de informes, y haga clic en ** archivo ** &gt; ** el informe de la vista ** abrir el informe en un explorador web. A continuación, puede copiar la dirección URL en la barra de dirección del explorador y pegarla en el campo **Vínculo de tareas** **URL**. 

Puede definir dependencias entre tareas en la plantilla. Si se ha configurado una tarea de depender de una o más tareas, dicha tarea no se puede marcar como completado hasta que todas las dependencias han finalizado. 

Puede crear plantillas cierre financieras operaciones. Puede utilizar las plantillas diferentes para seguir los procesos de cierre para los tipos del período distinto, como final de mes o de fin de año, o para realizar un seguimiento de las empresas que usan varios procesos de cierre. Una vez creada una plantilla, puede copiarla a una nueva plantilla y realizar los cambios necesarios. Puede asignar sólo una plantilla a cada programación cerrada.

### <a name="closing-schedules"></a>Programaciones de cierre

Use una programación cerrada para asignar una plantilla cercana financiera a un período financiero específico que debe ser cerrado. Las tareas de la plantilla continuación se generan automáticamente para el período específico, y la nueva programación cerrada se agrega al área de trabajo. Al crear una nueva programación cerrada, ** fecha final del período ** el campo se usa para determinar las fechas de vencimiento reales para las siguientes tareas de cierre, según la fecha de vencimiento relativa asignado en la plantilla cercana financiera. 

Asignar el calendario adecuado para la programación cerrada, para indicar los días laborables que se usará en la programación de tarea. Si no define un calendario específico, las fechas de vencimiento de la tarea utilizarán todos los días de la semana. 

También debe definir las empresas que se asociadas a la programación cerrada. Si las tareas de la plantilla se asignan a varias empresas, las tareas individuales se crearán para cada empresa que esté en la programación cierra y asignadas a la tarea de la plantilla. 

Después de que la programación cerrada se complete, seleccione ** cerrado ** la opción para él. El historial de la tarea se habrá disponible ** todas las tareas financieras de cierre del período ** de la página de lista, pero la programación cerrada se eliminará del espacio de trabajo. Una vez que se haya marcado una programación como cerrada ** ** cerrado, no podrá agregar tareas a ella, no edita tareas, no quita tareas de ella.


