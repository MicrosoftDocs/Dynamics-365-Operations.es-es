---
title: Novedades y cambios en Dynamics 365 Talent (8 de octubre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/08/2019
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
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 40898ca7f54089337180def964b8942e8653663b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529489"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-8-2019"></a>Novedades y cambios en Dynamics 365 Talent (8 de octubre de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2542. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="removal-of-benefits-open-enrollment-from-public-preview"></a>Eliminación de la inscripción abierta de beneficios de la versión preliminar pública

Junto con nuestro anuncio en la entrada de blog de [inversiones estratégica en la excelencia operativa de Core HR](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence/), Microsoft está quitando la característica de inscripción abierta de beneficios de la versión preliminar pública del 18 de octubre de 2019. En su lugar, la nueva funcionalidad se publicará en el futuro. No se admitirá el uso de la producción de la característica de inscripción abierta de beneficios que se encuentra actualmente en la versión preliminar pública. 

### <a name="common-data-service-integration-is-now-turned-off-by-default-on-new-provisions-343675"></a>La integración de Common Data Service está desactivada ahora de manera predeterminada en las nuevas provisiones (343675)
 
Cuando se aprovisionan los nuevos entornos, se desactiva ahora la integración de Common Data Service. Para obtener más información, consulte la sección [Configurar la integración Common Data Service](hr-common-data-service-integration.md).

### <a name="streamlined-employee-entry-and-navigation"></a>Entrada y navegación de empleados optimizadas

La funcionalidad para la navegación y la entrada de empleados está ahora disponible en todos los entornos. Para activar esta característica, vaya a **Administración del sistema \> Vínculos \> Configuración \> Parámetros del sistema \> Características de vista previa** y seleccione **Formulario y navegación de trabajador mejorado**. La característica se activa entonces para todos los usuarios. Puede desactivar esta opción en cualquier momento.

Para obtener más información, consulte [Entrada de datos aerodinámica del empleado](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/streamlined-employee-data-entry) en el plan de la oleada 2 de la versión Dynamics 365: 2019.

### <a name="attract-and-onboard-create-inactive-workers-in-core-hr-380517"></a>Attract y Onboard crean trabajadores inactivos en Core HR (380517)

La versión de esta semana corrige un error donde Attract y Onboard crean trabajadores inactivos en Core HR.

### <a name="the-workflow-fails-when-the-manager-is-signed-in-to-another-company-while-terminating-an-employee-346852"></a>Se produce un error en el flujo de trabajo cuando el director inicia sesión en otra empresa mientras que cesa a un empleado (346852)

Ya no se producirá un error en el flujo de trabajo en función de la entidad jurídica en la que el administrador ha iniciado sesión.

### <a name="missing-information-on-hcmonboardingworkerchecklisttaskentity-349591"></a>Falta información en HcmOnboardingWorkerChecklistTaskEntity (349591)

Esta versión incluye información adicional sobre **HcmOnboardingWorkerChecklistTaskEntity**. A continuación se incluyen algunos ejemplos:

- **Nombre de grupo** cuando el tipo asignado es **grupo**
- **Nombre de empleado** cuando el tipo asignado es **empleado**
- **Nombre del director** cuando el tipo asignado es **director**

### <a name="entities-arent-listed-in-alphabetical-order-in-common-data-service-administration-377414"></a>Las entidades no se muestran en orden alfabético en Administración de Common Data Service (377414)

Las entidades se muestran ahora en orden alfabético en la página **Administración de CDS**.

### <a name="changing-the-employment-type-with-a-future-date-doesnt-allow-a-position-assignment-339958"></a>El cambio del tipo de empleo con una fecha futura no permite una asignación de puesto (339958)

Este cambio permite asignaciones de puesto al cambiar los tipos de trabajador (por ejemplo, de empleado a contratista).

### <a name="updating-the-common-data-service-leave-bank-transaction-entity-creates-a-new-record-in-talent-352938"></a>La actualización de la entidad Transacción bancaria de bajas de Common Data Service crea un registro nuevo en Talent (352938)

La transacción de bajas se actualiza ahora cuando se realiza una actualización a Common Data Service para las transacciones bancarias de bajas.

### <a name="the-title-of-attachments-for-feedback-items-shows-the-feedback-description-343765"></a>El título de los datos adjuntos para los artículos de realimentación muestra la descripción de realimentación (343765)

La descripción de la realimentación ya no aparece en el título de datos adjuntos.

### <a name="compensation-workflow-comments-field-shows-incorrect-content-339297"></a>El campo de comentarios del flujo de trabajo de compensación muestra contenido incorrecto (339297)

Este cambio muestra el contenido del campo **%HcmActionState.HcmWorkerActionComment.Comments%**.

### <a name="workcalendarentity-and-workcalendardayentity-arent-exposed-through-odata-376329"></a>WorkCalendarEntity y WorkCalendarDayEntity no se exponen a través de OData (376329)

En esta versión, **WorkCalendarEntity** y **WorkCalendarDayEntity** están ahora disponibles a través del Open Data Protocol (OData).

### <a name="hcmworkerentity-is-slow-when-odata-is-used-375221"></a>HCMWorkerEntity es lento cuando se utiliza OData (375221)

Los cambios mejoran el rendimiento de **HCMWorkerEntity** cuando use el diseñador de libros de Microsoft Excel.

### <a name="manager-performance-journal-entry-shows-an-error-after-deleting-a-performance-journal-and-creating-a-new-one-336061"></a>El movimiento de diario de rendimiento del director muestra un error tras eliminar un diario de rendimiento y crear uno nuevo (336061)

Esta versión corrige un problema que se produce cuando se elimina un diario de rendimiento y se crea uno nuevo inmediatamente después. Esta corrección cambia el comportamiento del autoservicio del director.

## <a name="coming-soon"></a>Próximamente

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.


[!INCLUDE[footer-include](../includes/footer-banner.md)]