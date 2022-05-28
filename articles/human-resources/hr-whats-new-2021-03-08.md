---
title: Novedades y cambios en Dynamics 365 Human Resources (8 de marzo de 2021)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 8 de marzo de 2021.
author: marcelbf
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7b1e616f9bc72ab1f30f69671c673241096f3276
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687879"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Novedades y cambios en Dynamics 365 Human Resources (08 de marzo de 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas, han cambiado o estarán disponibles próximamente en Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas características y sus fechas de disponibilidad general previstas, consulte [Visión general del primer lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4017.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
| --- | --- | --- |
| Visión transversal de la licencia para responsables | [Visión transversal de la licencia de empleado para responsables](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parámetros de bajas y ausencias](./hr-leave-and-absence-parameters.md) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Emitir |  Descripción |
| --- | --- | --- |
| 486611 | La licencia se muestra en el calendario de licencia cuando **Desactivar la licencia en todos los calendarios** está habilitado | Si **Desactivar la licencia en todos los calendarios** está habilitada, la información de licencias ya no se muestra cuando la función de mejoras del calendario de licencias y ausencias está habilitada.|
| 508972 | A la entidad de transacción bancaria de ausencias y ausencias falta la validación de la inscripción | Cuando se utiliza la entidad Transacción bancaria de ausencias y ausencias, los empleados que no están inscritos en un plan ya no se pueden importar. |
| 554854 | Actualización del calendario en errores de entidad de empleo si la entidad jurídica predeterminada en las opciones de usuario es diferente | El uso de la entidad Empleo para actualizar el calendario de un empleado ya no genera un error si la entidad jurídica predeterminada en las opciones de usuario es diferente. |
| 558347 | "No se puede crear un registro en las configuraciones de formulario (FormRunConfiguration)" aparece al cargar la página de inicio. | Las personalizaciones causan el error "No se puede crear un registro en las configuraciones de formulario (FormRunConfiguration)" al cargar la página de inicio. |
| 557327 | Espacio de trabajo de gestión de beneficios: Aparece un espacio sobre la cuadrícula. | Se solucionó el problema de la experiencia del usuario con un espacio no deseado que aparecía en los bordes de la cuadrícula de la tabla en el espacio de trabajo Beneficios. |
| 557334 | Espacio de trabajo de gestión de beneficios: el cuadro desplegable de selección **Período** solo debe aparecer en la pestaña **Resumen** | Ahora El menú desplegable de selección de **Período** de Beneficios aparece solo cuando la pestaña **Resumen** está activa en el espacio de trabajo Beneficios y no en las secciones **Resultados del proceso** y **Enlaces**. |
| 557336 | Espacio de trabajo de gestión de beneficios: el texto de **Inscripción abierta con planes retirados** está truncado en la vista de la ventana | Se cambió el texto en la vista de la ventana a **Planes revisados ... inscripción abierta** para evitar el truncamiento del contexto necesario. |

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