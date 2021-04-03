---
title: Novedades y cambios en Dynamics 365 Human Resources (6 de octubre de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 6 de octubre de 2020.
author: jcart1106
manager: tfehr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 330b037e2ba50ed090fd41b0990d6cf37d9d8b01
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463559"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (6 de octubre de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources. Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.3636.

### <a name="new-features"></a>Nuevas características

La siguiente característica estará disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Información adicional sobre los calendarios de bajas | [Proporcionar información adicional sobre las vistas de calendarios de bajas](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [Ver calendario de equipo y empresa](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

>[!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir | Descripción |
| --- | --- | --- |
| 448806 | **Tipo de identificación predeterminado** se exporta como **RecID** en los parámetros de HCM | Este cambio en la entidad de parámetros de Human Resources agrega una columna adicional que muestra el **Tipo de identificación predeterminado**. |
| 492923 | Las grabaciones de tareas no se guardan en Lifecycle Services (LCS) | Ahora las grabaciones de tareas se pueden guardar en LCS. |
| 429950 | La compensación fija no vence correctamente al cambiar de cargo | Al cambiar el cargo de un trabajador en la página **Trabajador de transferencia**, la fecha de finalización de la compensación se fijó un día antes del final del cargo. La fecha de finalización de la compensación ahora es la misma que la fecha de finalización del cargo. |
| 467214 | **Análisis de asalariados** solo se muestra si la opción **Nombre de conversión de índice salarial** está establecida en **Anual** | Los índices salariales de asalariados que tengan un nombre distinto de **Anual** no se mostraban en Análisis de compensación. Con esta actualización, Análisis de compensación usa todas las conversiones de índice salarial. Al ejecutar los informes utilizando **Por hora** o **Salario**, cualquier conversión de índice salarial que utilice un período que no sea por hora se incluye en el filtro **Salario**. Solo los índices salariales con un período **Por hora** se incluyen en el filtro **Por hora**. |
| 482464 | Al ver **Revisiones**, la vista **Detalles** no cambia a la vista de cuadrícula después de aplicar un filtro | Después de aplicar un filtro, la cuadrícula de revisiones se muestra como se esperaba. |
| 483184 | Recursos humanos no genera acumulaciones de licencias cuando se selecciona **Base de nivel** como la **Fecha inicial ajustada** en el registro **Inscripción en baja** |La **Fecha inicial ajustada** se rellena y se utiliza al generar acumulaciones de licencias.  |
| 509731 | La solicitud de tiempo libre para futuros trabajadores despedidos causa problemas si solicitan tiempo libre después de la fecha de terminación | Ahora se pueden enviar solicitudes de tiempo libre para los empleados con una fecha de terminación futura, siempre que la solicitud sea anterior a la fecha de terminación. |
| 510716 | El Análisis de compensación incluye a empleados y empleadas en el **Pago promedio por hora para hombres** | En Análisis de compensación, el **Pago promedio por hora para hombres** del **Análisis demográfico de compensación** incluía el salario medio de las empleadas. Ahora solo incluye a los empleados del género masculino. |
| 511348 | El autoservicio de prestaciones solo debe mostrar los planes de prestaciones válidos desde hoy hasta el final del período de prestaciones | Los planes de prestaciones vencidos se mostraban a los empleados en la página **Inscripción en prestaciones**. Esta corrección elimina estos planes. |
| 512706 | Configure los siguientes campos para que sean de solo lectura:<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | Los botones **Agregar** y **Quitar** para los detalles de las dimensiones se habilitaron incorrectamente después de que se completara la acción. Esta actualización de la página **Detalle de acción de puesto** hace que los campos no se puedan editar una vez finalizada la acción. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Aplicación Human Resources en Microsoft Teams | [Experiencia de bajas y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicación Human Resources en Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md) |
| Solicitudes y aprobaciones de flujo de trabajo mejoradas | [Mejoras en la experiencia de los flujos de trabajo de organización y administración de personal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opción de configuración de la lista de elementos de trabajo de puesto asignados a mí](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entidades virtuales disponibles Dataverse para Human Resources | [Expandir datos básicos de Dynamics 365 Human Resources en Dataverse](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurar entidades virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>Próximamente

Las siguientes características nuevas están programadas para versiones futuras:

- **Entidades de lista de comprobación incluidas en Dataverse**: entidades de lista de comprobación para los procesos de Incorporación, Retirada, Transferencias y Empresa; pronto estarán disponibles en Dataverse.

- **Códigos de motivo de la administración de prestaciones**: estos códigos pronto se combinarán con los códigos de motivo existentes en Human Resources. Si creó códigos de motivo en la Administración de prestaciones que tienen más de 15 caracteres, debe cambiar el nombre del código de motivo en la Administración de prestaciones. Formulario de **Códigos de motivo** que tenga 15 caracteres o menos. Después de actualizar el nombre, el código de motivo aparecerá bajo el formulario de código de motivo existente en Administración de personal. Este cambio estará disponible en el futuro y no afectará la funcionalidad existente.

- **Vínculos personalizados en Autoservicio para directores**: para ayudar a los directores estamos ampliando la funcionalidad del autoservicio para directores. Estamos agregando la capacidad de agregar vínculos personalizados en la pestaña **Mi equipo**. Esta característica es similar a la función de vínculos personalizados en la pestaña **Mi información** del autoservicio para empleados. Para obtener más información, consulte [Vínculos personalizados en el autoservicio para directores](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service).

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2019](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Recursos adicionales

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]