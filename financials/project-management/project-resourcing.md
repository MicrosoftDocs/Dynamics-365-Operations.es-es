---
title: Recursos del proyecto
description: "Este tema proporciona información acerca resourcing del proyecto."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: cmercado
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: eb32cf1b96dfef75131b8c7541e20a93615a87f7
ms.openlocfilehash: c29c95fc6abd13e668c44d3ccf437bb0e879e46b
ms.lasthandoff: 03/31/2017


---

# <a name="project-resourcing"></a>Recursos del proyecto

Este tema proporciona información acerca resourcing del proyecto.

Un desafío para los directores de proyecto y los administradores de recursos durante la fase de planificación de proyectos es la asignación de recursos, donde deben determinar y reservar el recurso correcto para trabajar en un proyecto. En Microsoft Dynamics 365 para las operaciones, las capacidades de resourcing para proyectos le permite definir los roles que se tratan como los recursos temporales que se pueden reservar para un compromiso específicos, o parte de un compromiso. Este tipo de recursos permite a los directores de proyecto y a los directores de recursos completar las siguientes tareas:

-   Definir un rol que contenga las competencias necesarias para que sea sencillo asignar recursos.
-   Roles de uso para definir una programación inicial de compromiso que se basa en recursos reservas.
-   Estimar costes y determinar un presupuesto inicial, en función de los roles y los recursos asignados para un proyecto.
-   Use los roles para estimar el número de reservas de recursos necesarios para cada compromiso.
-   Estimar el número de recursos necesarios para el ciclo de vida completo de un proyecto.
-   Realizar un borrador de una estructura de descomposición del trabajo (WBS) mediante las asignaciones de recursos iniciales.

[ciclo de vida del proyecto![] (. /media/projectresourcing02-1024x812.jpg])(. /media/projectresourcing02.jpg) 

A medida que la planificación de proyectos avanzando, los recursos planificados se pueden sustituirán con los recursos proveídos de personal. El director de proyecto puede también volver y actualizar las reservas de resourcing durante etapas de proyecto cualquiera de los.

## <a name="set-up-project-resources"></a>Configurar recursos del proyecto
Debe configurar un calendario y asociarlo a un empleado o un trabajador. El calendario se usa para programar el proyecto y el horario de recursos que están reservadas para el proyecto. Durante la configuración del calendario, los directores de proyecto pueden realizar la nivelación de recursos como parte de la optimización de recursos. En función de la programación del calendario, se pueden aplicar restricciones en los recursos. Puede configurar un calendario ** en los calendarios ** la página. 

Al configurar un trabajador como recurso de proyecto, puede seleccionar de trabajadores que trabajan en la empresa para el que está configurando a recursos o, puede seleccionar trabajadores de otras empresas de la organización. Estos son recursos empresas vinculadas. Los procedimientos siguientes se explica cómo configurar un trabajador como recurso del proyecto dentro de la empresa y cómo configurar un recurso empresas vinculadas del proyecto.

### <a name="set-up-a-worker-as-a-project-resource"></a>Configurar un trabajador como recurso de proyecto

1.  En ** los trabajadores ** pagine, en ** los trabajadores ** la lista, seleccione el trabajador que desea agregar como recurso del proyecto, y abre el registro de trabajador.
2.  En el panel de acciones, haga clic en ** proyecto ** &gt; ** la configuración ** &gt; ** configurar ** proyecto.
3.  Seleccione un calendario, y cierre la página.

También puede especificar los proyectos predeterminados para un recurso como un tipo de asignación previa. Las asignaciones previas se pueden utilizar cuando el director de recursos o el director de proyecto sabe en qué proyectos trabajará el recurso por adelantado. Las asignaciones previas también se pueden basar en la solicitud de un cliente o patrocinador de proyecto. Para asignar previamente un proyecto, en la página **Asignar proyectos**, en la ficha **Proyectos**, en la lista **Proyectos restantes**, seleccione el proyecto adecuado.

### <a name="set-up-an-intercompany-resource"></a>Configurar un recurso empresas vinculadas

Al configurar un trabajador como recurso empresas vinculadas, debe completar la configuración de la empresa de préstamos y la empresa de préstamo. 

** En la empresa de préstamo: **

1.  En Dynamics 365 para las operaciones, compruebe que la empresa se selecciona del préstamo, y después realice el procedimiento anterior, “configuración un trabajador como recurso del proyecto.”
2.  Retroceda ** contabilidad general **&gt; ** la configuración de registro **&gt; ** contabilidad de empresas vinculadas **. Click **New**.
3.  En ** identificador de la entidad jurídica ** campo, seleccione la empresa de préstamo. Rellene los campos restantes según necesarios y, a continuación haga clic en Guardar ** **.
4.  Retroceda ** Gestión de proyectos y contabilidad **&gt; ** la configuración **&gt; ** los precios ** &gt; ** precio de transferencia **. ** **
5.  En ** precio de transferencia ** cajas, haga clic en ** nuevo **, y en ** pidiendo copiado la entidad jurídica ** campo, seleccione la empresa adecuada.
6.  Si sólo desea prestar a la empresa de préstamo el recurso que ha creado al principio de esta sección, en ** recurso ** campo, seleccione el nombre de recurso que ha creado. Si desea colocar todos los recursos en la empresa a disposición la empresa de préstamo, deje ** recurso ** el campo en blanco.
7.  Retroceda ** Gestión de proyectos y contabilidad **&gt; ** la configuración **&gt; ** parámetros de contabilidad y gestión de proyectos, ** ** y en las empresas vinculadas ** la ficha, establezca ** habilite la programación de recursos empresas vinculadas y las hojas de horas ** el campo ** Sí **.

** En la empresa de préstamo: **

1.  ** Van Gestión de proyectos y contabilidad ** &gt; ** los recursos de proyecto ** &gt; ** los recursos enumerados **.
2.  En el filtro de la búsqueda, escriba el nombre de recurso que creó en el procedimiento anterior para que la empresa de préstamo compruebe que el nombre está incluido en la lista de recursos para la empresa de préstamo.

## <a name="manage-resource-competencies"></a>Gestionar competencias de recurso
Las capacidades del recurso son una parte esencial de administración de recursos. Las competencias se pueden usar como línea base para determinar los recursos con el equilibrio correcto de aptitudes, formación, certificación y experiencia en proyectos. Debe configurar esta información para cada recurso y actualizarla periódicamente. De esta manera, puede maximizar las capacidades cuando las competencias de recursos específicas se concilian durante la asignación de recursos de proyectos. [ejemplos![de conocimientos, de certificaciones, de la formación, y la experiencia en proyectos (]. /media/projectresourcing06-1024x383.jpg])(. /media/projectresourcing06.jpg) 

Los procedimientos siguientes explican cómo configurar algunas de las capacidades para un recurso. 

Para configurar competencias para un trabajador, puede usar la página de lista **Trabajadores** en Recursos humanos o la página de lista **Recursos** en Administración de proyectos y contabilidad. Para los siguientes procedimientos, ** los trabajadores ** la página de lista en recursos humanos se usa.

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
1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** áreas de trabajo ** &gt; ** gestión de proyectos **.
2.  Haga clic en **Nuevo proyecto** y escriba los siguientes valores:
    -   ** Tipo de proyecto ** - Tiempo y material
    -   ** Nombre del proyecto ** 2 - fase de la actualización de XYZ
    -   ** Grupo de proyectos - ** TM\_trabajo en curso
    -   ** Identificador de contrato de proyecto ** - 00000002
3.  Haga clic en **Crear proyecto**.

### <a name="assign-a-resource-to-a-project"></a>Asignar un recurso a un proyecto

1.  ** Haga clic en recursos humanos ** &gt; ** trabajadores ** &gt; ** ** trabajadores.
2.  En la lista **Trabajadores**, seleccione el registro del trabajador para el que ha configurado anteriormente competencias y abra el registro de trabajador.
3.  En el panel de acciones, en la pestaña **Proyecto**, en el grupo **Configuración**, haga clic en **Asignar proyectos**.
4.  En la página **Asignaciones de proyectos de validación de recursos**, haga clic en la pestaña **Proyectos**.
5.  En ** agregue el proyecto a los proyectos seleccionados, ** filtro en el proyecto 2, fase de la actualización de XYZ
6.  En el panel **Proyectos restantes**, seleccione un proyecto y, a continuación, haga clic en la flecha para agregarlo al panel **Proyectos seleccionados**.
7.  Cierre la página.

Si es necesario, también puede asignar categorías para un recurso. El tipo de categoría es Coste o Ingresos. Esto lo determina la organización. Si no hay categorías asignadas para el recurso, Dynamics 365 para las operaciones por arriba consultará la categoría predeterminada en los precios de hora para cubrir el coste y los ingresos.

### <a name="set-up-project-resource-and-role-characteristics"></a>Configurar características de rol y recursos de proyectos

Un director de proyecto puede usar la funcionalidad de recursos de proyecto para crear los roles que se requieren para el proyecto. Los roles se pueden usar si los recursos confirmados son aún desconocidos cuando reservan a recursos. Los roles se pueden según lo planificado recursos temporalmente reservas, de modo que pueda continuar las etapas de planificación de proyectos. 

[ejemplo de![del rol] (. /media/projectresourcing05.jpg])(. /media/projectresourcing05.jpg) 

**Escenario:** Se contrató a Contoso para completar un proyecto de tiempo y material que tiene una acta de constitución de proyecto aprobada. El director de proyecto junior aún está completando el ámbito del proyecto. El administrador de recursos está actualmente identificando los recursos específicos que se reservarán para trabajar en el nuevo proyecto. Uno de los roles que el patrocinador de proyecto solicitó, debido a la naturaleza fundamental del proyecto, es el director de proyecto sénior. El administrador de recursos debe adquirir al nuevo recurso y definir el rol en el sistema en caso de que el director de proyecto menor requiera la información del recurso durante la planificación de proyectos. 

Los pasos siguientes muestran cómo el administrador de recursos puede configurar las características sénior del recurso del rol y de socio Director del proyecto a ella. Más adelante, el rol se puede usar para buscar los recursos disponibles que coinciden con las competencias de recursos necesarias.

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** configuración ** &gt; ** recursos ** &gt; ** roles de instalación **.
2.  Haga clic en **Nuevo** y escriba los siguientes valores:
    -   ** Actualizar el identificador ** - director de proyecto sénior
    -   ** Descripción ** - director de proyecto sénior
3.  Haga clic en **Crear**.
4.  Seleccione el rol **Director de proyecto principal** y, a continuación, haga clic en **Configurar características**.
5.  En el campo **Tipo de características**, seleccione **Aptitud**.
6.  En el campo **Características disponibles**, especifique la aptitud que busca.
7.  En el campo **Tipo de característica**, seleccione **Certificado**.
8.  En el campo **Características disponibles**, especifique el tipo de certificado que desea buscar.
9.  Haga clic en **Aceptar** y cierre la página.

### <a name="assign-a-project-resource-to-a-project"></a>Asignar un recurso de proyecto a un proyecto

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** común ** &gt; ** proyectos ** &gt; ** todos los proyectos **, y abre ** el proyecto de dos estrellas de la fase de la actualización de XYZ.
2.  En la pestaña **Equipo del proyecto y programación**, haga clic en **Agregar**.
3.  En el campo **Rol** seleccione **Miembro del equipo**.
4.  Haga clic en **Reservar desde calendario**.
5.  En la página **Disponibilidad de recursos**, haga clic en **Parámetros de visualización**.
6.  En la página **Ajustar parámetros de visualización**, especifique los valores siguientes:
    -   ** Formato para la vista de intervalo de fechas ** - día
    -   ** En las descripciones de visualización disponibilidad - Sí **
    -   ** Capacidad restante de la pantalla - Sí **
7.  En la lista de recursos, seleccione un recurso.
8.  Haga clic en ** libro duro ** &gt; ** capacidad plena **.
9.  Cierre la página.

### <a name="assign-a-resource-to-a-default-role"></a>Asignar un recurso a un rol predeterminado

Para ayudar a proyecto o los administradores de recursos, puede explorar en profundidad para fomentar en los recursos que pueden ser reservados para un proyecto. Puede asociar un rol predeterminado a un recurso existente o un recurso recién adquirido. Por ejemplo, el contratar a Daniel, tenía la experiencia y aptitudes para rellenar la función de la analista de negocios. El administrador de recursos asignado este rol como rol predeterminado de Daniel. Por lo tanto, la directora de recursos Daniel agregado a un conjunto de analistas de negocios disponibles para trabajar en proyectos. 

Durante la reserva del recurso, los directores de proyecto pueden filtrar el rol de los recursos disponibles para trabajar en proyectos. Pueden usar esta información como criterio cuando realicen análisis de decisiones de varios criterios durante el cumplimiento de recursos. También pueden agregar otras características de recursos al filtro para buscar recursos que tienen aptitudes, formación y experiencia específicas para un proyecto determinado. 

** Escenario: ** Un proyecto aprobado se ha iniciado, y el rol sénior Director del proyecto se ha reservado planificado como recurso durante la fase de planificación de proyectos. El responsable de recursos ha adquirido ahora a un recurso para cumplir el rol de director de proyecto principal.

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** recursos del proyecto ** &gt; ** enumeran los recursos **.
2.  En la lista **Recurso**, seleccione **Daniel Goldschmidt**.
3.  Haga clic en ** recurso del proyecto ** &gt; ** mantener ** &gt; ** rol del recurso **.
4.  Haga clic en **Nuevo** y escriba los siguientes valores:
    -   ** Efectivo ** - (la fecha actual)
    -   ** Caducidad ** - nunca
    -   ** Rol ** - director de proyecto sénior
5.  Haga clic en **Guardar** y, a continuación, cierre la página.
6.  En la pestaña **Competencias**, agregue la aptitud **ProjectMgmt** y el certificado **PMP**.

## <a name="set-up-role-based-pricing"></a>Configurar precios basados en roles
Todos los precios de coste, ventas y transferencia se pueden configurar para roles.

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** configuración ** &gt; ** precios ** &gt; ** precio de ventas (** hora).
2.  Click **New**.
3.  Especifique una fecha vigente.
4.  En la columna **Rol** seleccione un rol.
5.  En la columna **Precio**, especifique un precio para el rol del recurso seleccionado.

## <a name="form-a-project-team"></a>Formulario un equipo de proyecto
Para usar los roles que se han configurado previamente en un proyecto, un director de proyecto debe asociar los roles con el proyecto. Las varias funciones se pueden asignar para un proyecto, y Dynamics 365 para las operaciones automáticamente etiqueta estos roles durante la reserva para evitar confusiones. Por ejemplo, si el director de proyecto necesita a tres Software Engineers, tres funciones de la Engineer Software con la Engineer Software 1, la Engineer Software 2, y la Engineer Software 3 como sus etiquetas se generan automáticamente. Si se establecieron anteriormente características de rol para el rol, se aplican como filtro durante búsquedas para un recurso. Se pueden agregar características adicionales según sea necesario para restringir más la búsqueda. 

La configuración de la vista también se pueden personalizar para ofrecer una mejor vista de la disponibilidad de recursos. Hay opciones para mostrar la disponibilidad por hora, diaria, semanal, mensual, trimestral y anual. También hay una opción para mostrar la capacidad disponible y restante en los recursos. Esta opción es útil para la gestión del tiempo cuando se calcula el tiempo disponible para las actividades o la disponibilidad de recursos. 

El director de proyecto puede seleccionar un rol en la página y continuación, si hay un recurso no disponibles que el requisito, seleccione para reservar un recurso para rellenar el rol. Tenga en cuenta que los recursos no es necesario reservas en este momento durante la fase de planificación. Al crear un EDT, puede reemplazar roles con Recursos proveídos de personal para el proyecto. Si los roles se reemplazan con los recursos proveídos de personal en el EDT, el recurso configurar actualiza automáticamente la lista y la programación del equipo de proyecto. 

[lista de equipos de proyecto![que incluye funciones y los recursos reales (]. /media/projectresourcing03-1024x368.jpg])(. /media/projectresourcing03.jpg) 

El director de proyecto tiene varias opciones para reservar un recurso para un proyecto como **Capacidad restante**, **Capacidad total**, **Porcentaje de capacidad**, y **Especificar horas**. Estas opciones de reserva se pueden cancelar en cualquier momento si cambian las asignaciones de recursos. Se admiten dos tipos de reserva:

-   ** Se aprobó y se confirmó a la Libreta última ** – Reserva de recurso que funcionara en el compromiso para la duración especificada.
-   ** El libro Débil ** – las reservas de recurso se liquidó provisional para trabajar en el compromiso para la duración especificada.

El siguiente procedimiento explica cómo crear un equipo de proyecto.

### <a name="create-a-project-team"></a>Crear un equipo de proyecto

1.  En la página de lista **Todos los proyectos**, seleccione un proyecto y, a continuación, haga clic en **Editar**.
2.  En ** equipo y Programación de proyecto **, en la ficha ** fecha de finalización de la programación ** el campo, especifique la fecha inicial de la programación más un mes. Por ejemplo, si la fecha inicial de la programación es el 24 de junio de 2017 (24/06/2017), entre 24/07/2017 ** **.
3.  Click **Add**.
4.  En el panel **Agregar roles al proyecto**, en el campo **Rol **, seleccione **Director de proyecto principal**.
5.  Haga clic en **Competencias requeridas**.
6.  En la página **Elegir características**, las características que estableció anteriormente para el rol de director de proyecto principal se seleccionan de forma predeterminada. Haga clic en **Aceptar**.
7.  En la página **Agregue roles al proyecto**, en el campo **Número de recursos**, escriba **1**.
8.  En el campo **Recurso**, las búsquedas muestran todos los recursos con las competencias necesarias. Seleccione **Daniel Goldschmidt** y, a continuación, haga clic en **Crear**.
9.  En la página **Proyecto**, haga clic en **Agregar**.
10. En el panel **Agregar roles al proyecto**, en el campo **Rol **, seleccione **Miembro del equipo**. En el campo **Número de recursos**, escriba **5**.
11. Haga clic en **Crear**.
12. En la página **Proyectos**, haga clic en **Cumplir con recurso**.

## <a name="resource-capacity-synchronization"></a>Sincronización de capacidad de recursos
Los procesos para la sincronización de recursos ayudan a garantizar que la información del calendario y del calendario de base entran lentamente en la programación de recursos del proyecto. Si se modifica el calendario, los procesos realizan las actualizaciones necesarias a la programación de recursos del proyecto. Los procesos también ayudan a mejorar el rendimiento, porque la información del recurso del calendario se sincroniza por adelantado, de modo que las actualizaciones a la información de la programación de recursos se produce con mayor rapidez. Se recomienda la programación de los procesos como lote en lugar de uno cada vez. De no ser así, existe el riesgo de que alguien olvidará las fechas inclusivas en las que la información se sincronizó por última vez. Si no se usan fechas inclusivas, pueden producir huecos durante la sincronización de fecha.

### <a name="calendar-synchronizationmediaprojectresourcing04-1024x471jpg"></a>![Calendario la sincronización](./media/projectresourcing04-1024x471.jpg)

**Synchronize resource capacity roll-ups**

El proceso de sincronización está diseñado para sincronizar toda la información del calendario de recursos. Esta información incluye la información del calendario base sobre los cambios a la tabla de la capacidad del calendario de recursos del proyecto. Si agrega a los nuevos recursos del proyecto, ayuda de sincronización garantizan que la información del calendario esté disponible actualizada. Esta sincronización se puede realizar en cualquier momento. 

Recomendamos que use un lote. Las opciones están disponibles en la sincronización de reservas de capacidades.

-   ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** periódico ** &gt; ** sincronización de la capacidad ** &gt; ** sincronizar la capacidad enrollamiento- UPS de los recursos **.

| Opción | Descripción                                                                                                                                                                                          |
|--------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Sí    | Sincronizar todos los datos de recursos con la información del calendario y del calendario base, y reemplazar toda la información del calendario de la capacidad de recursos del proyecto.                                                  |
| No     | Sincronizar los datos de recursos, en función del código del intervalo de fechas, y las fechas inicial y final especificadas. Esta opción no quita los datos existentes y actualiza la información únicamente para los recursos recién agregados. |

[proceso de sincronización de![] (. /media/projectresourcing09.jpg])(. /media/projectresourcing09.jpg)

## <a name="set-up-roles-on-wbs-templates"></a>Configurar roles en plantillas de WBS
Los directores de proyecto pueden configurar plantillas de WBS que pueden aplicar al crear una WBS para proyectos nuevos. Los directores de proyecto pueden agregar roles cuando crean una plantilla. Use el procedimiento siguiente para asignar un rol a una plantilla de EDT. ** **

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** configuración ** &gt; ** proyectos ** &gt; ** plantillas de la estructura de descomposición del trabajo **.
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
<td>Agregue automáticamente recursos planificados mediante los roles asociados a una tarea. La Dynamics 365 para las operaciones sugiere automáticamente a recursos planificados mediante el análisis de decisiones de los criterios varios que se basa en roles. Después del establecimiento de los roles y del esfuerzo (horas) para las tareas de una WBS y de que se haya liberado la estructura, haga clic en <strong>Generar equipo automáticamente</strong>. El número necesario de recursos planificados se agrega a la WBS y la pestaña <strong>Equipo del proyecto y programación</strong>.</td>
</tr>
<tr class="odd">
<td>Recurso (lista desplegable)</td>
<td>En la página <strong>Iniciar asignación de recursos</strong>, puede seleccionar recursos para reservar en firme o reservar de forma provisional, en función de la duración especificada. Puede ajustar las opciones de visualización para ver y establecer la duración de las actividades de recursos. Puede seleccionar y asignar recursos en el nivel del paquete de trabajo mediante las siguientes opciones:
<ul>
<li><strong>Aceptar</strong>: Confirme los cambios al recurso asignado a una tarea.</li>
<li><strong>Cancelar</strong>: Cancele los cambios al recurso asignado a una tarea.</li>
<li><strong>Asignación automáticamente</strong> – Esta opción selecciona un recurso proporcionado de personal disponibles con un rol de coincidencia a la tarea seleccionada.</li>
</ul></td>
</tr>
</tbody>
</table>

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** proyectos ** &gt; ** todos los proyectos **.
2.  En la lista, seleccione el proyecto **Fase 2 de la actualización XYZ**.
3.  Haga clic en ** plan ** &gt; ** actividades ** &gt; ** estructura de descomposición del trabajo **.
4.  Haga clic en **Nuevo** para agregar las siguientes actividades de nivel uno a la WBS:
    -   Iniciación
    -   Planificación
    -   En ejecución
    -   Supervisión y control
    -   Cerrar

5.  Establecer fechas y el esfuerzo (horas), como se muestra en el captura de pantalla siguiente. [![que establece las fechas y el esfuerzo] (. /media/projectresourcing10.jpg])(. /media/projectresourcing10.jpg)
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
16. Haga clic en ** asignación débil ** &gt; ** capacidad plena **.
17. Haga clic en **Guardar** y cierre la página. 

> [!NOTE] 
> No recibe una advertencia que el recurso especificado es ahora de 2, dado que queda el número de recursos en 1.
18. En la página **Estructura de descomposición del trabajo **, valide la asignación de recursos en la WBS y, a continuación, haga clic en **Guardar**.

## <a name="resource-fulfillment-for-planned-resources"></a>Cumplimiento de recursos para recursos planificados
Un director de proyecto puede planificar los roles de recursos necesarios para un proyecto. El administrador de recursos verá estos recursos planificados como solicitudes en la página **Cumplimiento de recursos** y puede asignar recursos reales.

1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** proyectos ** &gt; ** todos los proyectos **.
2.  En la lista, seleccione el proyecto **Fase 2 de la actualización XYZ**.
3.  Haga clic en **Proyecto**.
4.  Haga clic en **Editar**.
5.  En ** equipo y Programación de proyecto ** la ficha, ** ** clic ** agregue **.
6.  En el cuadro de diálogo **Agregar roles**, seleccione el rol **Desarrollador de software**.
7.  Haga clic en **Crear**.
8.  Cierre la página del proyecto.
9.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** recursos del proyecto ** &gt; ** cumplimiento del recurso **.
10. Seleccione **Desarrollador de software 1** para el proyecto ** Fase 2 de la actualización XYZ**.
11. Seleccione un trabajador y haga clic en **Asignar**.
12. Compruebe que se ha eliminado la línea para **Desarrollador de software 1** para el proyecto **Fase 2 del proyecto de actualización de XYZ**.
13. En la pestaña **Equipo del proyecto y programación**, para el proyecto **Fase 2 de la actualización de XYZ**, compruebe que se ha agregado el trabajador que seleccionó en el paso 11 como **Desarrollador de software**.

## <a name="requests-for-project-resources"></a>Pedidos recursos del proyecto
La funcionalidad de programación de recursos del proyecto sólo admite a administradores de recursos para distribuir a recursos proveídos de personal en compromisos o proyectos. Para habilitar esta funcionalidad, realice las tareas siguientes, o comprobar que se han realizado.

-   Configurar secuencias numéricas.
-   Flujos de trabajo de contabilidad y gestión del proyecto.
-   Flujo de trabajo de la solicitud del recurso de permiso.

Una vez que haya comprobado o haya completado las tareas anterior, puede completar las tareas siguientes según sea necesario.

-   Crear una solicitud de recurso de un recurso proporcionado de personal tabla reservado.
-   Supervisar solicitudes del recurso.
-   Cumplir con solicitudes del recurso.
-   Solicitar un recurso proporcionado de personal del EDT.
-   Reservar a los recursos a un proyecto sin un pedido un recurso proporcionado de personal.

## <a name="monitor-project-teams"></a>Supervisar equipos de proyecto
1.  ** Haga clic en Gestión de proyectos y contabilidad ** &gt; ** proyectos ** &gt; ** todos los proyectos **.
2.  En la lista de proyectos, haga clic en el vínculo **Id. de proyecto** para el proyecto **Fase 2 de la actualización de XYZ**.
3.  En la ficha desplegable **Equipo del proyecto y programación**, compruebe que los recursos de proyectos mostrados son correctos.



