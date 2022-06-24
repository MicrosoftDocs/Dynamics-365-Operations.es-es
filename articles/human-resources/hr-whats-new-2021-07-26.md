---
title: Novedades o cambios en Dynamics 365 Human Resources 26 de julio de 2021
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 26 de julio de 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6c7211135733f45a9841ae5a80607b01999d7c69
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870940"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Novedades o cambios en Dynamics 365 Human Resources 26 de julio de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe las características que son nuevas, que se han cambiado o que vendrán próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas funciones y sus fechas de disponibilidad general previstas, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4384.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Platform update 10.0.20 | -- | [Actualizaciones de la plataforma para la versión 10.0.20 de las aplicaciones de finanzas y operaciones (agosto de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este artículo para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del artículo.

| Número del problema | Problema |  Description |
| --- | --- | --- |
| 600422 | La validación de la dirección de nómina falla para Listo para pagar. | La validación se ha actualizado para requerir solo una dirección del tipo 'Lugar de residencia de nómina' y solo una dirección del tipo 'Lugar de trabajo de nómina'. |
| 601226 | Problema de integración de datos: el proyecto de exportación de integración de nómina no tiene la opción de inserción completa | La integración de la nómina a Ceridian DayForce fue una inserción incremental en lugar de una inserción completa. Ceridian requiere estar siempre actualizado por completo. Este problema ahora está solucionado, las entidades en el proyecto de exportación de datos ya no cambiarán a la inserción incremental. |
| 602272 | Los iconos que se agregaron al espacio de trabajo de autoservicio para empleados ahora faltan y ya no se pueden agregar iconos | Hemos solucionado el problema de personalización del autoservicio de empleados. Se pueden agregar nuevos iconos a la vista y cualquier personalización existente será visible para los usuarios |
| 600711 | Campo de selección de definición de medio día habilitado para solicitudes de baja de día completo | Este problema ahora está solucionado y el campo de definición de medio día se habilitará solo cuando los empleados seleccionen un tipo de baja con la definición de medio día habilitada y medio día como el valor de cantidad seleccionado |
| 602208 | Unidades de tasa de acumulación que muestran horas en lugar de días | Este problema ahora está solucionado. El formulario **Tiempo libre** mostrará la unidad de baja correcta (horas o días) para la columna **Tasa de acumulación**. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)|
|  Habilitar a un administrador de ausencias para administrar la baja | [Habilitar a un administrador de ausencias para administrar la baja](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Con esta versión, estamos actualizando la vista del espacio de trabajo del administrador de ausencias. Para obtener más información, consulte [Configurar el rol de administrador de ausencias](https://go.microsoft.com/fwlink/?linkid=2168107).|
|  Configurar los requisitos de archivos adjuntos por tipo de licencia | [Configurar los requisitos de archivos adjuntos por tipo de licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurar unidades de baja por tipo de baja | [Configurar unidades de baja por tipo de baja](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permitir que los empleados se marquen como listos para recibir el pago | [Permitir que los empleados se marquen como listos para recibir el pago](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Listo para pagar](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Próximamente

Para obtener una lista completa de las funciones previstas y sus lanzamientos programados, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
