---
title: Novedades y cambios en Dynamics 365 Human Resources (20 de septiembre de 2021)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 20 de septiembre de 2021.
author: marcelbf
ms.date: 09/20/2021
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
ms.search.validFrom: 2021-09-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3f4fc4768f8c96678b216709f78af6d3ddfd4132
ms.sourcegitcommit: ba8ca42e43e1a5251cbbd6ddb292566164d735dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2021
ms.locfileid: "7556942"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-20-2021"></a>Novedades y cambios en Dynamics 365 Human Resources (20 de septiembre de 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este tema se describen las funciones que son nuevas, han cambiado o estarán disponibles próximamente en Microsoft Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas funciones y sus fechas de disponibilidad general previstas, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4464.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
|---|---|---|
| Habilitar la integración de nóminas simplificada (API de integración de nóminas) | [Habilitar la integración simplificada proveedores de nóminas](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md) |
| Permitir que los empleados se marquen como listos para recibir el pago | [Permitir que los empleados se marquen como listos para recibir el pago](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Listo para pagar](/dynamics365/human-resources/hr-compensation-payroll) |

### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Problema | Descripción |
|---|---|---|
| 619774 | La edición de la descripción de la dirección no se sincroniza con Dataverse en tiempo real. | Al editar la descripción de la dirección de un trabajador, la descripción actualizada no se sincroniza en tiempo real con Dataverse. La suscripción en la tabla **Ubicación Logística** se actualizó para enviar una actualización. |
| 614603| Error en la página **Trabajador** cuando el parámetro **Acciones del personal trabajador** no está seleccionado. | Al contratar a un nuevo trabajador o al navegar a la página **Trabajador**, aparece el siguiente error, "Campo **Tipo de acción del personal** debe completarse ", incluso si **Acciones de personal** están desactivadas. |
| 615367 | **Tiempo libre aprobado** la pestaña muestra una advertencia y se muestra incorrectamente. | Si la unidad de salida está configurada en **Días** antes de habilitar la función **Configurar unidades de licencia por tipo de licencia**, la pestaña **Tiempo libre aprobado** muestra una advertencia no válida y columnas incorrectas. |


## <a name="in-preview"></a>En vista previa

La siguientes características nuevas se incluyen como versión preliminar. Para obtener más información sobre activar las funciones, consulte [Administrar características](hr-admin-manage-features.md).

| Característica | Plan de lanzamiento | Documentación |
|---|---|---|
| Espacio de trabajo de administración de prestaciones | [Espacio de trabajo de administración de prestaciones (versión preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espacio de trabajo de administración de prestaciones](hr-benefits-management-workspace.md) |
| Campos personalizados en Idoneidad |[Compatibilidad de campos personalizados para el procesamiento de idoneidad](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Usar campos personalizados en el procesamiento de idomeidad](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |
| Declaración de prestaciones |[Declaración de prestaciones](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) | [Declaración de prestaciones](hr-benefits-statement.md) |

### <a name="benefits-statement-known-issues"></a>Problemas conocidos del extracto de prestaciones

| Problema | Descripción |
|---|---|
| La página **Parámetros de informe** en **Autoservicio para los empleados** para la declaración de prestaciones es incorrecta. | Al navegar a la **Declaración de prestaciones** en **Autoservicio para los empleados**, la página **Parámetros de informe** muestra las fichas desplegables **Registros para incluir** y **Ejecutar en segundo plano**.  Estos deben eliminarse. |
| Los períodos cerrados y futuros se muestran en la página **Parámetro de informes** para la declaración de prestaciones. | Al navegar a la página de destino **Informe de declaración de beneficios**, el usuario puede seleccionar períodos de planes de beneficios que están cerrados o con fecha futura, lo que da como resultado una página en blanco. Solo el período actual del plan de beneficios debe aparecer en la lista. |
|Error al enviar el informe por correo electrónico utilizando el destino del informe GER. | La declaración de beneficios se puede configurar para utilizar parámetros de correo electrónico dentro de la página **Destinos del informe GER**. Al completar la configuración e imprimir el informe, el usuario recibirá un error de formato y no se enviará la declaración de beneficios.|


## <a name="coming-soon"></a>Próximamente

Para obtener una lista completa de las funciones previstas y sus lanzamientos programados, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Característica | Detalles |
|---|---|
| Actualización de la plataforma 10.0.21 (45) | Está programado que el despliegue de la actualización de la plataforma 10.0.21 comience a implementarse con la próxima versión de servicio el 4 de octubre de 2021. Para obtener más información, consulte [Actualizaciones de la plataforma para la versión 10.0.21 de las aplicaciones de Finance and Operations (octubre de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
|Vista de informes ampliados de diarios de rendimiento | Esta función se habilitará de forma predeterminada en la próxima implementación. |


## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
