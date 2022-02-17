---
title: Crear un calendario de equipo
description: Vea y cree calendarios de equipo en Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ee39f35f9d81f47c5438ddf48451d24ab0c0ed3
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065262"
---
# <a name="view-team-and-company-calendars"></a>Ver calendarios de equipo y empresa


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede ver calendarios de equipo y empresa en Dynamics 365 Human Resources. Los calendarios de equipo solo muestran informes directos, tal como se define en la jerarquía de líneas.

## <a name="view-your-team-calendar-as-an-employee"></a>Ver el calendario de su equipo como empleado

- En el espacio de trabajo **Autoservicio para empleados**, seleccione **Calendario de ausencias del equipo** en **Resumen**.

## <a name="view-your-team-calendar-as-a-manager"></a>Ver el calendario de su equipo como gerente

1. En el espacio de trabajo **Autoservicio para empleados**, seleccione **Mi equipo**.

2. Seleccione **Bajas y ausencias** y luego seleccione **Ver calendario de ausencias del administrador**.

Los gerentes también pueden acceder al calendario del equipo desde **Solicitudes pendientes de mi equipo**, **Tiempo libre aprobado** y **Solicitudes de tiempo libre**. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>Ver el calendario de su administrador de ausencias como administrador de ausencias

> [!NOTE]
> Para ver el calendario del administrador de ausencias, primero debe activar la función **(Vista previa) Gestor de ausencias para gestionar la baja** en la gestión de funciones. Para obtener más información acerca cómo activar las características de vista previa, consulte [Administrar características](hr-admin-manage-features.md).

Los usuarios con la función de administrador de ausencias pueden ver las solicitudes de tiempo libre en su calendario. Siga estos pasos para acceder al calendario de bajas.

1. En el espacio de trabajo **Autoservicio para los empleados**, seleccione **Administración de bajas** y luego **Calendario del administrador de ausencias**.

2. En el campo **Fecha**, escriba la fecha deseadas.

3. Actualice las opciones de vista según sea necesario.

El calendario del administrador de ausencias muestra todos los registros de los empleados que informan al administrador de ausencias en la jerarquía de ausencias.

## <a name="view-a-company-calendar"></a>Ver un calendario de empresa

Las personas con roles de Recursos Humanos pueden ver calendarios de empresa. Los calendarios de empresa muestran todos los empleados. De manera predeterminada, el calendario muestra la fecha de hoy más 28 días, pero puede cambiar el intervalo de fechas. También puede filtrar el calendario por **Nombre**, **Número personal** y **Tipo de baja**.

1. En el espacio de trabajo **Bajas y ausencias**, seleccione **Vínculos**.

2. Seleccione **Calendario de bajas y ausencias**.

Los roles de recursos humanos también pueden acceder al calendario de la empresa desde **Solicitudes de licencia y ausencia**, **Tiempo libre aprobado** y **Solicitudes de tiempo libre**. 

Los calendarios ahora contienen filtros y opciones adicionales. Todos los calendarios incluyen opciones de visualización para:

- Solicitudes aprobadas
- Solicitudes pendientes
- Empleados con solicitudes de baja
- Empleados sin solicitudes de baja
- Cumpleaños de empleados
- Solicitudes de tiempo libre 
- Solicitudes de permiso para ausentarse

La configuración del calendario en la página **Parámetros de permisos y ausencias** determina las opciones de visualización disponibles.

También puede filtrar calendarios por gerente o departamento. La asignación de puesto principal determina los empleados que se muestran cuando se establecen estos filtros. 

> [!IMPORTANT]
> Puede activar la función **Vista de bajas cruzada en la compañía** en la gestión de funciones. Debe habilitar la característica en la página **Parámetros compartidos de recursos humanos** para mostrar el filtro de entidad jurídica en calendarios. Para más información, consulte [Configurar parámetros de bajas y ausencias](hr-leave-and-absence-parameters.md).
> 
> Puede filtrar el calendario por entidad jurídica. Para ver a todos los empleados independientemente de su entidad jurídica, desactive el campo de filtro y seleccione **Entrar**. 

Para obtener información acerca de la configuración del calendario, consulte [Configurar parámetros de calendario](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
