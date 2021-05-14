---
title: Novedades y cambios en Dynamics 365 Human Resources, 19 de abril de 2021
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 19 de abril de 2021.
author: marcelbf
ms.date: 04/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8968c9cb849901288d75cd5e539a57faf0045337
ms.sourcegitcommit: e24e335811727c4b12152323b2bcb25495c08c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "5934901"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Novedades y cambios en Dynamics 365 Human Resources, 19 de abril de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4113.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Actualización de la plataforma 10.0.17 (41) | -- | [Actualizaciones de plataforma para aplicaciones de la versión 10.0.17 de Finance and Operations (abril de 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| Soporte de campos personalizados en formularios de gestión de prestaciones | [Soporte de campos personalizados en gestión de prestaciones](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [Información general de administración de prestaciones](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir |  Descripción |
| --- | --- | --- |
| 552164 | **Vista guardada** en **Autoservicio para empleados > Cursos abiertos** no funciona para cursos que contienen una agenda | Si se utiliza una vista guardada en cursos abiertos (ESS) y uno de los cursos tiene una agenda adjunta, la vista ya no mostrará varias líneas para ese curso |
| 560614 | **Beneficios > Opciones de eventos de vida** muestran discrepancias en la documentación de información sobre herramientas y el comportamiento del código. | Información de herramientas actualizadas en **Opciones de eventos de vida** para mostrar un comportamiento correcto. |
| 560616 | **Prestaciones > Opciones de eventos de vida** son editables en el plan de beneficios para trabajadores, pero los cambios no se ven afectados. | Se actualizó el comportamiento de los conmutadores de opciones de eventos de vida para habilitar o deshabilitar, según las opciones dependientes, según la documentación de información sobre herramientas. |
| 565054 | No se puede ver el contenido de la lista **Trabajadores sin empleo** cuando **Acceso avanzado** está activado. | Esta versión corrige el problema donde, cuando **Acceso avanzado** estaba activado, solo los administradores del sistema podían ver el contenido de la lista **Trabajadores sin empleo**. Debido a que esta solución es un cambio de seguridad, deberá aceptarla en Administración de funciones. Una vez que la función está activada, los roles que tienen acceso al formulario verán el contenido, aunque el acceso avanzado esté activado. Para obtener más información, consulte [Trabajadores sin empleo](hr-personnel-workers-without-employment.md). |
| 570586 | La validación de la solicitud de licencia falla cuando el empleo finaliza antes de la última transacción para ese trabajador en todos los planes de bajas. | Una vez que finaliza un empleo, la validación de la solicitud de baja no falla en función de las transacciones de bajas del empleado.|
| 570783 | Habilitar y deshabilitar la baja entre empresas en los parámetros compartidos de Recursos Humanos cambia lo que los empleados empleados de una única empresa ven en las solicitudes de licencia. | Los empleados de una única empresa no ven cambios en la solicitud de persmisos si el parámetro está habilitado o deshabilitado. |
| 572343 | El código de motivo obligatorio no se muestra cuando está habilitada la función de vista de permisos entre empresas. | Cuando está habilitada la función de baja entre empresas, el código de motivo ahora aparece según se esperaba. |
| 573676 | No se puede agregar **Periodo** a **Gestión de prestaciones > Enlaces > Planes de prestaciones**. | Se han corregido errores por los que **Periodo** no se pudo agregar ni actualizar en el formulario **Plan de beneficios** existente. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Mejoras en la experiencia del flujo de trabajo de bajas y ausencias | [Mejoras en la experiencia del flujo de trabajo de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar permiso](hr-employee-self-service-request-time-off.md)|
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
| Las aptitudes introducidas por un director para sus empleados se pueden aprobar automáticamente mediante un flujo de trabajo | Próximamente. |
| Actualización de la plataforma 10.0.18 (42) | La actualización de la plataforma 10.0.18 está programada para comenzar a implementarse con la próxima versión de servicio el 17 de mayo de 2021. Para obtener más información, consulte [Actualizaciones de platforma para la versión 10.0.18 de aplicaciones de Finance and Operations (mayo de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Soporte de campos personalizados en las reglas de idoneidad de gestión de prestaciones  | [Soporte de campo personalizado para el procesamiento de idoneidad](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
