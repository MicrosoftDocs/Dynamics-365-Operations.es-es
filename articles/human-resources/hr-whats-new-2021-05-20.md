---
title: Novedades y cambios en Dynamics 365 Human Resources a 20 de mayo de 2021
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 20 de mayo de 2021.
author: marcelbf
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3a399e1c7ccbd85b58286ec4f3d294f80332c3fd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891303"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Novedades y cambios en Dynamics 365 Human Resources a 20 de mayo de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe las características que son nuevas, que se han cambiado o que vendrán próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4189.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Actualización de la plataforma 10.0.18 (42) | -- | [Platform updates para aplicaciones de la versión 10.0.18 de Finance and Operations (mayo de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| Aplicación Human Resources para Microsoft Teams ahora admite definiciones de medio día y capacidad de día dividido | -- | [Administrar solicitudes de bajas en Teams](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este artículo para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del artículo.

| Número del problema | Problema |  Description |
| --- | --- | --- |
| 583776 | La inscripción masiva de empleados en planes de vacaciones está provocando un error de registro duplicado | Este error se ha corregido con la última versión y las inscripciones al plan de licencia masiva deben procesarse correctamente. |
| 582263 | No se puede ejecutar el procesamiento de eventos de vida para todos los trabajadores a la vez | Cuando el campo **Trabajador** se deja en blanco para el procesamiento de eventos de vida, todos los trabajadores serán procesados. |
| 558383 | Beneficiario principal no marcado como 100% si no se selecciona la persona designada por defecto | El error se ha corregido para que el usuario solo tenga que seleccionar la alternancia del beneficiario principal.|
| 509404 | El análisis de la plantilla de departamento no tiene en cuenta el movimiento de empleados entre departamentos |Los análisis se han actualizado para incluir transferencias de empleados entre departamentos|
| 579420 | La función de congelación de columnas en cuadrículas aún no debería estar disponible | La función **Columnas de congelación en rejillas**, que no está disponible en Human Resources, se enumeró como disponible en Gestión de funciones. La función se ha eliminado de la lista de funciones para habilitar. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Soporte de campos personalizados en las reglas de idoneidad de gestión de prestaciones | [Soporte de campo personalizado para el procesamiento de idoneidad](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configurar reglas de elegibilidad](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Mejoras en la experiencia del flujo de trabajo de bajas y ausencias | [Mejoras en la experiencia del flujo de trabajo de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar permiso](hr-employee-self-service-request-time-off.md)|
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)|
| Auditoría de transacciones de acumulación de bajas | - | [Auditoría de transacciones de acumulación de bajas](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
|  Habilitar a un administrador de ausencias para administrar la licencia | [Habilitar a un administrador de ausencias para administrar la licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
