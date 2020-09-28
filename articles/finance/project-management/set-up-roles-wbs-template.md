---
title: Configurar roles en plantillas de estructura de descomposición del trabajo
description: Este tema proporciona información sobre cómo configurar la información de roles en las plantillas de la estructura de descomposición del trabajo.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5dfb429eae933ba4d687ec4cbd417d2f78308e47
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760656"
---
# <a name="set-up-roles-on-work-breakdown-structure-templates"></a>Configurar roles en plantillas de estructura de descomposición del trabajo

[!include [banner](../includes/banner.md)]

Los directores de proyecto pueden configurar plantillas de la estructura de descomposición del trabajo (WBS) que pueden aplicar al crear una WBS para proyectos nuevos. Los directores de proyecto pueden agregar roles al crear una plantilla. Use el siguiente procedimiento para asignar un rol a una plantilla de WBS. 

1. Seleccione **Administración de proyectos y contabilidad** > **Configurar** > **Proyectos** > **Plantillas de estructura de descomposición del trabajo**.
2. Seleccione **Detalles** para ver la plantilla de WBS seleccionada.
3. Seleccione una tarea en la lista y, a continuación, en el campo **Rol**, seleccione un rol para asignarlo a la tarea.

## <a name="work-with-a-wbs"></a>Trabajar con una WBS

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
<td>Agregue automáticamente recursos planificados mediante los roles asociados a una tarea. Finance sugiere automáticamente recursos planificados mediante el análisis de decisión de varios criterios que se basa en roles. Después de establecer los roles y el esfuerzo (horas) necesario para desempeñar las tareas de una WBS y de liberar la estructura, haga clic en <strong>Generar equipo automáticamente</strong>. El número necesario de recursos planificados se agrega a la WBS y la pestaña <strong>Equipo del proyecto y programación</strong>.</td>
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
2. Haga clic en **Plan** > **Actividades** > **Estructura de descomposición del trabajo**.
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
