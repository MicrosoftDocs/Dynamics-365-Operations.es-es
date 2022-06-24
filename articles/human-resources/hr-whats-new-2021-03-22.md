---
title: Novedades y cambios en Dynamics 365 Human Resources (22 de marzo de 2021)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 22 de marzo de 2021.
author: marcelbf
ms.date: 03/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2cfdd0fc1ca7ba206b0f447ecabd801a5a4e8c57
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859499"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Novedades y cambios en Dynamics 365 Human Resources (22 de marzo de 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe las características que son nuevas, que se han cambiado o que vendrán próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4049.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Opción para forzar la cancelación y restablecimiento de trabajos por lotes atascados (560976) | NA | [Restablecer trabajos por lotes atascados](./hr-admin-troubleshooting-batch-execution.md) |
| Actualizaciones menores de UX para crear un nuevo plan de prestaciones (419941) | NA | [Crear un nuevo plan de prestaciones](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este artículo para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del artículo.

| Número del problema | Problema |  Description |
| --- | --- | --- |
| 554239 | Mejoras de rendimiento para entidades relacionadas con la tabla **BusinessProcessTaskAssignment** | Mejorar el rendimiento de las entidades relacionadas con la tabla **BusinessProcessTaskAssignment** agregando índices sugeridos a la tabla. |
| 566061 | Eliminar el código de reserva de la entidad V2 de la sincronización nocturna | Elimina el código de reserva V2 para todas las sincronizaciones nocturnas de Dataverse. La reserva ya no es necesaria y evita que la sincronización filtrada funcione como se esperaba. El cambio mejora la coherencia de la sincronización de datos de Dataverse. |
| 538024 | Planes de prestaciones para trabajadores > Eliminar error de lanzamiento de retirada | Se corrigió un error al eliminar la retirada de la opción del plan de prestaciones del formulario de prestaciones del trabajador. |
| 557965 | Espacio de trabajo **Prestaciones**: el vínculo **Eventos de vida activa** debería estar siempre visible en la sección **Vínculos** | Problema solucionado, en el que el vínculo **Eventos de vida activa** era visible en la sección **Vínculos**, pero arrojaba un error al intentar navegar si la característica **(Vista previa) Espacio de trabajo de gestión de prestaciones** no estaba habilitada. Para obtener más información sobre cómo habilitar el espacio de trabajo, consulte [Espacio de trabajo de gestión de prestaciones](hr-benefits-management-workspace.md). |
| 556672 | No se pueden procesar las acumulaciones para un empleado que ya haya finalizado cuando **Entrada de empleados simplificada** está habilitado en la gestión de características | La opción de acumular planes de bajas y ausencias se ha agregado a **Mas opciones**, en **Historial de trabajo** para los empleados, cuando **Entrada de empleados simplificada** está habilitado en la gestión de características. |
| 562656 | El elemento del menú **SysRecordChangeLogValidTimeState** debe incluirse en un privilegio de seguridad y una extensión del deber de seguridad **SystemExternalBasicMaintain** | A los roles que no eran administradores del sistema les faltaba el botón **Ver cambios** en los formularios del administrador de fechas. |
| 505989 | Procesamiento de eventos de vida: el cambio de idoneidad no se ha procesado correctamente debido a la fecha utilizada | Se solucionó el problema por el cual el cambio en el procesamiento de idoneidad dependía de la fecha de inicio en el puesto y no solo del puesto actual. |
| 562286 | El trabajador que termina en al empresa envía múltiples actualizaciones a Dataverse | Cuando un trabajador termina en la empresa, se envía más de una operación de actualización a Dataverse, lo que genera dos notificaciones de actualización para el mismo cambio. Esto puede activar múltiples desencadenadores si un flujo de Power Automate está configurado para desencadenarse a partir de la acción. |
| 527340 | Aparece el error "Fecha y hora no representable" al abrir las inscripciones de bajas y ausencias | Al seleccionar una inscripción de baja y ausencia, el error ya no se muestra. |
| 561663 | Aumentar el intervalo de tiempo de espera para el aprovisionamiento de clústeres | Mejore la estabilidad de la infraestructura y la coherencia del aprovisionamiento con actualizaciones del aprovisionamiento de clústeres. |
| 486129 | No se pueden editar campos personalizados en **Posiciones > Gestionar cambios** | Se solucionó un problema por el cual los campos personalizados no se podían editar en la pestaña **Gestionar cambios** para **Posiciones**. |

## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información acerca cómo activar o desactivar características, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Restringir a los empleados para que no editen los detalles de los contactos comerciales | [Restringir a los empleados para que no editen los detalles de los contactos comerciales](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restringir la edición de información personal](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Próximamente

| Característica | Detalles |
| --- | --- |
| Las aptitudes introducidas por un director para sus empleados se pueden aprobar automáticamente mediante un flujo de trabajo | Próximamente. |

Para obtener una lista completa de las características previstas y sus lanzamientos programados, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]