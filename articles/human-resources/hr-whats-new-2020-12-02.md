---
title: Novedades y cambios en Dynamics 365 Human Resources (2 de diciembre de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 2 de diciembre de 2020.
author: marcelbf
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 89c5dbab58679dfe36f5eec0d6c5724f81c18523
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463463"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-december-2-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (2 de diciembre de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.3788.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Los responsables pueden enviar solicitudes de contratación para puestos | [Los responsables pueden enviar una solicitud de contratación para vacantes](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Agregar una solicitud de contratación](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Perfil de candidato mejorado en la Administración de personal | [Perfil de candidato mejorado en la administración de personal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Agregar o editar un perfil de candidato](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Habilitar integraciones simplificadas con proveedores de contratación | [Habilitar integraciones simplificadas con proveedores de contratación](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Contratar candidatos de trabajo](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |
| Vínculos personalizados en Autoservicio para directores | [Vínculos personalizados en el autoservicio para directores](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Vínculos personalizados en el autoservicio para directores](https://aka.ms/MSSCustomLinks) |


### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir | Descripción |
| --- | --- | --- |
| 514087 | BenefitEligibilityProcessResult debe incluir la fecha y hora que se utilizó en el procesamiento. | El resultado del procesamiento de BenefitEligibity ahora incluye la marca de fecha y hora para el último procesamiento, que faltaba anteriormente. |
| 526903 | Se produce un error en la inscripción a prestaciones para planes con dependientes cuando la opción **Seleccionar automáticamente personas designadas** está activada en **Parámetros compartidos de recursos humanos**. | Se solucionó el problema por el cual se producía un error en la inscripción de prestaciones para dependientes cuando la opción **Seleccionar automáticamente personas designadas** estaba activada para las personas designadas predeterminadas. |
| 521922 | El parámetro **Mostrar ausencia sin detalle** muestra detalles de solicitudes de tiempo libre en el calendario de ausencias del equipo. | El tipo de licencia, el color del tipo de licencia y los detalles del día se mostraban en el calendario de ausencias del equipo cuando la opción **Mostrar ausencia sin detalle** estaba establecida en **Sí** en **Parámetros de permisos y ausencias**. Esto se ha solucionado y ahora el tipo de licencia no se muestra y se usa el color del tipo de licencia predeterminado (azul oscuro) para todos los tipos de licencia en el calendario de ausencias del equipo. |
| 527316 | Los cambios de título para las notificaciones de Trabajo, Puesto y Trabajador no se sincronizan. | Anteriormente, se agregó una relación de Título a las entidades Trabajo, Puesto y Trabajador. La sincronización de esta relación funciona para la sincronización de Human Resources con Dataverse, pero no funcionó para las notificaciones de Dataverse. Esto se ha solucionado. |
| 512275 | Eliminar las opciones de color de **Parámetros de permisos y ausencias**. | Ahora que los colores están definidos en el tipo de licencia, las opciones de colores ya no son necesarias en **Parámetros de permisos y ausencias**, por lo que se eliminaron. |
| 437112 | Texto de mensaje de error engañoso durante la asignación del puesto de empleado. | Se actualizó el mensaje de error al contratar a un trabajador e intentar asignarlo a un puesto que no está activo. Mensaje actualizado **El puesto especificado no está activo desde la fecha de inicio del empleo. Compruebe la duración de este puesto.** |
| 527816 | Problemas de rendimiento con la página **Tiempo libre**. | Se ha mejorado el rendimiento en la página **Tiempo libre**. |
| 523158 | BenefitPeriodMigrationUpgrade y BenefitPlanMigrationUpgrade no se están ejecutando. | Problemas resueltos con trabajos de migración de prestaciones relacionados con que **Período** y **Plan** no se ejecutan correctamente. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Aplicación Human Resources en Microsoft Teams | [Experiencia de bajas y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicación Human Resources en Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md) |
| Solicitudes y aprobaciones de flujo de trabajo mejoradas | [Mejoras en la experiencia de los flujos de trabajo de organización y administración de personal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opción de configuración de la lista de elementos de trabajo de puesto asignados a mí](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Integración con LinkedIn Talent Hub | [Integración con LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrar con LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
|Visión transversal de la licencia para responsables | [Visión transversal de la licencia de empleado para responsables](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parámetros de bajas y ausencias](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Proporcionar información adicional sobre saldos de bajas| [Proporcionar información adicional sobre saldos de bajas](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Administrar bajas de empleados](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| Los responsables pueden enviar solicitudes de contratación para puestos | [Los responsables pueden enviar una solicitud de contratación para vacantes](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Agregar una solicitud de contratación](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Perfil de candidato mejorado en la Administración de personal | [Perfil de candidato mejorado en la administración de personal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Agregar o editar un perfil de candidato](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Habilitar integraciones simplificadas con proveedores de contratación | [Habilitar integraciones simplificadas con proveedores de contratación](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Contratar candidatos de trabajo](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Próximamente

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]