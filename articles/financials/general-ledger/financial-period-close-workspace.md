---
title: "Espacio de trabajo de cierre del período financiero"
description: "Este artículo proporciona una visión general del espacio de trabajo de cierre del período financiero y la configuración asociada."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerPeriodCloseProjectWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13791
ms.assetid: 6ee51758-639b-448e-9cb2-56cf1d804273
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: b5dbefc953c0f1608b6f5b5676850a0e9aba36cc
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="financial-period-close-workspace"></a>Espacio de trabajo de cierre del período financiero

[!include[banner](../includes/banner.md)]


Este artículo proporciona una visión general del espacio de trabajo de cierre del período financiero y la configuración asociada.

Espacio de trabajo de cierre del período financiero

El espacio de trabajo **Cierre de período financiero** le permite realizar un seguimiento de sus procesos de cierre financiero en las empresas, las áreas, y las personas. En función de su vista del espacio de trabajo **Cierre de período financiero**, verá todas las tareas y estados de una programación de cierre, o sólo de las tareas que tiene asignadas. 

Debe seleccionar una programación de cierre en la parte superior del espacio de trabajo. Todos los datos que se muestra en el espacio de trabajo se filtran por la programación de cierre seleccionada.

### <a name="summary-tiles"></a>Iconos de resumen

Los iconos de **Resumen** le ofrecen una visión general del proceso y los indicadores le ayudarán a realizar el seguimiento del proceso de cierre. Puede ver las tareas vencidas, las restantes del día, las tareas que vencen hoy pero que está bloqueadas debido a las dependencias y todas las tareas restantes del proceso. Esta información se muestra para todas las empresas incluidas en la programación de cierre seleccionada.

### <a name="tasks-and-status-section"></a>Sección Tareas y estados

En la sección **Estado de tareas**, se clasifica el estado de la programación de cierre total de varias maneras: estado por empresa, estado por área y estado por persona responsable. Puede ver el estado de todas las tareas en la programación de cierre, sólo las tareas que vencen hoy, o las tareas ya vencidas cambiando el filtro en la parte superior de la lista de tarjeta. También puede seleccionar el filtro de la empresa para ver el estado de una empresa específica. Cada ficha del estado ofrece un desglose por el porcentaje que se ha completado y por el número de tareas restantes. Haga clic en la acción **Ver detalles** para filtrar la lista de tareas detallada por la tarjeta seleccionada. 

La última ficha es para la lista de tareas detallada. Esta lista muestra la lista de tareas completa y se puede filtrar de modo que muestre solo la tareas que les interesen. Puede filtrar la lista de tareas de varias maneras. Por ejemplo, puede filtrar por fecha de vencimiento, empresa asociada, y área asociada. También puede seleccionar para mostrar u ocultar tareas completadas en la lista de tareas. 

Se usan dos indicadores para las tareas:

-   Un icono de signo de exclamación indica que la tarea está vencida. En las tareas vencidas, la fecha de vencimiento también se resaltada en rojo.
-   Un icono de candado indica que la tarea depende de otras tareas que no se han completado aún. Una tarea que está bloqueada por dependencias no se puede marcar como completada. Puede establecer las dependencias de una tarea mediante la acción **Establecer dependencia** .

El nombre de tarea es un hipervínculo a la página Microsoft Dynamics 365 for Operations o a otra página web donde el usuario debe ir para completar el trabajo. Puede establecer este hipervínculo mediante el campo **Vínculo de tareas** al editar o crear una tarea. 

Puede adjuntar archivos, notas, imágenes, y las direcciones URL a una tarea mediante la acción **Archivos adjuntos**. Por ejemplo, puede indicar los números de diarios que se utilizan como parte de una tarea, agregar comentarios acerca de una tarea específica, o adjuntar un archivo de informe impreso para una tarea. Un icono aparece en la columna **Archivos adjuntos** para la tarea si hay un archivo adjunto. 

La opción **Tarea completada** se debe seleccionar manualmente después de que la tarea se haya completado. Cuando una tarea se ha marcado como completada, el campo **Fecha de finalización** se actualiza automáticamente a la fecha y hora actuales. Los indicadores de la dependencia también se actualizarán como corresponda.

## <a name="all-financial-period-close-tasks-list-page"></a>Página de lista Todas las tareas de cierre del período financiero
Puede ver todas las tareas de cierre del período actual y anterior en la página de lista **Todas las tareas de cierre del período financiero** . Esta página de lista se puede usar para el análisis de historial del proceso de cierre, ya que incluye información acerca de la fecha de vencimiento programada, la fecha de finalización real y la persona que completó la tarea. Es fácil exportar la información de esta página de lista a Microsoft Excel con fines de informes y auditoría.

## <a name="financial-period-close-configuration-page"></a>Página Configuración de cierre del período financiero
Para poder usar el espacio de trabajo **Cierre del periodo financiero**, debe configurar el proceso en Microsoft Dynamics 365 for Finance and Operations con la página **Configuración de cierre del período financiero**. (Haga clic en **Contabilidad general** &gt; **Cierre de período** &gt; **Configuración de cierre del período financiero**.)

### <a name="resources"></a>Recursos

En la ficha **Recursos** se definen las personas implicadas en los procesos de cierre. Cualquier empleado responsable de una tarea de cierre primero se debe asignar aquí. También se debe especificar la vista de empleado en el espacio de trabajo. Están disponibles las siguientes opciones:

-   **Solo tareas asignadas**: el usuario verá solo las tareas que tiene asignadas.
-   **Todos los estados y tareas**: el usuario verá todas las tareas de cierre y los estados del proceso general.

Los usuarios que tienen permisos para ver solo sus tareas asignadas no podrán agregar tareas a la lista de tareas, editar tareas o quitar tareas de la lista de tareas.

### <a name="task-areas"></a>Áreas de tareas

Las áreas de tareas se usan para agrupar las tareas de cierre en áreas lógicas de propiedad dentro de su organización. Por ejemplo, Proveedores, Clientes o Contabilidad general se pueden usar como áreas de tareas.

### <a name="calendars"></a>Calendarios

Para crear y editar calendarios de cierre financiero use la pestaña Calendario. En esta pestaña, defina los días laborables para procesos de cierre y úsela también para programar tareas de cierre de programación.  Cree un calendario nuevo e indique los días laborables que se utilizarán para la programación de tarea.  Es lo mejor para crear un calendario para un período largo de tiempo, como un año o varios años, ya que se puede editar después de su creación.  Después de crear el calendario, haga clic en el botón Editar para actualizar el calendario en días específicos, como festivos.  Las siguientes tareas de cierre se programarán los días en que el valor de Control se haya establecido en Abierto.  Si las siguientes tareas de cierre no se deben programar en un día concreto, ese día debe tener el valor de Control establecido en Cerrado.

### <a name="templates"></a>Plantillas

Use una plantilla de cierre financiero para definir todas las tareas que forman parte de un proceso de cierre. Una tarea de cierre es un esfuerzo de trabajo periódico que se asigna a un usuario para que lo complete como parte de cada proceso de cierre. En la plantilla, debe definir una fecha de vencimiento relativa para cada tarea de cierre. La fecha de vencimiento relativa es el número de días antes o después de la fecha final del período definida en la que vencerá la tarea en cada período. También se asigna una hora de vencimiento a cada tarea. La hora de vencimiento se establece usando el contexto de su zona horaria y se convierte a la zona horaria de cada usuario. 

Puede asignar una tarea en la plantilla a una o más empresas en las que se aplica esa tarea. Si se asigna otra persona para completar ese esfuerzo de trabajo en cada empresa, es posible que resulte útil crear varias tareas para el mismo esfuerzo del trabajo. Cree una tarea para cada empresa. 

El elemento de menú **Vínculo de tarea** está asociado al esfuerzo de trabajo de la tarea y se puede usar para ir directamente a la página asociada desde el vínculo de la tarea en el espacio de trabajo. Por ejemplo, se puede vincular una tarea cerrada para ejecutar el proceso de revalorización de divisa para los proveedores a la página **Revalorización de divisa extranjera** asociada en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. También puede vincular a una dirección URL externa. 

> [Sugerencia] Si desea vincular un informe específico del Management Reporter a una tarea de cierre del período financiero, puede usar la dirección URL del informe. Para obtener acceso a la dirección URL del informe, abra el informe en el diseñador de informes y, a continuación, haga clic en **Archivo** &gt; **Ver informe** para abrir el informe en un explorador web. A continuación, puede copiar la dirección URL en la barra de dirección del explorador y pegarla en el campo **Vínculo de tareas** **URL**. 

Puede definir dependencias entre tareas en la plantilla. Si se ha configurado una tarea para que dependa de una o más tareas, esa tarea no se podrá marcar como completada hasta que se hayan completado todas las dependencias. 

Puede crear varias plantillas de cierre financiero. Puede utilizar las diferentes plantillas para realizar un seguimiento de los procesos de cierre de los diferentes tipos de períodos como final de mes o de fin de año, o para realizar un seguimiento de las empresas que usan procesos de cierre diferentes. Una vez creada una plantilla, puede copiarla en una nueva plantilla y realizar los cambios necesarios. Puede asignar sólo una plantilla a cada programación de cierre.

### <a name="closing-schedules"></a>Programaciones de cierre

Use una programación de cierre para asignar una plantilla de cierre financiero a un período financiero específico que se debe cerrar. Las tareas de la plantilla se generan automáticamente para el período específico, y la nueva programación de cierre se agrega al espacio de trabajo. Al crear una nueva programación de cierre, el campo **Fecha final del período** se usa para determinar las fechas de vencimiento reales de las tareas de cierre, según la fecha de vencimiento relativa asignada en la plantilla de cierre financiero. 

Asigne el calendario adecuado para la programación de cierre para indicar los días laborables que se usarán en la programación de tarea. Si no define un calendario específico, las fechas de vencimiento de la tarea utilizarán todos los días de la semana. 

También debe definir las empresas que se asociarán a la programación de cierre. Si las tareas de la plantilla se asignan a varias empresas, las tareas individuales se crearán para cada empresa que esté en la programación de cierre y se asignarán a la tarea de la plantilla. 

Después de finalizar una programación de cierre, seleccione la opción **Cerrada** . El historial de tareas seguirá estando disponible en la página de lista **Todas las tareas de cierre del período financiero**, pero la programación de cierre se eliminará del espacio de trabajo. Una vez que se haya marcado una programación de cierre como **Cerrada**, no podrá agregar tareas, editar tareas ni quitar tareas.




