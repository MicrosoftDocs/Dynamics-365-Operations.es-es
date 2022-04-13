---
title: Crear un calendario de horas de trabajo
description: Defina un calendario de horas de trabajo, días festivos y horas no laborables en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 163d7caf516d791fa54e2518d19798bdf3d58d3d
ms.sourcegitcommit: 67c4ed957e43d4d60bb609d93921a0be9619e675
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "8509623"
---
# <a name="create-a-working-time-calendar"></a>Crear un calendario de horas de trabajo


> [!Important]
> La funcionalidad mencionada en este tema está disponible actualmente para los clientes de Dynamics 365 Human Resources independiente. Algunas o todas las funciones estarán disponibles como parte de una versión futura de la infraestructura de Finance después de la versión 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un calendario de horas de trabajo en Dynamics 365 Human Resources muestra los días y las horas en que trabajan los empleados en su organización. Cuando un empleado envía una solicitud de tiempo libre, no tiene que preocuparse de días festivos y cierres.

Para agilizar las solicitudes de tiempo libre, configure estos elementos para su organización:

- Calendario de horario de trabajo
- Días festivos y cierres
- Tiempo no laborable

Puede agregar los dos últimos elementos mientras configura un calendario de horas de trabajo. También puede configurarlos o actualizarlos por separado.

## <a name="set-up-a-working-time-calendar"></a>Configurar un calendario de horas de trabajo

Configure al menos un calendario de tiempo laborable que muestre sus días y horas de operación. Si tiene ubicaciones en varios países y regiones, es posible que desee configurar un calendario de tiempo de trabajo para cada área.

1. En la página **Administración de la organización**, seleccione **Calendarios**.

2. Seleccione **Nuevo** y especifique un nombre y una descripción para su calendario.

3. En **Opciones de generación**, seleccione los días laborales para su organización e introduzca las horas de trabajo. 
   - Para agregar un día festivo o un cierre, seleccione el botón **Agregar** junto a **Días festivos y cierres**.
   - Para agregar tiempo no laborable, como almuerzos o descansos, seleccione **Agregar** debajo de **TIEMPO NO LABORABLE** e introduzca el nombre y el intervalo de tiempo.

4. En **Días**, seleccione **Generar** para generar los días en el calendario. Introduzca el intervalo de fechas para su calendario y luego seleccione **Generar días**.

5. Para agregar horarios de trabajo, en **Programación de trabajos**, seleccione **Agregar** y luego introduzca las horas para cada horario de trabajo.

## <a name="configure-holidays-and-closures"></a>Configurar días festivos y cierres

Puede agregar o cambiar días festivos y cierres por separado desde un calendario de horas de trabajo.

1. En la página **Administración de la organización**, seleccione **Días festivos y cierres**.

2. Seleccione **Nuevo** y especifique un nombre y una fecha para el día festivo o el cierre.

## <a name="configure-non-work-time"></a>Configurar tiempo no laborable

Puede agregar o cambiar horas no laborables por separado desde un calendario de horas de trabajo.

1. En la página **Administración de la organización**, seleccione **TIEMPO NO LABORABLE**.

2. Seleccione **Nuevo** y especifique un nombre e intervalo de tiempo para el tiempo no laborable.

Si ha habilitado la característica de vista previa de correcciones de días festivos de permisos y ausencias, Human Resources usa los días festivos y las fechas de cierre para determinar el número de días para ajustar para los empleados inscritos en el calendario.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Configurar tipos de permisos y ausencias](hr-leave-and-absence-types.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
