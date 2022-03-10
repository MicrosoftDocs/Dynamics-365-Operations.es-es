---
title: Configuración de cursos de formación.
description: Los administradores y directores de Recursos humanos pueden usar las características de los cursos para mantener información sobre la formación que se ofrece a los trabajadores.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c66459a044419535d66875cddac7eb73af744ca7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066759"
---
# <a name="set-up-training-courses"></a>Configuración de cursos de formación.


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Los administradores y directores de Recursos humanos pueden usar las características de los cursos para mantener información sobre la formación que se ofrece a los trabajadores.

##  <a name="set-up-prerequisites"></a> Requisitos previos de configuración

La siguiente información es necesaria y debe estar configurada antes de crear cursos.
-   **Tipos de curso**

La siguiente información es opcional que puede especificar para los cursos. Si sabe que se especificarán esta información para los cursos, debería configurar esta información antes de crear los registros del curso.
-   **Grupos de aulas**
-   **Grupos del curso**
-   **Ubicaciones de los cursos**
-   **Aulas**
-   **Instructores**

## <a name="course-types"></a>Tipos de curso
Puede usar tipos de curso para clasificar los cursos en función de su tipo, estructura o contenido. Puede crear tipos de cursos en la página **Tipos de curso**. Debe seleccionar un tipo de curso al crear el registro de un curso.

## <a name="course-setup-type"></a>Tipo de configuración del curso
En la tabla siguiente se muestran los tres tipos de configuración para los cursos. Los tipos de configuración determinan la estructura del curso.

<table>
<thead>
<tr class="header">
<th>Tipo de configuración</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Estándar</strong></td>
<td>Seleccione este tipo para los cursos que no tendrán un programa diario. Este es el tipo de configuración predeterminado al crear un nuevo curso.</td>
</tr>
<tr class="even">
<td><strong>Programa</strong></td>
<td>Seleccione este tipo para planificar los detalles de cada día de un curso que tenga lugar durante varios días.</td>
</tr>
<tr class="odd">
<td><strong>Agenda + sesión</strong></td>
<td>Seleccione este tipo para los cursos más complejos. Por ejemplo, puede dividir el programa del curso en trayectorias y sesiones.
<ul>
<li><strong>Trayectoria</strong>: las trayectorias son áreas temáticas específicas para un curso.</li>
<li><strong>Sesiones</strong>: las sesiones dividen las trayectorias y ayudan a identificar procesos o técnicas específicos pertinentes para la trayectoria.</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a>Tareas del curso
Para cada curso, puede realizar las tareas siguientes:
- Registrar participantes.
- Especificar una fecha límite del registro.
- Definir el número mínimo y máximo de participantes.
- Asignar una ubicación y un aula para el curso.
- Recomendar hoteles a los participantes en el curso.
- Crear una descripción del curso que puede anunciar en **Autoservicio para empleados**

  >**Nota** Solo puede eliminar un curso solo si nadie se ha registrado. 

## <a name="course-statuses"></a>Estados del curso
En la tabla siguiente se muestran los estados posibles del curso y las acciones que puede realizar cuando el curso tiene un estado concreto.

<table>
<thead>
<tr class="header">
<th>Estado</th>
<th>Acciones</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>Creado</strong></td>
<td><ul>
<li>Especificar y modificar la información del curso.</li>
<li>Cambie el estado del curso a <strong>Abierto</strong> de modo que los trabajadores puedan registrarse en él.</li>
</ul></td>
</tr>
<tr class="even">
<td><strong>Abrir</strong></td>
<td><ul>
<li>Registrar participantes en el curso.</li>
<li>Quitar participantes del curso.</li>
<li>Confirmar participantes en el curso.</li>
<li>Cambiar el estado del curso a<strong> Cerrado</strong> o <strong>Cancelado</strong>.</li>
<li>Planificar cuestionarios para participantes cuyo estado sea <strong>Confirmado</strong>.</li>
</ul></td>
</tr>
<tr class="odd">
<td><strong>Cerrado</strong></td>
<td>Puede volver a abrir el curso.</td>
</tr>
<tr class="even">
<td><strong>Cancelado</strong></td>
<td>Puede volver a abrir el curso.</td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a>Participantes en el curso
Los participantes del curso son trabajadores que participan en un evento o curso de aprendizaje. Solo es posible registrar participantes para cursos abiertos. El número mínimo y máximo de participantes que se pueden registrar para un curso se define en la ficha desplegable **General** en la página **Cursos**.

## <a name="workflow"></a>Flujo de trabajo

Los empleados que se registran para un curso por medio de la página **Autoservicio del empleado** pueden dirigir su registro a través del flujo de trabajo para su aprobación. Puede asignar un flujo de trabajo a un curso en la ficha desplegable **General** de la página **Cursos**.







[!INCLUDE[footer-include](../includes/footer-banner.md)]
