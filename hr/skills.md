---
title: "Alienación de las aptitudes de los recursos con las necesidades empresariales"
description: "Puede realizar un seguimiento de las aptitudes que los trabajadores, los candidatos o las personas de contacto tienen o deben tener para cumplir adecuadamente con sus funciones. También puede especificar las aptitudes necesarias para un puesto concreto."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 720a1f272948eb310dc3cd02588aeec40b556d20
ms.openlocfilehash: 31dda85ff2e4a4e5380401b031b2dd74acff394b
ms.lasthandoff: 03/31/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>Alienación de las aptitudes de los recursos con las necesidades empresariales

Puede realizar un seguimiento de las aptitudes que los trabajadores, los candidatos o las personas de contacto tienen o deben tener para cumplir adecuadamente con sus funciones. También puede especificar las aptitudes necesarias para un puesto concreto.

Estos son ejemplos de aptitudes de las que se puede hacer un seguimiento:
-   Supervisión: capacidad para supervisar el trabajo de los demás.
-   Liderazgo: capacidad para dirigir empleados y dominios de empresa.
-   Planificación: capacidad para anticipar las cosas, formar visiones de futuro y ponerlas en práctica.
-   HTML: capacidad de escribir código HTML.

Antes de poder asignar una aptitud a una persona o un puesto, crear una búsqueda de asignación de aptitudes o crear un perfil de aptitudes, debe especificar información sobre las aptitudes en la página **Aptitudes**. Para cada aptitud, puede seleccionar un tipo de aptitud y un modelo de evaluación.

## <a name="rating-models"></a>Modelos de tasación
Los modelos de evaluación ayudan a evaluar el nivel de aptitud real de una persona, el nivel que deben trabajar para lograr o el nivel de aptitud necesario para un puesto. Puede escribir hasta 10 niveles para un modelo de evaluación.  Cada nivel en un modelo de evaluación se asigna un factor.  El valor del factor se usará para normalizar decenas de las aptitudes que utilicen distintos modelos de evaluación.  El factor debe ser un número entre 0-9 y cada nivel debe tener un factor único.  Los niveles con valores más altos de factor conllevan más peso en un modelo de evaluación.

## <a name="specify-job-skills"></a>Especificar las aptitudes de trabajo
Al especificar la información acerca de un trabajo, puede especificar las aptitudes que si una persona tenga que realizar el trabajo necesario para el trabajo.  Además puede especificar el nivel deseado para cada aptitud también el nivel de importancia de la aptitud. Los distintos trabajos pueden requerir niveles distintos de importancia de la misma aptitud.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Especificar las aptitudes para trabajadores, candidatos o contactos
Puede especificar aptitudes objetivo o aptitudes reales para trabajadores, candidatos o contactos. Una aptitud objetivo es una aptitud una persona tiene previsto lograr. Una aptitud real es una aptitud que una persona tiene actualmente.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Distribución de habilidades y perfiles de distribución de habilidades
Puede crear una búsqueda de distribución de perfiles para encontrar un trabajador, un candidato, o a una persona de contacto que está habilitado para efectuar un tipo específico de tarea. Las búsquedas de distribución de perfiles relación a través de conocimientos, de la formación, de certificados, de puestos de confianza y de experiencia en proyectos y devuelven los resultados que coincidan con los criterios especificados.  Por ejemplo, puede que se útil saber qué trabajadores de la organización la hayan obtenido su CPA.

Los perfiles de asignación de aptitudes permiten que considere a empleados actuales o candidatos con calificaciones que se correspondan directamente al negocio necesitan.  Por ejemplo, podría crear un perfil de asignación de aptitudes para una vacante en su organización. Al crear un perfil para un determinado trabajo y copiar las aptitudes, la formación y los certificados de dicho trabajo al perfil, puede buscar rápidamente trabajadores, candidatos y personas de contacto que coincidan con uno o más de los criterios especificados en el perfil y ver una lista de los candidatos cuyas habilidades coincidan más con las aptitudes necesarias para el trabajo.

<table>
<thead>
<tr class="header">
<th><strong>Nota </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Solo los trabajadores, los candidatos y las personas de contacto que se seleccionan para incluirse en las búsquedas de distribución de aptitudes se pueden mostrar en una lista de los resultados correspondiente o incluirse en un perfil de aptitudes. Para incluir un trabajador, un candidato o una persona de contacto en búsquedas de distribución de perfiles, establezca <strong>Incluir en distribución de habilidades</strong> en Sí en las siguientes páginas:
<ul>
<li>Trabajador</li>
<li>Empleado</li>
<li>Candidato</li>
<li>Contactos</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Análisis de lagunas de aptitudes y análisis de perfiles de aptitudes
Puede crear un análisis de aptitud para ver una lista de las capacidades para un trabajador, un candidato o una persona de contacto a partir de una fecha específica. Puede crear un análisis de lagunas de aptitudes para comparar las aptitudes de una persona con las aptitudes necesarias para un puesto.  



<a name="see-also"></a>Consulte también
--------

[Human resources](index.md)


