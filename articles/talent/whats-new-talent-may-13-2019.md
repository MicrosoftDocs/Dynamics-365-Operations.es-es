---
title: Novedades y cambios en Dynamics 365 for Talent (13 de mayo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-05-13
ms.dyn365.ops.version: Talent
ms.openlocfilehash: dac453ee83492655b6681b9784af4712bf39fc2a
ms.sourcegitcommit: 2bbc0eeca6826c529fb729b82d16f287c1ce05bb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/16/2019
ms.locfileid: "1591511"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-may-13-2019"></a>Novedades y cambios en Dynamics 365 for Talent (13 de mayo de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent.

## <a name="coming-soon-in-attract"></a>Muy pronto en Attract

### <a name="job-approvals-on-home-page"></a>Aprobación de trabajos en la página principal

Las Aprobaciones aparecen en una sección **Aprobaciones** en el panel de información. Los aprobadores pueden revisar los aprobaciones en **Asignada a usted**, que muestra el identificador de trabajo, el título, otros aprobadores y la fecha asignada. Los usuarios que envían un trabajo para su aprobación pueden revisar los trabajos en **Solicitado por usted**, que muestra los aprobadores que aún deben aprobar el trabajo enviado.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Onboard

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2297. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="indicate-instance-type-when-provisioning-talent"></a>Indicar el tipo de instancia al aprovisionar Talent

Al aprovisionar una nueva instancia de Talent, podrá indicar si el tipo de instancia es **Producción** o **Espacio aislado**, lo que permite la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**. Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Soporte de la entidad de Common Data Service para los campos personalizados

En la versión de esta semana, las entidades siguientes de Common Data Service ahora admiten campos personalizados: Empleo, Cálculo de frecuencia de prestación, Cálculo de tasa de prestación, Tipo de Prestación, calendario laboral, calendario festivo laboral y Tipo de identificación.

### <a name="common-data-service-integration-page"></a>Página de integración de Common Data Service

Esta versión proporciona una nueva opción en **Administración del sistema > Vínculos > Integraciones > Configuración de Common Data Service**. La opción **Configuración de Common Data Service** permite a un administrador o director de gestión de datos algún flexibilidad e informaciones con los Common Data Service. Con esta opción, puede habilitar o deshabilitar la integración Common Data Service con una instancia de Talent y ver los detalles de la sincronización entre la instancia de Talent y Common Data Service.

### <a name="import-performance-data-with-final-employee-rating-316710"></a>Importar datos de rendimiento con la calificación final del empleado (316710)

En esta versión, puede importar datos históricos de clasificación de empleados. El campo **FinalEmployeeRatingId** ahora tiene permiso de escritura.

### <a name="cant-create-worker-address-in-common-data-service-and-sync-it-with-talent-317555"></a>No puede crear la dirección del trabajador en Common Data Service y la sincronización con Talent (317555)

Este cambio permite los datos de la dirección creados en Common Data Service sincronizarse con Talent.

## <a name="in-preview"></a>En vista previa

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nueva página para validar datos de la jerarquía de puestos

Los recursos humanos (HR) y los administradores ahora pueden validar la jerarquía directiva para cualquier referencia circular que podría haber sido importados de forma inadvertida. Puede obtener acceso a esta nueva página desde **Administración de organización > Vínculos > Puestos > Validación de la jerarquía de puestos**.

### <a name="specify-reason-codes-on-leave-types"></a>Especificar códigos de motivo en tipos de baja

Las organizaciones pueden requerir información adicional sobre las solicitudes de indisponibilidad. Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Requerir códigos de motivo para tipos de baja específicos y solicitudes de indisponibilidad

Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados envíen solicitudes de indisponibilidad. Este requisito podría existir debido a la directiva de la empresa o normas legales. Puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Proporcionar una lista de baja y la transacción de ausencia para recursos humanos

La capacidad de seguir la indisponibilidad del empleado y comprender cómo se calcula la indisponibilidad no solo ayuda a recursos humanos (RR.HH) a contestar las preguntas del empleado, también ayuda a garantizar proporcionar el tiempo de indisponibilidad preciso a los empleados. Recursos humanos ahora tiene una nueva vista de las transacciones (concesiones, acumulados, ajustes, y solicitudes) para que el personal de RR.HH. pueda ver las razones detrás de los saldos de ausencias.
