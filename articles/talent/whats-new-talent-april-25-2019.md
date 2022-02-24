---
title: Novedades y cambios en Dynamics 365 Talent (23 de abril de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/23/2019
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
ms.search.validFrom: 2019-04-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 53faf972759c8f770017fcd3a87920410988e626
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527201"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-23-2019"></a>Novedades y cambios en Dynamics 365 Talent (23 de abril de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2253. Los números entre paréntesis hacen referencia a los números de soporte en Lifecycle Services (LCS).

### <a name="common-data-service-entity-support-for-custom-fields"></a>Soporte de la entidad de Common Data Service para los campos personalizados
Con la versión de esta semana, las entidades siguientes admiten campos personalizados: Nivel de compensación, Opción de prestación, Tipo de aptitud, y Región de compensación.

### <a name="additional-odata-entities-302992"></a>Entidades adicionales OData (302992)
Ahora se admite a las entidades siguientes dentro de OData: Experiencia profesional del trabajador y Estudios del trabajador.
   
### <a name="performance-journal-attachments-for-managers-and-employees-308248"></a>Datos adjuntos de diario de rendimiento para los administradores y empleados (308248)
Con esta versión, los datos adjuntos están disponibles para los administradores y los empleados al crear y actualizar entradas del diario de rendimiento.

### <a name="employee-rehire-flag-always-available-310047"></a>Indicador de contratar de nuevo al empleado siempre disponible (310047)
La opción de contratar de nuevo al empleado disponible para actualizarse fuera del proceso de despido. 

### <a name="cannot-change-the-name-of-my-payment-method-308815"></a>No puede cambiar el nombre de **Mi método de pago** (308815)
La personalización se ha habilitado para permitir que la etiqueta **Mi método de pago** se cambie en el autoservicio del empleado.

### <a name="financial-dimensions-against-a-position-cant-be-deleted-293908"></a>Las dimensiones financieras con un puesto no se pueden eliminar (293908)
Las dimensiones financieras podrán eliminarse al solicitar un cambio para un puesto existente y cuando las dimensiones financieras traspasan límites de la empresa. 

### <a name="customer-is-unable-to-publish-back-data-into-talent-when-opening-the-data-from-excel-302955"></a>El cliente no puede publicar devolver datos a Talent al abrir los datos de Excel (302955)
Este cambio corrige un problema de la publicación al usar las tablas relacionadas.

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
## <a name="known-issues"></a>Problemas conocidos

### <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos
Con Platform update 26 para Finance and Operations, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando se activen con un evento.
