---
title: Configurar el rol de administrador de ausencias
description: Este tema explica cómo configurar el rol de administrador de ausencias para la gestión de las vacaciones de los empleados.
author: hasrivas
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8a8250b36d2774ac308637253b780592df316cd
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639615"
---
# <a name="configure-the-absence-manager-role"></a>Configurar el rol de administrador de ausencias

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

En algunas organizaciones, es posible que los gerentes de personas no administren la licencia para su equipo. En cambio, un administrador de ausencias podría manejar este proceso para los miembros del equipo en múltiples departamentos y equipos. Los administradores de ausencias tienen las siguientes capacidades para la gestión de licencias:

- Revise y apruebe el tiempo libre, según una jerarquía alternativa.
- Ver los saldos de los miembros del equipo.
- Ver el calendario de ausencias.

## <a name="turn-on-the-feature"></a>Activar la característica

1. En el espacio de trabajo **Administración del sistema**, seleccione **Administración de características**.

2. En la pestaña **Gestión de funciones**, habilite la característica **(Vista previa) Gestor de ausencias para gestionar bajas**.

## <a name="define-a-custom-hierarchy"></a>Definir una jerarquía personalizada

La funcionalidad del administrador de ausencias utiliza una jerarquía personalizada que debe configurarse.

1. En el espacio de trabajo **Administración de la organización** seleccione **Tipos de jerarquía de posición**.

2. Cree un tipo de jerarquía de posición que se denomine **Baja**.

3. En espacio de trabajo **Bajas y ausencias**, en **Enlaces** seleccione **Parámetros de bajas y ausencias**.

4. En la pestaña **General**, en la lista desplegable **Jerarquía de ausencias**, seleccione el tipo de jerarquía **Baja** que creó anteriormente. Esta asociación de jerarquía de bajas debe completarse para todas las entidades jurídicas donde se utilizará la funcionalidad del administrador de ausencias.

Una vez definido el tipo de jerarquía, el informe de jerarquía de puesto debe asignarse al puesto.

1. En el espacio de trabajo **Administración de la organización** seleccione **Todos los puestos**.

2. Seleccione el puesto al que agregar la Jerarquía de bajas.

3. En la pestaña **Relaciones**, seleccione **Agregar**.

4. En el campo **Nombre de jerarquía**, seleccione **Baja**.

5. En el campo **Notifica al puesto**, seleccione un puesto. El nombre del trabajador se completa automáticamente después de seleccionar un puesto.

## <a name="assign-the-absence-manager-role-to-a-user"></a>Asignar el rol de administrador de ausencias a un usuario

El rol de administrador de ausencias debe asignarse a los empleados para permitirles aprobar o rechazar las solicitudes de ausencias.

1. En el espacio de trabajo **Administrador de sistema**, seleccione **Enlaces**.

2. En la sección **Usuarios** seleccione el enlace **Usuarios**.

3. En la lista de usuarios, seleccione el usuario al que se le asignará el rol de administrador de ausencias.

4. En la pestaña **Roles de usuarios** seleccione **Asignar roles**.

5. En la lista, seleccione el rol **Gerente de ausencias**. A continuación seleccione **Aceptar**.

    > [!IMPORTANT]
    > Asegúrese de que el rol de empleado también se haya asignado al usuario al que le está asignando el rol de administrador de ausencias. De lo contrario, el trabajador no podrá utilizar la función.

6. Una vez que haya creado la jerarquía de bajas, puede verla siguiendo estos pasos:

    1. En el espacio de trabajo **Administración de la organización** seleccione **Jerarquía de posición**.
    
    2. En el campo **Tipo de jerarquía**, seleccione **Baja**.

## <a name="absence-manager-workspace"></a>Área de trabajo del administrador de ausencias

En el espacio de trabajo **Autoservicio para los empleados**, la pestaña **Gerente de ausencias** muestra la información de ausencias sobre los empleados que están asignados al administrador de ausencias en la jerarquía de ausencias.

En la pestaña **Bajas y ausencias**, las siguientes opciones están disponibles para cada empleado:

- **Tiempo libre** - Ver saldos, tiempo libre aprobado y solicitudes de tiempo libre para el empleado seleccionado.
- **Saldos de baja** - Ver una lista de los saldos de los diferentes planes de vacaciones para el empleado seleccionado.

## <a name="approve-time-off-requests"></a>Aprobar solicitudes de permisos

Los administradores de ausencias pueden aprobar o denegar las solicitudes de tiempo libre para los empleados. También pueden crear solicitudes en nombre de los empleados, según sea necesario.

> [!IMPORTANT]
> Antes de que los administradores de ausencia puedan aprobar o denegar las solicitudes de tiempo libre, el flujo de trabajo de la solicitud de ausencia debe configurarse para asignarles elementos de trabajo de solicitud de ausencia para su revisión.
>
> 1. En la página **Flujos de trabajo de recursos humanos**, seleccione o cree el flujo de trabajo de solicitud de permiso.
> 2. Seleccione la opción **Jerarquía asociada** y luego, en el campo **Nombre de la jerarquía**, seleccione **Baja**.
> 3. Actualice el flujo de trabajo en el diseñador de flujo de trabajo. En **Tipo de asignación**, seleccione la opción **Jerarquía**, y luego, en la pestaña **Selección de jerarquía**, seleccione **Jerarquía configurable**.
>
> Para obtener información sobre cómo crear los flujos de trabajo de solicitud de bajas, consulte [Crear un flujo de trabajo de solicitud de baja](hr-leave-and-absence-workflow.md).

1. En el espacio de trabajo **Autoservicio del empleado**, seleccione la pestaña **Administrador de ausencia**.

2. En la pestaña **Gerente de ausencias**, seleccione el empleado deseado.

3. Seleccione **Detalles** y luego **Tiempo libre**.

4. Busque la solicitud de tiempo libre y seleccione la opción **Aprobar** opción. Luego, puede seleccionar una opción para aprobar o cancelar la solicitud de tiempo libre.

Un estado de **Cancelar** indica que la solicitud ha sido denegada. Un estado de **Completado** indica que la solicitud ha sido aprobada.

## <a name="view-time-off-in-the-calendar"></a>Ver tiempo libre en el calendario

Los usuarios con la función de administrador de ausencias pueden ver las solicitudes de tiempo libre en su calendario. Siga estos pasos para acceder al calendario de bajas.

> [!IMPORTANT]
> Un administrador del sistema debe configurar las opciones de visualización para el calendario del administrador de ausencias. En la página **Parámetros de bajas y ausencias**, en la pestaña **Calendario**, hay opciones para ocultar o mostrar cumpleaños, ausencias sin detalles, permisos y solicitudes de permisos pendientes. También hay una opción para filtrar la opción de vista de calendario por tipo de trabajador.

1. En el espacio de trabajo **Autoservicio para los empleados**, seleccione **Gerente de ausencias** y luego **Calendario del administrador de ausencias**.

2. En el campo **Fecha**, escriba la fecha deseadas.

3. Actualice las opciones de vista según sea necesario.

El calendario del administrador de ausencias muestra todos los registros de los empleados que informan al administrador de ausencias en la jerarquía de ausencias.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Crear un flujo de trabajo de solicitud de baja](hr-leave-and-absence-workflow.md)
- [Ver calendarios de equipo y empresa](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
