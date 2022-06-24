---
title: Configurar el rol de administrador de ausencias
description: Este artículo explica cómo configurar el rol de administrador de ausencias para la gestión de las vacaciones de los empleados.
author: twheeloc
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 40f9607fb6fc16b96373141d8d2610538e3fdec7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8886113"
---
# <a name="configure-the-absence-manager-role"></a>Configurar el rol de administrador de ausencias

>[!Important]
>La funcionalidad mencionada en este artículo está disponible actualmente para los clientes de Dynamics 365 Human Resources independiente. Algunas o todas las funciones estarán disponibles como parte de una versión futura de la infraestructura de Finance después de la versión 10.0.26 de Finance.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En algunas organizaciones, es posible que los gerentes de personas no administren la licencia para su equipo. En cambio, un administrador de ausencias podría manejar este proceso para los miembros del equipo en múltiples departamentos y equipos. Los administradores de ausencias tienen las siguientes capacidades para la gestión de licencias:

- Revise y apruebe el tiempo libre, según una jerarquía alternativa.
- Ver los saldos de los miembros del equipo.
- Ver el calendario de ausencias.

## <a name="turn-on-the-feature"></a>Activar la característica

1. En el espacio de trabajo **Administración del sistema**, seleccione **Administración de características**.

2. En la pestaña **Administración de características**, habilite la característica **Gestor de ausencias para gestionar bajas**.

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

En el espacio de trabajo **Autoservicio para los empleados**, la pestaña **Administrador de bajas** muestra la información de ausencias de los empleados que están asignados al administrador de ausencias en la jerarquía de ausencias. Hay algunas opciones disponibles para el administrador de ausencias: 
 - Revise las solicitudes de permisos.</br>
 - Envíe una solicitud de permiso en nombre de un empleado.</br>
 - Vea todos los empleados asignados a ellos como parte de la jerarquía de bajas.</br>
 - Vea el calendario de administrador de ausencias.</br>

En el espacio de trabajo **Administrador de bajas**, hay dos pestañas:
 - **Solicitudes de permiso**: esta pestaña enumerará todas las solicitudes de permiso pendientes que el administrador de ausencias puede aprobar. El administrador de ausencias puede seleccionar varios registros y actuar sobre ellos al mismo tiempo. Si la vista de permisos entre empresas está habilitada, esta lista mostrará las solicitudes de permiso pendientes en todas las entidades legales a las que tienen acceso. De lo contrario, mostrará las solicitudes de permiso pendientes para la entidad legal actualmente seleccionada. </br>
 - **Todos los empleados**: esta pestaña mostrará una lista de todos los empleados que están asignados al administrador de ausencias en la jerarquía de permisos. Hay un par de opciones disponibles para cada empleado:
    - **Solicitar permiso**: envíe una nueva solicitud de permiso para el empleado seleccionado.</br>
    - **Tiempo libre** - Ver saldos, tiempo libre aprobado y solicitudes de tiempo libre para el empleado seleccionado.</br>

## <a name="approve-time-off-requests"></a>Aprobar solicitudes de permisos

Los administradores de ausencias pueden aprobar o denegar las solicitudes de permisos de los empleados. 

> [!IMPORTANT]
> Antes de que los administradores de ausencias puedan aprobar o denegar las solicitudes de tiempo libre, el flujo de trabajo de solicitudes de ausencia debe configurarse para asignar elementos de trabajo de solicitud de ausencia para su revisión.
>
> 1. En la página **Flujos de trabajo de recursos humanos**, seleccione o cree el flujo de trabajo de solicitud de permiso.
> 2. Seleccione la opción **Jerarquía asociada** y luego, en el campo **Nombre de la jerarquía**, seleccione **Baja**.
> 3. Actualice el flujo de trabajo en el diseñador de flujo de trabajo. En **Tipo de asignación**, seleccione la opción **Jerarquía**, y luego, en la pestaña **Selección de jerarquía**, seleccione **Jerarquía configurable**.
>
> Para obtener información sobre cómo crear los flujos de trabajo de solicitud de bajas, consulte [Crear un flujo de trabajo de solicitud de baja](hr-leave-and-absence-workflow.md).

1. En el espacio de trabajo **Autoservicio del empleado**, seleccione la pestaña **Administración de bajas**.

2. En la pestaña **Solicitudes de permiso**, seleccione las solicitudes de permiso en las que desea tomar medidas. Puede seleccionar varios registros en esta vista de lista.

3. Utilice los botones de acción en la parte superior de la cuadrícula para Aprobar, Denegar o Delegar la solicitud de permiso. 

Alternativamente, el usuario también puede utilizar el icono **Solicitudes de permiso** a la izquierda para navegar a la lista de todos los elementos de trabajo de solicitud de permiso. 

## <a name="view-time-off-in-the-calendar"></a>Ver tiempo libre en el calendario

Los usuarios con el rol Administrador de ausencias pueden ver las solicitudes de permisos en su calendario. Siga estos pasos para acceder al calendario de bajas.

> [!IMPORTANT]
> Un administrador del sistema debe configurar las opciones de visualización para el calendario del administrador de ausencias. En la página **Parámetros de bajas y ausencias**, en la pestaña **Calendario**, hay opciones para ocultar o mostrar cumpleaños, ausencias sin detalles, permisos y solicitudes de permisos pendientes. También hay una opción para filtrar la opción de vista de calendario por tipo de trabajador.

1. En el espacio de trabajo **Autoservicio para los empleados**, seleccione **Administración de bajas** y luego **Calendario del administrador de ausencias**.

2. En el campo **Fecha**, escriba la fecha deseadas.

3. Actualice las opciones de vista según sea necesario.

El calendario del administrador de ausencias muestra todos los registros de los empleados que informan al administrador de ausencias en la jerarquía de ausencias.

## <a name="see-also"></a>Consulte también

- [Visión general de bajas y ausencias](hr-leave-and-absence-overview.md)
- [Crear un flujo de trabajo de solicitud de baja](hr-leave-and-absence-workflow.md)
- [Ver calendarios de equipo y empresa](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
