---
title: Novedades y cambios en Dynamics 365 Human Resources, 22 de febrero de 2021
description: Este tema describe las características nuevas o modificadas en Microsoft Dynamics 365 Human Resources para el 22 de febrero de 2021.
author: marcelbf
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-02-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 53e9c42f718665165be97e5022a9e767b0436e59
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802224"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-22-2021"></a>Novedades y cambios en Dynamics 365 Human Resources, 22 de febrero de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.3988.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Aplicación Dynamics 365 Human Resources para Microsoft Teams | [Experiencia de bajas y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicación Human Resources en Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Administrar solicitudes de bajas en Teams](hr-teams-leave-app.md) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir |  Descripción |
| --- | --- | --- |
| 529994 | Modificar el campo **Conocido como** en el formulario **Trabajador** no desencadena una actualización de Dataverse | Se solucionó un problema donde Dataverse no se actualiza cuando el campo **Conocido como** se actualiza en el formulario **Trabajador**. |
| 532651 | El informe de PBI de análisis de compensación no utiliza la conversión de moneda al calcular métricas para todas las empresas | Se solucionó un problema por el cual el informe PBI de análisis de compensación no realizaba correctamente las conversiones de moneda. |
| 552226 | El procesamiento de eventos de vida cierra y reabre planes varias veces para un evento de vida único  | Se solucionó un problema por el cual un empleado está en varias entidades legales y ocurre un evento de vida, se genera un registro de evento de vida para cada entidad legal en la que se encuentra el empleado. Al procesar eventos de la vida, se debe seleccionar la entidad legal a procesar. Sin embargo, la lógica de procesamiento no se limita a esta entidad legal. En su lugar, procesa para todas las entidades legales y cierra y vuelve a abrir los planes en la entidad legal seleccionada. Esta acción es un evento de vida para procesar varias veces en la misma entidad legal, lo que resulta en múltiples cierres / reaperturas de cada plan afectado por el evento de vida. |
| 518064 | Solo un dependiente seleccionado en planes elegibles cuando más de uno están marcados como designados predeterminados | Se solucionó un problema por el cual varios designados predeterminados no se seleccionaban automáticamente en los planes elegibles. Ahora también puede designar un beneficiario principal para un contacto personal. El beneficiario principal figura como 100% en los planes elegibles cuando hay múltiples beneficiarios. |
| 552365 | Los trabajos de exportación de Traiga su propia base de datos (BYOD) fallan después de actualizar a la actualización de la plataforma 40 | Se solucionó un problema por el cual las exportaciones BYOD fallaban después de que la actualización de la plataforma 40 se aplicaba al entorno. |
| 547123 | Limite el número de tareas consultadas en la lista de tareas pendientes en el panel | El número de tareas que se muestra en la lista de tareas pendientes ahora está limitado a 15 para solucionar un problema de rendimiento causado por un número excesivo de tareas que intentan cargarse. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Visión transversal de la licencia para responsables | [Visión transversal de la licencia de empleado para responsables](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parámetros de bajas y ausencias](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Restringir a los empleados para que no editen los detalles de los contactos comerciales | [Restringir a los empleados para que no editen los detalles de los contactos comerciales](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restringir la edición de información personal](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
| Las aptitudes introducidas por un director para sus empleados se pueden aprobar automáticamente mediante un flujo de trabajo | Próximamente. |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Actualizaciones de terminología para Microsoft Dataverse

Desde noviembre de 2020, el nombre de Common Data Service pasa a ser [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Vea el [anuncio oficial](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) en el blog de Power Apps para obtener más información. Con este cambio de nombre, se ha actualizado parte de la terminología de Dataverse. Por ejemplo, *entidad* es ahora *tabla* y *campo* es ahora *columna*. Para más información, consulte [Actualizaciones de terminología](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

En esta versión, se ha actualizado la terminología relacionada con la integración de Dynamics 365 Human Resources con Dataverse en toda la aplicación para reflejar estos cambios. Por ejemplo, el formulario **Integración de Common Data Service** es ahora **Integración de Microsoft Dataverse**.

Para obtener más información sobre la integración de Dynamics 365 Human Resources con Microsoft Dataverse, consulte [Configurar la integración de Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) y [Configurar las tablas virtuales de Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="updates-to-service-deployment"></a>Actualizaciones de la implementación del servicio

A partir de la versión del 22 de febrero de 2021, estamos ajustando nuestra implementación de actualizaciones de servicios regionales. Los ajustes incluirán la rotación del orden en el que las regiones globales reciben actualizaciones para el servicio de Recursos Humanos y modificaciones en el tiempo de espera entre las etapas de actualización. Estos cambios nos alinean más con las Prácticas de implementación seguras (SDP) para mejorar la estabilidad, la calidad y la compatibilidad del servicio.

Continuaremos siguiendo la cadencia de implementación de dos semanas. Sin embargo, los clientes pueden notar que las actualizaciones generalmente se aplican a sus entornos de Recursos Humanos en un día diferente del ciclo de dos semanas que en versiones anteriores.

Para obtener más información sobre el proceso de actualización del servicio, consulte [Proceso de actualización](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-setup-update-process).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
