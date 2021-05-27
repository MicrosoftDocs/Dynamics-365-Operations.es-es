---
title: Novedades y cambios en Dynamics 365 Human Resources a 3 de mayo de 2021
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 3 de mayo de 2021.
author: marcelbf
ms.date: 05/03/2021
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
ms.author: marcelbf
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 944d5794bb535faa18b4f2de8b5382ebfb9bc2ce
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022072"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Novedades y cambios en Dynamics 365 Human Resources a 3 de mayo de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4140.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Agregue una barra de información cuando se creen eventos de vida. | - | Cuando cree un evento de vida, la barra de información muestra un mensaje que indica el tipo de evento de vida creado.

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir |  Descripción |
| --- | --- | --- |
| 559312 |  El nivel no se muestra al crear un plan de compensación fijo para un empleado. |  Cuando hay una discrepancia de zona horaria entre la zona horaria del usuario y la zona horaria de la empresa, no se puede leer el nivel de compensación en el trabajo. La consulta se ha actualizado para capturar información según la hora UTC. |
| 573676  | No se puede agregar un nuevo período en el formulario **Plan de prestaciones**. | Se ha actualizado el formulario para que el botón **Nuevo** se habilite en la ficha desplegable **Período** en **Planes de prestaciones**. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Mejoras en la experiencia del flujo de trabajo de bajas y ausencias | [Mejoras en la experiencia del flujo de trabajo de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar permiso](hr-employee-self-service-request-time-off.md)|
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)|
| Auditoría de transacciones de acumulación de bajas | - | [Auditoría de transacciones de acumulación de bajas](hr-leave-and-absence-accrue.md#preview-leave-accrual-transaction-auditing)|

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
