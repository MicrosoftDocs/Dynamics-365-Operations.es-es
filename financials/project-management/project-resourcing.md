---
title: Recursos del proyecto
description: "En este tema se proporciona información acerca de los recursos de proyectos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a7275e9ad8d655d0d2ee5ba90a792775dec0cf05
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# <a name="project-resourcing"></a>Recursos del proyecto

[!include[banner](../includes/banner.md)]


En este tema se proporciona información acerca de los recursos de proyectos.

Un desafío para los directores de proyecto y los directores de recursos durante la fase de planificación de proyecto es la asignación de recursos, donde deben determinar y reservar el recurso correcto para trabajar en un proyecto. En Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, las capacidades de recursos para proyectos le permiten definir roles que se tratan como recursos temporales que se pueden reservar para un compromiso específico o parte del compromiso. Este tipo de recursos permite a los directores de proyecto y a los directores de recursos completar las siguientes tareas:

-   Definir un rol que contenga las competencias necesarias para que sea sencillo asignar recursos.
-   Usar roles para definir una programación de compromisos que se base en recursos reservados.
-   Estimar costes y determinar un presupuesto inicial, en función de los roles y los recursos asignados para un proyecto.
-   Usar roles para estimar el número de reservas de recursos necesarias para cada compromiso.
-   Estimar el número de recursos necesarios para el ciclo de vida completo de un proyecto.
-   Realizar un borrador de una estructura de descomposición del trabajo (WBS) mediante las asignaciones de recursos iniciales.

[![Ciclo de vida del proyecto](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg) 

Conforme continúa la planificación del proyecto, los recursos planificados se pueden reemplazar por recursos de personal. El director de proyecto también puede volver y actualizar las reservas de recursos durante cualquiera de las etapas del proyecto.

## <a name="set-up-project-resources"></a>Configurar recursos del proyecto
Debe configurar un calendario y asociarlo a un empleado o un trabajador. El calendario se usa para programar el proyecto y el horario de trabajo de los recursos reservados para el proyecto. Durante la configuración del calendario, los directores de proyecto pueden realizar la nivelación de recursos como parte de la optimización de recursos. En función de la programación del calendario, se pueden aplicar restricciones en los recursos. Puede configurar un calendario en la página **Calendarios**. 

Si configura un trabajador como recurso de proyecto, puede seleccionar entre los trabajadores que trabajan en la empresa para la que está configurando recursos o puede seleccionar trabajadores de otras empresas de la organización. Estos son recursos de empresas vinculadas. Los procedimientos siguientes explican cómo configurar un trabajador como recurso del proyecto dentro de la empresa y cómo configurar un recurso de proyecto de empresas vinculadas.

### <a name="set-up-a-worker-as-a-project-resource"></a>Configurar un trabajador como recurso de proyecto

1.  En la página **Trabajadores**, en la lista **Trabajadores**, seleccione el trabajador que va a agregar como recurso del proyecto y abra el registro de trabajador.
2.  En el Panel de acciones, haga clic en **Proyecto** &gt; **Configuración** &gt; **Configuración del proyecto**.
3.  Seleccione un calendario y luego cierre la página.

También puede especificar los proyectos predeterminados para un recurso como un tipo de asignación previa. Las asignaciones previas se pueden utilizar cuando el director de recursos o el director de proyecto sabe en qué proyectos trabajará el recurso por adelantado. Las asignaciones previas también se pueden basar en la solicitud de un cliente o patrocinador de proyecto. Para asignar previamente un proyecto, en la página **Asignar proyectos**, en la ficha **Proyectos**, en la lista **Proyectos restantes**, seleccione el proyecto adecuado.

### <a name="set-up-an-intercompany-resource"></a>Configurar un recurso de empresas vinculadas

Al configurar un trabajador como recurso de empresas vinculadas, debe completar la configuración de la empresa de préstamo y la empresa que recibe el préstamo. 

**En la empresa de préstamo:**

1.  En Finance and Operations, compruebe que la empresa de préstamo esté seleccionada y después realice el procedimiento anterior, “Configurar un trabajador como recurso de proyecto”.
2.  Vaya a **Contabilidad general **&gt; ** Configuración del registro **&gt; **Contabilidad de empresas vinculadas**. Haga clic en **Nuevo**.
3.  En el campo **Id. de entidad jurídica**, seleccione la empresa de préstamo. Rellene los campos restantes según sea necesario y, a continuación haga clic en **Guardar**.
4.  Vaya a **Administración de proyectos y contabilidad **&gt; **Configurar**&gt; **Precios** &gt; **Precio de transferencia**.** **
5.  En el formulario **Precio de transferencia**, haga clic en **Nuevo** y en el campo **Entidad jurídica a la que se presta el trabajador**, seleccione la empresa adecuada.
6.  Si solo desea prestar a la empresa de solicitud del préstamo el recurso que ha creado al principio de esta sección, en el campo **Recurso**, seleccione el nombre de recurso que ha creado. Si desea que todos los recursos de la empresa estén a disposición de la empresa que solicita el préstamo, deje el campo **Recurso** en blanco.
7.  Vaya a ** Administración de proyectos y contabilidad**&gt; **Configuración **&gt; **Parámetros de gestión de proyectos y contabilidad** y en la ficha **Empresas vinculadas**, establezca el campo **Activar la programación de recursos y las hojas de horas de empresas vinculadas" en **Sí**.

**En la empresa que solicita el préstamo:**

1.  Vaya a **Administración de proyectos y contabilidad** &gt; **Recursos del proyecto** &gt; **Lista de recursos**.
2.  En el filtro de la búsqueda, escriba el nombre de recurso que creó en el procedimiento anterior para que la empresa de préstamo compruebe que el nombre está incluido en la lista de recursos para la empresa que solicita el préstamo.

## <a name="manage-resource-competencies"></a>Gestionar competencias de recurso
Las competencias de recurso son una parte esencial de la gestión de recursos. Las competencias se pueden usar como línea base para determinar los recursos con el equilibrio correcto de aptitudes, formación, certificación y experiencia en proyectos. Debe configurar esta información para cada recurso y actualizarla periódicamente. De esta manera, puede maximizar las capacidades cuando las competencias de recursos específicas se concilian durante la asignación de recursos de proyectos. [![Ejemplos de aptitudes, certificaciones, formación y experiencia en proyectos](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg) 

Los procedimientos siguientes explican cómo configurar algunas de las capacidades para un recurso. 

Para configurar competencias para un trabajador, puede usar la página de lista **Trabajadores** en Recursos humanos o la página de lista **Recursos** en Administración de proyectos y contabilidad. Para los siguientes procedimientos, utilizaremos la página de lista **Trabajadores** en Recursos humanos.

### <a name="set-up-competencies-certificates"></a>Configuración de competencias: certificados

1.  En la página de lista **Trabajadores**, seleccione la línea del trabajador para el que está agregando la información de certificado.
2.  En el panel de acciones, en la pestaña **Trabajador**, en el grupo **Competencias**, haga clic en **Certificados**.
3.  Haga clic en **Nuevo**.
4.  En el campo **Tipo de certificado**, seleccione **PMP**.
5.  En el campo **Fecha inicial**, seleccione **1/10/2015**.
6.  Haga clic en **Guardar** y, a continuación, cierre la página.

### <a name="set-up-competencies-skills"></a>Configurar competencia: aptitudes

1.  En la página de lista **Trabajadores**, asegúrese de que el trabajador que usó en el procedimiento anterior está aún seleccionado. A continuación, en el panel de acciones, en la pestaña **Trabajador**, en el grupo **Competencias**, haga clic en **Aptitudes**.
2.  Haga clic en **Nuevo**.
3.  En el campo **Aptitud**, seleccione **Gestión de proyectos**.
4.  En el campo **Nivel**, seleccione **5 Experto**.
5.  En el campo **Fecha de nivel**, seleccione **14/1/2014**.
6.  En el campo **Años de experiencia**, escriba **10**.
7.  Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="create-a-new-project"></a>Crear un proyecto nuevo
1.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Espacios de trabajo** &gt; **Gestión de proyectos**.
2.  Haga clic en **Nuevo proyecto** y escriba los siguientes valores:
    -   **Tipo de proyecto:** - Tiempo y material
    -   **Nombre del proyecto:** - Fase 2 de la actualización XYZ
    -   **Grupo de proyectos** - TM\_WIP
    -   **Id. de contrato de proyecto:** - 00000002
3.  Haga clic en **Crear proyecto**.

### <a name="assign-a-resource-to-a-project"></a>Asignar un recurso a un proyecto

1.  Haga clic en **Recursos humanos** &gt; **Trabajadores** &gt; **Trabajadores**.
2.  En la lista **Trabajadores**, seleccione el registro del trabajador para el que ha configurado anteriormente competencias y abra el registro de trabajador.
3.  En el panel de acciones, en la pestaña **Proyecto**, en el grupo **Configuración**, haga clic en **Asignar proyectos**.
4.  En la página **Asignaciones de proyectos de validación de recursos**, haga clic en la pestaña **Proyectos**.
5.  En **Agregar el proyecto a los proyectos seleccionados**, filtre el proyecto, Fase 2 de la actualización XYZ
6.  En el panel **Proyectos restantes**, seleccione un proyecto y, a continuación, haga clic en la flecha para agregarlo al panel **Proyectos seleccionados**.
7.  Cierre la página.

Si es necesario, también puede asignar categorías para un recurso. El tipo de categoría es Coste o Ingresos. Esto lo determina la organización. Si no hay categorías asignadas para el recurso, Finance and Operations buscará la categoría predeterminada en los precios de hora para costes e ingresos.

### <a name="set-up-project-resource-and-role-characteristics"></a>Configurar características de rol y recursos de proyectos

Un director de proyecto puede usar la funcionalidad de recursos de proyecto para crear los roles que se requieren para el proyecto. Los roles se pueden usar cuando los recursos confirmados son aún desconocidos cuando se reservan los recursos. Los roles se pueden reservar temporalmente como recursos planeados, de manera que pueda continuar las etapas de planificación de proyectos. 

[![Ejemplo de rol](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Escenario:** Se contrató a Contoso para completar un proyecto de tiempo y material que tiene una acta de constitución de proyecto aprobada. El director de proyecto junior aún está completando el ámbito del proyecto. El responsable de recursos está identificando actualmente recursos específicos que se reservarán para trabajar en el nuevo proyecto. Uno de los roles que el patrocinador de proyecto solicitó, debido a la naturaleza fundamental de proyecto, es director de proyecto principal. La directora de recursos debe adquirir el nuevo recurso y define el rol en el sistema, en el caso de que el director de proyecto junior requiera la información del recurso durante la planificación del proyecto. 

Los siguientes pasos muestran cómo el director de recursos puede configurar el rol de director de proyecto principal y asociarle características de recursos. Más adelante, el rol se puede usar para buscar los recursos disponibles que coinciden con las competencias de recursos necesarias.

1.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Configurar** &gt; **Recursos** &gt; **Configurar roles**.
2.  Haga clic en **Nuevo** y escriba los siguientes valores:
    -   **Id. de rol:** Director de proyecto principal
    -   **Descripción:** Director de proyecto principal
3.  Haga clic en **Crear**.
4.  Seleccione el rol **Director de proyecto principal** y, a continuación, haga clic en **Configurar características**.
5.  En el campo **Tipo de características**, seleccione **Aptitud**.
6.  En el campo **Características disponibles**, especifique la aptitud que busca.
7.  En el campo **Tipo de característica**, seleccione **Certificado**.
8.  En el campo **Características disponibles**, especifique el tipo de certificado que desea buscar.
9.  Haga clic en **Aceptar** y cierre la página.

### <a name="assign-a-project-resource-to-a-project"></a>Asignar un recurso de proyecto a un proyecto

1.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Común** &gt; **Proyectos** &gt; **Todos los proyectos** y abra el proyecto **Fase 2 de la actualización de XYZ**.
2.  En la pestaña **Equipo del proyecto y programación**, haga clic en **Agregar**.
3.  En el campo **Rol** seleccione **Miembro del equipo**.
4.  Haga clic en **Reservar desde calendario**.
5.  En la página **Disponibilidad de recursos**, haga clic en **Parámetros de visualización**.
6.  En la página **Ajustar parámetros de visualización**, especifique los valores siguientes:
    -   **Formato de la vista de intervalo de fechas:** Día
    -   **Mostrar descripciones de disponibilidad:** Sí
    -   **Mostrar capacidad restante:** Sí
7.  En la lista de recursos, seleccione un recurso.
8.  Haga clic en **Reserva en firme** &gt; **Capacidad total**.
9.  Cierre la página.

### <a name="assign-a-resource-to-a-default-role"></a>Asignar un recurso a un rol predeterminado

Para ayudar a los directores de proyecto o de recursos, puede explorar en profundidad en los recursos que se pueden reservar para un proyecto. Puede asociar un rol predeterminado a un recurso existente o un recurso recién adquirido. Por ejemplo, cuando se contrató a Daniel, este tenía la experiencia y aptitudes para ejercer la función de la analista de negocios. El administrador de recursos asignó este rol como rol predeterminado de Daniel. Por lo tanto, la directora de recursos agregó a Daniel a un conjunto de analistas de negocios disponibles para trabajar en proyectos. 

Durante la reserva de recursos, los directores de proyecto pueden filtrar los recursos de rol que están disponibles para trabajar en proyectos. Pueden usar esta información como criterio cuando realicen análisis de decisiones de varios criterios durante el cumplimiento de recursos. También pueden agregar otras características de recursos al filtro para buscar recursos que tienen aptitudes, formación y experiencia específicas para un proyecto determinado. 

**Escenario:** Se ha iniciado un proyecto aprobado y el rol de director de proyecto principal se reservó como recurso planeado durante la fase de planificación de proyectos. El responsable de recursos ha adquirido ahora a un recurso para cumplir el rol de director de proyecto principal.

1.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Recursos del proyecto** &gt; **Lista de recursos**.
2.  En la lista **Recurso**, seleccione **Daniel Goldschmidt**.
3.  Haga clic en **Recurso del proyecto** &gt; **Mantener** &gt; **Rol del recurso**.
4.  Haga clic en **Nuevo** y escriba los siguientes valores:
    -   **Vigente:** (La fecha actual)
    -   **Caducidad:** Nunca
    -   **Rol:** Director de proyecto principal
5.  Haga clic en **Guardar** y, a continuación, cierre la página.
6.  En la pestaña **Competencias**, agregue la aptitud **ProjectMgmt** y el certificado **PMP**.

## <a name="set-up-role-based-pricing"></a>Configurar precios basados en roles
Todos los precios de coste, ventas y transferencia se pueden configurar para roles.

1.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Configurar** &gt; **Precios** &gt; **Precio de venta (hora)**.
2.  Haga clic en **Nuevo**.
3.  Especifique una fecha vigente.
4.  En la columna **Rol** seleccione un rol.
5.  En la columna **Precio**, especifique un precio para el rol del recurso seleccionado.

## <a name="form-a-project-team"></a>Formación de un equipo de proyecto
Para usar los roles que se configuraron anteriormente en un proyecto, un director de proyecto debe asociar los roles al proyecto. Se pueden asignar varios roles para un proyecto y Finance and Operations etiqueta automáticamente estos roles durante la reserva para evitar confusiones. Por ejemplo, si el director de proyecto necesita tres ingenieros de software, se generan automáticamente tres roles de ingenieros de software que tienen las etiquetas ingeniero de software 1, ingeniero de software 2 e ingeniero de software 3. Si se establecieron anteriormente características de rol para el rol, se aplican como filtro durante búsquedas para un recurso. Se pueden agregar características adicionales según sea necesario para restringir más la búsqueda. 

La configuración de la vista también se pueden personalizar para ofrecer una mejor vista de la disponibilidad de recursos. Hay opciones para mostrar la disponibilidad por hora, diaria, semanal, mensual, trimestral y anual. También hay una opción para mostrar la capacidad disponible y restante en los recursos. Esta opción es útil para la gestión del tiempo cuando se calcula el tiempo disponible para las actividades o la disponibilidad de recursos. 

El director de proyecto puede seleccionar un rol en la página y, a continuación, si hay un recurso disponible que se adapta al requisito, seleccionarlo para reservar un recurso para ese rol. Tenga en cuenta que no es necesario que los recursos estén reservados a este momento durante la fase de planificación. Al crear un WBS, puede reemplazar roles por los recursos de personal para el proyecto. Si los roles se reemplazan con los recursos de personal en la WBS, la configuración de recursos actualiza automáticamente la programación y la lista del equipo del proyecto. 

[![Lista del equipo del proyecto que incluye tanto roles como recursos reales](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

El director de proyecto tiene varias opciones para reservar un recurso para un proyecto como **Capacidad restante**, **Capacidad total**, **Porcentaje de capacidad**, y **Especificar horas**. Estas opciones de reserva se pueden cancelar en cualquier momento si cambian las asignaciones de recursos. Se admiten dos tipos de reserva:

-   **Reserva en firme**: Se ha aprobado y confirmado la reserva de recursos para trabajar en el compromiso para la duración especificada.
-   **Reserva provisional**: Las reservas de recursos se establecieron provisionalmente para trabajar en el compromiso para la duración especificada.

El siguiente procedimiento explica cómo crear un equipo de proyecto.

### <a name="create-a-project-team"></a>Crear un equipo de proyecto

1.  En la página de lista **Todos los proyectos**, seleccione un proyecto y, a continuación, haga clic en **Editar**.
2.  En la pestaña **Equipo del proyecto y programación**, en el campo **Programar fecha final**, especifique la fecha inicial de la programación más un mes. Por ejemplo, si la fecha inicial de la programación es el 24 de junio de 2017 (24/06/2017), escriba **24/07/2017**.
3.  Haga clic en **Agregar**.
4.  En el panel **Agregar roles al proyecto**, en el campo **Rol**, seleccione **Director de proyecto principal**.
5.  Haga clic en **Competencias requeridas**.
6.  En la página **Elegir características**, las características que estableció anteriormente para el rol de director de proyecto principal se seleccionan de forma predeterminada. Haga clic en **Aceptar**.
7.  En la página **Agregue roles al proyecto**, en el campo **Número de recursos**, escriba **1**.
8.  En el campo **Recurso**, las búsquedas muestran todos los recursos con las competencias necesarias. Seleccione **Daniel Goldschmidt** y, a continuación, haga clic en **Crear**.
9.  En la página **Proyecto**, haga clic en **Agregar**.
10. En el panel **Agregar roles al proyecto**, en el campo **Rol**, seleccione **Miembro del equipo**. En el campo **Número de recursos**, escriba **5**.
11. Haga clic en **Crear**.
12. En la página **Proyectos**, haga clic en **Cumplir con recurso**.

## <a name="resource-capacity-synchronization"></a>Sincronización de capacidad de recursos
Los procesos para la sincronización de recursos ayudan a garantizar que la información del calendario y del calendario de base entran lentamente en la programación de recursos del proyecto. Si se modifica el calendario, los procesos realizan las actualizaciones necesarias a la programación de recursos del proyecto. Los procesos también ayudan a mejorar el rendimiento, porque la información del recurso del calendario se sincroniza por adelantado, de modo que las actualizaciones a la información de la programación de recursos se produce con mayor rapidez. Se recomienda la programación de los procesos como lote en lugar de uno cada vez. De no ser así, existe el riesgo de que alguien olvidará las fechas inclusivas en las que la información se sincronizó por última vez. Si no se usan fechas inclusivas, pueden producir huecos durante la sincronización de fecha.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Sincronización de calendario](./media/projectresourcing04-1024x471.jpg)

**Sincronizar acumulaciones de capacidad de recursos**

El proceso de sincronización está diseñado para sincronizar toda la información del calendario de recursos. Esta información incluye la información del calendario base sobre los cambios a la tabla de la capacidad del calendario de recursos del proyecto. Si se agregan nuevos recursos en el proyecto, la sincronización ayuda a garantizar que la información actualizada del calendario está disponible. Esta sincronización se puede realizar en cualquier momento. 

Recomendamos que use un lote. Las opciones están disponibles en la sincronización de reservas de capacidades.

-   Haga clic en **Administración de proyectos y contabilidad** &gt; **Periódico** &gt; **Sincronización de capacidad** &gt; **Sincronizar acumulaciones de capacidad de recursos**.

| Opción | Descripción                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sí    | Sincronizar todos los datos de recursos con la información del calendario y del calendario base, y reemplazar toda la información del calendario de la capacidad de recursos del proyecto.                                                  |
| No     | Sincronizar los datos de recursos, en función del código del intervalo de fechas, y las fechas inicial y final especificadas. Esta opción no quita los datos existentes y actualiza la información únicamente para los recursos recién agregados. |

[![Proceso de sincronización](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Configurar roles en plantillas de WBS
Los directores de proyecto pueden configurar plantillas de WBS que pueden aplicar al crear una WBS para proyectos nuevos. Los directores de proyecto pueden agregar roles al crear una plantilla. Use el siguiente procedimiento para asignar un rol a una plantilla de WBS.** **

1.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Configurar** &gt; **Proyectos** &gt; **Plantillas de estructura de descomposición del trabajo**.
2.  Haga clic en **Detalles** para una plantilla de WBS seleccionada.
3.  Seleccione una tarea en la lista y, a continuación, en el campo **Rol**, seleccione un rol para asignarlo a la tarea.

### <a name="work-with-a-wbs"></a>Trabajar con una WBS

Puede crear una nuevo WBS o puede copiar una WBS de una plantilla de WBS existente. Un director de proyecto puede gestionar fácilmente los recursos asignando roles a las nuevas tareas en la WBS. Los roles se pueden reemplazar después de adquirirse un recurso o después de que se identifique un recurso confirmado para trabajar en la tarea. Esta flexibilidad permite a los directores de proyecto realizar las tareas siguientes:

-   Identificar el número de recursos necesarios para los paquetes de trabajo de WBS.
-   Calcular costes del proyecto.
-   Determinar un presupuestario preliminar.
-   Estimar la duración de la actividad, en función de los roles y recursos.
-   Desarrollar algunos planes de gestión de proyectos, según la información del proyecto disponible.

Se han agregado opciones adicionales en la WBS para usar mejor mejor la funcionalidad de recursos.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Opción</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Asignaciones de recursos</td>
<td>Vea los recursos asignados, las fechas, el número de horas y el tipo de reserva para las tareas de la WBS.</td>
</tr>
<tr class="even">
<td>Generar equipo automáticamente</td>
<td>Agregue automáticamente recursos planificados mediante los roles asociados a una tarea. Finance and Operations sugiere automáticamente recursos planificados mediante el análisis de decisión de varios criterios que se basa en roles. Después del establecimiento de los roles y del esfuerzo (horas) para las tareas de una WBS y de que se haya liberado la estructura, haga clic en <strong>Generar equipo automáticamente</strong>. El número necesario de recursos planificados se agrega a la WBS y la pestaña <strong>Equipo del proyecto y programación</strong>.</td>
</tr>
<tr class="odd">
<td>Recurso (lista desplegable)</td>
<td>En la página <strong>Iniciar asignación de recursos</strong>, puede seleccionar recursos para reservar en firme o reservar de forma provisional, en función de la duración especificada. Puede ajustar las opciones de visualización para ver y establecer la duración de las actividades de recursos. Puede seleccionar y asignar recursos en el nivel del paquete de trabajo mediante las siguientes opciones:
<ul>
<li><strong>Aceptar</strong>: Confirme los cambios al recurso asignado a una tarea.</li>
<li><strong>Cancelar</strong>: Cancele los cambios al recurso asignado a una tarea.</li>
<li><strong>Asignar automáticamente</strong> – Esta opción selecciona un recurso de personal disponible con un rol que coincida para la tarea seleccionada.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  Haga clic en **Gestión de proyectos y contabilidad** &gt; **Proyectos** &gt; **Todos los proyectos**.
2.  En la lista, seleccione el proyecto **Fase 2 de la actualización XYZ**.
3.  Haga clic en **Plan** &gt; **Actividades** &gt; **Estructura de descomposición del trabajo**.
4.  Haga clic en **Nuevo** para agregar las siguientes actividades de nivel uno a la WBS:
    -   Iniciación
    -   Planificación
    -   En ejecución
    -   Supervisión y control
    -   Cerrar

5.  Defina las fechas y el esfuerzo (horas), tal y como se muestra en la captura de pantalla siguiente.[![Establecimiento de las fechas y el esfuerzo](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)
6.  Seleccione la línea de tareas **Iniciación** y, a continuación, en el campo **Rol**, seleccione **Director de proyecto principal**.
7.  Haga clic en **Publicar**.
8.  En la misma línea, en el campo **Recurso**, seleccione **Daniel Goldschmidt**.
9.  Haga clic en **Aceptar**.
10. Seleccione la línea de la tarea **Planificación** y, a continuación, en el campo **Rol**, seleccione **Analista de negocios**.
11. Haga clic en **Publicar** y, a continuación, en **Generar equipo automáticamente**.
12. En el cuadro de diálogo que aparece, haga clic en **Sí**.
13. En el campo **Recurso**, compruebe que el valor es **Analista de negocios 1**.
14. Para el recurso **Analista de negocios 1**, abra la búsqueda y haga clic en **Iniciar formulario de asignación de recursos**.
15. Seleccione un trabajador para la tarea.
16. Haga clic en **Asignación provisional** &gt; **Capacidad completa**.
17. Haga clic en **Guardar** y cierre la página. 

> [!NOTE] 
> No recibe una advertencia que el recurso especificado es ahora 2, porque el número de recursos sigue siendo 1.
18. En la página **Estructura de descomposición del trabajo**, valide la asignación de recursos en la WBS y, a continuación, haga clic en **Guardar**.

## <a name="resource-fulfillment-for-planned-resources"></a>Cumplimiento de recursos para recursos planificados
Un director de proyecto puede planificar los roles de recursos necesarios para un proyecto. El administrador de recursos verá estos recursos planificados como solicitudes en la página **Cumplimiento de recursos** y puede asignar recursos reales.

1.  Haga clic en **Gestión de proyectos y contabilidad** &gt; **Proyectos** &gt; **Todos los proyectos**.
2.  En la lista, seleccione el proyecto **Fase 2 de la actualización XYZ**.
3.  Haga clic en **Proyecto**.
4.  Haga clic en **Editar**.
5.  En la pestaña **Equipo del proyecto y programación**,** **haga clic en **Agregar**.
6.  En el cuadro de diálogo **Agregar roles**, seleccione el rol **Desarrollador de software**.
7.  Haga clic en **Crear**.
8.  Cierre la página del proyecto.
9.  Haga clic en **Administración de proyectos y contabilidad** &gt; **Recursos del proyecto** &gt; **Cumplimiento de recursos**.
10. Seleccione **Desarrollador de software 1** para el proyecto **Fase 2 de la actualización XYZ**.
11. Seleccione un trabajador y haga clic en **Asignar**.
12. Compruebe que se ha eliminado la línea para **Desarrollador de software 1** para el proyecto **Fase 2 del proyecto de actualización de XYZ**.
13. En la pestaña **Equipo del proyecto y programación**, para el proyecto **Fase 2 de la actualización de XYZ**, compruebe que se ha agregado el trabajador que seleccionó en el paso 11 como **Desarrollador de software**.

## <a name="requests-for-project-resources"></a>Solicitudes de recursos de proyecto
La funcionalidad de programación de recursos del proyecto solo admite a administradores de recursos para distribuir recursos de personal en compromisos o proyectos. Para habilitar esta funcionalidad, realice las tareas siguientes, o compruebe que se han realizado.

-   Configurar secuencias numéricas.
-   Configuración de flujos de trabajo de Gestión de proyectos y contabilidad.
-   Habilitar flujo de trabajo de solicitud de recurso.

Una vez que haya comprobado o haya completado las tareas anteriores, puede completar las tareas siguientes según sea necesario.

-   Cree una solicitud de recurso de un recurso con personal de reserva provisional.
-   Supervise las solicitudes de recursos.
-   Rellene las solicitudes de recursos.
-   Solicite un recurso de personal de EDT.
-   Reserve recursos para un proyecto sin un pedido de recurso de personal.

## <a name="monitor-project-teams"></a>Supervisar los equipos de proyecto
1.  Haga clic en **Gestión de proyectos y contabilidad** &gt; **Proyectos** &gt; **Todos los proyectos**.
2.  En la lista de proyectos, haga clic en el vínculo **Id. de proyecto** para el proyecto **Fase 2 de la actualización de XYZ**.
3.  En la ficha desplegable **Equipo del proyecto y programación**, compruebe que los recursos de proyectos mostrados son correctos.





