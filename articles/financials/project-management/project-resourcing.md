---
title: Recursos del proyecto
description: "En este tema se proporciona información acerca de los recursos de proyectos."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
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
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8139134ed230cc1525c698fadb20309afee0a68f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="project-resourcing"></a>Recursos del proyecto

[!include[banner](../includes/banner.md)]

En este tema se proporciona información acerca de los recursos de proyectos.

Un desafío para los directores de proyecto y los directores de recursos durante la fase de planificación de proyecto es la asignación de recursos, donde deben determinar y reservar el recurso correcto para trabajar en un proyecto. En Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, las capacidades de recursos para proyectos le permiten definir roles que se tratan como recursos temporales que se pueden reservar para un compromiso específico o como parte del compromiso. Este tipo de recursos permite a los directores de proyecto y a los directores de recursos completar las siguientes tareas:

- Definir un rol que contenga las competencias necesarias para que sea sencillo asignar recursos.
- Usar roles para definir una programación de compromisos que se base en recursos reservados.
- Estimar costes y determinar un presupuesto inicial, en función de los roles y los recursos asignados para un proyecto.
- Usar roles para estimar el número de reservas de recursos necesarias para cada compromiso.
- Estimar el número de recursos necesarios del ciclo de vida completo de un proyecto.
- Realizar un borrador de una estructura de descomposición del trabajo (WBS) mediante las asignaciones de recursos iniciales.

[![Ciclo de vida del proyecto](./media/projectresourcing02-1024x812.jpg)](./media/projectresourcing02.jpg)

Conforme continúa la planificación del proyecto, los recursos planificados se pueden reemplazar por recursos de personal. El director de proyecto también puede volver y actualizar las reservas de recursos durante cualquiera de las etapas del proyecto.

## <a name="set-up-project-resources"></a>Configurar recursos del proyecto
Debe configurar un calendario y asociarlo a un empleado o un trabajador. El calendario se usa para programar el proyecto y el horario de trabajo de los recursos reservados para el proyecto. Durante la configuración del calendario, los directores de proyecto pueden realizar la nivelación de recursos como parte de la optimización de recursos. En función de la programación del calendario, se pueden aplicar restricciones en los recursos. Puede configurar un calendario en la página **Calendarios**.

Al configurar un trabajador como recurso de proyecto, puede seleccionar aquellos trabajadores que estén trabajando en la compañía para la que esté configurando recursos. Asimismo, puede seleccionar los trabajadores de otras empresas que formen parte de su organización. Estos trabajadores se conocen como recursos de empresas vinculadas.

Los procedimientos siguientes explican cómo configurar un trabajador como recurso del proyecto en la empresa y cómo configurar un recurso de proyecto de empresas vinculadas.

### <a name="set-up-a-worker-as-a-project-resource"></a>Configurar un trabajador como recurso de proyecto

1. En la página **Trabajadores**, en la lista **Trabajadores**, seleccione el trabajador que va a agregar como recurso del proyecto y abra el registro de trabajador.
2. En el Panel de acciones, seleccione **Proyecto** &gt; **Configuración** &gt; **Configuración del proyecto**.
3. Seleccione un calendario y luego cierre la página.

También puede especificar los proyectos predeterminados para un recurso como un tipo de asignación previa. Las asignaciones previas se pueden utilizar cuando el director de recursos o el director de proyecto sabe en qué proyectos trabajará el recurso por adelantado. Las asignaciones previas también se pueden basar en la solicitud de un cliente o patrocinador de proyecto. Para asignar previamente un proyecto, en la página **Asignar proyectos**, en la ficha **Proyectos**, en la lista **Proyectos restantes**, seleccione el proyecto adecuado.

### <a name="set-up-an-intercompany-resource"></a>Configurar un recurso de empresas vinculadas

Al configurar un trabajador como recurso de empresas vinculadas, debe completar la configuración de la empresa de préstamo y la empresa que recibe el préstamo.

**En la empresa de préstamo**

1. En Finance and Operations, compruebe que la empresa de préstamo esté seleccionada y, a continuación realice el procedimiento que se detalló en la sección anterior, “Configurar un trabajador como recurso de proyecto”.
2. En la página **Contabilidad de empresas vinculadas**, seleccione **Nuevo**.
3. En el campo **Id. de entidad jurídica**, seleccione la empresa de préstamo. Rellene los campos restantes según sea necesario y, a continuación seleccione **Guardar**.
4. En la página **Precio de transferencia**, seleccione **Nuevo**.
5. En el campo **Entidad jurídica a la que se presta el trabajador**, seleccione la empresa adecuada.
6. Si solo desea prestar a la empresa de solicitud del préstamo el recurso que ha creado al principio de esta sección, en el campo **Recurso**, seleccione el nombre de recurso que haya creado. Si desea que todos los recursos de la empresa estén a disposición de la empresa que solicita el préstamo, deje el campo **Recurso** en blanco.
7. Vaya a la página **Parámetros de administración de proyectos y contabilidad** en la pestaña **Empresas vinculadas** y establezca la opción **Activar la programación de recursos y las hojas de horas de empresas vinculadas** en **Sí**.

**En la empresa que solicita el préstamo**

- En la página **Lista de recursos**, en el filtro de la búsqueda, escriba el nombre de recurso que creó para la empresa de préstamo y compruebe que el nombre está incluido en la lista de recursos de la empresa que solicita el préstamo.

## <a name="manage-resource-competencies"></a>Gestionar competencias de recurso
Las competencias de recurso son una parte esencial de la gestión de recursos. Las competencias se pueden usar como línea base para determinar los recursos con el equilibrio correcto de aptitudes, formación, certificación y experiencia en proyectos. Debe configurar esta información para cada recurso y actualizarla periódicamente. De esta manera, puede maximizar las capacidades cuando las competencias de recursos específicas se concilian durante la asignación de recursos de proyectos.

[![Ejemplos de aptitudes, certificaciones, formación y experiencia en proyectos](./media/projectresourcing06-1024x383.jpg)](./media/projectresourcing06.jpg)

Los procedimientos siguientes explican cómo configurar algunas de las capacidades para un recurso.

Para configurar competencias para un trabajador, puede usar la página de lista **Trabajadores** en Recursos humanos o la página de lista **Recursos** en Administración de proyectos y contabilidad. Para los siguientes procedimientos, utilizaremos la página de lista **Trabajadores** en Recursos humanos.

### <a name="set-up-competencies-certificates"></a>Configuración de competencias: certificados

1. En la página de lista **Trabajadores**, seleccione la línea del trabajador para el que está agregando la información de certificado.
2. En el panel de acciones, en la pestaña **Trabajador**, en el grupo **Competencias**, seleccione **Certificados**.
3. Seleccione **Nuevo** y, en el campo **Tipo de certificado**, seleccione **PMP**.
4. En el campo **Fecha inicial**, seleccione **10/1/2015** y seleccione **Guardar**.

### <a name="set-up-competencies-skills"></a>Configurar competencia: aptitudes

1. En la página de lista **Trabajadores**, asegúrese de que el trabajador que usó en el procedimiento anterior está aún seleccionado. A continuación, en el panel de acciones, en la pestaña **Trabajador**, en el grupo **Competencias**, seleccione **Aptitudes**.
2. Seleccione **Nuevo**.
3. En el campo **Aptitud**, seleccione **Gestión de proyectos**.
4. En el campo **Nivel**, seleccione **5 Experto**.
5. En el campo **Fecha de nivel**, seleccione **14/1/2014**.
6. En el campo **Años de experiencia**, escriba **10**.
7. Haga clic en **Guardar** y, a continuación, cierre la página.

## <a name="create-a-new-project"></a>Crear un proyecto nuevo
1. En la página **Administración de proyectos**, seleccione **Nuevo proyecto** y especifique los valores siguientes:

    - **Tipo de proyecto:** Tiempo y material
    - **Nombre del proyecto:** Fase 2 de la actualización XYZ
    - **Grupo de proyectos:** TM\_WIP
    - **Id. de contrato de proyecto:** 00000002

2. Seleccione **Crear proyecto**.

### <a name="assign-a-resource-to-a-project"></a>Asignar un recurso a un proyecto

1. En la página **Trabajadores**, en la lista **Trabajadores**, seleccione el registro del trabajador para el que ha configurado anteriormente las competencias y abra el registro de trabajador.
2. En el panel de acciones, en la pestaña **Proyecto**, en el grupo **Configuración**, seleccione **Asignar proyectos**.
3. En la página **Asignaciones de proyecto de validación de recursos**, en la pestaña **Proyectos** del campo **Agregar el proyecto a los proyectos seleccionados**, filtre el proyecto **Fase 2 de la actualización XYZ**.
4. En el panel **Proyectos restantes**, seleccione un proyecto y, a continuación, haga clic en el botón de la flecha para agregarlo al panel **Proyectos seleccionados**.

Si es necesario, también puede asignar categorías para un recurso. El tipo de categoría es **Coste** o **Ingresos**. La organización es la que se encarga de determinar el tipo de categoría. Si no hay categorías asignadas para el recurso, Finance and Operations buscará la categoría predeterminada en los precios de hora para costes e ingresos.

### <a name="set-up-project-resource-and-role-characteristics"></a>Configurar características de rol y recursos de proyectos

Un director de proyecto puede usar la funcionalidad de recursos de proyecto para crear los roles que se requieren para el proyecto. Los roles se pueden usar cuando los recursos confirmados son aún desconocidos cuando estos se reservan. Los roles se pueden reservar temporalmente como recursos planeados, de manera que pueda continuar las etapas de planificación de proyectos.

[![Ejemplo de rol](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg) 

**Escenario:** Se contrató a Contoso para completar un proyecto de tiempo y material que tiene una acta de constitución de proyecto aprobada. El director de proyecto junior aún está completando el ámbito del proyecto. El responsable de recursos está identificando actualmente recursos específicos que se reservarán para trabajar en el nuevo proyecto. Debido a la naturaleza fundamental de proyecto, uno de los roles que el patrocinador de proyecto solicitó, es el de director de proyecto principal. El director de recursos debe adquirir el nuevo recurso y definir el rol en el sistema, en el caso de que el director de proyecto junior requiera la información del recurso durante la planificación del proyecto.

Los siguientes pasos muestran cómo el director de recursos puede configurar el rol de director de proyecto principal y asociarle características de recursos. Más adelante, el rol se puede usar para buscar los recursos disponibles que coinciden con las competencias de recursos necesarias.

1. En la página **Configurar roles**, seleccione **Nuevo** y especifique los valores siguientes:

    - **Id. de rol:** Director de proyecto principal
    - **Descripción:** Director de proyecto principal

2. Seleccione **Crear**.
3. Seleccione el rol **Director de proyecto principal** y, a continuación, haga clic en **Configurar características**.
4. En el campo **Tipo de características**, seleccione **Aptitud**.
5. En el campo **Características disponibles**, especifique el tipo de aptitud que desea buscar.
6. En el campo **Tipo de característica**, seleccione **Certificado**.
7. En el campo **Características disponibles**, especifique el tipo de certificado que desea buscar.

### <a name="assign-a-project-resource-to-a-project"></a>Asignar un recurso de proyecto a un proyecto

1. En la página **Todos los proyectos**, seleccione el proyecto **Fase 2 de la actualización XYZ**.
2. En la pestaña **Equipo del proyecto y programación**, haga clic en **Agregar**.
3. En el campo **Rol** seleccione **Miembro del equipo**.
4. Seleccione **Reservar desde calendario**.
5. En la página **Disponibilidad de recursos**, haga clic en **Ver configuración**.
6. En la página **Ajustar parámetros de visualización**, especifique los valores siguientes:

    - **Formato de la vista de intervalo de fechas:** Día
    - **Mostrar descripciones de disponibilidad:** Sí
    - **Mostrar capacidad restante:** Sí

7. En la lista de recursos, seleccione un recurso.
8. Seleccione **Reserva en firme** y **Capacidad total**.


### <a name="assign-a-resource-to-a-default-role"></a>Asignar un recurso a un rol predeterminado

Para ayudar a los directores de proyecto o de recursos, puede explorar en profundidad en los recursos que se pueden reservar para un proyecto. Puede asociar un rol predeterminado a un recurso existente o un recurso recién adquirido. Por ejemplo, cuando se contrató a Daniel, este tenía la experiencia y aptitudes para ejercer la función de la analista de negocios. El administrador de recursos asignó este rol como rol predeterminado de Daniel. Por lo tanto, la directora de recursos agregó a Daniel a un conjunto de analistas de negocios disponibles para trabajar en proyectos.

Durante la reserva de recursos, los directores de proyecto pueden filtrar los recursos de rol que están disponibles para trabajar en proyectos. Pueden usar esta información como criterio cuando realicen análisis de decisiones de varios criterios durante el cumplimiento de recursos. También pueden agregar otras características de recursos al filtro para buscar recursos que tienen aptitudes, formación y experiencia específicas para un proyecto determinado.

**Escenario:** Se ha iniciado un proyecto aprobado y el rol de director de proyecto principal se reservó como recurso planeado durante la fase de planificación de proyectos. El responsable de recursos ha adquirido ahora a un recurso para cumplir el rol de director de proyecto principal.

1. En la página **Lista de recursos**, seleccione **Daniel Goldschmidt**.
2. En la página **Rol del recurso**, seleccione **Nuevo** y especifique los valores siguientes:

    - **Vigente:** escriba la fecha actual.
    - **Vencimiento:** seleccione **Nunca**.
    - **Rol:** escriba **Director de proyecto principal**.

3. Haga clic en **Guardar** y, a continuación, cierre la página.
4. En la pestaña **Competencias**, agregue la aptitud **ProjectMgmt** y el certificado **PMP**.

## <a name="set-up-role-based-pricing"></a>Configurar precios basados en roles
Todos los precios de coste, ventas y transferencia se pueden configurar para roles.

1. En la página **Precio de venta (hora)**, seleccione **Nuevo** y especifique una fecha de vigencia.
2. En la columna **Rol** seleccione un rol.
3. En la columna **Precio**, especifique un precio para el rol del recurso seleccionado.

## <a name="form-a-project-team"></a>Formación de un equipo de proyecto
Para usar los roles que se configuraron anteriormente en un proyecto, un director de proyecto debe asociar los roles al proyecto. Se pueden asignar varios roles en un proyecto. Para evitar confusiones, Finance and Operations etiqueta automáticamente esos roles durante la reserva. Por ejemplo, si el director de proyecto necesita tres ingenieros de software, se generan automáticamente tres roles de ingenieros de software que tienen las etiquetas **ingeniero de software 1**, **ingeniero de software 2** e **ingeniero de software 3**. Si se establecieron anteriormente características de rol para el rol, se aplican como filtro durante búsquedas para un recurso. Se pueden agregar características adicionales según sea necesario para restringir más la búsqueda.

La configuración de la vista también se pueden personalizar para ofrecer una mejor vista de la disponibilidad de recursos. Hay opciones para mostrar la disponibilidad por hora, diaria, semanal, mensual, trimestral y anual. También hay una opción para mostrar la capacidad disponible y restante en los recursos. Esta opción es útil para la gestión del tiempo cuando se calcula el tiempo disponible para las actividades o la disponibilidad de recursos.

El director de proyecto puede seleccionar un rol en la página y, a continuación, si hay un recurso disponible que se adapta al requisito, seleccionarlo para reservar un recurso para ese rol. Tenga en cuenta que no es necesario que los recursos estén reservados durante la fase de planificación. Al crear un WBS, puede reemplazar roles por los recursos de personal para el proyecto. Si los roles se reemplazan con los recursos de personal en la WBS, la configuración de recursos actualiza automáticamente la programación y la lista del equipo del proyecto.

[![Lista del equipo del proyecto que incluye tanto roles como recursos reales](./media/projectresourcing03-1024x368.jpg)](./media/projectresourcing03.jpg) 

El director de proyecto tiene varias opciones para reservar un recurso para un proyecto como **Capacidad restante**, **Capacidad total**, **Porcentaje de capacidad**, y **Especificar horas**. Estas opciones de reserva se pueden cancelar en cualquier momento si cambian las asignaciones de recursos. Se admiten dos tipos de reserva:

- **Reserva en firme**: Se ha aprobado y confirmado la reserva de recursos para trabajar en el compromiso para la duración especificada.
- **Reserva provisional**: Las reservas de recursos se establecieron provisionalmente para trabajar en el compromiso para la duración especificada.

El siguiente procedimiento explica cómo crear un equipo de proyecto.

### <a name="create-a-project-team"></a>Crear un equipo de proyecto

1. En la página de lista **Todos los proyectos**, seleccione un proyecto y, a continuación, haga clic en **Editar**.
2. En la pestaña **Equipo del proyecto y programación**, en el campo **Programar fecha final**, especifique la fecha inicial de la programación más un mes. Por ejemplo, si la fecha inicial de la programación es el 24 de junio de 2017 (24/06/2017), escriba **24/07/2017**.
3. Seleccione **Agregar**.
4. En el panel **Agregar roles al proyecto**, en el campo **Rol**, seleccione **Director de proyecto principal**.
5. Seleccione **Competencias requeridas**.
6. En la página **Elegir características**, las características que estableció anteriormente para el rol de director de proyecto principal se seleccionan de forma predeterminada. Seleccionar **Aceptar**.
7. En la página **Agregue roles al proyecto**, en el campo **Número de recursos**, escriba **1**.
8. En el campo **Recurso**, las búsquedas muestran todos los recursos con las competencias necesarias. Seleccione **Daniel Goldschmidt** y, a continuación, haga clic en **Crear**.
9. En la página **Proyecto** y haga clic en **Agregar**.
10. En el panel **Agregar roles al proyecto**, en el campo **Rol**, seleccione **Miembro del equipo**. En el campo **Número de recursos**, escriba **5**.
11. Seleccione **Crear**.
12. En la página **Proyectos**, seleccione **Cumplir con recurso**.

## <a name="resource-capacity-synchronization"></a>Sincronización de capacidad de recursos
Los procesos para la sincronización de recursos ayudan a garantizar que la información del calendario y del calendario de base se integren lentamente en la programación de recursos del proyecto. Si se modifica el calendario, los procesos realizan las actualizaciones necesarias a la programación de recursos del proyecto. Igualmente, los procesos también le permitirán mejorar el rendimiento, ya que la información de recursos del calendario se sincroniza previamente. Por lo tanto, verá con más frecuencia actualizaciones de información con la programación de recursos. Se recomienda la programación de los procesos como lote en lugar de uno cada vez. De no ser así, existe el riesgo de que alguien olvidará las fechas inclusivas en las que la información se sincronizó por última vez. Si no se usan fechas inclusivas, pueden producir huecos durante la sincronización de fecha.

![Sincronización de calendario](./media/projectresourcing04-1024x471.jpg)

### <a name="synchronize-resource-capacity-roll-ups"></a>Sincronizar acumulaciones de capacidad de recursos

El proceso de sincronización está diseñado para sincronizar toda la información del calendario de recursos. Esta información incluye la información del calendario base sobre los cambios realizados en la tabla de la capacidad del calendario de recursos del proyecto. Si se agregan nuevos recursos en el proyecto, la sincronización ayuda a garantizar que la información actualizada del calendario está disponible. Esta sincronización se puede realizar en cualquier momento.

Recomendamos que use un lote. Las opciones están disponibles durante la sincronización de reservas de capacidades.

1. Seleccione **Administración de proyectos y contabilidad** &gt; **Periódico** &gt; **Sincronización de capacidad** &gt; **Sincronizar acumulaciones de capacidad de recursos**.
2. Configure las opciones de la siguiente tabla.

    | Opción      | Descripción |
    |-------------|-------------|
    | Código del período | De forma opcional, puede seleccionar el código del intervalo de fechas del libro de contabilidad general para establecer las fechas inicial y final del proceso de sincronización de la acumulación de capacidad de recursos. |
    | Fecha de inicio  | Especifique la fecha inicial del proceso de sincronización de acumulación de capacidad de recursos. |
    | Fecha de finalización    | Especifique la fecha final del proceso de sincronización de acumulación de capacidad de recursos. |

[![Proceso de sincronización](./media/projectresourcing09.jpg)](./media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Configurar roles en plantillas de WBS
Los directores de proyecto pueden configurar plantillas de WBS que pueden aplicar al crear una WBS para proyectos nuevos. Los directores de proyecto pueden agregar roles al crear una plantilla. Use el siguiente procedimiento para asignar un rol a una plantilla de WBS. 

1. Seleccione **Administración de proyectos y contabilidad** &gt; **Configurar** &gt; **Proyectos** &gt; **Plantillas de estructura de descomposición del trabajo**.
2. Seleccione **Detalles** para ver la plantilla de WBS seleccionada.
3. Seleccione una tarea en la lista y, a continuación, en el campo **Rol**, seleccione un rol para asignarlo a la tarea.

### <a name="work-with-a-wbs"></a>Trabajar con una WBS

Puede crear una nuevo WBS o puede copiar una WBS de una plantilla de WBS existente. Un director de proyecto puede gestionar fácilmente los recursos asignando roles a las nuevas tareas en la WBS. Los roles se pueden reemplazar después de que se adquiera un recurso o después de que se identifique un recurso confirmado para trabajar en la tarea. Esta flexibilidad permite a los directores de proyecto realizar las tareas siguientes:

- Identificar el número de recursos necesarios para los paquetes de trabajo de WBS.
- Calcular costes del proyecto.
- Determinar un presupuestario preliminar.
- Estimar la duración de la actividad, en función de los roles y recursos.
- Desarrollar algunos planes de gestión de proyectos, según la información del proyecto disponible.

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
<td>Agregue automáticamente recursos planificados mediante los roles asociados a una tarea. Finance and Operations sugiere automáticamente recursos planificados mediante el análisis de decisión de varios criterios que se basa en roles. Después de establecer los roles y el esfuerzo (horas) necesario para desempeñar las tareas de una WBS y de liberar la estructura, haga clic en <strong>Generar equipo automáticamente</strong>. El número necesario de recursos planificados se agrega a la WBS y la pestaña <strong>Equipo del proyecto y programación</strong>.</td>
</tr>
<tr class="odd">
<td>Recurso (lista desplegable)</td>
<td>En la página <strong>Iniciar asignación de recursos</strong>, puede seleccionar recursos para reservar en firme o reservar de forma provisional, en función de la duración especificada. Puede ajustar las opciones de visualización para ver y establecer la duración de las actividades de recursos. Puede seleccionar y asignar recursos en el nivel del paquete de trabajo mediante las siguientes opciones:
<ul>
<li><strong>Aceptar</strong>: Confirme los cambios al recurso asignado a una tarea.</li>
<li><strong>Cancelar</strong>: Cancele los cambios al recurso asignado a una tarea.</li>
<li><strong>Asignar automáticamente</strong>: es un recurso de personal disponible que tenga un rol que coincida para la tarea seleccionada y que haya sido seleccionado y asignado a esta de forma automática.</li>
</ul></td>
</tr>
</tbody>
</table>

1. En la página **Todos los proyectos**, seleccione el proyecto **Fase 2 de la actualización XYZ**.
2. Haga clic en **Plan** &gt; **Actividades** &gt; **Estructura de descomposición del trabajo**.
3. Haga clic en **Nuevo** para agregar las siguientes actividades de nivel uno a la WBS:

    - Iniciación
    - Planificación
    - En ejecución
    - Supervisión y control
    - Cerrar

4. Establezca las fechas y el esfuerzo (horas) tal como se muestra en la siguiente ilustración.

    [![Establecer las fechas y el esfuerzo](./media/projectresourcing10.jpg)](./media/projectresourcing10.jpg)

5. Seleccione la línea de tareas **Iniciación** y, a continuación, en el campo **Rol**, seleccione **Director de proyecto principal**.
6. Seleccione **Publicar**.
7. En la misma línea, en el campo **Recurso**, seleccione **Daniel Goldschmidt** y, a continuación, seleccione **Aceptar**.
8. Seleccione la línea de la tarea **Planificación** y, a continuación, en el campo **Rol**, seleccione **Analista de negocios**.
9. Seleccione **Publicar** y, a continuación, **Generar equipo automáticamente**.
10. En el cuadro de mensaje que aparece, haga clic en **Sí**.
11. En el campo **Recurso**, compruebe que el valor es **Analista de negocios 1**.
12. Para el recurso **Analista de negocios 1**, abra la búsqueda y seleccione **Iniciar formulario de asignación de recursos**. A continuación, seleccione un trabajador para la tarea.
13. Seleccione **Asignación provisional** &gt; **Capacidad completa**.

    > [!NOTE] 
    > No recibirá una advertencia de que el recurso especificado es ahora 2, porque el número de recursos sigue siendo 1.

14. En la página **Estructura de descomposición del trabajo**, valide la asignación de recursos en la WBS y, a continuación, haga clic en **Guardar**.

## <a name="resource-fulfillment-for-planned-resources"></a>Cumplimiento de recursos para recursos planificados
Un director de proyecto puede planificar los roles de recursos necesarios para un proyecto. El administrador de recursos verá estos recursos planificados como solicitudes en la página **Cumplimiento de recursos** y puede asignar recursos reales.

1. En la página **Todos los proyectos**, seleccione el proyecto **Fase 2 de la actualización XYZ**.
2. Seleccione **Proyecto** y **Editar**.
3. En la pestaña **Equipo del proyecto y programación**, haga clic en **Agregar**.
4. En el cuadro de diálogo **Agregar roles**, seleccione el rol **Desarrollador de software**.
5. Haga clic en **Crear** y, a continuación, cierre la página del proyecto.
6. En la página **Cumplimiento de recursos**, seleccione **Programador de software 1** para el proyecto **Fase 2 del proyecto de la actualización XYZ**.
7. Seleccione un trabajador y seleccione **Asignar**.
8. Compruebe que se ha eliminado la línea para **Desarrollador de software 1** para el proyecto **Fase 2 del proyecto de actualización de XYZ**.
9. En la pestaña **Equipo del proyecto y programación**, del proyecto **Fase 2 de la actualización de XYZ**, compruebe que se ha agregado el trabajador que seleccionó en el paso anterior como **Desarrollador de software**.

## <a name="requests-for-project-resources"></a>Solicitudes de recursos de proyecto
La funcionalidad de programación de recursos del proyecto solo admite a administradores de recursos para distribuir recursos de personal en compromisos o proyectos. Para habilitar esta funcionalidad, realice las tareas siguientes o compruebe que se hayan realizado:

- Configurar secuencias numéricas.
- Configuración de flujos de trabajo de Gestión de proyectos y contabilidad.
- Habilitar los flujos de trabajo de las solicitudes de recursos

Una vez que haya completado las tareas anteriores, puede completar las tareas siguientes según sea necesario:

- Cree una solicitud de recurso de un recurso con personal de reserva provisional.
- Supervise las solicitudes de recursos.
- Rellene las solicitudes de recursos.
- Solicite un recurso de personal de WBS.
- Reserve recursos para un proyecto sin tener un pedido de recurso de personal.

## <a name="monitor-project-teams"></a>Supervisar los equipos de proyecto
1. En la página **Todos los proyectos**, seleccione el vínculo **Id. de proyecto** del proyecto **Fase 2 de la actualización de XYZ**.
2. En la ficha desplegable **Equipo del proyecto y programación**, compruebe que los recursos de proyectos mostrados son correctos.

