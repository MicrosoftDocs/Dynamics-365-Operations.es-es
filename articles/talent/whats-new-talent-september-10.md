---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (10 de septiembre de 2018)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: ff5d21a8a71b068a276bedaf6e4b9964adcb4027
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896759"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-10-2018"></a>Novedades y cambios en Dynamics 365 Talent - Core HR (10 de septiembre de 2018)

**Compilación 8.1.138.0**

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent: Core HR.

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a>Deje tiempo específico del día en las solicitudes de licencia (días)

Si ha configurado la licencia y la ausencia para registrar el tiempo libre en días, ahora puede activar una definición de medio día. A continuación, cuando los usuarios envíen solicitudes de tiempo libre, pueden especificar si están solicitando la primera mitad o la segunda mitad del día libre.

Esta opción está desactivada de forma predeterminada. Para que los empleados pidan la primera mitad o la segunda mitad del día libre, debe activar esta opción en el área **Bajas y ausencias** de los parámetros de recursos humanos.

El privilegio de seguridad para esta función es mantener parámetros de recursos humanos.

## <a name="validation-of-leave-and-absence-entries"></a>Validación de las entradas de la licencia y de la ausencia

En función de cómo se configure la licencia, los empleados que intenten enviar una solicitud de tiempo de licencia que dure más que su día laborable reciben un mensaje de advertencia. Es decir se les advierte si intentan tomarse más de un día completo libre en una determinada fecha.

Esta validación está siempre activada. Cada vez que los empleados superen el umbral del día que está definido, reciben una advertencia en la solicitud de tiempo de licencia.

## <a name="additional-fields-for-conditional-statements-in-workflows"></a>Campos adicionales para las instrucciones condicionales en los flujos de trabajo

Se han agregado campos adicionales a las instrucciones condicionales y a los marcadores de varios flujos de trabajo en Core HR.

Los siguientes campos se han agregado a los flujos de trabajo de compensación, finalización, y transferencia:

- EmploymentType
- LegalEntity
- AdjustedWorkerStartDate
- EmployerNoticeAmount
- EmployerUnitOfNotice
- TransitionDate
- WorkerNoticeAmount
- WorkerStartDate
- WorkerUnitOfNotice
- ProbationEndDate
- Posición
- Unión
- Departamento
- PositionType
- CompLocation
- Cargo
- Trabajo
- JobType
- JobFamily
- JobFunction

Los campos siguientes se han agregado al flujo de trabajo de posición:

- Posición
- Unión
- Departamento
- PositionType
- CompLocation
- Cargo
- Trabajo
- JobType
- JobFamily
- JobFunction

Los campos de las instrucciones condicionales y los marcadores están disponibles para todos los usuarios que tengan acceso para configurar los flujos de trabajo anteriormente mencionados.

## <a name="navigation-to-attract-from-personnel-management"></a>Navegación a Attract desde la dirección del personal

En dirección de personal, si Attract no se ha configurado, la sección **Candidatos a contratar** solicita a los usuarios que se familiaricen con Attract en vez de mostrar el mensaje “No se encontró nada para mostrar aquí”.

## <a name="other-changes"></a>Otros cambios

Este lanzamiento incluye varias correcciones de errores adicionales:

- Cuando se utiliza un contratista, la pestaña **Compensación** no debe estar disponible en la página de solicitud/acción.
- Durante el proceso de finalización de la solicitud, no puede continuar hasta que todos los campos necesarios contengan datos.
- Los problemas de visualización de fechas y de criterios de ordenación de los análisis de la dirección del personal se han abordado.
