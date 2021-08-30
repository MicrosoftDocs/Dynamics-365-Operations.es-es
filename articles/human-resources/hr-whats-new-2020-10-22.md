---
title: Novedades y cambios en Dynamics 365 Human Resources (22 de octubre de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 22 de octubre de 2020.
author: jcart1106
ms.date: 10/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 84bcf2ce850de95186c1ffee3bdd152255fc0d5c2832e47ea61918d240bcb1c6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772649"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (22 de octubre de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources. Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.3680.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Platform update 10.0.14(38) | -- | [Actualizaciones de plataforma para aplicaciones de la versión 10.0.14 de Finance and Operations (noviembre de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14.md) |
| Mejoras en la experiencia de los flujos de trabajo de organización y administración de personal | [Mejoras en la experiencia de los flujos de trabajo de organización y administración de personal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opción de configuración de la lista de elementos de trabajo de puesto asignados a mí](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema| Emitir  | Descripción|
| --- | --- | --- |
| 437922 | La importación de horas FMLA a través de la entidad DMF genera un error de solo lectura. | No se pudieron importar las horas asociadas a un caso FMLA mediante la entidad Horas FMLA. Hemos agregado lógica para garantizar que las horas importadas no excedan de las horas restantes para el caso. |
| 512019 | Importe de **Última transferencia** incorrecto. | En la página **Tiempo libre**, al cambiar **A partir de la fecha** al primer día del siguiente período fiscal se mostraba un importe de **Última transferencia** incorrecto para el tipo **Baja anual**. Ahora se muestra la cantidad correcta. |
| 458639 | La entidad **Contactos de trabajadores** no admite el modo de seguimiento de cambios. | Hemos actualizado la entidad **Contactos de trabajadores** para que pueda usarla en escenarios de llevar su propia base de datos (BYOD).|
| 505347 | Los directores de formación podían enviar una solicitud de baja para un empleado cuando estaba habilitada la característica de trabajador simplificada. | Los roles que no sean los de asistente de recursos humanos y director de recursos humanos no pueden enviar solicitudes de tiempo libre para los empleados. |
| 513490 | Registro de administración de prestaciones: agregue el registro para planes sin opciones de cobertura. | Hemos habilitado el registro de resultados para **Plan sin opciones de cobertura**. Ahora se muestran en la tabla **Resultados de proceso** y están ordenados correctamente de forma que se muestren en la parte superior. |
| 517021 | No se pueden seleccionar varios planes con el mismo código de **Tipo de plan** si **Tipo de plan** tiene una inscripción por tipo. | Hemos cambiado las restricciones para seleccionar planes en los que solo se permita una inscripción. Las restricciones están ahora en el nivel **Código de tipo de plan**, en lugar de en **Tipo de plan**. Este cambio permite planes como HSA y FSA, que son del mismo tipo, pero se les puede asignar un **Código de tipo de plan** independiente. De esta manera, puede seleccionar ambos planes para el mismo período de inscripción. |
| 444791 | No se puede ver la compensación en el autoservicio para empleados cuando el **Acceso restringido** está activado en el plan de compensación. | En la tarjeta **Compensación** del autoservicio para empleados, el importe de compensación actual y el porcentaje de aumento mostraban "0" si el empleado estaba inscrito en un plan con **Acceso restringido** activado y asignado a roles específicos. Hemos solucionado este problema de forma que el empleado y el director puedan ver siempre los detalles por sí mismos para ellos y para sus subordinados directos. |
| 457542 | Al actualizar los detalles del curso una vez cerrado el curso no se actualiza la misma información para el empleado que realizó el curso. | Ahora la información de los empleados se actualiza correctamente cuando se cambian los detalles del curso después de cerrar y volver a abrir un curso. |
| 515342 | No se pueden insertar datos a través de **CDSLeaveRequestDetailEntity**. No se encuentra la empresa o no existe. | Ahora puede usar **CDSLeaveRequestDetailEntity** para insertar datos. |
| 514743 | Error en el formulario **Parámetro de correo electrónico** al usar Microsoft Exchange. | Aparecía el mensaje "No se pudieron cargar los archivos o el ensamblado..." en la página **Parámetros de correo electrónico** cuando el proveedor de correo electrónico estaba establecido en **Exchange**. Esta corrección también permite que la página **Parámetros de correo electrónico** se cargue y se guarde de la forma esperada. |


## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Aplicación Human Resources en Microsoft Teams | [Experiencia de bajas y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicación Human Resources en Teams](./hr-admin-teams-leave-app.md)<br>[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md) |
| Solicitudes y aprobaciones de flujo de trabajo mejoradas | [Mejoras en la experiencia de los flujos de trabajo de organización y administración de personal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opción de configuración de la lista de elementos de trabajo de puesto asignados a mí](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entidades virtuales disponibles Dataverse para Human Resources | [Expandir datos básicos de Dynamics 365 Human Resources en Dataverse](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurar entidades virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |
| Integración con LinkedIn Talent Hub | [Integración con LinkedIn Talent Hub](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrar con LinkedIn Talent Hub](./hr-admin-integration-linkedin.md) |
| Vínculos personalizados en Autoservicio para directores | [Vínculos personalizados en el autoservicio para directores](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Vínculos personalizados en el autoservicio para directores](./hr-employee-manager-self-service-custom-links.md) |

## <a name="coming-soon"></a>Próximamente

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]