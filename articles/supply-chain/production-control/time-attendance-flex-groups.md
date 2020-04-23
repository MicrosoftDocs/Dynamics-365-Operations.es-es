---
title: Grupos de horario flexible
description: En este tema se describe cómo se utilizan los grupos de horario flexible en Tiempo y asistencia.
author: johanhoffmann
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgFlexGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 753874e4cf1d0403e9c422f44d159b11ef1d7247
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210235"
---
# <a name="flex-groups"></a>Grupos de horario flexible

[!include[banner](../includes/banner.md)]

El horario laboral flexible permite a las empresas minimizar los pagos por horas extra al ofrecer a los tabajadores tiempo libre adicional durante períodos en los que la carga de trabajo es baja. Esta función es relevante, por ejemplo, en los segmentos que experimentan cambios estacionales en la carga de trabajo.

Puede usar los grupos de horario flexible para definir las siguientes reglas y principios para el horario lexible de un trabajador:

- Reglas para normativas de horario flexible
- Principio para calcular el saldo de horario flexible del trabajador

## <a name="set-up-flexible-working-hours-in-flex-groups"></a>Configurar horas de trabajo flexibles en grupos de horario flexible

- Seleccione **Tiempo y asistencia** \> **Configurar** \> **Grupos** \> **Grupos de horario flexible** para configurar grupos de horarios flexibles para horas flexibles.

## <a name="associate-workers-with-flex-groups"></a>Asociar trabajadores a grupos de horario flexible

- Seleccione **Tiempo y asistencia** \> **Configurar** \> **Trabajadores con registro de horas**.

## <a name="rules-for-flex-regulations"></a>Reglas para normativas de horario flexible

Puede usar reglas para normativas de horario flexible para definir límites de horario flexible, o el número mínimo y máximo de horas permitidas en la cuenta de horario flexible del trabajador. Los límites de horario flexible se configuran en el grupo de horario flexible. Cuando se superen los límites de horario flexible, se puede ajustar el saldo de horario flexible y el sueldo del trabajador.

Si se supera el horario flexible mínimo permitido de un trabajador (es decir, si el número de horas en la cuenta de horario flexible se encuentra por debajo del mínimo especificado), puede utilizar estos métodos para ajustar los saldos de horario flexible del trabajador creando una normativa de horario flexible:

- La cuenta de horario flexible del trabajador se puede ajustar al horario mínimo permitido especificado, pero sin deducir el sueldo del trabajador para el número de horas que la cuenta de horario flexible está por debajo del mínimo permitido.
- El sueldo del trabajador puede deducirse por el número de horas que la cuenta de horario flexible está por debajo del mínimo permitido. Esta deducción se realiza generarando artículos del sueldo para un tipo de sueldo concreto con una unidad de sueldo positiva o negativa.

Si se supera el horario flexible máximo permitido del trabajador, puede usar estos métodos para ajustar los saldos de horario flexible del trabajador creando una normativa de horario flexible:

- La cuenta de horario flexible del trabajador se puede volver a ajustar al horario máximo permitido especificado, pero sin compensar el sueldo del trabajador para el número de horas que el trabajador trabajó po encima del máximo permitido.
- El número de horas que el trabajador trabajó por encima del máximo permitido se puede convertir en sueldo. Esta conversión se hace al generar artículos del sueldo para un tipo de sueldo específico.

Puede ajustar un saldo de horario flexible en las siguientes ocasiones:

- Cuando un archivo de pago que se basa en datos de nómina se exporta mediante el trabajo **Pagar de transferencia** . Los datos de nómina se generan cuando transfiere el registro del trabajador desde la página **Aprobar**.
- Cuando se procesa el trabajo **Ajustar saldo de horario flexible**.

> [!NOTE]
> Las normativas de horario flexible no aparecen durante la aprobación y la transferencia diarias de los registros del trabajador en la página **Aprobar**.

## <a name="principle-for-calculating-a-workers-flex-balance"></a>Principio para calcular el saldo de horario flexible de un trabajador

El principio para calcular las horas en que se ajusta el saldo de horario flexible del trabajador se configura en el grupo de horario flexible. Seleccione **Tiempo y asistencia** \> **Configurar** \> **Grupos** \> **Grupos de horario flexible**. 

Se pueden usar los siguientes dos principios:

- **Tiempo**: las horas flexibles del trabajador se calculan solo a partir del tiempo registrado del trabajador para el día. Cuando se calculan los registros diarios del trabajador, el número de horas de Horario flexible+ y de Horario flexible- para el día se calcula a partir de las zonas de Horario flexible+ y Horario flexible- definidas en el perfil de tiempo del trabajador.
- **Tipos de sueldo**: las horas flexibles del trabajador se calculan en función de las ganancias de los tipos de sueldo para Horario flexible+ y Horario flexible- definidas en el acuerdo de sueldo del trabajador. El acuerdo de sueldo se asocia al trabajador del registro de tiempo. Puede que desee usar tipos de sueldo para gestionar cuentas de horario flexible si, por ejemplo, desea aumentar la cuenta de horario flexible de un trabajador por un factor concreto en una o varias zonas de horario flexible.

### <a name="scenario-1-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-minimum-is-exceeded"></a>Escenario 1: Ajustar el sueldo y la cuenta de horario flexible de un trabajador porque se supera el horario flexible mínimo permitido

Un trabajador que puede trabajar en horarios flexibles tiene una cuenta de horario flexible negativa.

- **Cuenta de horario flexible:** -4

El trabajador se asocia a un grupo de horario flexible que tenga la configuración siguiente:

- **Horario flexible mínimo:** -0.5
- **Tipo de sueldo mínimo:** 1302
- **Factor del tipo de sueldo:** -1.00

Como indica la diferencia entre la cuenta de horario flexible del trabajador y su horario flexible mínimo permitido, el trabajador ha superado su horario flexible mínimo permitido en 3.5 horas.

Cuando el administrador de nóminas transfiere los datos del sueldo del trabajador ejecutando el trabajo **Transferir al sueldo** o **Ajuste de horario flexible**, se crean los siguientes ajustes:

- La cuenta de horario flexible del trabajador se ajusta en 3.5 horas. Por lo tanto, el saldo de horario flexible de -4.0 horas se adapta al horario flexible mínimo permitido del trabajador de -0.5 horas.
- Se crea un artículo de sueldo para el tipo de sueldo 1302. Este artículo de sueldo tiene una unidad de sueldo de -3.5 horas que se deducirá del sueldo del trabajador. En este caso, la unidad de sueldo es un número negativo, ya que el ajuste positivo de 3.5 horas se multiplica por el factor de tipo de sueldo negativo de -1.0 definido en el grupo de horario flexible. Este artículo de sueldo formará parte del archivo de pago generado por el trabajo **Transferir al sueldo** .

### <a name="scenario-2-adjusting-a-workers-pay-and-flex-account-because-the-allowed-flex-maximum-is-exceeded"></a>Escenario 2: Ajustar el sueldo y la cuenta de horario flexible de un trabajador porque se supera el horario flexible máximo permitido

Un trabajador que puede trabajar en horarios flexibles tiene una cuenta de horario flexible positiva.

- **Cuenta de horario flexible:** 6

El trabajador se asocia a un grupo de horario flexible que tenga la configuración siguiente:

- **Horario flexible máximo:** 2.0
- **Tipo de sueldo mínimo:** 1302
- **Factor del tipo de sueldo:** -1.0

Como indica la diferencia entre la cuenta de horario flexible del trabajador y su horario flexible máximo permitido, el trabajador ha superado su horario flexible máximo permitido en 4.0 horas.

Cuando el administrador de nóminas transfiere los datos del sueldo del trabajador ejecutando el trabajo **Transferir al sueldo** o **Ajuste de horario flexible**, se crean los siguientes ajustes:

- La cuenta de horario flexible del trabajador se ajusta en -4.0 horas. Por lo tanto, el saldo de horario flexible de 6.0 horas se adapta al horario flexible máximo permitido del trabajador de 2.0 horas.
- Se crea un artículo de sueldo para el tipo de sueldo 1302. Este artículo de sueldo tiene una unidad de sueldo de 4.0 horas que se agregará del sueldo del trabajador. En este caso, la unidad de sueldo es un número positivo, ya que el ajuste negativo de 4.0 horas se multiplica por el factor de tipo de sueldo negativo de -1.0 definido en el grupo de horario flexible. Este artículo de sueldo formará parte del archivo de pago generado por el trabajo **Transferir al sueldo** .

### <a name="scenario-3-managing-a-workers-flex-balance-based-on-pay-types"></a>Escenario 3: Administrar el saldo de horario flexible de un trabajador basado en tipos de sueldo

Como explicamos anteriormente, las cuentas de horario flexible se pueden administrar en función del tiempo que se registra en las zonas de Horario flexible+ y de Horario flexible- que se definen en el perfil de tiempo del trabajador, o en los tipos de sueldo que se definen en los acuerdos de sueldo del trabajador. Si se utilizan tipos de sueldo, una cuenta de horario flexible del trabajador se ajusta mediante los artículos del sueldo que se generan cuando transfiere el registro del trabajador desde la página **Aprobar**. Puede que desee usar tipos de sueldo para gestionar cuentas de horario flexible si, por ejemplo, desea aumentar la cuenta de horario flexible de un trabajador por un factor concreto en una o varias zonas de horario flexible.

Este escenario utiliza el siguiente perfil flexible que representa un día laborable.

| Tipo de perfil  | Inicio    | Fin      |
|---------------|----------|----------|
| Horario flexible+         | 12:00 a. m. | 08:00 a. m. |
| Hora de entrada      | 08:00 a. m. | 08:00 a. m. |
| Horario flexible-         | 08:00 a. m. | 09:00 a. m. |
| Hora estándar | 09:00 a. m. | 11:30 a. m. |
| Descanso pagado    | 11:30 a. m. | 12:00 p. m. |
| Horario flexible-         | 12:00 p. m. | 04:00 p. m. |
| Hora de salida     | 04:00 p. m. | 04:00 p. m. |
| Horario flexible+         | 04:00 p. m. | 12:00 a. m. |

En este caso, desea poder gestionar el saldo de horario flexible del trabajador basado en tipos de sueldo. Por lo tanto, debe establecer la opción **Basado en los tipos de sueldo** en **Sí** en el grupo de horario flexible del trabajador.

Para justificar las horas flexibles, también deberá definir un nuevo tipo de sueldo. Para este escenario, el tipo de pago se denominan **FlexCnt**.

| Tipo de sueldo | Descripción  |
|----------|--------------|
| FlexCnt  | Contador flexible |

A continuación, siga estos pasos para configurar un tipo de sueldo y agregar las líneas del nuevo tipo a un perfil de sueldo.

1. Seleccione **Tiempo y asistencia** \> **Configurar** \> **Grupos** \> **Grupos de horario flexible** y, a continuación, seleccione **Nuevo**.
2. En el campo **Horario flexible+** y el campo **Horario flexible-**, especifique el nuevo tipo de sueldo, **FlexCnt**.
3. Seleccione **Tiempo y asistencia** \> **Configurar** \> **Acuerdos de sueldo** y, a continuación, seleccione **Líneas de acuerdo**.
4. Para **Lunes**, para el tipo de perfil **Horario flexible+**, agregue las tres líneas siguientes.

    | Tipo de sueldo | Descripción  | Desde hora | Hasta hora  | Mínimo | Máximo | Factor |
    |----------|--------------|-----------|----------|---------|---------|--------|
    | FlexCnt  | Contador flexible | 12:00 a. m.  | 06:00 p. m. | 00:00   | 00:00   | 1,00   |
    | FlexCnt  | Contador flexible | 06:00 p. m.  | 12:00 a. m. | 00:00   | 02.00   | 1.50   |
    | FlexCnt  | Contador flexible | 06:00 p. m.  | 12:00 a. m. | 02.00   | 06.00   | 2.00   |

    > [!NOTE]
    > Cada línea se utiliza para un intervalo de tiempo distinto y tiene un factor diferente. Las horas flexibles que el trabajador trabaja en un intervalo de tiempo se multiplican por el factor para dicha línea. Por ejemplo, las horas que se trabajan desde las 06:00 a. m. a las 08:00 p. m. se multiplican por 1.50. El factor se especifica en el campo **Factor** en la pestaña **General** de la página **Líneas de acuerdo de sueldo**.

El trabajador introduce los siguientes registros para el día.

| Tipo de registro de diario | Inicio    | Fin      |
|---------------------------|----------|----------|
| Hora de entrada                  | 07:00 a. m. | 07:00 a. m. |
| Trabajo de producción            | 07:00 a. m. | 09:00 p. m. |
| Hora de salida                 | 09:00 p. m. | 09:00 p. m. |

El importe que se debe pagar se calcula en la página **Aprobar**, en función del registro del trabajador. Tras calcularse el registro, puede ver el resultado en la pestaña **Horas**. Para este escenario, le interesarán los campos siguientes.

| Horario flexible + | Horario flexible - | Hora  | Tiempo salarial |
|--------|--------|-------|----------|
| 6,00   | 0,00   | 13.50 | 08.00    |

La cantidad de tiempo de Horario flexible+ es de seis horas, y el cálculo se basa en las zonas de horario flexible en el perfil de tiempo. Esta cantidad se compone de una hora de tiempo de Horario flexible+ desde las 07:00 a. m. a las 08:00 a. m. y de cinco horas de Horario flexible+ desde las 04:00 p. m. a las 09:00 p. m.

Al transferir los registros, observará que la cantidad de tiempo de Horario flexible+ cambia de 6.0 horas a 8.0 horas.

| Horario flexible + | Horario flexible - | Hora  | Tiempo salarial |
|--------|--------|-------|----------|
| 8,00   | 0,00   | 13.50 | 08.00    |

Este cambio se produce después de la transferencia porque las horas flexible se han calculado según los tipos de sueldo en lugar del tiempo. En la siguiente tabla se muestra cómo se calculan las ocho horas.

| De     | A       | Hora | Factor    | Cuenta de horario flexible |
|----------|----------|------|-----------|--------------|
| 07:00 a. m. | 08:00 a. m. | 1    | 1         | 1            |
| 04:00 p. m. | 06:00 p. m. | 2    | 1         | 2            |
| 06:00 p. m. | 08:00 p. m. | 2    | 1.5       | 3            |
| 08:00 p. m. | 09:00 p. m. | 1    | 2         | 2            |
|          |          |      | **Total** | **8**        |
