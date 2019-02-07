---
title: Configurar los componentes de un trabajo
description: "Este tema describe los artículos conceptuales que un trabajo puede incluir y se proporcionan ejemplos de cómo se pueden usar los artículos en la organización."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle
audience: Application User
ms.author: rschloma
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent, Retail
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 82f039b305503c604d64610f39838fa86a8eb08a
ms.openlocfilehash: b40b81fc24086e73b54cfe0cb5e6a81ec5838ab5
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="set-up-the-components-of-a-job"></a>Configurar los componentes de un trabajo

[!include [banner](includes/banner.md)]


Este tema describe los artículos conceptuales que un trabajo puede incluir y se proporcionan ejemplos de cómo se pueden usar los artículos en la organización. 

Antes de poder crear trabajos, debe configurar información de referencia. Puede crear un trabajo que tiene solo un nombre. Sin embargo, incluyendo información adicional, como un puesto, ofrece los valores predeterminados para los puestos asignados al trabajo. Además, parte de la información que especifique se puede usar para filtrar planes de compensación para trabajos específicos. Si quiere configurar elegibilidad que pueda usar para filtrar planes de compensación para un trabajo específico, debe configurar funciones de trabajo y tipos de trabajo antes de configurar los trabajos. Con estos valores predeterminados disponibles, ahorrará tiempo al agregar puestos al trabajo. 

Algunos detalles del trabajo, como el título, tipo y función, tienen fechas de vigencia. Si crea un trabajo hoy pero no agrega estos detalles hasta una fecha posterior, y a continuación busca el trabajo a partir de la fecha de creación, estos detalles no aparecerán. Por lo tanto, debe crear parte de esta información de referencia antes de que la necesite. De esta manera, puede agregar la información a los nuevos trabajos cuando los crea.

## <a name="job-titles"></a>Cargos
Para crear trabajos, debe configurar cargos para dichos trabajos. Los puestos heredarán cargos de los trabajos con los que están asociados los puestos. 

Mantenga los cargos mediante la página **Cargos**, que puede abrir usando la función de búsqueda. En la página **Cargos**, especifique los puestos que pretende usar para sus trabajos.

## <a name="job-types"></a>Tipos de trabajo
Use los tipos de trabajo para agrupar trabajos similares en categorías. Los tipos de trabajos no son necesarios. Sin embargo, si planifica usar tipos de trabajos al configurar reglas de elegibilidad para la gestión de compensación, debe configurar tipos de trabajos antes de configurar trabajos. Algunos ejemplos de tipos de trabajo son a jornada completa y a tiempo parcial, o con sueldo y paga por horas. Se mantienen los tipos de trabajo mediante la página **Tipos de trabajo**. En la página **Tipos de trabajo**, especifique un nombre y una descripción breve para el tipo de trabajo. En el campo **Estado de exento**, seleccione una de las opciones siguientes para indicar el estado de exento de la Fair Labor Standards Act (ley sobre estándares de trabajo justo FLSA) de los trabajos que tienen este tipo de trabajo:

-   **Exento**: los trabajos están exentos de horas extra con la FLSA.
-   **No exento**: los trabajos no están exentos de horas extra con la FLSA.
-   **No aplicable**: la cobertura de FLSA no es aplicable.

## <a name="job-functions"></a>Funciones de trabajo
Las funciones de trabajo describen categorías funcionales de alto nivel y deberes de alto nivel relacionados. Las funciones de trabajo no son necesarias. Puede usar funciones de trabajo junto con tipos de trabajo para filtrar planes de compensación para trabajos específicos. Para asociar funciones y tipos de trabajo a planes de compensación, configure reglas de idoneidad en la página **Regla de idoneidad**. Después puede vincular un grupo de niveles a un plan de compensación que se aplique a la combinación específica de tipo y función de trabajo que ha definido mediante una regla de idoneidad. (Estas características se aplican a los planes de compensación fijos y los planes de compensación variables). Sin embargo, si planea usar funciones de trabajo al configurar reglas de idoneidad para la gestión de compensación, debe configurar funciones de trabajo antes de configurar trabajos. La tabla siguiente muestra algunos ejemplos de funciones de trabajo.

| Trabajo           | Función de trabajo         |
|---------------|----------------------|
| Director de ventas | Administrador de nivel medio    |
| Contable    | Profesionales        |

Se mantienen las funciones de trabajo mediante la página **Funciones de trabajo**. En la página **Funciones de trabajo**, especifique un código de identificación y una descripción breve para la función de trabajo.

## <a name="job-tasks"></a>Tareas de trabajo
Las tareas de trabajo describen las tareas básicas que un trabajador de un puesto debe completar para un trabajo. La misma tarea de trabajo se puede agregar a varios trabajos y a puestos para trabajos que usan dichas tareas de trabajo. La tabla siguiente muestra algunos ejemplos de tareas de trabajo.

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
<li><strong>Revisión de rendimiento</strong>: permite revisar el rendimiento de trabajo de cada vendedor.</li>
<li><strong>Revisión de ausencia</strong>: permite aprobar o rechazar solicitudes o registros de ausencia de cada vendedor.</li>
</ul></td>
</tr>
<tr class="even">
<td>Contable</td>
<td><strong>Informe financiero</strong>: permite presentar informes financieros semanales al director financiero.</td>
</tr>
</tbody>
</table>

Se mantienen las tareas de trabajo mediante la página **Tareas de trabajo**. En la página **Tareas de trabajo**, especifique un nombre y una descripción para la tarea de trabajo. En el campo **Nota** puede especificar información adicional opcionalmente. Las notas se pueden actualizar para un trabajo específico sin cambiar las notas que ha especificado aquí.

## <a name="areas-of-responsibility"></a>Áreas de responsabilidad
Use las áreas de responsabilidad para indicar los roles de trabajo, los procesos y los productos de los que sería responsable un trabajador en un puesto para dicho trabajo. Un ejemplo de área de responsabilidad para un trabajo denominado "Contable" podría ser "Informes financieros del producto A". Las áreas de responsabilidad se mantienen mediante la página **Áreas de responsabilidad** que puede encontrar mediante la función de búsqueda. En la página **Áreas de responsabilidad**, especifique un nombre y una descripción para la responsabilidad. En el campo **Nota** puede especificar información adicional opcionalmente. Las notas se pueden actualizar para un trabajo específico sin cambiar las notas que ha especificado aquí.

## <a name="steps-for-creating-a-job"></a>Pasos para crear un trabajo
Consulte la sección [Definir nuevos trabajos](../fin-and-ops/hr/tasks/define-new-jobs.md) para informarse del procedimiento detallado para crear un nuevo trabajo. 

