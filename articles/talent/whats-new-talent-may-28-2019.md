---
title: Novedades y cambios en Dynamics 365 Talent (28 de mayo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2019
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
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 29e941ddab1b2746ccd74d6e335fec7742d1391e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529617"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-may-28-2019"></a>Novedades y cambios en Dynamics 365 Talent (28 de mayo de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="coming-soon-in-attract"></a>Muy pronto en Attract

### <a name="job-approvals-on-home-page"></a>Aprobación de trabajos en la página principal

Las Aprobaciones aparecen en una sección **Aprobaciones** en el panel de información. Los aprobadores pueden revisar los aprobaciones en **Asignada a usted**, que muestra el identificador de trabajo, el título, otros aprobadores y la fecha asignada. Los usuarios que envían un trabajo para su aprobación pueden revisar los trabajos en **Solicitado por usted**, que muestra los aprobadores que aún deben aprobar el trabajo enviado.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2319.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Soporte de la entidad de Common Data Service para los campos personalizados

En esta versión, las entidades siguientes de Common Data Service ahora admiten campos personalizados: Detalle de tasa de prestación, línea de calendario festivo laboral y Empleo.

### <a name="copy-position-now-includes-payroll-details"></a>Copiar posición ahora incluye los detalles de nóminas
Cuando use **Copiar posición** y seleccione todas las opciones, la información de detalles de nóminas se incluirá ahora en la información de la copia. 

## <a name="in-preview-in-core-hr"></a>En Vista preliminar en Core HR

### <a name="restrict-the-leave-types-in-time-off-requests"></a>Limite los tipos de baja en las solicitudes de tiempo de indisponibilidad

Las organizaciones pueden proporcionar muchos tipos diferentes de bajas a los empleados. Algunos de estos tipos de baja no son adecuados para los empleados que solicitan tiempo de indisponibilidad y son administrados en su lugar por recursos humanos (RR. HH.) en su lugar. Con esta versión, puede configurar qué tipos de baja permiten que los empleados pueden enviar solicitudes de tiempo de indisponibilidad. 

### <a name="new-page-to-validate-position-hierarchy-data"></a>Nueva página para validar datos de la jerarquía de puestos

Los recursos humanos (RR. HH.) y los administradores ahora pueden validar la jerarquía directiva para cualquier referencia circular que podría haber sido importada de forma inadvertida. Puede obtener acceso a esta nueva página desde **Administración de organización > Vínculos > Puestos > Validación de la jerarquía de puestos**.

### <a name="specify-reason-codes-on-leave-types"></a>Especificar códigos de motivo en tipos de baja

Las organizaciones pueden requerir información adicional sobre las solicitudes de indisponibilidad. Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Requerir códigos de motivo para tipos de baja específicos y solicitudes de indisponibilidad

Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados envíen solicitudes de indisponibilidad. Este requisito podría existir debido a la directiva de la empresa o normas legales. Puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Proporcionar una lista de baja y la transacción de ausencia para recursos humanos

La capacidad de seguir la indisponibilidad del empleado y comprender cómo se calcula la indisponibilidad no solo ayuda a recursos humanos (RR.HH) a contestar las preguntas del empleado, también ayuda a garantizar proporcionar el tiempo de indisponibilidad preciso a los empleados. Recursos humanos ahora tiene una nueva vista de las transacciones (concesiones, acumulados, ajustes, y solicitudes) para que el personal de RR.HH. pueda ver las razones detrás de los saldos de ausencias.
