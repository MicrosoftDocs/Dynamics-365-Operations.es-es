---
title: Novedades y cambios en Dynamics 365 Human Resources (26 de septiembre de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 26 de septiembre de 2020.
author: jcart1106
ms.date: 09/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f78201585101e2848eded69e03d5eb4c22d7e9a
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9066774"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-26-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (26 de septiembre de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este artículo describe las características que son nuevas, que se han cambiado o que vendrán próximamente en Dynamics 365 Human Resources. Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.3589-hf.3.

### <a name="new-features"></a>Nuevas características

La siguiente característica estará disponible de forma generalizada en esta versión:

- **Platform update 10.0.13 ya está disponible**: para obtener más información sobre la actualización, consulte [Actualizaciones de la plataforma para aplicaciones de la versión 10.0.13 de finanzas y operaciones (octubre de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-13.md).

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este artículo para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del artículo.

| Número del problema | Problema | Description |
| --- | --- | --- |
| 469495 | Actualizar cuadro de diálogo y cuadrícula de dimensiones financieras predeterminadas | El nuevo cuadro de diálogo y la nueva cuadrícula de dimensiones financieras se han actualizado en Human Resources. |
| 474887 | El elemento de trabajo de solicitud de baja abre un vínculo incorrecto en una decisión manual | Cuando una configuración de flujo de trabajo contiene una decisión manual, navegar a la solicitud de baja desde **Elementos de trabajo asignados a mí** abre el vínculo incorrecto, que muestra un formulario o una solicitud de baja en blanco creados por el usuario actual, en lugar del que se le asignó para la decisión manual. |
| 474962 | La entidad de parámetros de bajas y ausencias tiene campos con etiquetas ambiguas | Se han actualizado las etiquetas de la entidad de parámetros de bajas y ausencias para que estén más claras. |
| 481401 | El procesamiento de acumulación se bloquea cuando la base de la fecha de acumulación es posterior a la fecha de inicio de acumulación y al final de mes | El procesamiento de acumulación se ha actualizado para que no haya demora cuando la base de la fecha de acumulación es posterior a la fecha de inicio de la acumulación y al final del mes. |
| 447167 | Las listas de registros que vencen incluyen los trabajadores inactivos | La pestaña **Registros que vencen** de **Administración de personal** incluía trabajadores inactivos. Ahora solo incluye trabajadores activos. |
| 486840 | Se abre una solicitud de excedencia incorrecta en **Elementos de trabajo asignados a mí** | Al seleccionar una solicitud de excedencia desde **Elementos de trabajo asignados a mí** ya no se abre la solicitud de excedencia más reciente asignada al usuario actual. |
| 506868 | El campo **Título** de Dataverse no está establecido para la entidad **Puesto de trabajo** | El campo **Título** de las entidades **Trabajo** y **Puesto de trabajo** se muestran como no especificadas. Ahora se muestra el campo **Título**. |
| 430359 | No se puede acceder a las tareas de la lista de comprobación de retirada con los roles de director y empleado asignados | Los trabajadores con una fecha de terminación futura no podían acceder a las tareas de su lista de comprobación si solo tenían un rol de empleado o director. Ahora, los usuarios que solo tengan un rol de empleado o director pueden acceder a las tareas de retirada con una fecha de terminación futura. |
| 458102 | El nuevo empleado no aparece en la entidad **Información de nómina de trabajadores** cuando se crea | Los nuevos empleados se incluyen en la entidad de información de nómina de trabajadores sin tener que abrir la información de nómina del empleado antes de exportar la entidad. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Aplicación Human Resources en Microsoft Teams | [Experiencia de bajas y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicación Human Resources en Teams](./hr-admin-teams-leave-app.md)<br>[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md) |
| Solicitudes y aprobaciones de flujo de trabajo mejoradas | [Mejoras en la experiencia de los flujos de trabajo de organización y administración de personal](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opción de configuración de la lista de elementos de trabajo de puesto asignados a mí](./hr-whats-new-2020-09-03.md#configuration-option-to-position-work-items-assigned-to-me-list-477004) |

## <a name="coming-soon"></a>Próximamente

La siguiente característica nueva está programada para una versión futura:

- [Vínculos personalizados en el autoservicio para directores](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service)

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2019](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Recursos adicionales

[Novedades y cambios de Human Resources](hr-admin-whats-new.md)
[Visión general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2020](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)
[Proceso de actualización](hr-admin-setup-update-process.md)
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
