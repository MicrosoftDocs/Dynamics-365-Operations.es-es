---
title: Registro para ejecución de fabricación
description: En este tema se describen los conceptos y los términos clave que necesita comprender para configurar y usar la ejecución de fabricación.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 70103
ms.assetid: 52ba1cdd-767f-4edd-896f-61adce8479d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 19b1bf7055132c824bc4043c0bd1dbad3afce2a9
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209356"
---
# <a name="registration-for-manufacturing-execution"></a>Registro para ejecución de fabricación

[!include [banner](../includes/banner.md)]

En este tema se describen los conceptos y los términos clave que necesita comprender para configurar y usar la ejecución de fabricación. 

El objetivo de la ejecución de fabricación es que la empleen principalmente las empresas de fabricación. Los trabajadores pueden registrar el consumo de tiempo y artículos en trabajos de producción mediante la página **Registro del trabajo**. Todos los registros se aprueban y posteriormente se transfieren a los módulos relevantes. Las aprobaciones y transferencias continuas de registros permiten a los gerentes hacer un fácil seguimiento de los costes reales de los pedidos de producción.

## <a name="manufacturing-execution-and-registration-terminology"></a>Terminología de registro y ejecución de fabricación
La siguiente tabla contiene términos relativos a la ejecución de fabricación y tareas de registro relacionadas.

| Condición                          | Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ejecución de fabricación       | Una función usada para registrar la hora, el consumo de materiales, los costes de trabajo de producción, los proyectos y otras actividades indirectas. El registro se realiza en un cliente de registro de una ejecución de fabricación.                                                                                                                                                                                                                                                                                                                                                                                                   |
| Lista de trabajos                      | En la página **Registro del trabajo** se muestra a los trabajadores la lista de trabajos que deben realizar en un recurso concreto, como por ejemplo una máquina. Los trabajadores pueden registrar la hora y el consumo de artículos en cada trabajo o tarea de la lista de trabajos.                                                                                                                                                                                                                                                                                                                                                                           |
| Agrupación de trabajos                  | Si un trabajador inicia más de un trabajo a la vez en la página **Registro del trabajo**, se denomina "agrupación de trabajos". El tiempo empleado en trabajos agrupados se puede asignar a trabajos individuales de distintas maneras, mediante las claves de asignación.                                                                                                                                                                                                                                                                                                                                                         |
| Registros pilotos o asistentes | Un trabajador puede registrarse como asistente en un recurso y crear un pequeño equipo en el que varios trabajadores pueden trabajar en los mismos trabajos de producción. Los recursos a los que están conectados los trabajadores como asistentes se llaman pilotos. Solo debe realizar registros el recurso responsable. Todos los ayudantes obtienen automáticamente los mismos registros. Si, por ejemplo, una máquina funciona como responsable, los trabajadores que se hayan registrado como asistentes para esa máquina pueden realizar registros en la página **Registro del trabajo**, y tanto la máquina como los trabajadores conectados como asistentes recibirán los mismos registros. |
| Actividad indirecta             | Una actividad o tarea que no está relacionada directamente a un trabajo de producción o un proyecto, como una reunión del departamento, un trabajo de limpieza o un trabajo de mantenimiento en la planta. Los trabajadores pueden realizar registros en actividades indirectas de la misma manera en la que pueden registrar trabajos de producción o proyectos.                                                                                                                                                                                                                                                                                                |

## <a name="registrations-in-manufacturing-execution"></a>Registros de la ejecución de fabricación
Los trabajadores pueden realizar diferentes tipos de registros de la ejecución de fabricación para el trabajo realizado en trabajos de producción. En función de la configuración del sistema, los trabajadores también podrán realizar registros sobre actividades de proyecto y sobre tareas no productivas, como descansos, ausencias y actividades indirectas. Estos son los tipos de registro:

-   **Horas de entrada o salida** (disponible con hora y asistencia): los trabajadores fichan cuando llegan al trabajo y cuando se van a casa.
-   **Registro de trabajos de producción**: los trabajadores puede hacer registros, como iniciar un trabajo y remitir comentarios sobre un trabajo, sobre trabajos de producción que aparecen en su lista de trabajos. Los trabajos pueden iniciar varios trabajos al mismo tiempo. Esto se conoce como agrupación de trabajos.
-   **Registro de inventario**: los trabajadores pueden realizar registros sobre los materiales utilizados en la planta pero que no están directamente relacionados con trabajos de producción. Estos podrían incluir grasa, lubricantes u otros materiales usados para mantener una máquina en funcionamiento. El registro se realiza en un diario de inventario.
-   **Registros en los proyectos** (disponible con tiempo y asistencia): los trabajadores pueden realizar registros, como el inicio y fin de trabajos en proyectos o actividades de proyecto que aparecen en su lista de trabajos.
-   **Registro de cuotas del proyecto y artículos del proyecto** (disponible con tiempo y asistencia): los trabajadores pueden registrar tarifas (gastos) asociadas con un proyecto en un diario de cuotas de proyecto, como kilometraje o peajes. Los trabajadores también pueden registrar el consumo de artículos en proyectos. Esto se realiza en un diario de artículos de proyecto.
-   **Registro como asistente de otro trabajador**: si dos o más trabajadores van a trabajar juntos en un proyecto o trabajo de producción, un trabajador puede registrarse como asistente de una máquina o de otro trabajador, que actuará como responsable. El responsable podrá seleccionar a otro trabajador como responsable, según sea oportuno.
-   **Registro de ausencias** (disponible con tiempo y asistencia): los trabajadores pueden registrar el tiempo en distintos códigos de ausencia configurados. Es posible indicar ausencia si un trabajador llega tarde, necesita ausentarse durante la jornada o se marcha antes de lo esperado de acuerdo al perfil estándar de horario laboral.
-   **Registro de descansos** (disponible con tiempo y asistencia): durante los días laborables, los trabajadores pueden registrar su salida de la estación de trabajo para descansos. Pueden configurarse varios tipos de descanso. Cuando un trabajador vuelve e inicia sesión de nuevo, el sistema registra que el trabajador ha vuelto y se detiene el registro de descanso.
-   **Registro en actividades indirectas** (disponible con tiempo y asistencia): las actividades indirectas son actividades no productivas que puede realizar un trabajador durante la jornada, como una reunión de departamento, una reunión de equipo o un trabajo de mantenimiento realizado en la planta. Los trabajadores pueden realizar registros en las actividades indirectas configuradas.
-   **Registro de horas extra** (disponible con tiempo y asistencia): los trabajadores a los que se ha pedido que trabajen más horas pueden seleccionar si las horas extra se deben registrar como horas extra u horario flexible.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]