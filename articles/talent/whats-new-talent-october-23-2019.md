---
title: Novedades y cambios en Dynamics 365 Talent (23 de octubre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-10-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 66419d9093cff68aa6109b22ab57bcb46ac6c718
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772905"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-23-2019"></a>Novedades y cambios en Dynamics 365 Talent (23 de octubre de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2569. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-30-for-finance-and-operations-apps"></a>Platform update 30 para aplicaciones de Finance and Operations

Para obtener más información, consulte [Novedades o cambios en la Platform update 30 para Finance and Operations (noviembre de 2019)](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/whats-new-platform-update-30).

### <a name="remove-benefits-open-enrollment-preview-feature"></a>Quitar la característica de vista previa de inscripción abierta de beneficios

Junto con nuestro anuncio en la entrada de blog de [inversiones estratégica en la excelencia operativa de Core HR](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence), Microsoft está quitando la característica de inscripción abierta de beneficios de la versión preliminar pública del 18 de octubre de 2019. En su lugar, la nueva funcionalidad se publicará en el futuro. No se admitirá el uso de la producción de la característica de inscripción abierta de beneficios que se encuentra actualmente en la versión preliminar pública.

### <a name="error-while-selecting-the-countryregion-on-the-worker-form-a-second-time-350294"></a>Error al seleccionar el país o la región en el formulario Trabajador una segunda vez (350294)

Con la publicación de esta semana, se ha corregido el problema al seleccionar un país o una región en el formulario **Trabajador**.

### <a name="financial-dimension-values-default-to-the-combination-display-field-when-do-not-allow-manual-entry-is-set-to-true-340097"></a>Los valores de la dimensión financiera establecen como valor predeterminado el campo Presentación de combinación cuando No permitir entrada manual se establece en verdadero (340097)

Con este cambio, al configurar las dimensiones financieras y usar la opción para no permitir la entrada manual, el sistema tomará correctamente como valor predeterminado el valor de la dimensión en el campo **Presentación de combinación**.

### <a name="new-relationship-types-should-be-added-to-relationship-lookup-in-the-personal-contacts-form-347691"></a>Los nuevos tipos de relación se deben agregar a la búsqueda de la relación en el formulario de contactos personales (347691)

Este lanzamiento incluye nuevas capacidades para agregar nuevos tipos de relación en la tabla **Tipos de relación** y reflejar dichos cambios en la búsqueda de relación para los contactos personales.

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-379599"></a>Los valores de lista adicionales de los campos personalizados no se reflejan en Common Data Service (379599)

Con el lanzamiento de esta semana, agregando un nuevo valor de lista a un campo personalizado existente que ya esté sincronizado con Common Data Service, los nuevos valores de la lista de selección aparecerán ahora después de aplicar los cambios a la entidad.

### <a name="on-the-terms-of-employment-page-all-employees-terms-of-employment-appear-after-selecting-open-in-excel-348073"></a>En la página Condiciones laborales, las condiciones laborales de todos los empleados aparecen después de seleccionar Abrir en Excel (348073)

Con esta versión, solo las condiciones laborales de los empleados seleccionados se abrirán en Excel. También se respeta toda la seguridad de la empresa.

### <a name="the-association-between-the-work-calendar-holiday-entity-and-the-work-calendar-entity-is-missing-in-common-data-service-324178"></a>Falta la asociación entre la entidad de calendario festivo laboral y la entidad de calendario laboral en Common Data Service (324178)

Esta relación se ha agregado con la versión. Este cambio permitirá que se muestren los días laborables de un empleado en PowerApps. 

### <a name="error-when-using-employee-self-service-workflows-with-configurable-hierarchies-370132"></a>Error al usar los flujos de trabajo de autoservicio de empleados con jerarquías configurables (370132)

En esta versión, hay disponible una mejor mensajería acerca de cómo configurar flujos de trabajo mediante jerarquías configurables. 

### <a name="system-allows-creation-of-new-positions-where-the-available-for-assignment-date-is-earlier-than-the-activation-date-340103"></a>El sistema permite la creación de nuevos puestos donde la fecha de Disponible para la asignación es anterior a la Fecha de activación (340103)

Este cambio mostrará una advertencia cuando la fecha **Disponible para la asignación** es anterior a la fecha **Activación** del puesto.

## <a name="coming-soon"></a>Próximamente

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.

### <a name="feature-management-workspace"></a>Espacio de trabajo Administración de características.

Las características se suman y se actualizan en cada versión. La experiencia de administración de características proporciona un espacio de trabajo en el que puede ver una lista de características que se han entregado en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación.

Para obtener más información acerca de los cambios que se incluyen con la administración de características, consulte [Visión general de la administración de características](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).
