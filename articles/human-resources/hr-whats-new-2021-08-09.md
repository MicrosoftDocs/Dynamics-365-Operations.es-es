---
title: Novedades y cambios en Dynamics 365 Human Resources, 9 de agosto de 2021
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 9 de agosto de 2021.
author: marcelbf
ms.date: 08/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f515b614aedce3d58994bf21104ada25702a71e
ms.sourcegitcommit: fc19ee0aba2a6174fef305d151f1eb23ca6c0346
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385709"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-9-2021"></a>Novedades y cambios en Dynamics 365 Human Resources, 9 de agosto de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este tema se describen las funciones que son nuevas, han cambiado o estarán disponibles próximamente en Microsoft Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas funciones y sus fechas de disponibilidad general previstas, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4393.

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Problema | Descripción |
| --- | --- | --- |
| 558385 | La persona designada predeterminada no se selecciona cuando la opción **Seleccionar automáticamente personas designadas** está activada para las personas designadas predeterminadas. | Este problema ahora está solucionado. Se seleccionan automáticamente varias personas designadas predeterminadas en los planes elegibles cuando la opción **Seleccionar automáticamente personas designadas** de la página **Parámetros compartidos de Human Resources** está activada. |
| 589617 | En la página **Tiempo libre**, los saldos de **Disponible para comprar** y **Disponible para vender** están en blanco cuando el acceso está restringido a una empresa específica. | Este problema ahora está solucionado. La página **Tiempo libre** muestra los saldos correctos de **Disponible para comprar** y **Disponible para vender** cuando el usuario está restringido a una empresa específica. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información sobre activar las funciones, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)|
| Habilitar a un administrador de ausencias para administrar la licencia | [Habilitar a un administrador de ausencias para administrar la licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | En esta versión, estamos actualizando la vista del espacio de trabajo del administrador de ausencias. Para obtener más información, consulte [Configurar el rol de administrador de ausencias](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurar los requisitos de archivos adjuntos por tipo de licencia | [Configurar los requisitos de archivos adjuntos por tipo de licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168108)|
| Configurar unidades de baja por tipo de baja | [Configurar unidades de baja por tipo de baja](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permitir que los empleados se marquen como listos para recibir el pago | [Permitir que los empleados se marquen como listos para recibir el pago](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Listo para pagar](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Próximamente

Para obtener una lista completa de las funciones previstas y sus lanzamientos programados, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Característica | Detalles |
| --- | --- |
| Actualización de la plataforma 10.0.21 (45) | Está programado que el despliegue de la actualización de la plataforma 10.0.21 comience a implementarse con la próxima versión de servicio el 4 de octubre de 2021. Para obtener más información, consulte [Actualizaciones de la plataforma para la versión 10.0.21 de las aplicaciones de Finance and Operations (octubre de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
