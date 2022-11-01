---
title: Información general de los cursos
description: Este artículo explica cómo los administradores y directores de Recursos humanos pueden usar las características de los cursos para mantener información sobre los cursos que están disponibles para los trabajadores.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable, HcmLearningWorkspace
audience: Application User
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a1fd00fb9feea9ab426f67095770389696452215
ms.sourcegitcommit: 0d5c07ba91a9ceb2eeb11db032fd28037216789d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2022
ms.locfileid: "9716343"
---
# <a name="courses-overview"></a>Información general de los cursos

Microsoft Dynamics 365 Human Resources proporciona una solución para las necesidades de aprendizaje de su organización. Esta solución ofrece dos rutas de cursos de aprendizaje: *virtual* y *dirigido por un instructor*.

*Aprendizaje virtual* es una experiencia de aprendizaje que se mejora a través de recursos en línea. En un *curso dirigido por un instructor*, un instructor facilita una sesión de formación para un grupo de trabajadores o alumnos.

En nuestro módulo de aprendizaje, los profesionales de recursos humanos, los administradores, los gerentes de capacitación y los gerentes pueden crear y asignar rutas de cursos de aprendizaje a los trabajadores.

> [!NOTE]
> Para utilizar los cursos virtuales, debe habilitar la función **Mejoras del curso** en Gestión de funciones.

## <a name="set-up-virtual-courses"></a>Configurar cursos virtuales

Para configurar cursos virtuales, debe habilitar la función **Mejoras del curso** en Gestión de funciones. Vaya a **Cursos \> Nuevo** y establezca la opción **Virtual** en **Sí**. Una vez habilitada la función, se requiere un enlace al curso. El campo **Estado del curso** se establecerá en **Abierto**. La opción **Permitir que el empleado se autorregistre** se establecerá en **Sí** pero se puede configurar como **No**.

Después de que la función **Mejoras del curso** está habilitada en Gestión de funciones, se producen los siguientes cambios:

- Se debe definir una fecha de vencimiento para la asignación del curso.
- Se requiere un enlace del curso.
- **Autoservicio para los empleados** mostrará una descripción general de los empleados en **Cursos**. El usuario puede ver los cursos vencidos, vencidos pronto y asignados.
- Los trabajadores pueden completar cursos virtuales y dar fe de ellos.

## <a name="set-up-instructor-led-courses"></a>Configurar cursos dirigidos por un instructor

Los cursos dirigidos por un instructor no tienen que configurarse antes de usarse.

La siguiente información es opcional y se puede especificar para los cursos. Si esta información se ingresará para los cursos, debe configurarse antes de que se creen los registros del curso:

- Tipo de curso
- Grupos de aulas
- Grupos del curso
- Ubicaciones de los cursos
- Aulas
- Instructores
- Tipos de curso

Puede usar *tipos de curso* para clasificar los cursos en función de su estructura o contenido. Puede crear tipos de cursos en la página  **Tipos de curso**.

El número mínimo y máximo de participantes que se pueden registrar para un curso se define en la ficha desplegable **General** en la página **Cursos**.

### <a name="course-setup-type"></a>Tipo de configuración del curso 

Los *tipos de configuración* determinan la estructura del curso. Hay tres tipos de configuración para los cursos.

| Tipo de configuración | Description |
|------|--------|
| Estándar | Los cursos de este tipo de configuración no tienen una agenda diaria. Es el tipo de configuración predeterminado al crear un nuevo curso. |
| Programa | Seleccione este tipo de configuración para planificar los detalles de cada día de un curso que tenga lugar durante varios días. |
| Agenda + sesión | <p>Seleccione este tipo de configuración para los cursos más complejos. Por ejemplo, puede dividir el programa del curso en *trayectorias* y *sesiones*:</p><ul><li>Las *trayectorias* son áreas temáticas específicas para un curso.</li><li>Las *sesiones* dividen las trayectorias y ayudan a identificar procesos o técnicas específicos pertinentes para una trayectoria.</li></ul> |

### <a name="course-tasks"></a>Tareas del curso

Para cada curso, puede realizar las tareas siguientes:

- Registrar participantes.
- Especificar una fecha límite del registro.
- Definir el número mínimo y máximo de participantes.
- Asignar una ubicación y un aula para el curso.
- Recomendar hoteles a los participantes en el curso.
- Crear una descripción del curso, que se puede publicar en **Autoservicio para empleados**.

> [!NOTE]
> Solo puede eliminar un curso solo si nadie se ha registrado.

### <a name="course-statuses"></a>Estados del curso

La siguiente tabla enumera los estados del curso y las acciones que se completan para cada uno.

| Status | Acciones |
|------|--------|
| Creada | <ul><li>Especificar y modificar la información del curso.</li><li>Cambie el estado del curso a **Abierto**, de modo que los trabajadores puedan registrarse en él.</li></ul> | 
| Abrir | <ul><li>Registrar participantes en el curso.</li><li>Quitar participantes del curso.</li><li>Confirmar participantes en el curso.</li><li>Cambiar el estado del curso a **Cerrado** o **Cancelado** para los participantes cuyo estado es **Confirmado**.</li></ul>|
| Cerrada | Puede volver a abrir el curso. |
| Canceladas | Puede volver a abrir el curso. |

### <a name="course-participants"></a>Participantes en el curso

Los *participantes del curso* son trabajadores que participan en un evento o curso de aprendizaje. Solo es posible registrar participantes para cursos abiertos.

### <a name="workflow"></a>Flujo de trabajo

Los empleados que se registran para un curso por medio de la página **Autoservicio del empleado** pueden dirigir su registro a través de un flujo de trabajo para su aprobación. Puede asignar un flujo de trabajo a un curso en la ficha desplegable **General** de la página **Cursos**.
