---
title: Crear un calendario de equipo
description: Vea y cree calendarios de equipo en Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cedff4031c6455b446af9c56a770a00f3b2efc80
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052106"
---
# <a name="view-team-and-company-calendars"></a>Ver calendarios de equipo y empresa

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Puede ver calendarios de equipo y empresa en Dynamics 365 Human Resources. Los calendarios de equipo solo muestran informes directos, tal como se define en la jerarquía de líneas.

## <a name="view-your-team-calendar-as-an-employee"></a>Ver el calendario de su equipo como empleado

1. En el espacio de trabajo **Autoservicio para empleados**, seleccione **Calendario de ausencias del equipo** en **Resumen**.

## <a name="view-your-team-calendar-as-a-manager"></a>Ver el calendario de su equipo como gerente

1. En el espacio de trabajo **Autoservicio para empleados**, seleccione **Mi equipo**.

2. Seleccione **Bajas y ausencias** y luego seleccione **Ver calendario de ausencias del administrador**.

Los gerentes también pueden acceder al calendario del equipo desde **Solicitudes pendientes de mi equipo**, **Tiempo libre aprobado** y **Solicitudes de tiempo libre**. 

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

La configuración del calendario en los parámetros de permisos y ausencias determina las opciones de visualización disponibles.

También puede filtrar calendarios por gerente o departamento. La asignación de puesto principal determina los empleados que se muestran cuando se establecen estos filtros. 

>[!IMPORTANT]
>La visualización de permisos y ausencias en todas las empresas se encuentra actualmente en versión preliminar. Deberá habilitarlo en su entorno de **Espacio** aislado. Para obtener más información sobre cómo habilitar las características en versión preliminar, consulte [Administrar características](hr-admin-manage-features.md).<br><br>
>A continuación, debe habilitar la característica en **Parámetros compartidos de recursos humanos** para mostrar el filtro de entidad jurídica en calendarios. Para más información, consulte [Configurar parámetros de bajas y ausencias](hr-leave-and-absence-parameters.md).<br><br>
>Puede filtrar el calendario por entidad jurídica. Si desea ver a todos los empleados independientemente de su entidad jurídica, desactive la casilla de filtro y seleccione Entrar. 

Para obtener información acerca de la configuración del calendario, consulte [Configurar parámetros de calendario](hr-leave-and-absence-parameters.md?configure-calendar-parameters).



[!INCLUDE[footer-include](../includes/footer-banner.md)]