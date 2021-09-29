---
title: Novedades y cambios en Dynamics 365 Human Resources (6 de septiembre de 2021)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 6 de septiembre de 2021.
author: marcelbf
ms.date: 09/06/2021
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
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2add53b4b014cb65caacff03bf175078d2b70d8f
ms.sourcegitcommit: a73df4ddc7f8ddc9e37269c0236dc1bb9b7c7966
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485916"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Novedades y cambios en Dynamics 365 Human Resources (6 de septiembre de 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este tema se describen las funciones que son nuevas, han cambiado o estarán disponibles próximamente en Microsoft Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas funciones y sus fechas de disponibilidad general previstas, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4443.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
|---|---|---|
| Habilitar a un administrador de ausencias para administrar la baja | [Habilitar a un administrador de ausencias para administrar la baja](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | En esta versión, estamos actualizando la vista del espacio de trabajo del administrador de ausencias. Para obtener más información, consulte [Configurar el rol de administrador de ausencias](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurar los requisitos de archivos adjuntos por tipo de licencia | [Configurar los requisitos de archivos adjuntos por tipo de licencia](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168108) |
| Configurar unidades de baja por tipo de baja | [Configurar unidades de baja por tipo de baja](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [Configurar tipos de bajas y ausencias](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Problema | Descripción |
|---|---|---|
| 610128 | Error al publicar datos al usar HcmDiscussionOverallCommentEntity | Cuando se publican datos desde un libro de Excel en la entidad HcmDiscussionOverralCommentEntity, se produce el siguiente error: "No se puede encontrar el registro de origen de datos del tipo HcmTopicOverrall". |
| 589073 | El informe EEO-1 cuenta los valores "No específicos" y en blanco para el campo **Género** como valor "Mujer". | Si **Hombre** no se especificada para el campo **Género**, el informe EEO-1 genera un valor predeterminado de **Mujer**. |
| 589617 | Los saldos de la tarjeta de permisos, Disponible para comprar y Disponible para vender no aparecen cuando los roles de usuario están restringidos a una entidad legal específica. | Si el usuario (rol de empleado) está restringido a una entidad legal específica, los saldos no aparecen correctamente en la tarjeta **Saldos de permisos** ni en los campos **Disponible para comprar** y **Disponible para vender**. |
| 604310 | La pestaña del administrador de ausencias debe estar oculta cuando el usuario no tiene asignada una jerarquía de ausencias. | Para una entidad legal dada, la pestaña **Administrador de ausencias** debe estar oculta en el portal de autoservicio, a menos que el parámetro entre empresas esté habilitado y al menos una jerarquía de ausencias esté asociada con el usuario. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información sobre activar las funciones, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
|---|---|---|
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md) |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Permitir que los empleados se marquen como listos para recibir el pago | [Permitir que los empleados se marquen como listos para recibir el pago](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Listo para pagar](/dynamics365/human-resources/hr-compensation-payroll) |
| Campos personalizados en Idoneidad |[Compatibilidad de campos personalizados para el procesamiento de idoneidad](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Usar campos personalizados en el procesamiento de idomeidad](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>Próximamente

Para obtener una lista completa de las funciones previstas y sus lanzamientos programados, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Característica | Detalles |
|---|---|
| Actualización de la plataforma 10.0.21 (45) | Está programado que el despliegue de la actualización de la plataforma 10.0.21 comience a implementarse con la próxima versión de servicio el 4 de octubre de 2021. Para obtener más información, consulte [Actualizaciones de la plataforma para la versión 10.0.21 de las aplicaciones de Finance and Operations (octubre de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
| Declaración de prestaciones | Declaración de prestaciones para ver las elecciones de prestaciones actuales de un empleado. Para más información, consulte [Declaración de prestaciones](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) en el documento Lanzamiento de versiones. |

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
