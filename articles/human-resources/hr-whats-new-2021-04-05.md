---
title: Novedades y cambios en Dynamics 365 Human Resources, 5 de abril de 2021
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 5 de abril de 2021.
author: marcelbf
ms.date: 04/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-04-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 19ac856de0fed9253bf79cb4c06d4347e5a19c77
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8693483"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-5-2021"></a>Novedades y cambios en Dynamics 365 Human Resources, 5 de abril de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4074.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Restringir a los empleados para que no editen los detalles de los contactos comerciales | [Restringir a los empleados para que no editen los detalles de los contactos comerciales](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restringir la edición de información personal](./hr-employee-self-service-restrict-editing.md)|

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir |  Descripción |
| --- | --- | --- |
| 550852 | El botón **Aprobación** no se valida con los campos obligatorios establecidos en el formulario **Revisar**. | Cuando configura un campo en el formulario **Revisar** como obligatorio y publicar los cambios para el rol de Gerente, el formulario no se valida como se esperaba. |
| 559564 | Las acciones históricas de los trabajadores para el cambio de compensación fija dan error para los usuarios despedidos. | La acción del trabajador de la compensación de un empleado salido da un error. Después de que se despide a un empleado, la acción de promoción del trabajador antes de la terminación da un error. |
| 560074 | El menú desplegable de categorías de empleo no se filtra por **Tipo de trabajador** y muestra categorías para empleados y contratistas. | Sobre el formulario **Empleado**, el menú desplegable **Categoría de empleo** debe mostrar las categorías de empleados o contratistas, según el tipo de trabajador del empleado. |
| 567388 | Parte de la información de los empleados recién creados no se sincroniza inmediatamente con la tabla **cdm_worker** en Dataverse. | Al crear un nuevo registro de empleado, el nuevo registro se sincronizaría con la tabla **cdm_worker** en Dataverse, pero no todas las propiedades se incluirían en el registro de Dataverse. |
| 563837 | Se muestran las funciones que no están disponibles en Recursos humanos. | Varias funciones que no se aplican a los recursos humanos se muestran en la gestión de funciones. Estas funciones ahora se eliminan de la lista de funciones disponibles para habilitar en Recursos humanos. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |

## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
| Las aptitudes introducidas por un director para sus empleados se pueden aprobar automáticamente mediante un flujo de trabajo | Próximamente. |
| Actualización de la plataforma 10.0.17 (41) | La actualización de la plataforma 10.0.17 está programada para comenzar a implementarse con la próxima versión el 19 de abril de 2021. Para obtener más información, consulte [Platform updates para la versión 10.0.17 de aplicaciones de finanzas y operaciones (abril de 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md). |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]