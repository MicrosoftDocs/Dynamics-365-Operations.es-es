---
title: Novedades y cambios en Dynamics 365 Human Resources (16 de septiembre de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 16 de septiembre de 2020.
author: jcart1106
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-09-16
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf0e2d90b07cb488429311d04dfbc4d1d3520842
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800102"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-16-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (16 de septiembre de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las funciones que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3557. Los números entre paréntesis que aparecen en algunos encabezados hacen referencia a los números de soporte de Lifecycle Services (LCS) para referencia.

## <a name="included-in-this-release"></a>Se incluye en esta versión

-  [Vistas guardadas: disponibilidad general](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability)<br>- Para obtener más información, consulte [Vistas guardadas](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/saved-views). 

- El formulario **Acciones de puestos** tiene una cuadrícula de dimensiones actualizada y un nuevo cuadro de diálogo (469495).

- Si establece **Restringir el acceso a la información de los trabajadores** en Sí en **Acceso avanzado** > **Parámetros compartidos de recursos humanos**, los formularios de prestaciones solo mostrarán los trabajadores correspondientes (393384).

- Nuevas opciones de generación de calendarios en la entidad **WorkCalendar** (477055):<br>- Hora de finalización predeterminada<br>- Hora de inicio predeterminada<br>- Es viernes día laborable<br>- Es lunes día laborable<br>- Es sábado día laborable<br>- Es domingo día laborable<br>- Es jueves día laborable<br>- Es martes día laborable<br>- Es miércoles día laborable<br>- Id. de festivo de calendario laboral

- Ahora la entidad **LeaveBankTransactionV1** incluye el código de motivo (477823).

- Ahora puede guardar grabaciones de tareas (492923).

- Ahora los datos se publican correctamente desde **HCMWorkerContactEntity** (427620).

- Ahora la ficha desplegable **Compensación** se muestra para el tipo de trabajador contratista en el formulario **Acciones de trabajador** (482494).

- Ahora los campos **Nivel** y **Plan** son obligatorios si se establece **Compensación fija**. Si deja estos campos en blanco aparecerá un mensaje de error (482497).

- Ahora el campo **Tipo de plan** de **Prestaciones** es una lista desplegable (488768).

- Ahora los administradores de sistemas reciben una notificación si se elimina un campo personalizado de Recursos humanos (481408).

- Durante el proceso de despido de empleados, Recursos Humanos se comporta como se esperaba y no cambia la empresa seleccionada después de parecer bloqueada (479877). 

- Los administradores ya no pueden agregar una columna numérica mediante personalización (485317).

- Los administradores ya no pueden quitar el filtro de intervalo de datos de los números de identificación que venzan (485321).

- Cuando el campo **Notifica al puesto** está vacío, los detalles del puesto se muestran al pasar el cursor sobre la posición (433328).

- Ahora los empleados pueden ver la información del plan de prestaciones en autoservicio para empleados (481676).

- Ahora los empleados pueden ver todos los cursos registrados (429048).

- Ahora puede restringir las opciones de visualización para la página **Certificados profesionales**. Puede restringir las opciones de visualización a la entidad jurídica actual, por estado de trabajador y por tipo de trabajador (451501). 


## <a name="in-preview"></a>En vista previa

### <a name="human-resources-app-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para obtener más información, consulte:

- [Experiencia de bajas y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
- [Aplicación Human Resources en Teams](https://go.microsoft.com/fwlink/?linkid=2127841) en la documentación de Human Resources

### <a name="human-resources-app-in-teams-preview-features"></a>Características en vista previa (GB) de la aplicación Human Resources en Teams
 
-  **Notificaciones**: los remitentes y aprobadores de solicitudes de permisos se notificarán en la aplicación Human Resources en Teams. Los aprobadores pueden aprobar o rechazar solicitudes de tiempo libre. Los remitentes serán notificados si la solicitud fue aprobada o denegada. Para obtener más información, consulte:
   - [Experiencia de permisos y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
   - [Habilitar notificaciones para la aplicación Human Resources en Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#enable-notifications-for-the-human-resources-app-in-teams) en la documentación de Human Resources
   - [Activar o desactivar las notificaciones de Teams para usuarios individuales](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-teams-leave-app#turn-teams-notifications-on-or-off-for-individual-users) en la documentación de Human Resources
   - [Notificaciones de Teams](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#teams-notifications) en la documentación de Human Resources
   - [Ver el calendario de vacaciones de su equipo](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) en la documentación de Human Resources
 
- **Calendario de permisos del gerente**: los gerentes pueden ver los permisos aprobados y pendientes para sus subordinados directos en una vista de calendario. Esta vista proporciona un fácil reconocimiento de cuándo los miembros del equipo están fuera del trabajo. Para obtener más información, consulte:
   - [Experiencia de permisos y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
   - [Ver el calendario de vacaciones de su equipo](https://docs.microsoft.com/dynamics365/human-resources/hr-teams-leave-app#view-your-teams-leave-calendar) en la documentación de Human Resources

### <a name="configuration-option-to-position-work-items-assigned-to-me-list-477004"></a>Opción de configuración para posicionar la lista Elementos de trabajo asignados a mí (477004)

Ahora hay una nueva opción disponible para colocar a lista **Elementos de trabajo asignados a mí** en la columna de la derecha del panel de información. Con este cambio, todos los elementos de trabajo y las listas de tareas se muestran en la misma área. Habilite esta funcionalidad activando **(Versión preliminar) Mejoras en la experiencia del flujo de trabajo** en Administración de características. Para obtener más información acerca cómo activar las características de vista previa, consulte [Administrar características](hr-admin-manage-features.md).

Esta característica también promueve las opciones de flujo de trabajo que aparecen en los formularios de acciones del personal. Las opciones de flujo de trabajo también aparecen encima de la pestaña de acción rápida para un acceso rápido. Para obtener más información, consulte: 

- [Mejoras en la experiencia del flujo de trabajo de gestión de personal y organización](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) en el plan del segundo lanzamiento de versiones de 2020 de Dynamics 365

![Elementos de trabajo asignados a mí](./media/hr-workflow-work-items-assigned-to-me.png)

![Acceso rápido a elementos de flujo de trabajo](./media/hr-workflow-quick-access.png)

### <a name="leave-and-absence-calendar"></a>Calendario de bajas y ausencias

Esta versión incluye opciones de calendario adicionales para los calendarios de bajas y ausencias. Para más información, consulte [Ver calendarios de equipo y empresa](https://docs.microsoft.com/dynamics365/human-resources/hr-employee-self-service-calendar).

## <a name="coming-soon"></a>Próximamente

### <a name="checklist-entities-included-in-dataverse"></a>Lista de entidades incluidas en Dataverse

Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.

### <a name="benefits-management-reason-codes"></a>Códigos de motivo de la administración de prestaciones

Los códigos de motivo de la administración de prestaciones pronto se combinarán con los códigos de motivo existentes en Human Resources. Si creó códigos de motivo en la Administración de prestaciones que tienen más de 15 caracteres, debe cambiar el nombre del código de motivo en la Administración de prestaciones. Formulario de **Códigos de motivo** que tenga 15 caracteres o menos. Después de actualizar el nombre, el código de motivo aparecerá bajo el formulario de código de motivo existente en Administración de personal. Este cambio estará disponible en el futuro y no afectará la funcionalidad existente.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]