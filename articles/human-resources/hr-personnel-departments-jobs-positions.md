---
title: Organizar los recursos mediante departamentos, trabajos y puestos
description: Este artículo describe información conceptual sobre departamentos, trabajos y puestos, que son elementos organizativos que se mantienen en Recursos humanos.
author: twheeloc
ms.date: 01/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmPosition, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 87933
ms.assetid: eb5dcacb-a5fe-451d-b30a-7ef14da65d81
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 0cb4e745eb6531d90a02778ba85e6caf790f2d46
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874286"
---
# <a name="organize-your-workforce-by-using-departments-jobs-and-positions"></a>Organizar los recursos mediante departamentos, trabajos y puestos


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Los departamentos, los trabajos y los puestos son elementos de organización que se mantienen dentro de Recursos Humanos. En este artículo se describe información conceptual acerca de estos elementos. 

El siguiente ejemplo se usa para ilustrar los conceptos descritos en este artículo.

|**Departamento**|**Posición**|**Trabajo**|
|---|---|---|
|**Ventas**|Director de ventas (Este)|Director de ventas|
|**Ventas**|Director de ventas (Oeste)|Director de ventas|
|**Ventas**|Director de ventas (Central)|Director de ventas|
|**Contabilidad**|Supervisor contable|Administrador contable|
|**Contabilidad**|Contabilidad-A|Contable|
|**Recursos humanos**|Director de RR. HH. (Este)|Director de RR. HH.|
|**Recursos humanos**|Director de RR. HH. (Oeste)|Director de RR. HH.|
|**Recursos humanos**|Director de RR. HH. (Central)|Director de RR. HH.|


##  <a name="departments"></a>Departamentos

Un departamento es una unidad operativa que representa una categoría o un área funcional de una organización que es responsable de un área específica de la organización, tal como las ventas o la contabilidad. Un departamento se usa para informar sobre las áreas funcionales y puede tener responsabilidad de pérdidas y ganancias. Además, un departamento puede incluir un grupo de centros de coste. Las ventas, la contabilidad y los recursos humanos son algunos ejemplos de los departamentos de una organización.

## <a name="jobs-and-positions"></a>Trabajos y puestos
Un trabajo es un conjunto de tareas y responsabilidades que deberá cumplir la persona que realiza un trabajo. Un puesto es un caso individual de un trabajo. Las áreas de responsabilidad, las tareas de trabajo, las funciones de trabajo, las aptitudes, la información sobre los estudios y los certificados necesarios para un trabajo también se requieren para puestos asociados a un trabajo.

### <a name="job-tasks"></a>Tareas de trabajo

Puede crear tareas de trabajo que describen las tareas básicas que un trabajador de un puesto debe completar para dicho trabajo. La misma tarea de trabajo se puede agregar a varios trabajos, y los puestos para dichos trabajos heredarán dichas tareas de trabajo. En la tabla siguiente se muestran algunos ejemplos de tareas de trabajo.

| Trabajo           | Tarea de trabajo                                                |
|---------------|-------------------------------------------------------------|
| Director de ventas | Revisión de rendimiento: permite revisar el rendimiento de trabajo de cada vendedor.    |
| Contable    | Revisión de ausencia: permite aprobar o rechazar solicitudes o registros de ausencia de cada vendedor. |


### <a name="job-functions"></a>Funciones de trabajo

Las funciones de trabajo son similares a las tareas de trabajo. Una función de trabajo describe una o más tareas, deberes o responsabilidades asignados a un trabajo. Las funciones de trabajo se pueden asignar a trabajos y usarse para configurar e implementar reglas de idoneidad para los planes de compensación. En la tabla siguiente se muestran algunos ejemplos de funciones de trabajo.

| Trabajo           | Función de trabajo                                                |
|---------------|-------------------------------------------------------------|
| Director de ventas | Gestionar personas: permite gestionar las personas subordinadas al usuario.               |
| Contable    | Revisión financiera: permite mantener datos financieros para un conjunto de cuentas. |

### <a name="job-types"></a>Tipos de trabajo

Use los tipos de trabajo para clasificar trabajos similares en categorías. Los tipos de trabajo, al igual que las funciones de trabajo, se pueden asignar a trabajos y usarse para configurar e implementar reglas de idoneidad para los planes de compensación. En la lista siguiente se incluyen algunos ejemplos de tipos de trabajo:
-   Jornada completa
-   A tiempo parcial
-   Sueldo
-   Paga por horas

### <a name="areas-of-responsibility"></a>Áreas de responsabilidad

Use las áreas de responsabilidad para indicar los roles de trabajo, los procesos y los productos de los que sería responsable un trabajador en un puesto para dicho trabajo. Un ejemplo de un área de responsabilidad para un trabajo denominado "Contable" podría ser "Informes financieros del producto A".

## <a name="positions"></a>Puestos

Los puestos son un aspecto importante del nivel inferior de una jerarquía organizativa. Un puesto es un caso individual de un trabajo. Por ejemplo, el puesto "Director de ventas (Este)" es solo uno de los puestos asociados al trabajo "Director de ventas". Los puestos existen en un departamento y se asignan a los trabajadores.
### <a name="position-creation-and-maintenance"></a>Creación y mantenimiento de puestos

-   Puede ver un historial de cambios de sistema relacionados con el puesto en una página de lista de fácil acceso.
-   Puede crear códigos de motivo que los usuarios pueden seleccionar al crear o modificar puestos.
-   Puede crear tipos de acción de personal y asignar una secuencia numérica a las acciones de personal.
-   Puede configurar un flujo de trabajo para que las adiciones y los cambios en los puestos requieran aprobación.

### <a name="position-duration"></a>Duración del puesto
Cada puesto tiene una duración de vigencia. Este período de tiempo se conoce como duración. Por ejemplo, los puestos de verano podrían tener una duración del 1 de mayo de 2015 hasta el 31 de agosto de 2015.

### <a name="worker-assignments"></a>Asignaciones de trabajadores
Al asignar un trabajador a un puesto, se ocupa dicho puesto. Puede asignar trabajadores a varios puestos, pero solo se puede asignar un único trabajador a un puesto al mismo tiempo.

### <a name="reporting-relationships"></a>Relaciones jerárquicas
Los puestos son elementos importantes del nivel inferior de una jerarquía organizativa. En la página **Puesto**, puede especificar el puesto de mayor jerarquía para un puesto subordinado. Al asignar un trabajador a un puesto que es subordinado de otro puesto, crea una relación jerárquica entre los trabajadores asignados a los dos puestos. Por ejemplo, el puesto "Contable-A" es subordinado del puesto "Supervisor de contabilidad". Ana Bowman se asigna al puesto "Supervisor de contabilidad" y Felix Henderson se asigna al puesto "Contable-A". Esto significa que Felix Henderson informa a Ana Bowman. 

Si la organización usa una jerarquía de matriz u otra jerarquía personalizada, puede configurar tipos de jerarquía de puestos y agregar relaciones jerárquicas a los puestos para cada tipo de jerarquía que configure. Por ejemplo, Olivia Wilson es directora general de Adventure Works y está asignada al puesto "Director general". Olivia gestiona el desarrollo de un producto que se usa para limpiar widgets. Olivia necesita un contable para ayudarle con las finanzas del desarrollo del producto. Por lo tanto, reclutó a Felix Henderson para ser su contable. Felix es subordinado directo de Ana Bowman, pero también trabaja con Olivia Wilson en su trabajo relacionado con las finanzas para el desarrollo del limpiador widgets. 

Para el ejemplo anterior, se completaría las tareas siguientes para configurar la relación de trabajo entre Felix Henderson y Ana Bowman:
1.  Cree un tipo de jerarquía de puestos personalizado denominado "Widget" para crear una jerarquía que incluya los puestos responsables de trabajar en el producto limpiador de widgets.
2.  Asigne el puesto Director general como puesto del que será subordinado el puesto Contable-A en la jerarquía de Widget.

Use la página **Jerarquía de puestos** para ver la estructura de la jerarquía de puestos subordinados. Si tiene varias jerarquías de puestos, puede ver la jerarquía para cada tipo de jerarquía en la **Jerarquía de puestos**. Además, puede buscar un puesto por el identificador de puesto o mediante el nombre del trabajador asignado al puesto. La **Jerarquía de puestos** es una jerarquía organizativa.

## <a name="date-effective-records"></a>Registros de fecha de vigencia
Para algunos registros, puede especificar cambios futuros al registro. La siguiente información está sujeta a fechas de vigencia.

<table>
<thead>
<tr class="header">
<th>Registros</th>
<th>Información sobre las fechas de vigencia</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Trabajos</td>
<td><ul>
<li>Información detallada sobre el trabajo</li>
<li>Información sobre la clasificación del trabajo</li>
<li>Información sobre la compensación</li>
</ul></td>
</tr>
<tr class="even">
<td>Puestos</td>
<td><ul>
<li>Información detallada sobre el puesto</li>
<li>Asignaciones de trabajadores</li>
<li>Duraciones del puesto</li>
<li>Jerarquías de puestos</li>
</ul></td>
</tr>
</tbody>
</table>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
