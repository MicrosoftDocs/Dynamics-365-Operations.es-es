---
title: Novedades y cambios en Dynamics 365 Human Resources (03 de septiembre de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 3 de septiembre de 2020.
author: andreabichsel
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d1cc3a64e6c345df7727f5ca7336821388c9dbcf
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063552"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-3-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (3 de septiembre de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este tema describe las funciones que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3504. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte para referencia de Lifecycle Services (LCS).

Para obtener más información sobre las próximas funciones de Recursos humanos, consulte [Visión general del segundo lanzamiento de versiones de 2019 de Dynamics 365 Human Resources](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/). Para obtener más información sobre el proceso de actualización de Human Resources, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

## <a name="in-this-release"></a>En este lanzamiento

### <a name="new-default-financial-dimensions-grid-and-dialog-pattern-throughout-human-resources-469495"></a>Nueva cuadrícula de dimensiones financieras y patrón de diálogo predeterminados en Human Resources (469495)

El nuevo patrón para las dimensiones financieras ya está disponible en las siguientes áreas:

- Acciones de posición (formulario: **HcmPositionActionDetail**)
- Códigos de ingresos de nómina (formulario: **PayrollEarningCode**)

### <a name="entries-dont-appear-in-company-leave-calendar-if-leave-and-absence-calendar-enhancements-arent-enabled-484406"></a>Las entradas no aparecen en el calendario de ausencias de la empresa si las mejoras del calendario de permisos y ausencias no están habilitadas (484406)

Esta versión corrige un problema por el cual las entradas de permisos no se muestran en el calendario de permisos de la empresa. Este problema solo ocurre cuando la opción de administración de características **Mejoras en el calendario de permisos y ausencias** no está habilitada.

### <a name="benefitplanemployeeentity-issue-467597"></a>Problema BenefitPlanEmployeeEntity (467597)

Esta versión corrige un problema con la entidad **BeneficiosPlanEmpleado**. Al importar inscripciones de trabajadores, el **Código de cobertura** y el **Código de tipo de plan** se han configurado ahora correctamente. Este problema hace que los planes de beneficios para empleados se muestren incorrectamente en el formulario **Plan de beneficios para trabajadores** y en los formularios **Inscripción abierta** en el Autoservicio para empleados.

### <a name="electronic-file-1094-c-output-missing-letter-in-xml-435190"></a>Falta la letra de salida del archivo electrónico 1094-C en XML (435190)

Este cambio corrige un problema con el archivo de salida 1094-C al que le falta un carácter necesario al enviarlo al IRS.

### <a name="employee-variable-compensation-table-mapped-to-fixed-compensation-form-476117"></a>Tabla de compensación variable de empleados asignada a formulario de compensación fija (476117)

Este cambio alinea los campos de compensación fija con el formulario de compensación fija. Los campos de compensación variable ahora solo están disponibles con el formulario de compensación variable.

### <a name="leave-requests-allowed-before-enrollment-if-that-leave-type-has-a-negative-minimum-balance-469917"></a>Solicitudes de permiso permitidas antes de la inscripción si ese tipo de permiso tiene un saldo mínimo negativo (469917)

Este cambio prohíbe especificar solicitudes de permiso antes de inscribirse en el plan, incluso si la inscripción tiene un saldo mínimo negativo. Solo puede especificar o enviar solicitudes cuando el plan está activo.

### <a name="document-templates-dont-download-457279"></a>Las plantillas de documentos no se descargan (457279)

Con este cambio, ahora puede descargar todas las plantillas de documentos. 

### <a name="data-displays-as-column-headers-instead-of-rows-for-the-pay-rate-field-in-the-compensation-plan-report-476077"></a>Los datos se muestran como encabezados de columna en lugar de filas para el campo Tasa de pago en el informe del plan de compensación (476077)

El informe de análisis ahora muestra la información correcta para **Tarifa de pago**.

## <a name="in-preview"></a>En vista previa

### <a name="human-resources-application-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para obtener más información, consulte:

- [Experiencia de bajas y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
- [Aplicación Human Resources en Teams](./hr-admin-teams-leave-app.md) en la documentación de Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Características en vista previa (GB) de la aplicación Human Resources en Teams
 
-  **Notificaciones**: los remitentes y aprobadores de solicitudes de permisos se notificarán en la aplicación Human Resources en Teams. Los aprobadores podrán aprobar o rechazar solicitudes de tiempo libre. Los remitentes serán notificados si la solicitud fue aprobada o denegada. Para obtener más información, consulte:
   - [Experiencia de permisos y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
   - [Habilitar notificaciones para la aplicación Human Resources en Teams](./hr-admin-teams-leave-app.md#enable-notifications-for-the-human-resources-app-in-teams) en la documentación de Human Resources
   - [Activar o desactivar las notificaciones de Teams para usuarios individuales](./hr-admin-teams-leave-app.md#turn-teams-notifications-on-or-off-for-individual-users) en la documentación de Human Resources
   - [Notificaciones de Teams](./hr-teams-leave-app.md#respond-to-teams-notifications) en la documentación de Human Resources
   - [Ver el calendario de vacaciones de su equipo](./hr-teams-leave-app.md#view-your-teams-leave-calendar) en la documentación de Human Resources
 
- **Calendario de permisos del gerente**: los gerentes podrán ver los permisos aprobados y pendientes para sus subordinados directos en una vista de calendario. Esta vista proporciona un fácil reconocimiento de cuándo los miembros del equipo están fuera del trabajo. Para obtener más información, consulte:
   - [Experiencia de permisos y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
   - [Ver el calendario de vacaciones de su equipo](./hr-teams-leave-app.md#view-your-teams-leave-calendar) en la documentación de Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opción de configuración para posicionar la lista Elementos de trabajo asignados a mí (477004)

Ahora hay una nueva opción disponible para colocar a lista **Elementos de trabajo asignados a mí** en la columna de la derecha del panel de información. Con este cambio, todos los elementos de trabajo y las listas de tareas se muestran en la misma área. Habilite esta funcionalidad activando **(Versión preliminar) Mejoras en la experiencia del flujo de trabajo** en Administración de características. Para obtener más información acerca cómo activar las características de vista previa, consulte [Administrar características](hr-admin-manage-features.md).

Esta característica también promueve las opciones de flujo de trabajo que aparecen en los formularios de acciones del personal. Las opciones de flujo de trabajo también aparecen encima de la pestaña de acción rápida para un acceso rápido. Para obtener más información, consulte: 

- [Mejoras en la experiencia del flujo de trabajo de gestión de personal y organización](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) en el plan del segundo lanzamiento de versiones de 2020 de Dynamics 365

![Mis elementos de trabajo.](./media/hr-workflow-work-items-assigned-to-me.png)

![Acceso rápido a elementos de flujo de trabajo.](./media/hr-workflow-quick-access.png)

## <a name="coming-soon"></a>Próximamente

### <a name="checklist-entities-included-in-dataverse"></a>Lista de entidades incluidas en Dataverse

Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.

### <a name="benefits-management-reason-codes"></a>Códigos de motivo de la administración de prestaciones

Los códigos de motivo de la administración de prestaciones pronto se combinarán con los códigos de motivo existentes en Human Resources. Si creó códigos de motivo en la Administración de prestaciones que tienen más de 15 caracteres, debe cambiar el nombre del código de motivo en la Administración de prestaciones. Formulario de **Códigos de motivo** que tenga 15 caracteres o menos. Después de actualizar el nombre, el código de motivo aparecerá bajo el formulario de código de motivo existente en Administración de personal. Este cambio estará disponible en el futuro y no afectará la funcionalidad existente.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
