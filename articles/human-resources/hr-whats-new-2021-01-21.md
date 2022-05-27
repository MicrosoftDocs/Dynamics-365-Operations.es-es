---
title: Novedades y cambios en Dynamics 365 Human Resources del 21 de enero de 2021
description: Este tema describe las características nuevas o modificadas en Microsoft Dynamics 365 Human Resources para el 21 de julio de 2021.
author: marcelbf
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: be50596cd64839ba82b847b2fabb0f46dc749a3f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686866"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Novedades y cambios en Dynamics 365 Human Resources del 21 de enero de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.3866.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Platform update 10.0.16(40) | -- | [Platform updates para aplicaciones de la versión 10.0.16 de Finance and Operations (febrero de 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16.md) |
| Solicitudes y aprobaciones de flujo de trabajo mejoradas | [Mejoras en la experiencia de los flujos de trabajo de organización y administración de personal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opción de configuración de la lista de elementos de trabajo de puesto asignados a mí](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Actualizaciones de cumplimiento de la Ley del Cuidado de salud asequible (ACA) en el Formulario 1095-C, Formulario 1095-B e informes electrónicos en prestaciones heredadas | -- | -- | 
| Ahora la administración de prestaciones admite informes de cumplimiento de ACA para entidades jurídicas con sede en EE. UU. | -- | [Generar informes de ACA en la Administración de prestaciones](hr-benefits-management-aca-reports.md) |
| Ahora la Administración de prestaciones tiene niveles de tasa de prestación y entidades de doble nivel de tasa de prestación expuestas  | -- | -- |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir |  Descripción |
| --- | --- | --- |
| 533079 | Error de navegación "Se llamó incorrectamente al formulario" al intentar analizar las deducciones. | Error corregido al ver las deducciones de las prestaciones con la vista **A partir de la fecha**. |
| 543641 | El código postal no se rellena en los informes electrónicos.  | Se ha corregido un error interno en el código postal que no aparecía en los informes electrónicos de la ACA para la Administración de prestaciones cuando el código de cobertura va de la M a la Q. |
| 542815 | La pantalla de contacto personal en el autoservicio para empleados permite a los empleados ver los contactos personales de otros. | Se ha corregido un error por el que el formulario **Editar** para contactos personales de autoservicio de empleados no restringía su consulta lo suficiente como para garantizar que solo se recuperara un único contacto personal individual, lo que permitía a un usuario utilizar métodos abreviados de teclado para ver los contactos de otras personas. |
| 536157 | No se puede abrir la página **Integración de Microsoft Dataverse** en la administración del sistema a causa de la llamada IsVirtualEntityPackageInstalled(). | El problema impide que se cargue la página **Integración de Microsoft Dataverse** en Human Resources. |
| 533079 | Error de navegación "Se llamó incorrectamente al formulario" al intentar analizar las deducciones. | Se ha corregido un error que se producía en el formulario **Deducciones** para la Administración de prestaciones cuando se ve **A partir de la fecha**. |
| 537264 | Falta la ficha desplegable **Información personal** del registro del candidato. | Ahora la información personal del candidato está disponible en el registro del candidato. |
| 537267 | No se muestra **Experiencia profesional** en los registros internos de candidatos. | Ahora la ficha desplegable **Experiencia profesional** se muestra en los registros internos de los candidatos. Anteriormente, si el candidato era interno, **Experiencia profesional** se reemplazaba con **Historial de empleo**, que es el historial laboral del candidato dentro de la organización. Ambos son aplicables y deben mostrarse para los candidatos internos. |
| 537067 | No se muestra **Permitir contacto con empresa**. | Se ha agregado el control **Permitir contacto con empresa** al panel **Editar experiencia profesional** para un registro de candidato. |
| 525957 | **Estado de candidato** no actualiza los candidatos internos cuando se completa la transferencia. | Cuando se completa una transferencia (se selecciona el botón **Cambiar puesto** o **Continuar** en la página **Transferir trabajador a una nueva asignación de puesto**), el valor de **Estado** en el registro del candidato debe cambiar a **Contratado**. |
| 537051 | Los símbolos de divisa para la rupia india y la lira turca no se sincronizan correctamente con Dataverse | Ahora los símbolos de la rupia india y la lira turca se sincronizan correctamente con Dataverse. |
| 534846 | Las tablas de contratación deben estar habilitadas para la Administración de datos. | Ahora las nuevas tablas creadas para las solicitudes de contratación y los candidatos están habilitadas para Administración de datos. Esto permite habilitar el seguimiento de cambios para las tablas, habilitando el seguimiento de cambios de OData en las tablas virtuales de Dataverse. |
| 533474 | Se ha corregido una referencia que falta a Microsoft.SqlServer.XEvent.dll. | Las excepciones de carga de ensamblado para Microsoft.SqlServer.XEvent.dll impedían la configuración de las tablas virtuales de Dataverse en algunos entornos. |
| 481122 | El espacio de trabajo **Personas** muestra puestos retirados. | Se mostraban puestos retirados como vacantes en el espacio de trabajo **Personas**. Ya no se muestran los puestos retirados. | 
| 541978 | Agregue la dirección de correo electrónico principal a la entidad BaseWorker. | Este cambio agregó la dirección de correo electrónico principal del trabajador a HcmWorkerBaseEntity. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Aplicación Human Resources en Microsoft Teams | [Experiencia de bajas y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicación Human Resources en Teams](./hr-admin-teams-leave-app.md)<br>[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md) |
| Integración con LinkedIn Talent Hub | [Integración con LinkedIn Talent Hub](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrar con LinkedIn Talent Hub](./hr-admin-integration-linkedin.md) |
| Visión transversal de la licencia para responsables | [Visión transversal de la licencia de empleado para responsables](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parámetros de bajas y ausencias](./hr-leave-and-absence-parameters.md) |
|Proporcionar información adicional sobre saldos de bajas| [Proporcionar información adicional sobre saldos de bajas](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Administrar bajas de empleados](./hr-leave-and-absence-manage-employee-leave.md) |
| Los responsables pueden enviar solicitudes de contratación para puestos | [Los responsables pueden enviar una solicitud de contratación para vacantes](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Agregar una solicitud de contratación](./hr-personnel-recruit.md#add-a-recruiting-request) |
| Perfil de candidato mejorado en la Administración de personal | [Perfil de candidato mejorado en la administración de personal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Agregar o editar un perfil de candidato](./hr-personnel-recruit.md#add-or-edit-a-candidate-profile) |
| Habilitar integraciones simplificadas con proveedores de contratación | [Habilitar integraciones simplificadas con proveedores de contratación](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Contratar candidatos de trabajo](./hr-personnel-recruit.md) |

## <a name="coming-soon"></a>Próximamente
| Característica | Detalles |
| --- | --- |
| Confirmación por correo electrónico para inscripción en prestaciones | Esta característica proporcionará la opción de enviar un correo electrónico de confirmación a los empleados cuando comprueben las experiencia de inscripción de prestaciones en el autoservicio para empleados. Para obtener más información, consulte [Configurar parámetros de Administración de prestaciones por empresa](hr-benefits-setup-parameters-per-company.md). |
| Las aptitudes introducidas por un director para sus empleados se pueden aprobar automáticamente mediante un flujo de trabajo | Próximamente. |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Actualizaciones de terminología para Microsoft Dataverse

Desde noviembre de 2020, el nombre de Common Data Service pasa a ser [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Vea el [anuncio oficial](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) en el blog de Power Apps para obtener más información. Además de este cambio de nombre, se ha actualizado parte de la terminología de Dataverse. Por ejemplo, *entidad* es ahora *tabla* y *campo* es ahora *columna*. Para más información, consulte [Actualizaciones de terminología](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

En esta versión, se ha actualizado la terminología relacionada con la integración de Dynamics 365 Human Resources con Dataverse en toda la aplicación para reflejar estos cambios. Por ejemplo, el formulario **Integración de Common Data Service** es ahora **Integración de Microsoft Dataverse**.

Para obtener más información sobre la integración de Dynamics 365 Human Resources con Microsoft Dataverse, consulte [Configurar la integración de Microsoft Dataverse](./hr-admin-integration-common-data-service.md) y [Configurar las tablas virtuales de Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]