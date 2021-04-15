---
title: Registro de ausencia en Tiempo y asistencia
description: Este tema explica cómo administrar los registros de ausencia en Tiempo y asistencia.
author: johanhoffmann
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JMGParameters, JmgAbsenceCalendar
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b765ae63cfb17e26439758f2a0ed64770ef70881
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809287"
---
# <a name="absence-registration-in-time-and-attendance"></a>Registro de ausencia en Tiempo y asistencia

[!include [banner](../includes/banner.md)]

Este tema describe los conceptos para ausencia y explica cómo gestionar ausencia en Tiempo y asistencia.

## <a name="absence-that-is-based-on-regular-work-hours"></a>Ausencia que se basa las horas de trabajo normales

Los trabajadores se consideran ausentes por las horas que no trabajen durante las horas de trabajo normales. Las horas de trabajo normales se definen en el perfil de tiempo estándar de un trabajador.

Por ejemplo, un trabajador trabaja en un perfil de día que tiene hora de entrada a las 7:00 y salida a las 15:00. Si el trabajador entra a trabajar a las 9:00, se considera ausentes de 7:00 a 9:00 ese día.

En este caso, se pide a los trabajadores que especifiquen un motivo de la ausencia. Pueden especificar un motivo seleccionando un código de ausencia.

## <a name="absence-codes"></a>Códigos de ausencias

Los códigos de ausencia definen los diferentes tipos de ausencia. Los códigos de ausencia están definidos por la empresa.

Se pueden aplicar distintas reglas a códigos de ausencia. Por ejemplo, se puede configurar un código de ausencia para deducir o conceder un pago.

Por ejemplo, una empresa define un código de ausencia **Tarde** que los trabajadores usan si llegan tarde y no tienen un buen motivo. La empresa también define un código de ausencia **Curso interno** que los trabajadores usan para el tiempo que dedican a asistir a cursos internos. Estos códigos de ausencia pueden configurarse para que **Tarde** se deduzca del sueldo del trabajador pero **Curso interno** pero no se deduzca del sueldo del trabajador.

Puede configurar códigos de ausencia automáticos. Estos códigos de ausencia se pueden utilizar para calcular el tiempo de un trabajador cuando no se registra ninguna ausencia. El perfil de tiempo de un trabajador determina si se usa el código de ausencia para tiempo estándar o tiempo flexible.

### <a name="set-up-standard-time-and-flex-time"></a>Configurar tiempo estándar y tiempo flexible

- Configure los parámetros para tiempo estándar y tiempo flexible utilizando las opciones **Insertar autom. ausencia** e **Insertar autom. horario flexible-** en la página **Parámetros de Tiempo y asistencia**.

## <a name="absence-groups"></a>Grupos de ausencias

Los códigos de ausencia se agrupan en grupos de ausencia. Puede utilizar grupos de ausencia para agrupar los códigos de ausencia con características comunes. Algunos ejemplos son: códigos de ausencia por una ausencia legal, o ausencia por una cita con médico, obligación de jurado o enfermedad de un hijo.

## <a name="planned-absence"></a>Ausencia planificada

Si sabe que un trabajador estará ausente durante un período, como vacaciones próximas, puede usar ausencia planificada. Establezca la ausencia planificada configurando el código de ausencia de modo que considere la ausencia planificada. Al configurar una ausencia planificada, no se solicitará un código de ausencia durante el período de ausencia cuando se calculen los registros de horas del usuario. La ausencia planificada se puede definir para un solo trabajador, o puede definir un trabajo por lotes para que actualice de forma masiva la ausencia planificada para los trabajadores.

### <a name="set-up-planned-absence"></a>Configurar ausencia planificada

1. Seleccione &gt; **Recursos humanos** **Trabajadores** &gt; **Empleados** y seleccione un empleado.
2. Seleccione **Tiempo** &gt; **Asignaciones de tiempo** &gt; **Registro de ausencia de tiempo**, y configure la ausencia planificada.

## <a name="interrupted-planned-absence"></a>Ausencia planificada interrumpida

Si aplica la opción **Interrumpir** cuando configura una ausencia planificada, la ausencia planificada se interrumpirá si el trabajador inicia sesión durante el período de ausencia planificada. La ausencia planificada se marcará como **Interrumpida** y no tendrá efecto en los cálculos futuros.

### <a name="set-up-a-planned-absence-for-interruption"></a>Configurar una ausencia planificada para interrupción

1. Abra la página **Registro de ausencia de tiempo** tal como se describe en el procedimiento para configurar ausencia planificada.
2. Seleccione **Interrumpir**.

La opción **Interrumpir** se aplica cuando el tiempo se registra mediante el terminal de planta o el dispositivo de planta. La opción no se aplica si los registros se especifican en las páginas de cálculo y aprobación, o en la página **Tarjeta de hora electrónica**.

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a>Ejemplos de uso de ausencia en un perfil flexible

Los tres ejemplos siguientes muestran cómo se calcula la ausencia en un perfil que tiene períodos de horario flexible.

Los ejemplos usan el perfil siguiente.

| Registrar la hora de entrada | Hora estándar    | Descanso             | Hora estándar | Horario flexible-        | Registrar la hora de salida | Horario flexible+        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| 8 AM     | 9 AM a 11:30 AM | 11:30 AM a 12 PM | 12 PM a 3 PM | 3 PM a 4 PM | 4 PM      | 4 PM a 6 PM |

### <a name="example-1-signing-out-during-a-flex--period"></a>Ejemplo 1: Cerrar sesión durante un período de horario flexible-

El trabajador entra a las 8:00 y sale a las 15:30. En este caso, dado que el trabajador sale durante un período de horario flexible-, no se calcula ninguna ausencia, y se deduce media hora del saldo de horario flexible del trabajador.

### <a name="example-2-signing-out-in-during-standard-time-period"></a>Ejemplo 2: Cerrar sesión durante período de tiempo estándar

El trabajador entra a las 8:00 y sale a las 14:30. En este caso, dado que el trabajador sale durante el periodo de hora estándar, la ausencia se calcula de las 14:30 a las 16, y se registra un período de ausencia de 1,5 horas. Se requiere un código de ausencia para ese período.

### <a name="example-3-signing-out-during-a-flex-period"></a>Ejemplo 3: Cerrar sesión durante un período de horario flexible+

El trabajador entra a las 8:00 y sale a las 16:30. En este caso, dado que el trabajador sale durante un período de horario flexible+, no se calcula ninguna ausencia, y se agrega media hora al saldo de horario flexible del trabajador.

## <a name="absence-in-the-calculation-and-approval-process"></a>Ausencia en el proceso de cálculo y aprobación

Los registros de tiempo del trabajador se deben calcular y aprobar antes de que puedan transferirse a un sistema de nóminas como elementos del sueldo.

Un aprobador puede modificar los registros de tiempo de un trabajador. El aprobador puede incluso cambiar cualquier ausencia que el trabajador haya registrado. Si el aprobador especifica manualmente un período de tiempo que tenga un código de ausencia, el código de ausencia para dicho período no es anulado por el código de ausencia predeterminado de los parámetros de Tiempo y asistencia.

Por ejemplo, una trabajador entra a las 10 y selecciona un código de ausencia que indica que llega tarde. Más adelante, la trabajadora notifica a su supervisor que tenía una cita médica de 8 a 10. Una cita médica no debe producir una reducción del sueldo del trabajador. Por tanto, en este caso, el supervisor puede ajustar las dos horas de ausencia de 8 a 10 manualmente especificando un código de ausencia que indica enfermedad por esas dos horas.

### <a name="calculate-and-approve-absence"></a>Calcular y aprobar ausencia

- Seleccione **Asistencia de tiempo** &gt; **Revisar y aprobar** &gt; **Aprobar o calcular**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]