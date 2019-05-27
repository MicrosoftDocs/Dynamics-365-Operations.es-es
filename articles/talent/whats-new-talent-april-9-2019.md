---
title: Novedades y cambios en Dynamics 365 for Talent (9 de abril de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/09/2019
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
ms.search.validFrom: 2019-04-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 25ef0d49c2600833aefa84d404e00c0c57cfbf52
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519001"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-april-9-2019"></a>Novedades y cambios en Dynamics 365 for Talent (9 de abril de 2019)

[!include [banner](includes/banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integración de Lifecycle Services (LCS) con "informar de un problema"
En Attract y Onboard, los problemas registrados por los usuarios finales mediante la función de informar de un problema ahora crean automáticamente problemas de soporte en el proyecto LCS del cliente. Los administradores podrán realizar la evaluación de prioridades de los problemas y enviarlos a Microsoft cuando sea necesario. Esto es coherente con cómo los Core HR gestiona los problemas de soporte del usuario final.

### <a name="relevance-search"></a>Búsqueda por relevancia
En las reservas de talentos, ahora puede buscar en toda la base de datos del candidato las aptitudes en particular, nombres, o formación académica. Ya no necesita especificar en qué sección del perfil de un candidato desea buscar. Attract busca todo el perfil y resalta todas las coincidencias que se muestran. Attract también busca todos los documentos que están disponibles para un candidato y ordena de forma inteligente los resultados de la búsqueda. Además, puede filtrar los resultados por origen o si son un medallista de plata. Para más información, consulte [Buscar y ver perfiles de candidato](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/attract-talent-pools#search-and-view-candidate-profiles).

### <a name="prospect-recommendations"></a>Recomendaciones de candidato
Attract puede ayudar a iniciar el abastecimiento de un trabajo en cuanto lo active, creando recomendaciones inteligentes de candidatos de la base de datos de candidatos de su organización. Las recomendaciones incluyen las aptitudes y la información de formación identificada mientras se buscan para clientes potenciales relevantes. Estas recomendaciones aparecen en la pestaña **Clientes potenciales** bajo un trabajo, si se habilita durante el proceso de contratación del trabajo. Para obtener más información, consulte [Recomendaciones de clientes potenciales](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/intelligent-recommendations#prospect-recommendations).

### <a name="interviewer-availability-statuses"></a>Estados de disponibilidad del entrevistador
Los programadores de la entrevista pronto podrán ver los estados **Fuera de la oficina, trabajando en otra parte** para los entrevistadores, para ayudar a programar las horas que pueden funcionar mejor para los entrevistadores.

### <a name="candidate-interview-experience-save-calendar-invites"></a>Experiencia de la entrevista del candidato: guardar invitaciones en el calendario
Los candidatos pueden ahora descargar y guardar los eventos de la entrevista en sus calendarios personales mediante un archivo .ics vinculado al correo electrónico con el resumen de la entrevista enviado al candidato.

## <a name="changes-in-onboard"></a>Cambios en Onboard

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integración de Lifecycle Services (LCS) con informar de un problema
En Attract y Onboard, los problemas registrados por los usuarios finales mediante la función de informar de un problema ahora crean automáticamente problemas de soporte en el proyecto LCS del cliente. Los administradores podrán realizar la evaluación de prioridades de los problemas y enviarlos a Microsoft cuando sea necesario. Esto es coherente con cómo los Core HR gestiona los problemas de soporte del usuario final.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2225.

### <a name="percent-of-basis-variable-plans-load-incorrect-amount"></a>Los porcentajes de bases variables cargan la cantidad incorrecta
La versión de esta semana corrige un problema al cargar las primas de compensación variable mediante el porcentaje de planes base.
 
### <a name="date-picker-on-last-day-worked-doesnt-work-correctly"></a>El recolector de la fecha del último día trabajado no funciona correctamente
Este cambio corrige el problema: Cuando un usuario edita **Fecha final del empleo** y selecciona la fecha mediante el control del calendario, se agrega un día a la selección.

###  <a name="limit-personnel-action-types-by-the-action-taken"></a>Limitar tipos de acción de personal por la acción realizada
Este cambio limita los tipos de acción que aparecen al realizar acciones específicas. Por ejemplo, cuando se requiera un puesto nuevo, sólo las nuevas acciones del puesto aparecen en la lista de acciones a seleccionar. Anteriormente aparecían acciones nuevas y editables. 

### <a name="transferring-an-employee-with-compensation-in-a-second-legal-entity"></a>Transferir a un empleado con compensación en una segunda entidad jurídica
Esta versión permite que la compensación termine en una segunda entidad jurídica si la transferencia es para una transferencia entre empresas.

### <a name="unable-to-select-compensation-for-a-future-employment-during-a-transfer"></a>Incapaz de seleccionar la compensación para un empleo futuro durante una transferencia
Al transferir un empleado a una nueva entidad jurídica, ahora puede establecer la compensación para la nueva entidad jurídica durante el proceso de transferencia.

### <a name="user-isnt-able-to-assign-compensation-during-position-assignment"></a>El usuario no puede asignar la compensación durante la asignación de puesto
Agregar una nueva asignación de puesto ahora permite configurar los registros de compensación fija. 

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

###  <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos
Con Platform update 25, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando se activen con un evento. 
