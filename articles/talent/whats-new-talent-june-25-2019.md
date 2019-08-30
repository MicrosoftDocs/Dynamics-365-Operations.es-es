---
title: Novedades o cambios en Dynamics 365 for Talent (25 de junio de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 06/25/2019
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
ms.search.validFrom: 2019-06-25
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e32768c898e2934b95eb8ab7b212337aff0c1556
ms.sourcegitcommit: fbe6d35ed35aa01f438990e2880c3a3cf223ea8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2019
ms.locfileid: "1704478"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-june-25-2019"></a>Novedades o cambios en Dynamics 365 for Talent (25 de junio de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Muy pronto en Attract

### <a name="job-approvals-appear-on-the-home-page"></a>Aprobaciones de trabajos que aparecen en la página principal

Las Aprobaciones aparecen en una sección **Aprobaciones** en el panel de información. Los aprobadores pueden revisar sus aprobaciones en **Asignada a usted**, que muestra el id. de trabajo, el cargo, otros aprobadores y la fecha en la que se asignó el trabajo. Los usuarios que envían un trabajo para su aprobación pueden revisar los trabajos en **Solicitado por usted**, que muestra los aprobadores que aún deben aprobar el trabajo enviado.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia del Dynamics 365 Talent: Onboard

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2357.

### <a name="incorrect-value-displayed-for-primary-position-314266"></a>Se muestra un valor incorrecto para la posición principal (314266)

Estos cambios mostrarán sistemáticamente la configuración **Posición principal** en todas las páginas.

### <a name="cant-edit-after-recalling-the-workflow-in-review-318180"></a>No se puede editar después de recuperar el flujo de trabajo en Revisión (318180)

Ahora se podrán editar las revisiones que se han recuperado mediante el flujo de trabajo.

### <a name="final-comments-field-in-reviews-isnt-translated-325921"></a>El campo de comentarios finales en Revisiones no se traduce (325921)

La etiqueta **Comentarios finales** se traduce en Talent.

### <a name="preview-features-will-be-enabled-only-in-sandbox-environments"></a>Las características de vista previa solo se habilitarán en entornos de espacio aislado

Al aprovisionar una nueva instancia de Talent, puede indicar si el tipo de instancia es **Producción** o **Espacio aislado**. El tipo de instancia **Espacio aislado** permite la prueba temprana de nuevas características. Todas las instancias existentes de Talent se actualizarán el tipo de instancia de **Producción**. Si desea que una de las instancias existentes se actualicen al tipo de instancia de **Espacio aislado**, contacte con el [Soporte](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

## <a name="in-preview"></a>En vista previa

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limite los tipos de baja en las solicitudes de tiempo de indisponibilidad

Las organizaciones pueden proporcionar muchos tipos de bajas a los empleados. Sin embargo, puede que no sea adecuado que los empleados envíen solicitudes de tiempo de indisponibilidad para algunos tipos de baja. En su lugar, Recursos Humanos (RR. HH.) puede administrar estos tipos de baja. En esta versión, puede configurar qué tipos de baja permiten que los empleados pueden enviar solicitudes de tiempo de indisponibilidad. 

## <a name="coming-soon-in-core-hr"></a>Próximamente en Core HR

### <a name="feature-management-area-in-talent"></a>Área de administración de características en Talent

**Administración de características** se eliminará de **Administración del sistema** debido a problemas con la característica. Volveremos a introducir **Administración de características** en una versión futura. 

### <a name="common-data-service-entity-support-for-custom-fields"></a>Soporte de la entidad de Common Data Service para los campos personalizados

Las siguientes entidades admitirán campos personalizados: **Código de ganancias de nómina**, **Evento de compensación fija**, **Cuadrícula de compensación**, **Período de pago** y **Punto de referencia de compensación**. 

### <a name="new-common-data-service-entities"></a>Nuevas entidades de Common Data Service

La entidad **Códigos de motivo** se agregará a Common Data Service.

### <a name="view-performance-information-for-direct-and-extended-reports-in-manager-self-service"></a>Ver la información de rendimiento para los informes directos y ampliados en autoservicio para directores

Una nueva opción permitirá a los directores ver el rendimiento tanto de los informes directos como de sus informes ampliados. Actualmente, los administradores de línea pueden asignar y actualizar objetivos de rendimiento y emitir nuevos revisiones. Además, los administradores directos y sus empleados pueden mantener y actualizar diarios de rendimiento a fin de garantizar que el proceso de evaluación del rendimiento se desarrolla correctamente. Cuando se implementa este cambio, los administradores podrán ver y mantener la información relacionada con el rendimiento en los informes ampliados además de sus informes directos.

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Los empleados, los administradores y RR. HH. podrán imprimir la evaluación del rendimiento de un empleado.