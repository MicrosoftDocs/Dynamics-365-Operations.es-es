---
title: Paga basada en los registros
description: Este tema explica cómo se calcula el sueldo en función de los registros del trabajador.
author: johanhoffmann
ms.date: 03/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgCalcApproveWeekView, JmgProdStatusListPagePayrollCostDetails, JmgPayCountTable, JmgPayStatConfig, JmgOvertimeSlize, JmgPayAgreementOverride, JmgPayCountSum, JmgPayAdjustSetup, JmgPayAdjustCostType, JmgPayEmployee, JmgMESBreak, JmgPayAddTable, JmgPayAddTransSelectTransId, JmgPayrollCostDetailsPart, jmgProdStatusListPagePayrollCosts, JmgPayrollCostPart, JmgPayEvents, JmgTermRegPayStatSetup, JmgPayStatGroup, JmgPayAddTrans, JmgPayStatTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-03-20
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 58ff2629c2894e85ca5529df5f995ffa5273de67e1c22564f5f9911ea86fbd95
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6715731"
---
# <a name="pay-based-on-registrations"></a>Paga basada en los registros

[!include [banner](../includes/banner.md)]

Este tema explica en detalle cómo se calcula el sueldo en función de los registros del trabajador. Incluye los ejemplos que muestran cómo las diferentes combinaciones de opciones de configuración que están disponibles para el cálculo afectan al resultado. Estas son algunas de las áreas que se cubrirán:

- Horario flexible
- Horas extra
- Descansos
- Códigos de cambio
- Detalles del sueldo
- Acuerdos de sueldo
- Parámetros de cálculo de Tiempo y asistencia
- Ausencia

## <a name="the-use-of-flex-time"></a>El uso del tiempo flexible

Los períodos de tiempo flexible se configuran en los perfiles de tiempo que se utilizan en tiempo y asistencia. Existen dos tipos de perfil flexible: **Horario flexible+** y **Horario flexible-**. Cuando un trabajador registra tiempo en un período de Horario flexible+, el saldo de horario flexible del trabajador se incrementa en función de las horas que se trabajaron. El trabajador no recibe ninguna compensación por las horas que se trabajaron durante el período flexible+. Sin embargo, el trabajador puede disfrutar de tiempo libre durante períodos de horario flexible- y ser compensado con horas de su saldo de horario flexible. Por lo tanto, el sistema considera el tiempo libre durante los períodos de horario flexible como una ausencia.

## <a name="scenarios-based-on-flex-periods"></a>Situaciones basadas en períodos de horario flexible

Las dos situaciones que siguen se basan en un perfil flexible que represente un día laborable. Para las dos situaciones, el pago se calcula en función del período de horario flexible en el que el trabajador entra y sale.

### <a name="flex-profile-for-one-workday"></a>Perfil flexible para un día laborable

| Tipo de perfil  | Inicio    | Fin      | Día     |
|---------------|----------|----------|---------|
| Horas extra     | 00:00 a. m. | 06:00 a. m. | Lunes  |
| Horario flexible+         | 06:00 a. m. | 07:00 a. m. | Lunes  |
| Hora de entrada      | 07:00 a. m. | 07:00 a. m. | Lunes  |
| Hora estándar | 07:00 a. m. | 02:30 p. m. | Lunes  |
| Horario flexible-         | 02:30 p. m. | 03:30 p. m. | Lunes  |
| Hora de salida     | 03:30 p. m. | 03:30 p. m. | Lunes  |
| Horas extra     | 03:30 p. m. | 06:00 a. m. | Martes |

### <a name="scenario-1-a-worker-registers-clock-in-during-a-flex-period-and-clock-out-during-a-flex--period"></a>Escenario 1: Un trabajador registra la hora de entrada durante un período de Horario flexible+ y registra la hora de salida durante un período de horario flexible-

Los registros del trabajador para el día se parecen a esto.

| Tipo de registro de diario | Inicio    | Fin      |
|---------------------------|----------|----------|
| Hora de entrada                  | 06:30 a. m. | 06:30 a. m. |
| Trabajo de producción            | 06:30 a. m. | 02:45 p. m. |
| Hora de salida                 | 02:45 p. m. | 02:45 p. m. |

Los registros del trabajador para el día se calculan y se transfieren para liquidar en la página **aprobar** (**Tiempo y asistencia** &gt; **Revisar y aprobar** &gt; **aprobar**). Después de que se hayan calculado los registros, el resultado del cálculo se puede ver en la pestaña **Tiempos**. 

Para comprender esta situación, vea los campos siguientes.

| Horario flexible + | Horario flexible - | Hora | Tiempo salarial |
|--------|--------|------|----------|
| 0,50   | 0.75   | 8.25 | 8.50     |

#### <a name="calculation-of-flex"></a>Cálculo del horario flexible+.

De acuerdo con el perfil flexible, el tiempo entre las 06:00 a. m. y las 07:00 a. m. es un período de horario flexible+. Por lo tanto, si el trabajador entra a las 06:30, obtiene 0,5 horas. Esta cantidad de tiempo se agrega a la cuenta de horario flexible del trabajador.

#### <a name="calculation-of-flex-"></a>Cálculo del horario flexible-

De acuerdo con el perfil flexible, el período de horario flexible comienza a las 02:30 p. m. y finaliza las 03:30 p. m. Por lo tanto, si el trabajador registra la hora de salida a las 02:45 P.M., los 45 minutos (0.75 horas) que permanecen en el período de horario flexible- se registran como tiempo salarial, y la misma cantidad de tiempo se deduce de la cuenta de horario flexible del trabajador. Los 45 minutos se incluyen en tiempo salarial porque se le concederá al trabajador un sueldo para los 45 minutos restantes en el período de horarios flexibles. Si el trabajador está ausente durante el período de horario flexible-, los 45 minutos se deducirán de su cuenta de horario flexible.

#### <a name="calculation-of-time"></a>Cálculo del tiempo

El tiempo se calcula como el tiempo entre la hora de entrada y la hora de salida, es decir, de 06:30 AM a las 14:45 P.M., lo que da 8.25 horas.

#### <a name="calculation-of-pay-time"></a>Cálculo del tiempo salarial

El tiempo salarial es el tiempo por el que se concede a un trabajador un sueldo. En este escenario, el trabajador está en el trabajo durante 8.25 horas (**Tiempo**). Sin embargo, **Tiempo salarial** se calcula como 8,50 horas porque el trabajador recibe paga durante el período de horario flexible- después de que registrara la salida. El tiempo salarial es igual a las horas laborables planificadas porque el tiempo de horario flexible+ se agrega a la cuenta de horario flexible del trabajador, no al tiempo salarial. El tiempo de ausencia durante el período de horario flexible se compensa con el tiempo salarial y se deduce de la cuenta de horario flexible del trabajador.

| Hora              | Tipo de registro | Tiempo salarial (horas)      |
|-------------------|-------------------|-----------------------|
| 6:30 a. m. - 7:00 a. m. | Horario flexible+             | 0                     |
| 7:00 a. m. – 2:45 p. m. | Hora estándar     | 7.75                  |
| 2:45 p. m. – 3:30 p. m. | Horario flexible-             | 0,75 (período de ausencia) |
|                   | Total             | 8.50                  |

### <a name="scenario-2-a-worker-works-during-the-whole-flex--period-and-also-works-overtime"></a>Escenario 2: Un trabajador trabaja durante el período de horario flexible completo y también realiza horas extra

Los registros del trabajador para el día se parecen a esto.

| Tipo de registro de diario | Inicio    | Fin      |
|---------------------------|----------|----------|
| Hora de entrada                  | 06:30 a. m. | 06:30 a. m. |
| Trabajo de producción            | 06:30 a. m. | 05:00 p. m. |
| Hora de salida                 | 05:00 p. m. | 05:00 p. m. |

Una vez que haya calculado los registros de diario en la página **Aprobar**, puede ver el resultado del cálculo en la pestaña **Tiempos**. Para comprender esta situación, vea los campos siguientes.

| Horario flexible + | Horario flexible - | Hora  | Tiempo salarial | Horas extra de sueldo |
|--------|--------|-------|----------|--------------|
| 0,50   | 0,00   | 10,50 | 10,00    | 1.50         |

#### <a name="calculation-of-flex"></a>Cálculo del horario flexible+.

De acuerdo con el perfil flexible, el tiempo entre las 06:00 a. m. y las 07:00 a. m. es un período de horario flexible+. Por lo tanto, si la trabajadora entra a las 06:30, gana 0,5 horas de tiempo de horario flexible+ en su saldo de horario flexible.

#### <a name="calculation-of-flex-"></a>Cálculo del horario flexible-

Dado que el trabajador trabaja durante el período de horario flexible, el horario flexible no se calcula. El horario flexible solo se calcula si el trabajador se ausenta durante el período de horario flexible-. Desde una perspectiva de pago, si el trabajador trabaja durante el período de horario flexible-, se le concede el índice salarial que se define para el tiempo estándar. Si el trabajador está ausente durante el período de horario flexible-, los 45 minutos se deducen de su cuenta de horario flexible.

#### <a name="calculation-of-time"></a>Cálculo del tiempo

El tiempo se calcula como el tiempo entre la hora de entrada a las 06:30 AM y la hora de salida a las 05:00 P.M., lo que da 10.50 horas.

#### <a name="calculation-of-pay-time"></a>Cálculo del tiempo salarial

En este escenario, el trabajador trabaja durante 10.50 horas (**Tiempo**). Sin embargo, **Tiempo salarial** se calcula como 10,00 horas porque el trabajador no recibe paga durante el período de horario flexible+.

#### <a name="calculation-of-pay-overtime"></a>Cálculo del sueldo de horas extra

| Hora               | Tipo de registro | Tiempo salarial (horas) |
|--------------------|-------------------|------------------|
| 6:30 a. m. - 7:00 a. m.  | Horario flexible+             | 0                |
| 7:00 a. m. – 2:30 p. m.  | Hora estándar     | 7.50             |
| 2:30 p. m. – 3:30 p. m.  | Horario flexible-             | 1,00             |
| 3:30 p. m. – 05:00 p. m. | Horas extra          | 1.50             |
|                    | Total             | 10,00            |

### <a name="generation-of-pay-items"></a>Generación de artículos de sueldo

Los registros del trabajador para el día se pueden transferir desde la página **aprobar** . Durante el proceso de tranferencia, se generan los elementos de pago y los registros transferidos. Los detalles del sueldo representan un desglose del tiempo salarial en tiempo estándar, horas extra, tiempo de descanso pagado, y así sucesivamente.

Para abrir la lista de elementos de sueldo, seleccione **Tiempo y asistencia** &gt; **Revisar y aprobar** &gt; **aprobar**. A continuación seleccione **Consulta** &gt; **Registros transferidos**.

Los elementos de pago son la base del sueldo del trabajador. Puede generar un archivo que incluya la información de los elementos del sueldo y transferir dicho archivo a un sistema de nóminas.

Como parte del proceso de transferencia, el tiempo y el coste de la producción y las actividades de proyecto se transfieren a los diarios de producción y de proyecto para contabilizar el tiempo y de coste del gasto. Los registros transferidos constituyen la base para la hora y el precio de coste por hora de los pedidos de producción y los proyectos. Puede abrir los registros transferidos mediante el menú **Consulta** en la página **aprobar** .

Por ejemplo, para el escenario 2, se generan los siguientes elementos de sueldo.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice  | Coste total |
|---------------|----------|-----------|-------|------------|
| Hora estándar | 1201     | 10.0      | 10    | 100        |
| Horas extra      | 1301     | 1.50      | 5     | 7.50       |
|               |          |           | Total | 107.50     |

El elemento de pago para el tiempo estándar tiene una unidad de sueldo de 10 horas que cubre el tiempo estándar, el tiempo flexible, y las horas extra. El tiempo estándar, el tiempo flexible, y las horas extras se consolidan en un solo elemento de pago ya que todos los tipos se calculan como horario estándar, en función de la configuración predeterminada de un parámetro en la página **Parámetros de cálculo** (**Tiempo y asistencia** &gt; **Configuración** &gt; **Parámetros de cálculo**). Las horas extra se calculan en adición del tiempo estándar utilizando un índice adicional de 5.

Si desea distinguir claramente el tiempo estándar y las horas extra, para que las las unidades de sueldo para los tipos de sueldo cubran solo el tiempo real dedicado en tiempo estándar y horas extra, las unidades de sueldo para el tiempo estándar deben calcularse como 8.50, y las unidades de sueldo para las horas extra se deben calcular como 1.50.

Para configurar el sistema para distinguir claramente el tiempo estándar y las horas extra, debe excluir las horas extra del tiempo estándar. También debe cambiar la configuración del tipo de sueldo para las horas extra de modo que la tasa de pago para las horas extra cubra todos los pagos de las horas que se emplearon en horas extra.

### <a name="exclude-overtime-from-the-standard-time"></a>Excluir horas extra del tiempo estándar

En la página **Parámetros de cálculo**, seleccione **Horas extra** como el tipo de especificación de perfil y establezca la opción **Tiempo salarial** en **No**, como se muestra aquí.

| Especificación del registro | Tipo de especificación de perfil | Cálculo   | Configuración | Pagado         | Configuración |
|--------------------|----------------------------|---------------|-----|--------------|-----|
| Horario de trabajo       | Horas extra                   | Hora estándar | Sí | Tiempo salarial     | N.º  |
|                    |                            | Tiempo salarial      | Sí | Horas extra de sueldo | Sí |

Después de ajustar los parámetros de cálculo, se generan los siguientes elementos de sueldo.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice  | Coste total |
|---------------|----------|-----------|-------|------------|
| Hora estándar | 1201     | 8.50      | 10    | 85.0       |
| Horas extra      | 1301     | 1.50      | 15    | 22.50      |
|               |          |           | Total | 107.50     |

> [!NOTE]
> Los parámetros de cálculo tienen una configuración estándar recomendada. Normalmente debe tener cuidado al modificar estos parámetros. Para restablecer la configuración estándar recomendada, en la página **Parámetros de cálculo**, seleccione **Restaurar valores**.

### <a name="allow-a-deviation-from-the-standard-pay-profiles"></a>Permitir una desviación de los perfiles de pago estándar

En la página **Perfiles** (**Tiempo y asistencia** &gt; **Configuración** &gt; **Perfiles de tiempo** &gt; **Perfiles**), puede configurar tipos de perfil que contengan códigos de cambio y descansos.

### <a name="switch-codes"></a>Códigos de cambio

Puede usar códigos de cambio para permitir que los trabajadores se desvíen del tipo de perfil cambiando a otro tipo de perfil. Por ejemplo, puede permitir que un trabajador cambie el tiempo de horario flexible+ a horas extra. Un trabajador puede agregar un código de cambio durante el registro o bien asignar la tarea de agregar un código de cambio al aprobador de los registros.

Para que un código de cambio se pueda usar, debe definirlo como tipo de actividad indirecta. Después debe agregar el código de cambio al perfil de tiempo para el período en el que desea permitir un cambio de tipo de perfil. Por ejemplo, siga estos pasos para crear un código de cambio que permita que el período de horario flexible+ se cambie desde las 06:00 a. m. a 07:00 a. m. a horas extra.

1. Crear un código de cambio que se llame **OTBCI (convertir periodo flexible a horas extra antes de la hora de entrada)**. Seleccione **Tiempo y asistencia** &gt; **Gestionar actividades indirectas** &gt; **Actividades indirectas**.
2. En la columna **Cambiar el código**, agregue OTBCI a la línea de Horario flexible+ en el perfil del tiempo.
3. En la columna **Secundario**, agregue el tipo de perfil **Horas extra**.

Considere el siguiente perfil flexible que representa un día laborable.

| Tipo de perfil  | Inicio    | Fin      | Día     |
|---------------|----------|----------|---------|
| Horas extra     | 00:00 a. m. | 06:00 a. m. | Lunes  |
| Horario flexible+         | 06:00 a. m. | 07:00 a. m. | Lunes  |
| Hora de entrada      | 07:00 a. m. | 07:00 a. m. | Lunes  |
| Hora estándar | 07:00 a. m. | 02:30 p. m. | Lunes  |
| Horario flexible-         | 02:30 p. m. | 03:30 p. m. | Lunes  |
| Hora de salida     | 03:30 p. m. | 03:30 p. m. | Lunes  |
| Horas extra     | 03:30 p. m. | 06:00 a. m. | Martes |

Estos son los registros del trabajador para el día.

| Tipo de registro de diario | Inicio    | Fin      |
|---------------------------|----------|----------|
| Hora de entrada                  | 06:30 a. m. | 06:30 a. m. |
| Trabajo de producción            | 06:30 a. m. | 02:45 p. m. |
| Hora de salida                 | 05:00 p. m. | 05:00 p. m. |

Los siguientes elementos de sueldo se generan después de la transferencia.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice  | Coste total |
|---------------|----------|-----------|-------|------------|
| Hora estándar | 1201     | 8.50      | 10    | 85.0       |
| Horas extra      | 1305     | 1.50      | 15    | 22.50      |
|               |          |           | Total | 107.50     |

En la página **aprobar**, desmarque la transferencia, y use el menú **Cambiar el código** para aplicar el código de cambio **OTBCI**. Cuando transfiere los registros una segunda vez, se generan los siguientes elementos de sueldo.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice  | Coste total |
|---------------|----------|-----------|-------|------------|
| Hora estándar | 1201     | 8.50      | 10    | 80.0       |
| Horas extra      | 1305     | 2.00      | 15    | 30.0       |
|               |          |           | Total | 107.50     |

> [!NOTE]
> Al aplicar el código de turno, se aumentan las horas extra en 0.5 horas, de 1.50 a 2.00. Las 0.5 horas son la conversión del tiempo de horario flexible+ registrado, desde las 6:30 a las 07:00 en horas extra.

### <a name="breaks"></a>Descansos

Los descansos de trabajo afectan al cálculo del sueldo del trabajador. Los descansos se definen como tipo de actividad indirecta. Pueden definirse como **Pagado**, para permitir que el descanso se agregue al sueldo del trabajador, o **Sin pagar** para evitar que el descanso se agregue al sueldo del trabajador. Un descanso también se puede definir como **Planificado** o **Registrado**.

#### <a name="planned-breaks"></a>Descansos planificados

Si una empresa tiene un tiempo de descanso fijo, como un descanso fijo para el almuerzo, el descanso se puede predefinir en el perfil de tiempo. En este caso, el trabajador no tiene que registrar el descanso en las páginas de la tarjeta de trabajo. En su lugar, el descanso se tiene en cuenta automáticamente cuando se calculan los registros del trabajador en la página **aprobar** .

#### <a name="registered-breaks"></a>Descansos registrados

Si una empresa no usa descansos planificados, los trabajadores pueden registrar descansos durante la jornada laboral. Los descansos registrados se pueden utilizar, por ejemplo, si un trabajador está trabajando con un perfil de tiempo flexible que no tenga definidos horarios de registro de entrada y de salida. Los descansos registrados son un tipo de actividad indirecta. El trabajador registra el descanso en la página de terminal **Tarjeta de trabajo** o en la página de dispositivo **Tarjeta de trabajo** . En estas dos páginas, el usuario puede seleccionar el tipo de descanso en una lista de actividades de descanso predefinidas.

#### <a name="paid-and-unpaid-breaks"></a>Descansos pagados y no pagados

Las actividades de descanso se pueden configurar como **Pagado** o **Sin pagar**. Una descanso pagado se incluye en el cálculo del tiempo salarial y el sistema utiliza el tipo de sueldo que se define en el acuerdo de pago para el tipo de registro **Descanso**.

### <a name="example-of-a-planned-break"></a>Ejemplo de un descanso planificado

Considere el siguiente perfil de tiempo que incluya descansos para comer no remunerados.

| Tipo de perfil  | Inicio    | Fin      | Día     |
|---------------|----------|----------|---------|
| Horas extra     | 00:00 a. m. | 06:00 a. m. | Lunes  |
| Horario flexible+         | 06:00 a. m. | 07:00 a. m. | Lunes  |
| Hora de entrada      | 07:00 a. m. | 07:00 a. m. | Lunes  |
| Hora estándar | 07:00 a. m. | 12:00 p. m. | Lunes  |
| Descanso         | 12:00 p. m. | 12:30 p. m. | Lunes  |
| Hora estándar | 12:30 p. m. | 02:30 p. m. | Lunes  |
| Horario flexible-         | 02:30 p. m. | 03:30 p. m. | Lunes  |
| Hora de salida     | 03:30 p. m. | 03:30 p. m. | Lunes  |
| Horas extra     | 03:30 p. m. | 06:00 a. m. | Martes |

Estos son los registros del trabajador para el día.

| Tipo de registro de diario | Inicio    | Fin      |
|---------------------------|----------|----------|
| Hora de entrada                  | 06:30 a. m. | 06:30 a. m. |
| Trabajo de producción            | 06:30 a. m. | 02:45 p. m. |
| Hora de salida                 | 05:00 p. m. | 05:00 p. m. |

Una vez que haya calculado los registros de diario en la página **Aprobar**, puede ver el resultado del cálculo en la pestaña **Tiempos**. Para comprender esta situación, vea los campos siguientes.

| Horario flexible + | Horario flexible - | Hora  | Tiempo salarial | Tiempo de descanso no pagado | Horas extra de sueldo |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9.50     | 0.5                 | 1.50         |

> [!NOTE] 
> El sistema calculó 0.5 horas de tiempo de descanso sin pagar, y ese tiempo no forma parte del tiempo salarial.

### <a name="example-of-a-registered-break"></a>Ejemplo de un descanso registrado

Considere el siguiente perfil de tiempo que no incluya descansos planificados.

| Tipo de perfil  | Inicio    | Fin      | Día     |
|---------------|----------|----------|---------|
| Horas extra     | 00:00 a. m. | 06:00 a. m. | Lunes  |
| Horario flexible+         | 06:00 a. m. | 07:00 a. m. | Lunes  |
| Hora de entrada      | 07:00 a. m. | 07:00 a. m. | Lunes  |
| Hora estándar | 07:00 a. m. | 02:30 p. m. | Lunes  |
| Horario flexible-         | 02:30 p. m. | 03:30 p. m. | Lunes  |
| Hora de salida     | 03:30 p. m. | 03:30 p. m. | Lunes  |
| Horas extra     | 03:30 p. m. | 06:00 a. m. | Martes |

Estos son los registros del trabajador para el día.

| Tipo de registro de diario | Inicio    | Fin      |
|---------------------------|----------|----------|
| Hora de entrada                  | 06:30 a. m. | 06:30 a. m. |
| Trabajo de producción            | 06:30 a. m. | 05:00 p. m. |
| Descanso                     | 12:03 p. m. | 12:32 p. m. |
| Hora de salida                 | 05:00 p. m. | 05:00 p. m. |

Cuando se calculan los registros, el tiempo de las actividades se calcula.

| Tipo de registro de diario | Inicio    | Fin      | Hora  |
|---------------------------|----------|----------|-------|
| Hora de entrada                  | 06:30 a. m. | 06:30 a. m. |       |
| Trabajo de producción            | 06:30 a. m. | 05:00 p. m. | 10,00 |
| Descanso                     | 12:03 p. m. | 12:32 p. m. | 0,50  |
| Hora de salida                 | 05:00 p. m. | 05:00 p. m. |       |

> [!NOTE]
> La hora para el descanso se ejecuta en paralelo con la hora de la actividad (un trabajo de producción, en este ejemplo). Este comportamiento siempre se usa para las actividades de descanso. Cuando se calculan los registros, el tiempo de descanso se resta del tiempo de actividad. En este caso, el trabajo de producción tiene una duración de 10.50 horas, pero el tiempo se calcula como 10 porque 0.5 horas de tiempo de descanso se sustraen del tiempo de actividad.

Una vez que haya calculado los registros de diario en la página **Aprobar**, puede ver el resultado del cálculo en la pestaña **Tiempos**. Para comprender esta situación, vea los campos siguientes.

| Horario flexible + | Horario flexible - | Hora  | Tiempo salarial | Tiempo de descanso no pagado | Horas extra de sueldo |
|--------|--------|-------|----------|---------------------|--------------|
| 0,50   | 0,00   | 10,50 | 9.50     | 0.5                 | 1.50         |

Si el descanso planificado se hubiera pagado en lugar de no pagado, el resultado del cálculo se parecería este.

| Horario flexible + | Horario flexible - | Hora  | Tiempo salarial | Tiempo de descanso pagado | Horas extra de sueldo |
|--------|--------|-------|----------|-----------------|--------------|
| 0,50   | 0,00   | 10,50 | 10,00    | 0.5             | 1.50         |

### <a name="pay-items-and-paid-breaks"></a>Detalles del sueldo y descansos remunerados

Al transferir registros en la página **aprobar**, se generan los detalles del sueldo. Se genera un artículo de sueldo por separado para los descansos pagados.

La tasa de pago para un descanso pagado se determina en función del tipo de sueldo que se configura en los acuerdos de sueldo para el descanso. En lugar de usar un tipo de sueldo, puede configurar el precio de coste por hora en la interrupción para un intervalo de fechas definido.

Considere el siguiente perfil de tiempo.

| Tipo de perfil  | Inicio    | Fin      | Día     |
|---------------|----------|----------|---------|
| Horas extra     | 00:00 a. m. | 06:00 a. m. | Lunes  |
| Horario flexible+         | 06:00 a. m. | 07:00 a. m. | Lunes  |
| Hora de entrada      | 07:00 a. m. | 07:00 a. m. | Lunes  |
| Hora estándar | 07:00 a. m. | 02:30 p. m. | Lunes  |
| Horario flexible-         | 02:30 p. m. | 03:30 p. m. | Lunes  |
| Hora de salida     | 03:30 p. m. | 03:30 p. m. | Lunes  |
| Horas extra     | 03:30 p. m. | 06:00 a. m. | Martes |

Estos son los registros del trabajador para el día.

| Tipo de registro de diario | Inicio    | Fin      | Hora |
|---------------------------|----------|----------|------|
| Hora de entrada                  | 07:00 a. m. | 07:00 a. m. |      |
| Trabajo de producción            | 07:00 a. m. | 03:00 p. m. | 7.5  |
| Descanso (pagado)              | 12:00 p. m. | 12:30 p. m. | 0.5  |
| Hora de salida                 | 03:00 p. m. | 03:00 p. m. |      |

Para este ejemplo, el tipo de sueldo para tiempo estándar está establecido en **1201** y un índice salarial de **10** en el acuerdo de sueldo. El descanso pagado tiene un tipo de sueldo **1301** y un índice salarial de **8**. Cuando se transfieren los registros, se generan los siguientes elementos de sueldo.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 7.50      | 10   |
| Horario flexible-         | 1201     | 0,50      | 10   |
| Descanso (pagado)  | 1301     | 0,50      | 8    |

## <a name="how-the-cost-of-paid-breaks-is-allocated-to-projects-and-production-orders"></a>Cómo se asigna el coste de los descansos remunerados a los proyectos y los pedidos de producción

El coste por hora en actividades de proyecto y trabajos de producción se puede configurar de modo que se determine según los índices salariales que se calculan en tiempo y asistencia o según las categorías de coste que se definen para las actividades.

Para configurar la categoría de coste, seleccione &gt; **Control de producción** **Configuración** &gt; **Ejecución de fabricación** &gt; **Valores predeterminados del pedido de producción**, y establezca el campo **Categoría de coste** en **Sí** o **No**.

- **No** El coste se calcula en función de los índices salariales definidos para los tipos de registro de tiempo y asistencia.
- **Sí** El coste se calcula en función de las categorías de coste para la producción y las actividades del proyecto.

### <a name="cost-calculation-based-on-pay-rates-that-are-calculated-in-time-and-attendance"></a>Cálculo de coste basado en las tasas de pago que se calculan en tiempo y asistencia

El ejemplo siguiente muestra cómo se calcula el coste por hora cuando se configura el coste de modo que se calcula basándose en tasas de pago.

El índice de coste por hora que se usa para los pedidos de producción y los proyectos se calcula durante el proceso de transferencia. Para ver el precio por hora por actividad, abra la página **aprobar** en Tiempo y asistencia, y después seleccione **Consulta** &gt; **Registros transferidos**. Puede encontrar el índice de coste por hora por registro en la pestaña **Precios de coste**.

Considere los siguientes registros que utilizan el mismo perfil de tiempo que el ejemplo anterior.

| Tipo de registro de diario | Inicio    | Fin      | Hora |
|---------------------------|----------|----------|------|
| Hora de entrada                  | 07:00 a. m. | 07:00 a. m. |      |
| Procesamiento (pedido: 4711)     | 07:00 a. m. | 11:00 a. m. | 4    |
| Procesamiento (pedido: 4712)     | 11:00 a. m. | 03:00 p. m. | 3.50 |
| Descanso (pagado)              | 12:00 p. m. | 12:30 p. m. | 0,50 |
| Hora de salida                 | 03:00 p. m. | 03:00 p. m. |      |

Una vez transferidos los registros, se generan los siguientes registros transferidos.

| Tipo de registro     | Hora | Precio de coste por hora |
|-----------------------|------|---------------------|
| Registrar la hora de entrada              | 0,00 | 0,00                |
| Procesamiento (pedido: 4711) | 4,00 | 10,00               |
| Procesamiento (pedido: 4712) | 3.50 | 11.14               |
| Descanso (pagado)          | 0,50 | 0,00                |
| Hora de salida             | 0,00 | 0,00                |

El cálculo del precio de coste por hora para el descanso pagado depende de un valor para los costes directos de nómina. Seleccione **Tiempo y asistencia** &gt; **Configuración** &gt; **Parámetros de tiempo y asistencia**. En la pestaña **Precio de coste**, en **Costes directos de nómina**, en el campo **Tiempo estándar**, puede seleccionar **Sí**, **No** o **asignación**.

- **Sí** Este valor se usa para el ejemplo anterior. El coste se asigna a la producción o a la actividad de proyecto que se ejecuta en paralelo con la actividad de descanso pagado. En el ejemplo, esta actividad es el trabajo de producción para la orden 4712. Como puede ver, el precio de coste por hora para la descanso pagado es 0 (cero) y está asignado al trabajo que se ejecuta en paralelo con el descanso.

    El descanso pagado tiene una duración de 0.5 horas, y el índice salarial es 8. Por lo tanto, el coste total del descanso pagado es 4. El coste total se asigna al trabajo del proceso de 3.5 horas. Por lo tanto, el descanso pagado contribuye en 1.14 por hora al coste (4 ÷ 3.5 = 1.14).

- **Asignación** El descanso pagado se distribuye equitativamente entre los trabajos que se registran para el día. Si este valor se usa para el ejemplo anterior, se generan los registros transferidos siguientes.

    | Tipo de registro     | Hora | Precio de coste por hora |
    |-----------------------|------|---------------------|
    | Registrar la hora de entrada              | 0,00 | 0,00                |
    | Procesamiento (pedido: 4711) | 4,00 | 10.53               |
    | Procesamiento (pedido: 4712) | 3.50 | 10.53               |
    | Descanso (pagado)          | 0,50 | 0,00                |
    | Hora de salida             | 0,00 | 0,00                |

    El tiempo de proceso total de los dos trabajos de producción es de 7.5 horas, y el coste total del descanso pagado es 4. Por lo tanto, el coste del descanso se calcula como 0.53 (= 4 ÷ 7.5).

- **No** El coste del descanso pagado no incrementa el coste por hora de las actividades de proceso.

    | Tipo de registro     | Hora | Precio de coste por hora |
    |-----------------------|------|---------------------|
    | Registrar la hora de entrada              | 0,00 | 0,00                |
    | Procesamiento (pedido: 4711) | 4,00 | 10,00               |
    | Procesamiento (pedido: 4712) | 3.50 | 10,00               |
    | Descanso (pagado)          | 0,50 | 0,00                |
    | Hora de salida             | 0,00 | 0,00                |

## <a name="absence"></a>Ausencia

Un código de ausencia se usa para registrar el período de ausencia de un trabajador. Al igual que los descansos y los códigos de cambio, un código de ausencia es un tipo de actividad indirecta. El tiempo de ausencia puede ser planificado o registrado y la ausencia puede ser legal o no válida. Los ejemplos de la ausencia legal incluyen una cita médica, un seminario o el servicio como jurado. La ausencia no válida es una ausencia que no tiene un buen motivo, como cuando un trabajador llegó tarde al trabajo. Normalmente, la ausencia legal no produce una reducción del sueldo del trabajador, mientras que la ausencia no válida produce una deducción.

### <a name="planned-absence"></a>Ausencia planificada

Puede crear una ausencia planificada para los trabajadores en la página **Crear ausencia planificada** (**Tiempo y asistencia** &gt; **Crear ausencia planificada**). Allí, la ausencia planificada se registra como un trabajo de ausencia de un intervalo especificado de fecha y hora.

El trabajo se basa en una consulta. Por lo tanto, puede crear una ausencia planificada para varios trabajadores, como trabajadores que pertenecen al mismo grupo de cálculos. Si la ausencia planificada es para un único trabajador, el registro se puede especificar desde la página **Asistencia** o la página **Trabajadores con registro de horas** .

- Para especificar un registro de ausencia de la página **Asistencia**, seleccione **Tiempo y asistencia** &gt; **Consultas e informes** &gt; **Asistencia** &gt; **Asistencia** y, a continuación, seleccione **Registro de ausencia**.
- Para especificar un registro de ausencia de la página *<strong><em>Trabajadores con registro de horas</em></strong>*, seleccione <strong>Tiempo y asistencia</strong> &gt; <strong>Configuración</strong> &gt; <strong>Trabajadores con registro de horas</strong> y, a continuación, en la pestaña <strong>Tiempo</strong>, en <strong>Asignación de tiempo</strong>, seleccione <strong>Registros de ausencia</strong>.

Puede usar el informe **Ausencias planificadas** para obtener una visión general de las ausencias planificadas para trabajadores. Para abrir este informe, seleccione **Tiempo y asistencia** &gt; **Consultas e informes** &gt; **Informes de ausencias** &gt; **Ausencias planificadas**.

### <a name="registered-absence"></a>Ausencia registrada

Normalmente se considera que los trabajadores están ausentes si no están en el trabajo durante el período comprendido entre su hora de entrada planificada y la hora de salida planificada. Si los trabajadores se registran después de lo planificado, o si salen antes de lo planificado, se les pedirá que seleccionen un código de ausencia para indicar el motivo de la ausencia. Un código de ausencia se puede configurar para que sea aplicable al registro. Solo los códigos aplicables estarán disponibles para su selección en la lista.

## <a name="scenarios-based-on-various-combinations-of-work-hour-registrations"></a>Situaciones basadas en varias combinaciones de registros de hora de trabajo

Las situaciones siguientes muestran los artículos y las entradas de sueldo para la aprobación que se generan para los trabajadores en función de sus registros. Todos los escenarios se basan en el siguiente perfil de tiempo:

| Tipo de perfil  | Inicio    | Fin      | Día     |
|---------------|----------|----------|---------|
| Horas extra     | 00:00 a. m. | 06:00 a. m. | Lunes  |
| Horario flexible+         | 06:00 a. m. | 07:00 a. m. | Lunes  |
| Hora de entrada      | 07:00 a. m. | 07:00 a. m. | Lunes  |
| Hora estándar | 07:00 a. m. | 02:30 p. m. | Lunes  |
| Horario flexible-         | 02:30 p. m. | 03:30 p. m. | Lunes  |
| Hora de salida     | 03:30 p. m. | 03:30 p. m. | Lunes  |
| Horas extra     | 03:30 p. m. | 06:00 a. m. | Martes |

### <a name="scenario-1-the-worker-clocks-in-later-than-planned"></a>Escenario 1: el trabajador entra más tarde de lo planificado

El trabajador entra a trabajar a las 08:30. Dado que la hora de entrada planificada es a las 07:00 a. m., ha llegado 1,50 horas tarde al trabajo. Dado que 1,50 horas se consideran tiempo de ausencia, el trabajador tendrá que seleccionar un código de ausencia. El trabajador sale a las 03:30 P.M., que es la hora de salida planificada. Cuando se calculan y se aprueban los registros del trabajador, el registro de ausencia, junto con el código de ausencia que el trabajador seleccionó al entrar, aparece para el tiempo entre las 07:00 AM y las 08:30 AM.

En el perfil de hora, puede configurar el tipo de registro **hora de entrada** de modo que haya una tolerancia cuando los trabajadores lleguen tarde al trabajo. Por ejemplo, si configura una tolerancia de 5, solo se le solicitará al trabajador un código de ausencia si se registra más tarde de las 07:05 a. m.

En este caso, dado que el trabajador no tiene un buen motivo para llegar tarde al trabajo, selecciona un código de ausencia definido para ausencias no válidas. Un código de ausencia se considera aplicable a la ausencia no válida si el valor de la deducción de horas extra se habilita para el grupo de ausencias al que pertenece el código de ausencia. Para establecer el valor, seleccione **Tiempo y asistencia** &gt; **Configuración** &gt; **Grupos** &gt; **Grupos de ausencias**, y a continuación seleccione la casilla de verificación **Deducir horas extra**.

Así es cómo los registros del trabajador para el día aparecen en la página **Aprobar** después del cálculo.

| Tipo de registro de diario         | Inicio    | Fin      | Hora |
|-----------------------------------|----------|----------|------|
| Ausencia (no válida - tarde al trabajo) | 07:00 a. m. | 08:30 a. m. | 1.5  |
| Hora de entrada                          | 08:30 a. m. | 08:30 a. m. |      |
| Trabajo de producción                    | 07:30 a. m. | 03:30 p. m. | 7.0  |
| Hora de salida                         | 03:30 p. m. | 03:30 p. m. |      |

Este es el artículo del pago resultante después de transferir los registros.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 7,00      | 10   |

### <a name="scenario-2-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-standard-time-period"></a>Escenario 2: El trabajador registra la hora de salida antes de la hora de salida planificada durante un periodo de tiempo estándar

El trabajador entra a las 7:00 y sale pronto a las 13:00. Dado que la 01:00 p. m. es anterior a la hora de salida planificada de las 03:30 p .m. y la 01:00 a. m. es en un plazo de tiempo estándar, el trabajador tendrá que seleccionar un código de ausencia. El trabajador selecciona un código de ausencia para una visita al médico, que se define como ausencia legal. La tasa de pago para la ausencia legal se define en los acuerdos de sueldo para el tipo de registro **Ausencia** (**Tiempo y asistencia** &gt; **Configuración** &gt; **Salario** &gt; **Acuerdos de sueldo**).

Así es cómo los registros del trabajador para el día aparecen en la página **Aprobar** después del cálculo.

| Tipo de registro de diario              | Inicio    | Fin      | Hora |
|----------------------------------------|----------|----------|------|
| Hora de entrada                               | 07:00 a. m. | 07:00 a. m. |      |
| Trabajo de producción                         | 07:00 a. m. | 01:00 p. m. | 4.0  |
| Hora de salida                              | 01:00 p. m. | 01:00 p. m. |      |
| Ausencia (legal – cita médica) | 01:00 p. m. | 03:30 p. m. | 3.5  |

Este es el artículo del pago resultante después de transferir los registros.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 7.50      | 10   |

### <a name="scenario-3-the-worker-clocks-out-before-the-planned-clock-out-time-during-a-flex--period"></a>Escenario 3: El trabajador registra la hora de salida antes de la hora de salida planificada durante un periodo de tiempo flexible

El trabajador entra a las 07:00 y sale a las 02:15 P.M., que es el período flexible planificado. El tiempo entre la hora de salida real y la hora de salida planificada no se considera ausencia, y no se solicita al trabajador que seleccione un código de ausencia. El importe se deduce de la cuenta de horario flexible del trabajador y, se garantiza al trabajador la paga durante la parte restante del período de horario flexible, desde las 02:15 a las 03:30 P.M.

Así es cómo los registros del trabajador para el día aparecen en la página **Aprobar** después del cálculo.

| Tipo de registro de diario | Inicio    | Fin      | Hora |
|---------------------------|----------|----------|------|
| Hora de entrada                  | 07:00 a. m. | 07:00 a. m. |      |
| Trabajo de producción            | 07:00 a. m. | 02:15 p. m. | 7.25 |
| Hora de salida                 | 02:15 p. m. | 02:15 p. m. |      |

Este es el artículo del pago resultante después de transferir los registros.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 8.50      | 10   |

### <a name="scenario-4-the-worker-clocks-in-late-and-clocks-out-after-the-planned-clock-out-time-during-an-overtime-period"></a>Escenario 4: El trabajador registra la hora de entrada con retraso y registra la hora de salida después de la hora planificada de salida durante un periodo de tiempo de horas extra

El trabajador entra tarde a las 09:30 y para compensar por llegar tarde, realiza horas extra y registra la hora de salida en las 05:00 P.M. Dado que el trabajador llegó tarde y lo compensó trabajando más tiempo, la empresa no desea conceder el pago de horas extra del trabajador por las horas trabajadas entre la hora de salida planificada de las 03:30 p. m. y su hora de salida real a las 05:00 p. m., aunque este período se define como hora extra en el perfil de tiempo.

Para gestionar este escenario, el código de ausencia se puede configurar para reducir las horas extra en función de cualquier ausencia no válida que el trabajador tenga en el mismo día. Seleccione **Tiempo y asistencia** &gt; **Configuración** &gt; **Grupos** &gt; **Grupos de ausencias**, y seleccione la casilla de verificación **Deducir horas extra** para restar horas extra de las horas de ausencia no válida.

Así es cómo los registros del trabajador para el día aparecen en la página **Aprobar** después del cálculo.

| Tipo de registro de diario         | Inicio    | Fin      | Hora |
|-----------------------------------|----------|----------|------|
| Ausencia (no válida - tarde al trabajo) | 07:00 a. m. | 09:30 a. m. | 1.5  |
| Hora de entrada                          | 09:30 a. m. | 09:30 a. m. |      |
| Trabajo de producción                    | 09:30 a. m. | 05:00 p. m. | 7.5  |
| Hora de salida                         | 05:30 p. m. | 05:30 p. m. |      |

Si la casilla de verificación **Deducir horas extra** se ha activado para el código de ausencia seleccionado, el pago de horas extra se deduce por las horas que el trabajador estuvo en ausencia no válida. En este caso, los siguientes elementos de pago se generan una vez transferidos los registros.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 9,00      | 10   |
| Horas extra      | 1301     | 0.5       | 15   |

Aquí, las 1,5 horas de ausencia no válida, desde las 07:00 a. m. hasta las 09:30 a. m., deducen las 2,0 horas extra, desde las 03:30 p. m. hasta las 05:30 p. m. El resultado del registro es 1,5 horas de tiempo estándar y 0,5 horas extra.

Por el contrario, si la casilla de verificación **Deducir horas extra** se deseleccionan para el código de ausencia seleccionado, el pago de horas extra se concede al trabajador, aunque éste haya llegado tarde y tenga una ausencia no válida. En este caso, los siguientes elementos de pago se generan una vez transferidos los registros.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 7.50      | 10   |
| Horas extra      | 1301     | 2.0       | 15   |

### <a name="scenario-5-the-worker-clocks-out-before-the-planned-clock-out-time-and-can-convert-the-absence-period-to-a-flex--period"></a>Escenario 5: el trabajador registra la hora de salida antes de la hora de salida planificada y puede convertir el período de ausencia en un período de horario flexible

El siguiente ejemplo muestra cómo una cuenta de horario flexible de un trabajo puede ser reducida convirtiendo el período de ausencia en un período de horarios flexibles.

El trabajador entra a las 7:00 y sale a las 13:00. El trabajador tiene un acuerdo de que puede irse a casa durante el fin de semana si deducen estas horas de su cuenta flexible. Cuando la trabajadora registra la hora de salida a la 01:00 P.M., se le pide que seleccione un código de ausencia, ya que el período de ausencia para la parte restante del día laborable afectado no es un período de horario flexible- planificado. Para convertir la parte restante del día laborable a un período de horario flexible-, el trabajador puede seleccionar un código de ausencia que esté configurado para reducir su cuenta de horario flexible.

Para reducir el saldo de horas flexibles de los trabajadores que registran ausencia en un día laborable, seleccione **Tiempo y asistencia** &gt; **Configuración** &gt; **Grupos** &gt; **Grupos de ausencias** y seleccione la casilla de verificación **Reducir horario flexible**.

Así es cómo los registros del trabajador para el día aparecen en la página **Aprobar** antes del cálculo.

| Tipo de registro de diario | Inicio    | Fin      | Hora |
|---------------------------|----------|----------|------|
| Hora de entrada                  | 07:00 a. m. | 07:00 a. m. |      |
| Trabajo de producción            | 07:00 a. m. | 01:00 p. m. | 6,0  |
| Hora de salida                 | 01:00 p. m. | 01:00 p. m. |      |

Si el trabajador selecciona un código de ausencia para una ausencia no válida, así se mostrará el elemento de pago resultante después de que se transfiera el registro.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 6,00      | 10   |

Si el trabajador selecciona un código de ausencia para la ausencia legal y el código de ausencia está configurado para reducir su cuenta de horario flexible, así es cómo se mostrarán los elementos de pago resultantes después de se transfieran los registros.

| Tipo de salario     | Tipo de sueldo | Unidades de sueldo | Índice |
|---------------|----------|-----------|------|
| Hora estándar | 1201     | 8.50      | 10   |

En este caso, el saldo de horario flexible del trabajador se reduce por las horas comprendidas entre la hora de salida real y la hora de salida planificada (es decir, las 2.5 horas desde las 01:00 P.M. hasta las 03:30 P.M.).

> [!NOTE]
> No se recomienda que seleccione la casilla de verificación **Deducir horario flexible** y la casilla de verificación **Deducir horas extra** para un código de ausencia, porque esta configuración deducirá las horas no válidas de las horas extra del trabajador y al mismo tiempo reducirá la cuenta de horario flexible del trabajador.

### <a name="scenario-6-there-is-no-planned-absence-for-the-day-and-no-worker-attendance-for-the-day"></a>Escenario 6: No hay ausencia planificada para el día y ninguna asistencia del trabajador para el día

Si el trabajador no aparece en el trabajo en un día laborable y no hay ausencia planificada para el trabajador en ese día, se usa un código de ausencia predeterminado para el cálculo de los registros del trabajador. Para definir códigos de ausencia predeterminados, seleccione **Tiempo y asistencia** &gt; **Parámetros de tiempo y asistencia**. A continuación puede seleccionar un código de ausencia en los siguientes campos:

- Insertar autom. horario flexible-
- Insertar autom. ausencia

Cuando los registros diarios se calculan para un trabajador que está habilitado para horas flexibles, el código de ausencia que se especifica en el campo **Insertar autom. horario flexible-** se usa como código de ausencia predeterminado. Si el trabajador no está habilitado para horas flexibles, se usa el código de ausencia que se especifica en el campo **Ausencia de inserción automática**. Si una empresa tiene una combinación de trabajadores que están habilitados para horas flexibles y trabajadores que no están habilitados para horas flexibles, ambos parámetros deben estar configurados.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]