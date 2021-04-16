---
title: Gestión del tiempo y la asistencia en Retail
description: Este tema describe los escenarios que se admiten para la gestión del tiempo y la asistencia en Dynamics 365 Commerce.
author: aamirallaqaband
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9bec213cd4954f69605387ae2801d8af98a8111c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791904"
---
# <a name="time-and-attendance-management-in-retail"></a>Gestión del tiempo y la asistencia en Retail

[!include [banner](includes/banner.md)]

Este tema describe los escenarios que se admiten para la gestión del tiempo y la asistencia en Dynamics 365 Commerce.

## <a name="manage-worker-setup-and-scheduling"></a>Gestionar la configuración y la programación de trabajadores

### <a name="initial-configuration"></a>Configuración inicial

- Ejecutar el asistente para la configuración.
- Registrar a los trabajadores como trabajadores con registro de horas.

### <a name="plan-worker-schedules"></a>Planificar las programaciones de los trabajadores

- Aplicar perfiles mediante el planificador de trabajo. Para obtener más información, vea [Aplicar perfiles mediante el planificador de trabajo](https://technet.microsoft.com/library/aa551234.aspx).

Para obtener información sobre los pasos de configuración, consulte [Configuración del tiempo y la asistencia](https://technet.microsoft.com/library/aa496971.aspx).

### <a name="commerce-specific-configuration"></a>Configuración específica de Commerce

- Habilitar un perfil de funcionalidad para reloj de tiempo, para los trabajadores a los que desee habilitar registros de horas. Haga clic en **Perfiles de la funcionalidad del PDV** &gt; **Funciones** &gt; **Registros de hora del PDV** &gt; **Habilitar registros de horas**.
- Configure grupos de permisos del punto de venta (PDV) para habilitar el permiso de las entradas de Visualizar reloj de tiempo. Este permiso permite que un usuario vea los registros del reloj de tiempo de otros trabajadores en la tienda (y de cualquier otra tienda a la que esté asociado el usuario, a través de la libreta de direcciones). Es posible que desee habilitar este permiso para un rol de administrador pero no para un rol de cajero. Haga clc en **Grupos de permiso del PDV** &gt; **Ver entradas del reloj de tiempo**.

## <a name="register-time"></a>Hora de registro

### <a name="cashier-and-non-cashier-time-registrations"></a>Registros de tiempo del cajero y fuera del cajero

- En PDV:

    - Operaciones de entrada:

        - Inicie sesión con una operación que no sea del cajón o Turno nuevo
        - Seleccione una operación del reloj de tiempo
        - Seleccione la operación que desee:

            - Registrar la hora de entrada
            - Descanso de trabajo
            - Descanso para el almuerzo
            - Registrar la hora de salida

        <table>
        <thead>
        <tr>
        <th>Estado actual</th>
        <th>Operaciones disponibles</th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td>Registrar la hora de entrada</td>
        <td>
        <ul>
        <li>Descanso de trabajo</li>
        <li>Descanso para el almuerzo</li>
        <li>Registrar la hora de salida</li>
        </ul>
        </td>
        </tr>
        <tr>
        <td>Descanso de trabajo</td>
        <td>Registrar la hora de entrada</td>
        </tr>
        <tr>
        <td>Descanso para el almuerzo</td>
        <td>Registrar la hora de entrada</td>
        </tr>
        <tr>
        <td>Registrar la hora de salida</td>
        <td>Registrar la hora de entrada</td>
        </tr>
        </tbody>
        </table>

        [![Estados del reloj de tiempo](./media/timeclockstates.png)](./media/timeclockstates.png)

- Vea el mensaje de confirmación y compruebe que el tiempo de la actividad actual es correcto.
- Libro de registros:

    - Haga clic en **Libro de registros** para ver la actividad del reloj de tiempo.
    - Use los filtros de tiempo para seleccionar diferentes ventanas de tiempo.
    - Si trabaja en varias ubicaciones de tienda, verá los registros de tiempo de todas las tiendas en las que ha registrado el tiempo. Puede usar el filtro de tienda para ver los registros de tiendas de una tienda seleccionada.

- Diferentes zonas horarias:

    - Si ve el tiempo desde otra ubicación (para el registro de cajero, o mediante **Ver entradas de reloj de tiempo** para una situación de gerente), y esa ubicación se encuentra en una zona horaria diferente, los registros de tiempo que ve se convierten a su zona horaria local. Por ejemplo, usted es el gerente de dos tiendas, una en Barcelona y otra en Londres. Un cajero registra la hora de entrada a las 9:00 de la mañana en Barcelona. En ese momento, en Londres son las 8:00 de la mañana. Por lo tanto, si está en la tienda de Londres y mira los registros de horas, el registro de hora se marca como 8 de la mañana.

## <a name="view-worker-time-registrations"></a>Ver registros de horas del trabajador

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Ver los registros de horas del trabajador y filtrar por tipo de tienda o de actividad

En PDV:

- Seleccione **Ver entradas de reloj de tiempo**.
- Verá actividades de registro del reloj de tiempo de todos los trabajadores asignados a las mismas tiendas a las que usted está asignado.
- Puede usar los filtros de tipo de actividad y de tienda para filtrar los registros de hora.

## <a name="process-and-manage-time-registrations"></a>Procesar y gestionar registros de tiempo

Un usuario de Commerce sigue al flujo de trabajo para calcular, aprobar y transferir registros de tiempo a las nóminas.

### <a name="primary-operations"></a>Operaciones primarias

- Calcular
- Aprobar
- Enviar a nóminas

### <a name="other-common-operations"></a>Otras operaciones comunes

- Hora de salida en masa
- Registrar ausencias

Para obtener más información sobre cómo procesar los registros de tiempo y asistencia, consulte [Procesar registros de tiempo y asistencia](https://technet.microsoft.com/library/aa573180.aspx).


[!INCLUDE[footer-include](../includes/footer-banner.md)]