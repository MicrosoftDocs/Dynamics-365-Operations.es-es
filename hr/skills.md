---
title: "Alienación de las aptitudes de los recursos con las necesidades empresariales"
description: "Puede realizar un seguimiento de las aptitudes que los trabajadores, los candidatos o las personas de contacto tienen o deben tener para cumplir adecuadamente con sus funciones. También puede especificar las aptitudes necesarias para un puesto concreto."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
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
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ae940cdbab2166d8fe3f2f396c84ed4a09c2ca7e
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>Alienación de las aptitudes de los recursos con las necesidades empresariales

[!include[banner](includes/banner.md)]


Puede realizar un seguimiento de las aptitudes que los trabajadores, los candidatos o las personas de contacto tienen o deben tener para cumplir adecuadamente con sus funciones. También puede especificar las aptitudes necesarias para un puesto concreto.

Estos son ejemplos de aptitudes de las que se puede hacer un seguimiento:
-   Supervisión: capacidad para supervisar el trabajo de los demás.
-   Liderazgo: capacidad para dirigir empleados y dominios de empresa.
-   Planificación: capacidad para anticipar las cosas, formar visiones de futuro y ponerlas en práctica.
-   HTML: capacidad de escribir código HTML.

Antes de poder asignar una aptitud a una persona o un puesto, crear una búsqueda de asignación de aptitudes o crear un perfil de aptitudes, debe especificar información sobre las aptitudes en la página **Aptitudes**. Para cada aptitud, puede seleccionar un tipo de aptitud y un modelo de evaluación.

## <a name="rating-models"></a>Modelos de tasación
Los modelos de evaluación ayudan a evaluar el nivel de aptitud real de una persona, el nivel que deben trabajar para lograr o el nivel de aptitud necesario para un puesto. Puede escribir hasta 10 niveles para un modelo de evaluación.  Cada nivel del modelo de clasificación tiene asignado un factor.  El valor de factor se usará para normalizar las puntuaciones de las aptitudes que utilicen distintos modelos de clasificación.  El factor debe ser un número del 0 al 9 y cada nivel debe tener un factor único.  Los niveles con valores más altos de factor conllevan más peso en un modelo de evaluación.

## <a name="specify-job-skills"></a>Especificar las aptitudes de trabajo
Cuando se incluye información acerca de un trabajo, se pueden especificar las aptitudes que debe tener una persona para realizar el trabajo necesario.  Además, puede especificar el nivel deseado para cada aptitud y el nivel de importancia de la aptitud. Los distintos trabajos pueden requerir niveles distintos de importancia de la misma aptitud.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Especificar las aptitudes para trabajadores, candidatos o contactos
Puede especificar aptitudes objetivo o aptitudes reales para trabajadores, candidatos o contactos. Una aptitud objetivo es una aptitud una persona tiene previsto lograr. Una aptitud real es una aptitud que una persona tiene actualmente.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Distribución de habilidades y perfiles de distribución de habilidades
Puede crear una búsqueda de distribución de aptitudes para encontrar un trabajador, un candidato o una persona de contacto cualificada para realizar un tipo específico de tarea. Las búsquedas de distribución de aptitudes realizan búsquedas de aptitudes, formación, certificados, puestos de confianza y experiencia en proyectos, y devuelven los resultados que coincidan con los criterios especificados.  Por ejemplo, puede ser útil saber qué trabajadores de su organización tienen determinados certificados.

Los perfiles de distribución de aptitudes le permiten buscar empleados o candidatos actuales con cualificaciones que se correspondan directamente con sus necesidades empresariales.  Por ejemplo, podría crear un perfil de distribución de aptitudes para una vacante en su organización. Al crear un perfil para un determinado trabajo y copiar las aptitudes, la formación y los certificados de dicho trabajo al perfil, puede buscar rápidamente trabajadores, candidatos y personas de contacto que coincidan con uno o más de los criterios especificados en el perfil y ver una lista de los candidatos cuyas habilidades coincidan más con las aptitudes necesarias para el trabajo.

>**Nota** Solo los trabajadores, los candidatos y las personas de contacto que se seleccionan para incluirlas en las búsquedas de distribución de aptitudes se pueden mostrar en una lista de resultados de distribución de aptitudes o incluir en un perfil de aptitudes. Para incluir un trabajador, un candidato o una persona de contacto en búsquedas de distribución de perfiles, establezca **Incluir en distribución de habilidades** en Sí en las siguientes páginas:

> + Trabajador
> + Empleado
> + Candidato
> + Contactos

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Análisis de lagunas de aptitudes y análisis de perfiles de aptitudes
Puede crear un análisis de aptitud para ver una lista de las capacidades para un trabajador, un candidato o una persona de contacto a partir de una fecha específica. Puede crear un análisis de lagunas de aptitudes para comparar las aptitudes de una persona con las aptitudes necesarias para un puesto.  



<a name="see-also"></a>Consulte también
--------

[Recursos humanos](index.md)




