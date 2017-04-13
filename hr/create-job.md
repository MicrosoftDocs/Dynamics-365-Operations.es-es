---
title: "Configuración de los componentes de un trabajo"
description: "Este tema describe los artículos conceptuales que un trabajo puede incluir y se proporcionan ejemplos de cómo se pueden usar los artículos de la organización."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: d96b1f01a5cb4370436888deae8fd4835a0dbb80
ms.openlocfilehash: b8143db5b133337603a7f2f46028d91bb81cd947
ms.lasthandoff: 03/31/2017


---

# <a name="setting-up-the-components-of-a-job"></a>Configuración de los componentes de un trabajo

Este tema describe los artículos conceptuales que un trabajo puede incluir y se proporcionan ejemplos de cómo se pueden usar los artículos de la organización. 

Para poder crear trabajos, debe configurar información de referencia. Puede crear un trabajo que tiene sólo un nombre. Sin embargo, incluida la información adicional, como un puesto, ofrece los valores predeterminados para los puestos asignados a trabajo. Además, parte de la información que especifique se puede usar para filtrar planes de compensación para trabajos específicos. Si desea configurar la idoneidad que se puede usar para filtrar planes de compensación para un trabajo específico, debe configurar funciones y tipos de trabajo antes de configurar trabajos de la configuración. Con estos valores predeterminados disponibles, se permitirá ahorrar tiempo en el que agrega puestos al trabajo. 

Algunos detalles del trabajo, como el título, tipo y función, son fechas reales. Si crea un trabajo actual pero no agrega estos detalles hasta una fecha posterior, y a continuación buscará el trabajo a partir de la fecha de creación, estos detalles no aparecerán. Por lo tanto, debe crear parte de esta información de referencia antes de que se requiera la. De esta manera, puede agregar información a los nuevos trabajos al configurar crea.

## <a name="job-titles"></a>Puestos
Para crear trabajos, debe configurar cargos para dichos trabajos. Los puestos heredarán cargos de los trabajos con los que están asociados los puestos. 

Mantener los puestos ** mediante los puestos ** la página, que puede abrir mediante la función de búsqueda. En ** los puestos ** la página, especifique los puestos que pretende usar para sus trabajos.

## <a name="job-types"></a>Tipos de trabajo
Los tipos de trabajo para agrupar trabajos similares en categorías. Los tipos de trabajos no son necesarios. Sin embargo, si planifica usar tipos de trabajos al configurar reglas de elegibilidad para la gestión de compensación, debe configurar tipos de trabajos antes de configurar trabajos. Algunos ejemplos de tipos de trabajo son a jornada completa y a tiempo parcial, o sueldo y paga por horas. Se mantiene tipos de trabajo mediante ** los tipos de trabajo ** la página. En ** los tipos de trabajo ** la página, especifique un nombre y una breve descripción para el tipo de trabajo. En ** estado de exento ** campo, seleccione una de las opciones siguientes para indicar el estado de exento de (FLSA) de FLSA Ley de los estándares de trabajo de trabajos que tienen este tipo de trabajo:

-   ** ** – Los trabajos exentos están exentos de horas extra con el FLSA.
-   ** ** – los trabajos no exentos no están exentos de horas extra con el FLSA.
-   ** No se aplica – ** el alcance de FLSA no es aplicable.

## <a name="job-functions"></a>Funciones de trabajo
Las uniones de trabajo categorías describen funcionales de alto nivel y deberes relacionadas de alto nivel. Las funciones de trabajo no son necesarias. Puede usar funciones de trabajo, junto con tipos de trabajo, para filtrar planes de compensación para trabajos específicos. Para asociar funciones y tipos de trabajo a planes de compensación configurando reglas de idoneidad en ** las reglas de idoneidad ** la página. A continuación puede vincular un conjunto de niveles al plan de compensación que se apliquen a la combinación específica de una función del tipo de trabajo y de trabajo que ha definido mediante una regla de idoneidad. (Estas características se aplican a planes de compensación fija y los planes de compensación variable.) Sin embargo, si planifica usar funciones de trabajo al configurar reglas de elegibilidad para la gestión de compensación, debe configurar funciones de trabajos antes de configurar trabajos de la configuración. En la tabla siguiente se muestran algunos ejemplos de las funciones de trabajo.

| Trabajo           | Función de trabajo         |
|---------------|----------------------|
| Director de ventas | Administrador de nivel medio    |
| Contable    | Profesionales        |

Se mantiene funciones de trabajo mediante ** las funciones de trabajo ** la página. ** En las funciones de trabajo ** la página, especifique un código de identificación y una descripción breve para la función de trabajo.

## <a name="job-tasks"></a>Tareas de trabajo
Las tareas de trabajo se describen tareas básicas que un trabajador que se encuentra en un puesto para un trabajo debe completar. La misma tarea de trabajo se puede agregar a varios trabajos, y a los puestos para los trabajos que usan esas tareas de trabajo. En la tabla siguiente se muestran algunos ejemplos de tareas de trabajo.

<table>
<thead>
<tr class="header">
<th>Trabajo</th>
<th>Tarea de trabajo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Director de ventas</td>
<td><ul>
<li><strong>Perforación- revisión</strong> – Revisar el rendimiento en el trabajo de cada vendedor.</li>
<li><strong>ABS- revisión</strong> Permite aprobar o rechazar solicitudes de ausencia o los registros de cada vendedor.</li>
</ul></td>
</tr>
<tr class="even">
<td>Contable</td>
<td><strong>Aleta-informe</strong> – Actuales informes financieros semanales al director financiero.</td>
</tr>
</tbody>
</table>

Se mantiene tareas de trabajo mediante ** las tareas de trabajo ** la página. ** En las tareas de trabajo ** la página, especifique un nombre y una descripción de la tarea de trabajo. En ** nota ** campo, puede especificar opcionalmente la información adicional. Las notas se pueden actualizar para un trabajo específico sin cambiar las notas que ha especificado aquí.

## <a name="areas-of-responsibility"></a>Áreas de responsabilidad
Se usa áreas de responsabilidad para indicar los roles de trabajo, los procesos, los productos y que un trabajador que se encuentra en un puesto para un trabajo es el responsable de. Por ejemplo, para un trabajo que se denomina “,” contable un área de responsabilidad será “informe financiero para el producto A.” Se mantiene áreas de responsabilidad ** mediante las áreas de responsabilidad ** la página, que puede encontrar mediante la función de búsqueda. ** En las áreas de responsabilidad ** la página, especifique un nombre y una descripción para la responsabilidad. En ** nota ** campo, puede especificar opcionalmente la información adicional. Las notas se pueden actualizar para un trabajo específico sin cambiar las notas que ha especificado aquí.


