---
title: Novedades y cambios en Dynamics 365 Talent (2 de abril de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 04/02/2019
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
ms.search.validFrom: 2019-04-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 04b5a006d4580fe419d81986a90851bc8d611722
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528228"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-april-2-2019"></a>Novedades y cambios en Dynamics 365 Talent (2 de abril de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="approval-emails-in-attract"></a>Los mensajes de correo electrónico de aprobación en Attract
Los nuevos correos electrónicos de aprobación mejoran la visibilidad del proceso de aprobación. Los mensajes de correo electrónico se envían a los aprobadores cuando se da uno de los siguientes escenarios:

- Un solicitante envía un trabajo para su aprobación.
- Se rechaza o aprueba un trabajo.
- Un aprobador no ha actuado sobre una solicitud de aprobación en 24 horas.

Puede personalizar el contenido de los mensajes de correo electrónico de la aprobación con plantillas nuevas.

### <a name="application-and-profile-attachments"></a>Datos adjuntos de la aplicación y del perfil
Las mejoras a la ficha **Documentos** en solicitudes y perfiles de reserva de talentos muestran ahora el nombre del documento y su tipo.

## <a name="changes-in-onboard"></a>Cambios en Onboard
Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="coming-soon-attract-and-onboard"></a>Muy pronto (Attract y Onboard)

### <a name="lifecycle-services-lcs-integration-with-report-a-problem"></a>Integración de Lifecycle Services (LCS) con informar de un problema
En Attract y Onboard, los problemas registrados por los usuarios finales mediante la función de informar de un problema ahora crean automáticamente problemas de soporte en el proyecto LCS del cliente. Los administradores podrán realizar la evaluación de prioridades de los problemas y enviarlos a Microsoft cuando sea necesario. Esto es coherente con cómo los Core HR gestiona los problemas de soporte del usuario final.

## <a name="changes-in-core-hr"></a>Cambios en Core HR
Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2216.

### <a name="platform-update-25-for-finance-and-operations"></a>Platform update 25 para Finance and Operations
Para obtener más información acerca de la Platform update 25 para Finance and Operations, consulte [Características de vista previa en Dynamics 365 for Finance and Operations Platform update 25 (abril de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-25).

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Seguridad de compensación avanzada (fija y variable)
En muchas organizaciones, los administradores de compensación y prestaciones solo pueden tener acceso a ciertos registros de compensación. Estos puede incluir registros para ejecutivos o empleados regionales. Con este cambio, recursos humanos puede administrar y mantener los planes de compensación para distintos grupos de empleados en la organización. Puede asignar roles de seguridad a los planes fijos y variables. Estos roles de seguridad determinan el acceso a los planes y los datos relacionados del empleado, como los registros de sueldo o prima, de forma que sólo dichos roles pueden procesar la compensación para los grupos de empleados.

### <a name="upgrade-to-common-data-service"></a>Actualice a Common Data Service
Las fechas límites para actualizarse a Common Data Service se acercan rápidamente. Inicie sesión en el centro de gestión de Microsoft Power Apps para determinar si su base de datos debe actualizarse. Para obtener más información acerca de las fechas límites y de los pasos necesarios para realizar la actualización, consulte [Actualizar a Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="in-preview"></a>En vista previa

### <a name="allow-reason-codes-to-be-specified-on-leave-types"></a>Permitir a los códigos de motivo ser especificados en los tipos de baja
Las organizaciones pueden necesitar información adicional sobre las solicitudes de indisponibilidad. Ahora puede especificar códigos de motivo para tipos de baja y permitir a empleados seleccionar un código de motivo en sus solicitudes de indisponibilidad.

### <a name="require-reason-codes-for-certain-leave-types-on-time-off-requests"></a>Requerir códigos de motivo para ciertos tipos de baja y solicitudes de indisponibilidad
Las organizaciones pueden requerir códigos de motivo en tipos específicos de baja cuando los empleados registren la indisponibilidad. Esto puede deberse a la política de empresa o a las normas legales. Ahora puede especificar qué tipos de baja requieren un código de motivo, y puede requerir a los empleados especificar un código de motivo para el tipo de baja en sus solicitudes de indisponibilidad.

## <a name="coming-soon"></a>Próximamente

### <a name="improvements-to-the-user-interface-for-duplicate-employee-check"></a>Mejoras a la interfaz de usuario para la comprobación de empleado duplicado
Con este cambio, se detectan los duplicados a medida que se especifican los campos de nombre, y un estado muestra el número de duplicados encontrado. Puede seleccionar el vínculo proporcionado para abrir una nueva página para evaluar si utilizar la coincidencia detectada. Para evitar interrumpir la entrada de datos, el formulario de los duplicados no se abre automáticamente.

###  <a name="email-support-for-alerts"></a>Soporte de correo electrónico para avisos
Con Platform update 25 para Finance and Operations, los usuarios pueden crear reglas de alertas que envían notificaciones por correo electrónico a los contactos cuando se activen con un evento. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]