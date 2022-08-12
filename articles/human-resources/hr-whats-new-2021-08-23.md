---
title: Novedades y cambios en Dynamics 365 Human Resources, 23 de agosto de 2021
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 23 de agosto de 2021.
author: marcelbf
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a6c92167a9b67c3be1cdad18293e8ab6d2ba03d4
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069858"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Novedades y cambios en Dynamics 365 Human Resources, 23 de agosto de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe las características que son nuevas, que se han cambiado o que vendrán próximamente en Microsoft Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas funciones y sus fechas de disponibilidad general previstas, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4419.

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este artículo para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del artículo.

| Número del problema | Problema | Description |
| --- | --- | --- |
| 594066 | No se puede eliminar la información de contacto | Al seleccionar eliminar un registro de información de contacto de un empleado, en su lugar se elimina un registro de información de contacto que no sea el registro seleccionado. |
| 611339 | Agregar una personalización hace que la cuenta bancaria ignore el filtro y obtenga el primer registro | Agregar una personalización hace que la lista de cuentas bancarias ejecute una consulta de personalización después de que se ejecute la consulta de la fuente de datos, lo que da como resultado que la consulta obtenga el registro superior independientemente del trabajador para el que se están viendo los detalles. |
| 591806 | Las tareas de fecha de vencimiento de incorporación se calculan incorrectamente | Las fechas de vencimiento se calculan incorrectamente cuando existen las siguientes condiciones: Las listas de verificación que se crean utilizan un calendario que usa un rango de tiempo extendido (por ejemplo, de 2005 a 2050) y las preferencias del usuario utilizan una zona horaria diferente a la hora estándar central. |   
| 592749 | Dejar saldo incorrecto en **Autoservicio para los empleados** | Si el empleado tiene empleo en más de una entidad jurídica y está habilitada la vista de permisos entre empresas, es posible que el saldo de permisos sea incorrecto. |
| 603133 | Advertencia inesperada al solicitar tiempo libre | Al solicitar tiempo libre, llenando el campo **Medio día** antes del campo **Monto** provocará una advertencia inesperada. |
| 606546 | Seleccionar campo no visible en Tiempo libre aprobado | La casilla de verificación para seleccionar varias solicitudes de licencia aprobadas no estaba visible. |
| 597059 | Trabajador no visible en **Calendario de licencias y ausencias de la empresa** | Un trabajador no es visible en el **Calendario de licencias y ausencias de la empresa** si el rango de fechas aplicado incluye cualquier día para el cual se les ha denegado una solicitud de licencia. |


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
| Actualización de la plataforma 10.0.21 (45) | Está programado que el despliegue de la actualización de la plataforma 10.0.21 comience a implementarse con la próxima versión de servicio el 4 de octubre de 2021. Para obtener más información, consulte [Platform updates para la versión 10.0.21 de aplicaciones de finanzas y operaciones (octubre de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

