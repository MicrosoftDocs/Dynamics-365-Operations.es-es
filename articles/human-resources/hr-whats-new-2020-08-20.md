---
title: Novedades y cambios en Dynamics 365 Human Resources (20 de agosto de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 20 de agosto de 2020.
author: andreabichsel
ms.date: 08/20/2020
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
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a97997212a090f141c7280f7e48fd116a1f31481
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062170"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (20 de agosto de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3478. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte para referencia de Lifecycle Services (LCS).

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>Mostrar información de permisos de ausencia próximos y pendientes en tarjetas en el espacio de trabajo Personas

Las opciones de solicitud de bajas pendientes y próximas ya están disponibles en las tarjetas de Permisos y ausencias del espacio de trabajo **Personas**.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>El campo Privado no tiene el valor Sí de forma predeterminada para el rol de empleado en el autoservicio de empleados (477106)

El campo **Privado** ahora tiene como valor predeterminado **Sí** cuando los empleados agregan nuevos registros de dirección a través de la página **Informacion personal** del Autoservicio para empleados. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>La ficha desplegable Candidatos a contratar de Gestión de personal muestra un recuento incorrecto de candidatos (470110)

La página **Gestión de personal** ahora muestra con precisión el número de candidatos a contratar. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>No se puede introducir la enfermedad para empleados despedidos cuando la acumulación se establece en cero (446195)

Las transacciones de bajas ahora están permitidas para los empleados que se despidan en el futuro y la acumulación se establece en cero. Las transacciones de bajas se pueden introducir hasta la fecha de terminación del empleado. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>La adición de campos personalizados al nuevo formulario Trabajador deshabilita los campos en el Panel Acciones para Administrar bajas (473314)

Las opciones del Panel Acciones en el nuevo formulario **Trabajador** en **Gestionar baja** ya no se deshabilitarán si se han agregado campos personalizados al nuevo formulario **Trabajador**.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>Hacer obligatorio el campo Dejar comentario permite enviar una solicitud de baja cuando no se introduce ningún comentario (473543)

Los campos de comentarios ahora pueden ser obligatorios y las solicitudes de baja respetan esta configuración. Los campos obligatorios son una Característica en vista previa (GB).

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidad DMF disponible para suspensiones acumuladas

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="in-preview"></a>En vista previa

### <a name="mandatory-fields"></a>Campos obligatorios

Ahora puede hacer que los campos sean obligatorios mediante las características de personalización de Recursos Humanos. Esta característica requiere **Vistas guardadas**. Para obtener más información sobre las vistas guardadas, consulte:

- [Vistas guardadas: disponibilidad general](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) en el plan del segundo lanzamiento de versiones de Dynamics 365 en 2020
- [Crear formularios que usan completamente las vistas guardadas](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para obtener más información, consulte:

- [Experiencia de bajas y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
- [Aplicación Human Resources en Teams](./hr-admin-teams-leave-app.md)

## <a name="coming-soon"></a>Próximamente

### <a name="human-resources-app-in-teams-preview-features"></a>Características en vista previa (GB) de la aplicación Human Resources en Teams
 
-  **Notificaciones**: los remitentes y aprobadores de solicitudes de permisos se notificarán en la aplicación Human Resources en Teams. Los aprobadores podrán aprobar o rechazar las solicitudes de permisos, y los remitentes recibirán notificación de si la solicitud fue aprobada o denegada.
 
- **Calendario de permisos del gerente**: los gerentes podrán ver los permisos aprobados y pendientes para sus subordinados directos en una vista de calendario. Esta vista proporciona un fácil reconocimiento de cuándo los miembros del equipo están fuera del trabajo.

### <a name="checklist-entities-included-in-dataverse"></a>Lista de entidades incluidas en Dataverse

Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.

## <a name="known-issues"></a>Problemas conocidos

Es posible que el espacio de trabajo **Administración de características** muestre características que están deshabilitadas como características en versión preliminar cuando estén disponibles de forma generalizada. A continuación se muestra una lista de características disponibles de forma generalizada que indican un estado incorrecto. 

- Administración de prestaciones
- Gestión de casos
- Registro de base de datos (auditoría)
- Acumulación de bajas para una sola empresa o un solo plan
- Suspensión de acumulación de permisos y ausencias
- Código de motivo de ajuste de saldo y comentario
- Comprar y vender bajas
- Calendario de bajas y ausencias
- Reglas transferibles de baja
- Auditoría de acumulación de bajas
- Eliminación de acumulaciones de bajas
- Redondeo de acumulación de bajas
- Configurar varios tipos de baja en un solo plan de bajas
- Actualizar mejoras de permiso
- Usar FTE de un empleado para acumulaciones
- Vista de compensación entre empresas
- Imprimir evaluaciones del rendimiento
- Correcciones de vacaciones de acumulación de bajas

### <a name="benefit-plan-employee-entity"></a>Entidad de empleados del plan de prestaciones 

Recientemente hemos descubierto dos problemas relacionados con la entidad **BenefitsPlanEmployee**. Al importar inscripciones de trabajadores, el **Código de cobertura** y el **Código de tipo de plan** se están configurando incorrectamente. Este problema hace que los planes de beneficios para empleados se muestren incorrectamente en el formulario **Plan de beneficios para trabajadores** y en el formulario **Inscripción abierta** en el Autoservicio para empleados. Este problema también puede afectar la capacidad del empleado para seleccionar planes en el Autoservicio del empleado. Actualmente no existe una solución alternativa. Estamos tratando esto como una solución de alta prioridad y la implementaremos con nuestra próxima versión.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]