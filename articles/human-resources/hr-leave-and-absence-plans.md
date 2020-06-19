---
title: Crear un plan de permisos y ausencias
description: Crear planes de ausencias en Dynamics 365 Human Resources para diferentes tipos de baja.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 75a70c5784e7032cfebbe58c1d173923a3023507
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428718"
---
# <a name="create-a-leave-and-absence-plan"></a>Crear un plan de permisos y ausencias

Defina planes de permisos y ausencias en Dynamics 365 Human Resources para cada tipo de licencia que ofrezca. Los planes de permisos y ausencias pueden acumularse en diferentes frecuencias, como anualmente, mensualmente o cada dos meses. También puede definir un plan como concesión, donde una sola acumulación se produce en una fecha específica. Por ejemplo, puede crear un plan que conceda vacaciones flotantes anualmente.

Los planes de baja por niveles permiten a los empleados recibir beneficios en función de la cantidad de tiempo que han pasado con una organización. Los planes por niveles permiten la inscripción automática en horas de prestaciones adicionales.

Puede especificar los importes máximos de traspaso o los saldos mínimos para garantizar que los empleados usen solo las horas de prestación que han acumulado.

Por ejemplo, con un plan por niveles, puede otorgar un beneficio de 80 horas de tiempo libre remunerado (PTO) a los nuevos empleados. A continuación, puede conceder 120 horas de 60 meses de servicio.

También puede crear prestaciones de bajas basadas en el puesto, como horas de prestaciones solo para ejecutivos.

## <a name="create-a-leave-plan"></a>Crear un plan de bajas

1. En la página **Permisos y ausencias**, seleccione **Crear nuevo plan**.

2. En **Detalles**, introduzca el **Nombre**, la **Fecha de inicio**, la **Descripción** y el **Tipo de baja** para su plan.

Si la característica **Configure múltiples tipos de permiso para un solo plan de permiso y ausencia** está habilitada, los tipos de permisos se configuran en **Programación de acumulación** en lugar de en **Detalles**. Para cada registro de la tabla de programación de acumulación, puede definir un tipo de licencia.

 > [!IMPORTANT]
   > Después de habilitar esta función, no puede desactivarla.

3. Defina acumulaciones en la pestaña **Acumulaciones**. Las acumulaciones determinan cuándo y con qué frecuencia se le concede tiempo libre a un empleado. En este paso, usted define directivas acerca de cuándo se deben otorgar acumulaciones y directivas acerca del prorrateo de las prestaciones de bajas.

   1. Seleccione un valor en el cuadro desplegable **Frecuencia de acumulación**:

      - Diario
      - Semanalmente
      - Quincenal
      - Bimensual
      - Mensualmente
      - Trimestral
      - Semestral
      - Anual
      - Ninguno

   2. Seleccione una opción en el cuadro desplegable **Base del período de acumulación** para determinar la fecha de inicio que se usa para calcular períodos de acumulación:

      | Base del período de acumulación | Descripción |
      | --- | --- |
      | **Fecha inicial de plan** | La fecha de inicio del período de acumulación es la fecha en que el plan está disponible. |
      | **Fecha específica del empleado** | La fecha de inicio del período de acumulación depende de un evento del empleado:</br><ul><li>Personalizado (debe especificar una base de fecha de acumulación para cada inscripción individual)</li><li>Fecha de aniversario</li><li>Fecha de contratación original</li><li>Antigüedad</li><li>Fecha inicial ajustada del trabajador</li><li>Primer día de trabajo del trabajador</li></ul> |

   3. Seleccione una opción en el cuadro desplegable **Fecha de prima de acumulación**:

      - **Fecha final del período de acumulación**: al empleado se le concede tiempo libre en el último día del período de prima. Para acumular el importe correcto, el proceso de acumulación debe incluir todo el período. Por ejemplo, si el período de acumulación es del 1 de enero de 2020 al 31 de enero de 2020, debe ejecutar la acumulación para el 1 de febrero de 2020 para incluir enero.

      - **Fecha inicial del período de acumulación**: al empleado se le concede tiempo libre en el primer día del período de prima.

   4. Seleccione una opción en el cuadro desplegable **Directiva de acumulación en la inscripción**. Este valor define cómo calcular la acumulación cuando un empleado se inscribe en medio de un período de acumulación.

      - **Prorrateado**: el intervalo de fechas entre la fecha de inscripción y la fecha inicial se usa para determinar la diferencia en días. Se aplica esa diferencia cuando se procesan las acumulaciones.

      - **Acumulación completa**: el importe de acumulación completo, en función del nivel, se concede durante el primer procesamiento de la acumulación.

      - **Ninguna acumulación**: no se otorga ninguna acumulación hasta el período de acumulación siguiente.

   5. Seleccione una opción en el cuadro desplegable **Directiva de acumulación para la anulación de la inscripción**. Este valor define cómo calcular la acumulación cuando un empleado anula la inscripción en medio de un período de acumulación.

      - **Prorrateado** El intervalo de fechas entre la fecha de inscripción y la fecha inicial se usa para determinar la diferencia en días. Se aplica esa diferencia cuando se procesan las acumulaciones.

      - **Acumulación completa** El importe de acumulación completo, en función del nivel, se concede durante el primer procesamiento de la acumulación.

      - **Ninguna acumulación** No se otorga ninguna acumulación hasta el período de acumulación siguiente.

4. Defina la programación de acumulación en la pestaña **Programación de la acumulación**. La programación de acumulación determina:

   - Cómo un empleado acumula tiempo libre
   - Qué importes acumulará el empleado
   - Qué importes se transferirán

   Puede crear niveles para conceder el tiempo libre basándose en diferentes niveles.

   Si tiene empleados por horas, puede conceder tiempo libre en función de las horas trabajadas en lugar de ocupación en su organización. Las datos de las horas trabajadas se almacenan normalmente en un sistema de asistencia y tiempo. Puede importar las horas regulares y extras trabajadas desde el sistema de tiempo y asistencia y utilizarlas como base para la prima de un empleado.
   
    1. Seleccione una opción en el cuadro desplegable **Tipo de acumulación**:

      - **Meses de servicio**: base de la programación de acumulación en meses de servicio.

      - **Horas trabajadas**: base de la programación de acumulación en horas trabajadas. Para obtener más información sobre las acumulaciones por horas trabajadas, consulte [Acumular permiso en función de las horas trabajadas](hr-leave-and-absence-plans.md?accrue-time-off-based-on-hours-worked).

      Para obtener más información acerca de los saldos de acumulación, consulte [Acumular permiso en función de las horas trabajadas](hr-leave-and-absence-plans.md?enrollments-and-balances).

    2. Introduzca valores en la tabla de programación de acumulación:

      - **Meses de servicio**: el número mínimo de meses que los empleados deben trabajar para ser autorizados a tener acumulaciones. Si no requiere un mínimo, establezca el valor en 0.

      - **Horas trabajadas**: el número mínimo de horas que los empleados deben trabajar por período de acumulaciones para ser autorizados a tener acumulaciones. Si no requiere un mínimo, establezca el valor en 0.

      - **Importe de acumulación**: el número de horas o de días que los empleados acumulan por período. El período se basa en la frecuencia de acumulación.

      - **Saldo negativo**: puede usar un valor negativo para el saldo mínimo si los empleados pueden solicitar más bajas de las que tienen disponibles.

      - **Transferencia máxima**: el proceso de acumulación ajusta los saldos de licencia que superen el saldo máximo transferible en el aniversario de la fecha de inicio.

      - **Importe de la concesión**: el número inicial de horas o días que se concede a los empleados cuando se inscriben por primera vez en el plan de baja. El importe no se acumula para cada período de acumulación.
      
Si la característica **Configure múltiples tipos de permiso para un solo plan de permiso y ausencia** está habilitada, seleccione una opción en **Tipo de permiso**. 

   > [!IMPORTANT]
   > Después de habilitar esta función, no puede desactivarla.

Si la característica **Usar equivalencia de jornada completa**, Human Resources utiliza la equivalencia de jornada completa (FTE) definida para el puesto para prorratear la acumulación de un empleado. Por ejemplo, si la FTE es 0,5 y la cantidad acumulada es 10, el empleado acumulará 5. Solo puede usar esta característica si habilita varios tipos de baja.  

5. Seleccione **Guardar**.

## <a name="accrue-time-off-based-on-hours-worked"></a>Acumular permiso en función de las horas trabajadas

Si tiene empleados por horas, puede conceder tiempo libre en función de las horas trabajadas en lugar de ocupación en su organización. Los datos de las horas trabajadas se almacenan normalmente en un sistema de asistencia y tiempo. Puede importar las horas regulares y extras trabajadas desde el sistema de tiempo y asistencia y utilizarlas como base para la prima de un empleado.

Cuando seleccione las horas trabajadas como el tipo de acumulación, puede usar dos tipos de horas para la acumulación: regulares y horas extra. El procesamiento de la acumulación de los planes de horas trabajadas usa la frecuencia de acumulación, junto con la base del período de acumulación para determinar las horas que se acumularán.

### <a name="annual-accrual-frequency"></a>Frecuencia de acumulación anual

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2085                | 144                 |        
| 12/31/2018            | 2080                 | 144                   | 1/1/2018-31/12/2018  | 2000                | 0                 |


### <a name="monthly-accrual-frequency"></a>Frecuencia de acumulación mensual

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 160                  | 12                    | 1/8/2018-31/8/2018   | 184                 | 12                  |        
| 8/31/2018             | 160                  | 3                     | 1/8/2018-31/8/2018   | 184                 | 3                   |

### <a name="semi-monthly-accrual-frequency"></a>Frecuencia de acumulación semimensual

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 81                  | 6                  |        
| 8/31/2018             | 80                   | 6                     | 16/8/2018-31/8/2018  | 75                  | 0                   |

### <a name="weekly-accrual-frequency"></a>Frecuencia de acumulación semanal

| Fecha de asignación de acumulación    | Nivel de horas trabajadas    | Importe de acumulación        | Fechas de horas trabajadas   | Datos reales de horas trabajadas| Prima               |
| --------------------- | -------------------- | --------------------- | -------------------- |-------------------- |-------------------- |
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 42                  | 3                  |        
| 8/31/2018             | 40                   | 3                     | 27/8/2018-31/8/2018  | 35                  | 0                   |

### <a name="employee-assigned-leave-plans"></a>Planes de licencias asignados al empleado

En los planes de la licencia asignados del empleado, se muestran la base del nivel y el tipo de horas para los planes de horas trabajadas. Las horas reales trabajadas para los períodos de acumulación a partir de la fecha actual también se muestran para los planes activos.

### <a name="loading-data"></a>Cargando datos

Puede importar las horas reales usando la entidad **Horas de ausencia y baja trabajadas** en la administración de datos. Si utiliza calendarios de horario de trabajo, la importación valida que las horas normales trabajadas no superen las horas programadas en un día definidas mediante el calendario. La importación también comprueba que las horas trabajadas de un día determinado no superen 24 horas. 

Necesita la siguiente información para importar las horas reales que se utilizarán en el proceso de acumulación de licencia:

- Número de personal 
- Fecha trabajada
- Tipo
- Horas

Una única fecha solo puede tener uno de cada tipo asociada a ella.

| Número de personal       | Fecha trabajada           | Tipo                  | Horas                |
| --------------------- | -------------------- | --------------------- | -------------------- |
| 000337                | 8/6/2018             | Normal               | 8                    |       
| 000337                | 8/7/2018             | Normal               | 8                    |
| 000337                | 8/7/2018             | Horas extra              | 3                    |
| 000337                | 8/8/2018             | Normal               | 8                    |
| 000337                | 8/7/2018             | Normal               | 8                    |
| 000337                | 8/9/2018             | Normal               | 8                    |

## <a name="enrollments-and-balances"></a>Inscripciones y saldos

### <a name="enrollment-date"></a>Fecha de inscripción

La fecha de inscripción determina cuándo un empleado puede comenzar a acumular tiempo libre. Por ejemplo, un empleado inscrito en un plan de vacaciones el 15 de junio de 2018, no puede acumular tiempo libre antes del 15 de junio de 2018.

### <a name="current-balance"></a>Saldo actual

El saldo actual es la cantidad de licencia que esté disponible para las solicitudes de tiempo libre. Este importe incluye acumuaciones, solicitudes aprobadas, y ajustes hasta la fecha actual.

### <a name="current-balance-examples"></a>Ejemplos de saldo actual

#### <a name="annual-plan"></a>Plan anual

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 1 de enero de 2019 (1/1/2019), para incluir el período completo.

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

Las acumulaciones se procesan el 1 de mayo de 2018 (5/1/2018), para incluir el período completo.

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

Las acumulaciones se procesan el 1 de mayo de 2018 (5/1/2018), para incluir el período completo.

**Resultados**

| Importe de acumulación | Saldo mínimo | Transferencia máxima | Importe solicitado | Saldo actual (el 1/1/2019) |
|----------------|-----------------|-----------------------|----------------|----------------------------------|
| 5              | 0               | 120                   | 8              | 7                                |

Saldo actual (7) = importe de acumulación (5 x 3) – Importe solicitado (8)

### <a name="forecasted-balance"></a>Saldo previsto

El *saldo previsto* es el importe de licencia que está disponible en una fecha futura. Las acumulaciones y los ajustes de transferencian se pronostican hasta dicha fecha.

Recursos humanos utiliza la siguiente fórmula:

Saldo previsto para el lunes = Saldo actuale – solicitudes + acumulaciones – ajuste de transferencia

### <a name="forecasted-balance-examples"></a>Ejemplos previstos de saldo

#### <a name="annual-plan"></a>Plan anual

**Configuración del plan**

| Fecha inicial del plan | Fecha de inscripción | Frecuencia de acumulación | Base del período de acumulación | Fecha de prima de acumulación    |
|-----------------|-----------------|-------------------|----------------------|-----------------------|
| 1/1/2018        | 1/1/2018        | Anual            | Fecha inicial del plan      | Fin del período de acumulación |

Las acumulaciones se procesan el 15 de febrero de 2019 (2/15/2019), para incluir el período completo.

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

Las acumulaciones se procesan el 15 de febrero de 2019 (2/15/2019), para incluir el período completo.

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

Las acumulaciones se procesan el 15 de febrero de 2019 (2/15/2019), para incluir el período completo.

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
| Jeannette Nicholson | 0,00              | 6/1/2018        | 6/1/2018   | 1,00           | 9/1/2018        | 3.00    |
| Jay Norman          | 0,00              | 6/15/2018       | 6/15/2018  | 1.00           | 9/1/2018        | 2.00    |

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Configurar tipos de permisos y ausencias](hr-leave-and-absence-types.md)
- [Acumular planes de permisos y ausencias](hr-leave-and-absence-accrue.md)
