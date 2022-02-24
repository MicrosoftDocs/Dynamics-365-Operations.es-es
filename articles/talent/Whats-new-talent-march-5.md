---
title: Novedades y cambios en Dynamics 365 Talent (5 de marzo de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/05/2019
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
ms.search.validFrom: 2019-03-05
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 115d7cd3d71eaddce2434cb1939c503d36bccdf8
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527299"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-march-5-2019"></a>Novedades y cambios en Dynamics 365 Talent (5 de marzo de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="extending-option-sets-in-attract"></a>Ampliación de conjuntos de opciones en Attract

En Attract, hay varios campos que son conjuntos de opciones en Common Data Service. Se han introducido nuevas capacidades para extender los conjuntos de opciones, comenzando por el campo de motivo **Rechazo**, el campo **Tipo de empleo** , y el campo **Tipo de la antigüedad**.

> [!IMPORTANT]
> La propuesta de empleo en la funcionalidad de LinkedIn requiere el uso de los campos **Tipo de empleo** y **Tipo de antigüedad** en la página **Detalles del trabajo**. Los valores predeterminados de estos campos son compatibles con LinkedIn y se visualizan cuando se registra el trabajo. Si va a publicar trabajos en LinkedIn y modifica los valores del conjunto de opciones existente para estos campos, el trabajo seguirá publicado, pero LinkedIn no mostrará los valores de **Tipo de empleo** y **Tipo de la antigüedad** personalizados.

## <a name="changes-in-onboarding"></a>Cambios en Onboarding

### <a name="private-preview-for-onboard-teams"></a>Versión preliminar privada para los equipos Onboard
Ahora puede compartir y colaborar fácilmente en las plantillas de toda la organización. Para obtener más información, consulte [Compartir prácticas recomendadas en toda la organización mediante los equipos de Onboard](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/share-best-practices-teams).

### <a name="private-preview-for-assignee-placeholders"></a>Vista previa privada para marcadores asignados
Puede enriquecer las plantillas asignando actividades a roles en lugar de personas. Los roles se asignan a individuos en el momento de la creación de la Guía. Para obtener más información, consulte [Optimizar la administración de guías asignando actividades a roles](https://docs.microsoft.com/business-applications-release-notes/April19/dynamics365-talent/onboard/assign-activities-roles)

## <a name="changes-in-core-hr"></a>Cambios en Core HR
**Compilación 8.1.2178**

### <a name="configure-workflow-to-auto-approve-or-follow-workflow-when-an-hr-or-line-manager-submits-or-updates-time-off-requests"></a>Configuración del flujo de trabajo para la aprobación automática o para seguir un flujo de trabajo cuando un director de RR.HH o de línea envía o actualiza solicitudes de licencia
Se han agregado nuevas condiciones de flujo de trabajo para permitir que las solicitudes de la licencia automáticamente sean aprobadas si las envía el jefe de un empleado o RR.HH. Una forma de conseguir esta aprobación automática en un flujo de trabajo es habilitar una acción automática en la aprobación de flujo de trabajo.

Las condiciones que se han agregado son:

- Registrado por - utilizado para evaluar el Id. de usuario del sistema del usuario que envió la solicitud al flujo de trabajo.
- Registrado en nombre de - utilizado para evaluar si la solicitud de licencia se muestra en nombre del trabajador asociado a la solicitud.
- Registrado por recursos humanos - utilizado para evaluar si el usuario del sistema que envió la solicitud al flujo de trabajo tiene un rol de recursos humanos.
- Registrado por el administrador - utilizado para evaluar si el usuario que envió la solicitud de la licencia al flujo de trabajo es administrador de la jerarquía de la línea del trabajador asociado a la solicitud.

### <a name="enable-employee-fixed-compensation-for-future-position-assignments"></a>Habilitación de la compensación fija del empleado para asignaciones de puesto futuras
Es típico que los empleados entren en una organización con una fecha de inicio futura. Este cambio permite definir la compensación fija para los empleados que tienen asignaciones de puesto futuras.

### <a name="position-payroll-fields-are-blank-when-editing-the-position"></a>Los campos de nóminas del puesto están en blanco al editar el puesto
Con este cambio, al solicitar cambios en puestos ya existentes, los campos de nóminas ahora toman como valor predeterminado los valores actuales.

### <a name="other-miscellaneous-bug-fixes"></a>Otras correcciones de errores diferentes
En esta versión se incluyen otras correcciones de errores menores.

### <a name="upgrade-to-common-data-service"></a>Actualice a Common Data Service
Las fechas límites para actualizarse a Common Data Service se acercan rápidamente. Inicie sesión en el centro de gestión de Power Apps para determinar si su base de datos debe actualizarse. Para obtener más información acerca de las fechas límites y de los pasos necesarios para realizar la actualización, consulte [Actualizar a Common Data Service](https://docs.microsoft.com/common-data-service/upgradecds/introduction-upgrade-cds).

## <a name="coming-soon"></a>Próximamente

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Seguridad de compensación avanzada (fija y variable)
En muchas organizaciones, los administradores de compensación y prestaciones solo pueden acceder a ciertos registros de compensación, como registros para los ejecutivos o los empleados basados en regiones. Con este cambio, puede administrar y mantener los planes de compensación para distintos grupos de empleados en la organización. Se pueden asignar roles de seguridad a los planes fijos y variables, lo que determinará el acceso a los planes y los datos del empleado relacionados con los planes, como el salario y los registros de bonificaciones. Solo los roles con acceso podrán procesar la compensación para dichos empleados.

###  <a name="platform-update-24-for-finance-and-operations"></a>Platform update 24 para Finance and Operations
Para obtener detalles adicionales sobre Platform update 24 para Finance and Operations, consulte [Novedades o cambios en la platform update 24 de Finance and Operations (marzo de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-24).
