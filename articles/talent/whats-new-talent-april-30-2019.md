---
title: Novedades y cambios en Dynamics 365 Talent (30 de abril de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/30/2019
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
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2539baba84bffeb21d351cc307191eea3e940515
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528204"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-30-2019"></a>Novedades y cambios en Dynamics 365 Talent (30 de abril de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2270. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="provide-feedback"></a>Proporcionar comentarios

La opción de proporcionar comentarios se encuentra en el menú **Ayuda** (**?**) en Talent. Este menú proporciona acceso a los siguientes recursos:

- Realimentación
- Ayuda
- Introducción
- Soporte
- Ideas
- Acerca de

### <a name="improvements-to-the-user-interface-for-duplicate-employee-detection"></a>Mejoras a la interfaz de usuario para la detección de empleado duplicado

Debido a este cambio, los duplicados ahora se detectan mientras establece los campos del nombre y un indicador de estado muestra el número de duplicados que se han detectado. Se proporciona un vínculo que abre una página donde puede evaluar si debe usar uno de los duplicados. Para evitar interrumpir la entrada de datos, la página de los duplicados no se abre automáticamente. Debe seleccionar el vínculo para abrir la página.

### <a name="common-data-service-entity-support-for-custom-fields"></a>Soporte de la entidad de Common Data Service para los campos personalizados

En la versión de esta semana, las entidades siguientes admiten ahora campos personalizados: Empleo, Tipo de prestación, y Ciclo de pago.

### <a name="an-error-occurs-when-an-off-boarding-checklist-is-assigned-299877"></a>Se produce un error cuando se asigna una lista de comprobación de retirada (299877)

Este cambio corrige un mensaje de error que aparece cuando asigna una lista de comprobación de retirada a un empleado fuera del proceso de despido.

### <a name="the-exited-workers-link-opens-the-wrong-worker-309939"></a>El vínculo de los trabajadores que han salido abre el trabajador incorrecto (309939)

Este cambio corrige un problema que se da cuando se vuelve a contratar a un empleado de otra entidad jurídica e intentará ir al empleado en la lista de salida de trabajadores.

### <a name="the-employee-self-service-compensation-card-doesnt-show-summary-values-when-advanced-security-is-turned-on-315231"></a>La tarjeta de compensación de auto servicio del empleado no muestra valores de resumen cuando la seguridad avanzada está activada (315231)

Este cambio corrige un problema que aparecerá cuando utiliza la seguridad de compensación avanzada. Cuando la seguridad avanzada está activada, el autoservicio para empleados muestra los importes de resumen de compensación para los empleados y los administradores. Antes de este cambio, los valores de resumen aparecían como 0 (cero).

### <a name="if-a-position-without-a-title-is-created-in-common-data-service-no-position-is-created-in-talent-314562"></a>Si se crea un puesto sin un título en Common Data Service, no se creará ninguna posición en Talent (314562)

Los cambios de esta semana corrigen un problema que se daba al crear puestos en Common Data Service pero no se proporcionaba un título.

### <a name="error-message-in-performance-journal-entries-in-employee-self-service-314134"></a>Mensaje de error en entradas del diario de rendimiento del autoservicio del empleado (314134)

Este cambio corrige un problema que aparece cuando adjunta objetivos de rendimiento a las entradas del diario de rendimiento del autoservicio del empleado.

## <a name="in-preview"></a>En vista previa

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir a los códigos de motivo ser especificados en los tipos de baja

Las organizaciones pueden requerir información adicional sobre las solicitudes de indisponibilidad. Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="require-reason-codes-for-specific-leave-types-on-time-off-requests"></a>Requerir códigos de motivo para tipos de baja específicos y solicitudes de indisponibilidad

Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados envíen solicitudes de indisponibilidad. Este requisito podría existir debido a la directiva de la empresa o normas legales. Ahora puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.

### <a name="provide-a-leave-and-absence-transaction-list-for-hr"></a>Proporcionar una lista de baja y la transacción de ausencia para recursos humanos

La capacidad de seguir la indisponibilidad del empleado y comprender cómo se calcula la indisponibilidad no solo ayuda a recursos humanos (RR.HH) a contestar las preguntas del empleado, también ayuda a garantizar proporcionar el tiempo de indisponibilidad preciso a los empleados. Recursos humanos ahora tiene una nueva vista de las transacciones (concesiones, acumulados, ajustes, y solicitudes) para que el personal de RR.HH. pueda ver las razones detrás de los saldos.

## <a name="coming-soon"></a>Próximamente

### <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos

En la platform update 26 para Finance and Operations, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando las notificaciones se desencadenen con un evento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]