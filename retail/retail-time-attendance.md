---
title: Tiempo y asistencia en la venta minorista
description: "Este tema describe las situaciones que se admiten para la administración de tiempo y asistencia en Microsoft Dynamics 365 para las operaciones (al por menor."
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: eac0b85a17df33c860333c5c19d4fb58f160930f
ms.lasthandoff: 03/31/2017


---

# <a name="retail-time-and-attendance"></a>Tiempo y asistencia en la venta minorista

Este tema describe las situaciones que se admiten para la administración de tiempo y asistencia en Microsoft Dynamics 365 para las operaciones (al por menor. 

<a name="manage-worker-setup-and-scheduling"></a>Gestionar la configuración y la programación del trabajador
----------------------------------

### <a name="initial-configuration"></a>Configuración inicial

-   Ejecutar el asistente para la configuración.
-   Registrar a los trabajadores como trabajadores con registro de horas.

### <a name="plan-worker-schedules"></a>Planificar las programaciones de los trabajadores

-   Aplicar perfiles mediante el planificador de trabajo. Para obtener más información, consulte <https://technet.microsoft.com/en-us/library/aa551234.aspx>.

Para obtener información sobre los pasos de configuración, vea <https://technet.microsoft.com/en-us/library/aa496971.aspx>.

### <a name="retail-specific-configuration"></a>Configuración específica a la venta minorista

-   Habilitar un perfil de funcionalidad para reloj de tiempo, para los trabajadores a los que desee habilitar registros de horas. Haga clic en ** perfiles de funcionalidad de PDV ** &gt; ** funciones ** &gt; ** registros de horas de PDV ** &gt; ** registros de horas de permiso **.
-   Configure grupos de permisos del punto de venta (PDV) para habilitar el permiso de las entradas de Visualizar reloj de tiempo. Este permiso permite que un usuario vea los registros del reloj de tiempo de otros trabajadores en la tienda (y de cualquier otra tienda a la que esté asociado el usuario, a través de la libreta de direcciones). Es posible que desee habilitar este permiso para un rol de administrador pero no para un rol de cajero. Haga clic en ** grupos de permisos de PDV ** &gt; ** entradas de hora de tiempo de la vista **.

## <a name="register-time"></a>Hora de registro
### <a name="cashier-and-non-cashier-time-registrations"></a>Registros de tiempo del cajero y fuera del cajero

-   En PDV:
    -   Operaciones de entrada:
        -   Inicie sesión con una operación que no sea del cajón o Turno nuevo
        -   Seleccione una operación del reloj de tiempo
        -   Seleccione la operación que desee:
            -   Registrar la hora de entrada
            -   Descanso de trabajo
            -   Descanso para el almuerzo
            -   Registrar la hora de salida

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Estado actual</th>
    <th>Operaciones disponibles</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Registrar la hora de entrada</td>
    <td><ul>
    <li>Descanso de trabajo</li>
    <li>Descanso para el almuerzo</li>
    <li>Registrar la hora de salida</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Descanso de trabajo</td>
    <td>Registrar la hora de entrada</td>
    </tr>
    <tr class="odd">
    <td>Descanso para el almuerzo</td>
    <td>Registrar la hora de entrada</td>
    </tr>
    <tr class="even">
    <td>Registrar la hora de salida</td>
    <td>Registrar la hora de entrada</td>
    </tr>
    </tbody>
    </table>

    ![TimeClockStates [] (. /media/timeclockstates.png])(. /media/timeclockstates.png)
-   Vea el mensaje de confirmación y compruebe que el tiempo de la actividad actual es correcto.
-   Libro de registros:
    -   Haga clic en **Libro de registros** para ver la actividad del reloj de tiempo.
    -   Use los filtros de tiempo para seleccionar diferentes ventanas de tiempo.
    -   Si trabaja en varias ubicaciones de tienda, verá los registros de tiempo de todas las tiendas en las que ha registrado el tiempo. Puede usar el filtro de tienda para ver los registros de tiendas de una tienda seleccionada.

<!-- -->

-   Diferentes zonas horarias:
    -   Si ve el tiempo desde otra ubicación (para el registro de cajero, o mediante **View timeclock entries** para una situación de gerente), y esa ubicación se encuentra en una zona horaria diferente, los registros de tiempo que ve se convierten a su zona horaria local. Por ejemplo, es un administrador para dos almacenes, uno en Arizona y otro en Nevada. Un cajero registra una entrada 9:00 a.m. Arizona en. En ese momento, en Londres son las 8:00 de la mañana. Por lo tanto, si está en la tienda de Londres y mira los registros de horas, el registro de hora se marca como 8 de la mañana.

## <a name="view-worker-time-registrations"></a>Registros de horas de trabajador de la vista
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Ver los registros de horas del trabajador y filtrar por tipo de tienda o de actividad

En PDV:

-   Seleccione **Ver entradas de reloj de tiempo**.
-   Verá actividades de registro del reloj de tiempo de todos los trabajadores asignados a las mismas tiendas a las que usted está asignado.
-   Puede usar los filtros de tipo de actividad y de tienda para filtrar los registros de hora.

## <a name="process-and-manage-time-registrations"></a>De proceso y gestionar los registros de horas
Una Dynamics 365 para las operaciones (el usuario al por menor sigue el flujo de trabajo para calcular, aprueba, y transferir registros de tiempo a las nóminas.

### <a name="primary-operations"></a>Operaciones primarias

-   Calcular
-   Aprobar
-   Enviar a nóminas

### <a name="other-common-operations"></a>Otras operaciones comunes

-   Hora de salida en masa
-   Registrar ausencias

Para obtener más información sobre cómo procesar los registros de tiempo y asistencia, consulte <https://technet.microsoft.com/en-us/library/aa573180.aspx>.


