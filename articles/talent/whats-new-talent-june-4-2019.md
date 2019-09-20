---
title: Novedades o cambios en Dynamics 365 for Talent (4 de junio de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/04/2019
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
ms.search.validFrom: 2019-06-04
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e19e5d3f1cb2305e5a4153de3e4d0e8f4c7d31ac
ms.sourcegitcommit: 1bf6a8b2f872394a4f242f9ff13c67e8e1ae8f65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/03/2019
ms.locfileid: "1856338"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-4-2019"></a>Novedades o cambios en Dynamics 365 for Talent (4 de junio de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 for Talent: Attract.

## <a name="coming-soon-in-attract"></a>Muy pronto en Attract

### <a name="job-approvals-on-the-home-page"></a>Aprobación de trabajos en la página principal

Las Aprobaciones aparecen en una sección **Aprobaciones** en el panel de información. Los aprobadores pueden revisar sus aprobaciones en **Asignadas a usted**. Esta sección muestra el id. de trabajo, el título, otros aprobadores y la fecha en la que se asignó el trabajo. Los usuarios que envían un trabajo para su aprobación pueden revisar sus trabajos en **Solicitado por usted**. En esta sección se muestran los aprobadores que todavía deben aprobar el trabajo enviado.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 for Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2330.

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nueva página para validar datos de la jerarquía de puestos

El personal de recursos humanos (RR. HH.) y los administradores pueden validar la jerarquía directiva para cualquier referencia circular que se importó de forma inadvertida. Puede obtener acceso a esta nueva página en **Administración de organización \> Vínculos \> Puestos \> Validación de la jerarquía de puestos**.

### <a name="specify-reason-codes-on-leave-types"></a>Especificar códigos de motivo en tipos de baja

Las organizaciones pueden requerir información adicional sobre las solicitudes de indisponibilidad. Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Requerir códigos de motivo para tipos de baja específicos y solicitudes de indisponibilidad

Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados envíen solicitudes de indisponibilidad. Este requisito podría existir debido a la directiva de la empresa o normas legales. Puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Proporcionar una lista de baja y la transacción de ausencia para recursos humanos

La capacidad de seguir la indisponibilidad del empleado y comprender cómo se calcula la indisponibilidad no solo ayuda a recursos humanos (RR. HH) a contestar las preguntas del empleado, sino que también ayuda a garantizar el tiempo de indisponibilidad preciso a los empleados. Recursos humanos ahora tiene una nueva vista de las transacciones (concesiones, acumulados, ajustes, y solicitudes) para que el personal de RR.HH. pueda ver las razones detrás de los saldos de ausencias.

### <a name="deleting-a-record-from-talent-doesnt-remove-the-record-from-common-data-service"></a>Eliminar un registro de Talent no quita el registro de Common Data Service

Los registros que se eliminan de Talent Core HR también se eliminan ahora de Common Data Service.

### <a name="variable-compensation-plan-valid-fromto-dates-arent-being-honored"></a>Las fechas Desde y Hasta válidas del plan de compensación variable no se respetan

En esta versión, no puede inscribir a un empleado en un plan de compensación variable si la fecha inicial es anterior a la fecha inicial del plan o si la fecha final es posterior a la fecha final del plan. 

### <a name="performance-review-comments-are-removed-when-users-select-cancel"></a>Los comentarios de la revisión del rendimiento se eliminan cuando los usuarios seleccione Cancelar

Esta versión corrige un problema cuando los comentarios de la revisión se eliminan si un usuario empieza a cambiar un comentario pero luego selecciona **Cancelar**. 

## <a name="in-preview"></a>En vista previa

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Las características de la vista previa solo están habilitado en instancias de espacio aislado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es **Producción** o **Espacio aislado**. Las instancias del tipo **Espacio aislado** permiten la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**. Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Limitar los tipos de baja en las solicitudes de tiempo de indisponibilidad

Las organizaciones pueden proporcionar muchos tipos diferentes de bajas a los empleados. Sin embargo, puede que no sea adecuado que los empleados envíen solicitudes de tiempo de indisponibilidad para algunos tipos de baja. En su lugar, RR. HH. puede administrar estos tipos de baja. En esta versión, puede configurar qué tipos de baja permiten que los empleados pueden enviar solicitudes de tiempo de indisponibilidad. 

## <a name="coming-soon-in-core-hr"></a>Próximamente en Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Ver información ampliada para el rendimiento en autoservicio para directores

Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados. Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones, que sus empleados gestionan en conjunto. Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente. Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos. 

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Los empleados, los administradores y RR. HH. podrán imprimir la evaluación del rendimiento de un empleado.
