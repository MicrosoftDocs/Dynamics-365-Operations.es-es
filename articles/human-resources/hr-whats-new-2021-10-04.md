---
title: Novedades y cambios en Dynamics 365 Human Resources (5 de octubre de 2021)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 5 de octubre de 2021.
author: marcelbf
ms.date: 10/05/2021
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
ms.search.validFrom: 2021-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 206c7f590b495278b7899271db0e83b3a4da3edc
ms.sourcegitcommit: 42bd701179e664947b6eafcd1804c83a5e64abcb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2021
ms.locfileid: "7641439"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-5-2021"></a>Novedades y cambios en Dynamics 365 Human Resources (5 de octubre de 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este tema se describen las funciones que son nuevas, han cambiado o estarán disponibles próximamente en Microsoft Dynamics 365 Human Resources.

Para obtener más información sobre el proceso de actualización y la programación, consulte [Proceso de actualización](hr-admin-setup-update-process.md).

Para obtener más información sobre las nuevas funciones y sus fechas de disponibilidad general previstas, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>En este lanzamiento

Esta versión incluye las características nuevas y correcciones de errores siguientes. Los cambios se aplican al número de compilación 8.1.4485.

### <a name="new-features"></a>Nuevas características

Las siguientes características estarán disponible de forma generalizada en esta versión.

| Característica | Plan de lanzamiento | Documentación |
|---|---|---|
| Actualización de la plataforma 10.0.21 (45) | -- | [Actualizaciones de plataforma para aplicaciones de la versión 10.0.21 de Finance and Operations (octubre de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21) |


### <a name="bug-fixes"></a>Correcciones de errores

En esta versión se incluyen las siguientes correcciones de errores.

> [!NOTE]
> Nuestro objetivo es hacer llegar esta información lo antes posible. Puede que haya actualizaciones de este tema para incluir correcciones de errores que se incluyeron en la compilación después de la publicación inicial del tema.

| Número del problema | Problema | Descripción |
|---|---|---|
| 598896 | El importe del empleado no se muestra hasta que el empleado haya completado la inscripción | En la página **Autoservicio para el empleado**, no se mostraba el importe del empleado por el beneficio. Ahora se muestra el importe del empleado en la página **Autoservicio de prestaciones**.  |
| 613440 | No se pueden exportar datos de **Administración de datos** | Al exportar datos para un proyecto en **Administración de datos**, la exportación falla inesperadamente. |
| 618327 | Los períodos cerrados y futuros se muestran en la página **Parámetros de informes** para la declaración de prestaciones | Al navegar a la **Declaración de prestaciones** en **Autoservicio para los empleados**, la página **Parámetros de informe** muestra las fichas desplegables **Registros para incluir** y **Ejecutar en segundo plano**. Estas secciones fueron eliminadas.|
| 618326 | Una página de **Parámetros de informe** incorrecta se muestra en **Autoservicio para los empleados** para la declaración de prestaciones| Al navegar a la página de destino **Informe de declaración de prestaciones**, el usuario podía seleccionar períodos de planes de prestaciones que están cerrados o con fecha futura, lo que da como resultado una página en blanco. Solo el período actual del plan de beneficios debe aparecer en la lista. |

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
|Error al enviar el informe por correo electrónico utilizando el **destino del informe GER** | La declaración de prestaciones se puede configurar para utilizar parámetros de correo electrónico dentro de la página **Destinos del informe GER**. Al completar la configuración e imprimir el informe, el usuario recibirá un error de formato y no se enviará la declaración de beneficios.|

## <a name="feature-management-changes"></a>Cambios de la administración de características

| Característica | Descripción |
|---|---|
|Vista de informes ampliados de diarios de rendimiento | Esta función se habilitará de forma predeterminada en esta versión. |

## <a name="coming-soon"></a>Próximamente

Para obtener una lista completa de las funciones previstas y sus lanzamientos programados, consulte [Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Característica | Detalles |
|---|---|
| Actualización de la plataforma 10.0.22 (46) | Está programado que el despliegue de la actualización de la plataforma 10.0.22 comience a implementarse con la próxima versión de servicio el 1 de noviembre de 2021. Para obtener más información, consulte [Actualizaciones de la plataforma para la versión 10.0.22 de las aplicaciones de Finance and Operations (noviembre de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-22). |



## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Información general del segundo lanzamiento de versiones de Dynamics 365 Human Resources en 2021](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
