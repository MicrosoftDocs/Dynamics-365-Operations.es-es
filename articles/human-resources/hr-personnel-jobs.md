---
title: Configurar los componentes de un trabajo
description: Este tema describe los artículos conceptuales que un trabajo puede incluir y se proporcionan ejemplos de cómo se pueden usar los artículos en la organización.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmJob, HcmJobFunction, HcmJobTask, HcmTitle, HcmPersonnelManagementWorkspace, HCMJobFamily
audience: Application User
ms.author: twheeloc
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: de828bc1ab764a8a1bd084a508f38ff19a3947d5
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693595"
---
# <a name="set-up-the-components-of-a-job"></a>Configurar los componentes de un trabajo


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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

## <a name="job-family"></a>Familia de trabajos
Una familia de trabajos es un grupo de trabajos que implican un trabajo similar y que requieren capacitación, habilidades, conocimientos y experiencia similares. Una familia de trabajos puede vincularse a un trabajo en la ficha desplegable **Clasificación de Trabajo** de la página **Trabajos** y en la ficha desplegable **General** de la página **Todas las posiciones**. Las familias de puestos pueden ser amplias o específicas, según su negocio y los requisitos de informes. Algunos ejemplos de amplias familias laborales son **Mano de obra calificada** y **Trabajo que no requiere especialización**. Algunos ejemplos de familias laborales específicas son **Contabilidad**, **Fabricación** y **Ventas**.

Mantenga las familias de cargos mediante la página **Familia de cargos**, que puede abrir usando la función de búsqueda. Sobre la página **Familia de cargos**, ingrese un nombre único para la familia e ingrese una descripción detallada que planea usar para sus trabajos.

## <a name="job-functions"></a>Funciones de trabajo
Las funciones de trabajo describen categorías funcionales de alto nivel y deberes de alto nivel relacionados. Las funciones de trabajo no son necesarias. Puede usar funciones de trabajo junto con tipos de trabajo para filtrar planes de compensación para trabajos específicos. Para asociar funciones y tipos de trabajo a planes de compensación, configure reglas de idoneidad en la página **Regla de idoneidad**. Después puede vincular un grupo de niveles a un plan de compensación que se aplique a la combinación específica de tipo y función de trabajo que ha definido mediante una regla de idoneidad. (Estas características se aplican a los planes de compensación fijos y los planes de compensación variables). Sin embargo, si planea usar funciones de trabajo al configurar reglas de idoneidad para la gestión de compensación, debe configurar funciones de trabajo antes de configurar trabajos. La tabla siguiente muestra algunos ejemplos de funciones de trabajo.

| Trabajo           | Función de trabajo         |
|---------------|----------------------|
| Director de ventas | Administrador de nivel medio    |
| Contable    | Profesionales        |

Se mantienen las funciones de trabajo mediante la página **Funciones de trabajo**. En la página **Funciones de trabajo**, especifique un código de identificación y una descripción breve para la función de trabajo.

## <a name="compensation"></a>Compensación
Para asignar un plan de compensación fijo a un empleado que tiene un puesto en un trabajo, debe establecer niveles de compensación en el trabajo. El **Nivel de compensación** se utiliza cuando las cantidades mínima, media y máxima se establecen en una estructura de compensación (cuadrícula de compensación). Cuando se crea un plan de compensación fijo, se selecciona la estructura de compensación. La estructura de compensación también incluye el nivel de compensación. Cuando selecciona un plan de compensación fijo para un empleado, los niveles de compensación que están disponibles para la selección dependen del trabajo al que está asociado el puesto del empleado. Para obtener más información acerca de cómo configurar la compensación, consulte [Planes de compensación](hr-compensation-overview.md).

## <a name="job-skills"></a>Aptitudes de trabajo
Las habilidades laborales describen las habilidades que se requieren para realizar un trabajo. Un nivel de habilidad debe estar asociado con cada habilidad laboral. Los niveles de habilidad los define el usuario. Indican el nivel de conocimiento o competencia que se requiere para la habilidad. Por ejemplo, las empresas pueden configurar niveles numéricos, como del 1 al 5, donde **1** indica un principiante y **5** indica un experto. Alternativamente, las empresas pueden configurar niveles etiquetados **Principiante**, **Intermedio** o **Experto**. Una vez establecido el nivel de habilidad, también se puede establecer la importancia de la habilidad. Por ejemplo, si se requiere que un contador tenga un conocimiento sólido de Microsoft Excel, una habilidad que se llama **Conocimiento de Excel** se puede crear. A continuación, el nivel de habilidad se puede establecer en **Intermedio** y la importancia se puede establecer en **La mayoría**.

Las habilidades que se encuentran en un trabajo se pueden usar en el mapeo de habilidades. El mapeo de habilidades puede comparar el conjunto de habilidades que se requiere para un trabajo y las habilidades asociadas con un trabajador. Luego puede determinar un porcentaje de coincidencia, basado en habilidades superpuestas. Para obtener más información sobre el mapeo de habilidades, consulte [Configurar habilidades](hr-develop-skills.md). 

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
Consulte el artículo [Definir nuevos trabajos](./hr-personnel-define-jobs.md) para informarse del procedimiento detallado para crear un nuevo trabajo. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
