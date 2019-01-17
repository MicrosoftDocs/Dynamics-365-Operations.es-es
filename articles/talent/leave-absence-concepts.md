---
title: Conceptos de bajas y ausencias
description: "Este tema describe conceptos de baja y de ausencia, y cómo se determinan los saldos de tiempo de reposo."
author: jcart
manager: AnnBe
ms.date: 01/03/2019
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: a388e0efe6c19a3aabe04e7fff039ce11ae023c4
ms.openlocfilehash: 563593d6c93b0488c681f5b43004f5c0d22cc004
ms.contentlocale: es-es
ms.lasthandoff: 01/07/2019

---

# <a name="leave-and-absence-concepts"></a>Conceptos de bajas y ausencias

[!include[banner](../includes/banner.md)]

Los conceptos y los términos que se describen en este tema pueden ayudarle a determinar cómo se concede a un empleado tiempo libre, y cómo se calculan los saldos del tiempo de ese empleado. Para obtener más información acerca de la administración de baja y de ausencia, consulte [Administración de licencias y de ausencias](https://docs.microsoft.com/dynamics365/unified-operations/talent/leave-absence-overview).

## <a name="leave-plan-details"></a>Detalles del plan de licencia

### <a name="start-date"></a>Fecha de inicio

La fecha de inicio es la fecha en la que se inicia el procesamiento de la acumulación. La fecha inicial también sirve como la fecha del aniversario que se usa para calcular los importes transferibles.

## <a name="accruals"></a>Provisiones

Las acumulaciones determinan cuándo y con qué frecuencia se concede a un empleado tiempo libre. Las directivas acerca de cuándo las acumulaciones se deben conceder y las directivas sobre el prorrateo se definen en la sección **Acumulaciones** al configurar el plan de licencia y de ausencia.

### <a name="accrual-frequency"></a>Frecuencia de acumulación

La frecuencia de acumulación define con qué frecuencia se acumula o se concede la licencia. Las opciones siguientes están disponibles:

- Diariamente
- Semanal
- Quincenal
- Bimensual
- Mensual
- Trimestral
- Semestral
- Anualmente
- Nuevo

### <a name="accrual-period-basis"></a>Base del período de acumulación

La base del período de acumulación determina la fecha que se usa para calcular los períodos de acumulación. Las opciones siguientes están disponibles:

- **Fecha inicial del plan**
- **Fecha específica del empleado** Cuando se selecciona esta opción, el valor determina el origen del valor de fecha inicial que se usa para calcular períodos de acumulación. Las opciones siguientes están disponibles:

    - Personalizado
    - Fecha de aniversario
    - Fecha de contratación original
    - Antigüedad
    - Fecha inicial ajustada del trabajador
    - Primer día de trabajo del trabajador

### <a name="accrual-award-date"></a>Fecha de prima de acumulación

La fecha de prima de acumulación determina cuándo se concede a un empleado tiempo libre. Las opciones siguientes están disponibles:

- **Fecha final del período de acumulación** Conceden el empleado tiempo libre en el último día del período de prima.

    Para acumular el importe correcto, el proceso de acumulación debe incluir todo el período. Por ejemplo, el período de acumulación va del 1 de enero de 2018 al 31 de enero de 2018. En este caso, para que esté incluido enero, la acumulación se debe ejecutar para el 1 de febrero de 2018.

- **Fecha inicial del período de acumulación** Conceden el empleado tiempo libre en el primer día del período de prima.

### <a name="accrual-policy-on-enrollment"></a>Directiva de acumulación en la inscripción

La directiva de acumulación en la inscripción define cómo se calcula la acumulación cuando un empleado se inscribe a mediados de un período de acumulación. Las opciones siguientes están disponibles:

- **Prorrateado** El intervalo de fechas entre la fecha de inscripción y la fecha inicial se usa para determinar la diferencia en días. Se aplica esa diferencia cuando se procesan las acumulaciones.
- **Acumulación completa** El importe de acumulación completo, en función del nivel, se concede durante el primer procesamiento de la acumulación.
- **Ninguna acumulación** No se otorga ninguna acumulación hasta el período de acumulación siguiente.

### <a name="accrual-policy-on-unenrollment"></a>Directiva de acumulación para la anulación de la inscripción

La directiva de acumulación para la anulación de la inscripción define cómo se calcula la acumulación cuando se anula la inscripción de un empleado a mediados de un período de acumulación. Las opciones siguientes están disponibles:

- **Prorrateado** El intervalo de fechas entre la fecha de inscripción y la fecha inicial se usa para determinar la diferencia en días. Se aplica esa diferencia cuando se procesan las acumulaciones.
- **Acumulación completa** El importe de acumulación completo, en función del nivel, se concede durante el primer procesamiento de la acumulación.
- **Ninguna acumulación** No se otorga ninguna acumulación hasta el período de acumulación siguiente.

## <a name="accrual-schedule"></a>Programa de acumulación

La programación de acumulación determina cómo un empleado acumulará tiempo libre, y qué importes se acumularán y transferirán para dicho empleado. Los niveles se pueden crear para conceder el tiempo libre basándose en diferentes niveles.

### <a name="months-of-service"></a>Meses de servicio

El valor **Meses de servicio** define el número mínimo de meses que los empleados deben trabajar para ser autorizados a tener acumulaciones. Si no se requiere ningún mínimo para los empleados, establezca el valor en **0**.

### <a name="hours-worked"></a>Horas trabajadas

El valor **Horas trabajadas** define el número mínimo de horas que los empleados deben trabajar por período de acumulaciones para ser autorizados a tener acumulaciones. Si no se requiere ningún mínimo para los empleados, establezca el valor en **0**.

### <a name="accrual-amount"></a>Importe de acumulación

El importe de acumulación es el número de horas o de días que los empleados acrecentarán por período. El período se basa en la frecuencia de acumulación.

### <a name="minimum-balance"></a>Saldo mínimo

Un valor negativo se puede usar para el saldo mínimo si los empleados pueden solicitar más bajas de las que tienen disponibles.

### <a name="maximum-carry-forward"></a>Transferencia máxima

El proceso de acumulación ajustará los saldos de la licencia que superen el saldo máximo transferible en el aniversario de la fecha de inicio.

### <a name="grant-amount"></a>Importe de la concesión

El importe de la concesión es el número inicial de horas o días que se concede a los empleados cuando se inscriben por primera vez en el plan de baja. El importe no se acumula para cada período de acumulación.

## <a name="enrollments-and-balances"></a>Inscripciones y saldos

### <a name="enrollment-date"></a>Fecha de inscripción

La fecha de inscripción determina cuándo un empleado puede comenzar a acumular tiempo libre. Por ejemplo, si una empleada se inscribe en un plan de las vacaciones el 15 de junio de 2018, no puede acumular tiempo libre antes del 15 de junio de 2018.

### <a name="current-balance"></a>Saldo actual

El saldo actual es la cantidad de licencia que esté disponible para las solicitudes de tiempo libre. Este importe incluye acumuaciones, solicitudes aprobadas, y ajustes hasta la fecha actual.

### <a name="current-balance-examples"></a>Ejemplos de saldo actual

#### <a name="annual-plan"></a>Plan anual

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 1 de enero de 2019 (1/1/2019), de modo que el período completo esté incluido.

**Resultados**

| Importe de acumulación | Saldo mínimo | Transferencia máxima | Importe solicitado | Saldo actual (el 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 200            | 0               | 120                   | 40             | 160                              |

Saldo actual (160) = importe de acumulación (200) – Importe solicitado (40)

#### <a name="semimonthly-plan"></a>Plan quincenal

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensual       | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 1 de mayo de 2018 (5/1/2018), de modo que el período completo esté incluido.

**Resultados**

| Importe de acumulación | Saldo mínimo | Transferencia máxima | Importe solicitado | Saldo actual (el 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 22                               |

Saldo actual (22) = importe de acumulación (5 x 6) – Importe solicitado (8)

#### <a name="monthly-plan"></a>Plan mensual

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensual       | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 1 de mayo de 2018 (5/1/2018), de modo que el período completo esté incluido.

**Resultados**

| Importe de acumulación | Saldo mínimo | Transferencia máxima | Importe solicitado | Saldo actual (el 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Saldo actual (7) = importe de acumulación (5 x 3) – Importe solicitado (8)

### <a name="forecasted-balance"></a>Saldo previsto

El *saldo previsto* es el importe de licencia que está disponible en una fecha futura. Las acumulaciones y los ajustes de transferencian se pronostican hasta dicha fecha.

Se usa la siguiente fórmula:

Saldo previsto para el lunes = Saldo actuale – solicitudes + acumulaciones – ajuste de transferencia

### <a name="forecasted-balance-examples"></a>Ejemplos previstos de saldo

#### <a name="annual-plan"></a>Plan anual

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 15 de febrero de 2019 (2/15/2019), de modo que el período completo esté incluido.

**Resultados**

| Importe de acumulación | Saldo mínimo | Transferencia máxima | Saldo actual | Saldo previsto (el 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 20             | 0               | 20                    | 40              | 40                                   |

Saldo previsto (40) = Importe acumulación (20) + Saldo actual (40) – ajuste de transferencia (20)

#### <a name="semimonthly-plan"></a>Plan quincenal

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensual       | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 15 de febrero de 2019 (2/15/2019), de modo que el período completo esté incluido.

**Resultados**

| Importe de acumulación | Saldo mínimo | Transferencia máxima | Saldo actual | Saldo previsto (el 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 5              | 0               | 20                    | 40              | 35                                   |

Saldo previsto (35) = Importe acumulación (5 x 3) + Saldo actual (40) – ajuste de transferencia (20)

#### <a name="monthly-plan"></a>Plan mensual

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 2/1/2018        | Bimensual       | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 15 de febrero de 2019 (2/15/2019), de modo que el período completo esté incluido.

**Resultados**

| Importe de acumulación | Saldo mínimo | Transferencia máxima | Saldo actual | Saldo previsto (el 15/2/2019) |
|----------------|-----------------|-----------------------|-----------------|--------------------------------------|
| 10             | 0               | 20                    | 40              | 30                                   |

Saldo previsto (30) = Importe acumulación (10 x 1) + Saldo actual (40) – ajuste de transferencia (20)

### <a name="proration-balance-examples"></a>Ejemplos de prorrateo de saldo

#### <a name="prorated-monthly-plan"></a>Plan mensual prorrateado

**Configuración del plan**

| Fecha inicial del plan | Frecuencia de acumulación | Base del período de acumulación |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensual           | Fecha inicial del plan      |

**Resultados**

| Empleado            | Meses de servicio | Fecha de inscripción | Fecha de inicio | Importe de acumulación | Acumulación de proceso | Saldo |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.53    |

#### <a name="full-accrual-monthly-plan"></a>Plan mensual de acumulación completa

**Configuración del plan**

| Fecha inicial del plan | Frecuencia de acumulación | Base del período de acumulación |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensual           | Fecha inicial del plan      |

**Resultados**

| Empleado            | Meses de servicio | Fecha de inscripción | Fecha de inicio | Importe de acumulación | Acumulación de proceso | Saldo |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 3,00    |

#### <a name="no-accrual-monthly-plan"></a>Sin plan mensual de acumulación

**Configuración del plan**

| Fecha inicial del plan | Frecuencia de acumulación | Base del período de acumulación |
|-----------------|-------------------|----------------------|
| 1/1/2018        | Mensual           | Fecha inicial del plan      |

**Resultados**

| Empleado            | Meses de servicio | Fecha de inscripción | Fecha de inicio | Importe de acumulación | Acumulación de proceso | Saldo |
|---------------------|-------------------|-----------------|------------|----------------|-----------------|---------|
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3,00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1,00           | 9/1/2018        | 2.00    |

