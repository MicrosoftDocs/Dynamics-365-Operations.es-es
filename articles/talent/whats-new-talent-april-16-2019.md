---
title: Novedades y cambios en Dynamics 365 Talent (16 de abril de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/16/2019
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
ms.search.validFrom: 2019-04-16
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0781a479ebf37334d8eba18ea6d69d7cfb9db9ea
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024146"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-16-2019"></a>Novedades y cambios en Dynamics 365 Talent (16 de abril de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="process-auditing"></a>Auditoría de proceso

Ahora puede realizar el seguimiento de los cambios realizados a los candidatos, las vacantes de trabajo, o a las solicitudes de trabajo. Para obtener más información, consulte [Seguir los cambios en los datos de contratación](process-auditing.md).

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2239. Los números entre paréntesis hacen referencia a los números de soporte en Lifecycle Services (LCS).

### <a name="compensation-region-compensation-level-benefit-option-and-skill-type-entities-in-common-data-service-updated-to-include-customer-field-support"></a>Las entidades de la región de compensación, nivel de compensación, opción de prestación y del tipo de aptitud en Common Data Service se actualizaron para incluir el soporte del campo del cliente

Con esta versión, se han actualizado a estas entidades de Common Data Service para incluir la capacidad de incluir el campo personalizado agregado con el Talent: Core HR.

### <a name="new-common-data-service-entity-support-for-compensation-vesting-rules-compensation-variable-plan-variable-compensation"></a>Nuevo soporte de la entidad de Common Data Service para: Reglas de atribución de compensación, Plan de compensación variable y Compensación variable

Con esta versión se han agregado las Reglas de atribución de compensación, el Plan variable de compensación, y a las entidades de Compensación variable a Common Data Service. Estas entidades también son compatibles con campos personalizados agregados a través de Talent: Core HR.

### <a name="powerbi-refresh-issues-314342"></a>Problemas de actualización de PowerBI (314342)

Este cambio corrige un problema con los informes de PowerBI actualizándose correctamente.

### <a name="unable-to-click-directly-through-on-transition-tasks-in-employee-self-service-303309"></a>Incapaz de hacer clic directamente en las tareas de transición en el autoservicio del empleado (303309)

Este cambio permite a los usuarios con el rol de empleado seleccionar y actualizar tareas de transición desde la lista de tareas pendientes.

### <a name="performance-feedback-email-message-updated-309615"></a>Actualizado el correo electrónico de comentarios de rendimiento (309615)

Con este cambio, aparece un mensaje de confirmación cuando se registra correctamente un comentario.

### <a name="missing-tables-in-word-template-308048"></a>Faltan tablas en la plantilla de Word (308048)

Con este cambio, al crear una plantilla de Word con el empleado y la información de aptitudes, sólo las aptitudes del empleado seleccionado aparecen en el documento de Word.

### <a name="when-applying-an-offboarding-checklist-an-error-is-displayed-299877"></a>Al aplicar una lista de comprobación de desvinculación se mostrará un error. (299877)

Este cambio corrige un error cuando se aplica una lista de comprobación de desvinculación directamente desde el formulario del trabajador.

## <a name="in-preview"></a>En vista previa

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir a los códigos de motivo ser especificados en los tipos de baja

Las organizaciones pueden necesitar información adicional sobre las solicitudes de indisponibilidad. Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Requerir códigos de motivo para ciertos tipos de baja y solicitudes de indisponibilidad

Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados registren la indisponibilidad. Esto puede deberse a la política de empresa o a las normas legales. Ahora puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.

### <a name="provide-leave-and-absence-transaction-list-for-hr"></a>Proporcionar lista de baja y la transacción de ausencia para recursos humanos

Seguir la indisponibilidad del empleado y comprender cómo se calcula la indisponibilidad no solo ayuda a recursos humanos a contestar las preguntas del empleado, también garantiza proporcionar el tiempo de indisponibilidad preciso a los empleados. Recursos humanos ahora tiene una nueva vista de las transacciones (concesiones, acumulados, ajustes, y solicitudes) para ver las razones detrás de los saldos.

## <a name="coming-soon"></a>Próximamente

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Mejoras a la interfaz de usuario para la comprobación de empleado duplicado

Con este cambio, se detectan los duplicados a medida que se especifican los campos de nombre, y un estado muestra el número de duplicados encontrado. Puede seleccionar el vínculo proporcionado para abrir una nueva página para evaluar si utilizar la coincidencia detectada. Para evitar interrumpir la entrada de datos, el formulario de los duplicados no se abre automáticamente.

### <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos

Con Platform update 25 para Finance and Operations, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando se activen con un evento.


