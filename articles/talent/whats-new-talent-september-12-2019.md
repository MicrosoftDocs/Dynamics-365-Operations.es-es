---
title: Novedades y cambios en Dynamics 365 for Talent (10 de septiembre de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 9/10/2019
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
ms.search.validFrom: 2019-09-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0aadecd5b37759492f7895ccfda1a777793a08b3
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462464"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-10-2019"></a>Novedades y cambios en Dynamics 365 for Talent (10 de septiembre de 2019)

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

### <a name="candidate-e-mail-login"></a>Inicio de sesión de correo electrónico del candidato

Los candidatos pueden usar ahora una dirección de correo electrónico para crear una cuenta y un inicio de sesión en el sitio de empleo Talent para solicitar trabajos y ver el estado de la solicitud. Esto es además de ya de poder iniciar sesión en el sitio de empleo Talent usando sus cuentas sociales o sus credenciales de organización.

### <a name="job-activation-and-posting"></a>Activación y registro de trabajo

Hemos realizado algunos cambios en la activación y registro de trabajo. Es necesario activar trabajos antes de enviarlos al sitio de empleo Talent o a cualquier sitio de trabajo externo, incluido LinkedIn o Broadbean.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2482. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Puede habilitar las características de vista previa en los entornos tanto de prueba como de entorno cerrado

Al aprovisionar una nueva instancia de Talent, puede especificar si el tipo de instancia es Producción o Espacio aislado. Las instancias del tipo Espacio aislado permiten la prueba temprana de nuevas características. Si desea que una de las instancias existentes se actualicen al tipo de instancia de Espacio aislado, contacte con el Soporte para iniciar la solicitud de cambio.

Para obtener más información sobre cómo se publican los cambios, consulte [Aprovisionar Talent](./provisioning-talent.md).

### <a name="platform-update-29"></a>Actualización 29 de la plataforma

Para obtener más información acerca de la Platform update 29, consulte [Características de vista previa en Dynamics 365 for Finance and Operations platform update 29 (octubre de 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).

### <a name="new-job-base-entity-available-in-data-management-framework-347202"></a>Nueva entidad de la base de trabajo disponibles en el marco de gestión de datos (347202)

En esta versión hay disponible una nueva entidad base de trabajo disponible para importar/exportar datos. 

### <a name="worker-advanced-security-policy-incorrectly-displays-positions-in-position-hierarchy-354868"></a>La política de seguridad avanzada del trabajador muestra puestos incorrectos en la Jerarquía de puestos (354868)

Con esta versión, los puestos ya no aparecen abiertos con un empleado en "blanco" cuando los usuarios tienen acceso restringido.

### <a name="job-form-close-box-wont-close-form-in-certain-situations-342467"></a>El cuadro de cierre desde el formulario de trabajo no cierra formulario en ciertas situaciones (342467)

Esta versión incluye un cambio que permite al formulario de Trabajo cerrarse en todos los escenarios.

### <a name="new-case-on-employee-record-is-locked-for-human-resources-manager-role-337111"></a>El nuevo caso en el registro de empleado se ha bloqueado para su rol de administrador de recursos humanos (337111)

Con este cambio, el formulario de la gestión de casos no está bloqueado al obtener acceso desde el formulario del empleado.

### <a name="employment-end-date-always-defaults-to-235959-351492"></a>La fecha de finalización del empleo siempre usa como predeterminado las 23:59:59 (351492)

Con este cambio, puede cambiar la fecha de empleo a una hora distinta de las 23:59: 59 al finalizar un empleo manualmente.

### <a name="unable-to-set-up-expiration-date-on-an-earning-code-through-data-management-336604"></a>No se puede configurar la fecha de vencimiento en un código de ganancia a través de la gestión de datos (336604)

En esta versión, puede configurar los códigos de ganancias que vencerán a través de la entidad **PayrollWorkerPositionEarningCodeEntity**.

### <a name="employee-development-analytic-report-doesnt-display-data-348737"></a>El informe analítico de desarrollo de empleado no muestra datos (348737)

En la versión de esta semana, los análisis de las aptitudes del empleado se han actualizado para proporcionar el informe de errores correcto.

### <a name="terms-of-employment-datetime-dont-default-to-beginning-of-day-349101"></a>Las condiciones laborales fecha/hora no vuelven al valor predeterminado de comienzo del día (349101)

Con este cambio la fecha/hora inicial usa de forma predeterminada el comienzo del día y la fecha/hora final usa de forma predeterminada el final del día.

### <a name="changing-the-employment-end-date-on-worker-action-form-displays-an-error-354092"></a>Cambiar la fecha final del empleo en el formulario de acción del trabajador muestra un error (354092) 

Este cambio corrige un problema al modificar la fecha de finalización del empleo como parte de la acción del trabajador.

### <a name="applying-onboarding-checklists-across-companies-338433"></a>Aplicar listas de comprobación de incorporación en varias compañías (338433)

Esta versión ahora proporciona la capacidad de aplicar las listas de comprobación de los empleados contratados en entidades jurídicas distintas de la entidad jurídica registrada.

## <a name="in-preview"></a>En vista previa

### <a name="streamlined-employee-entry-and-navigation"></a>Entrada y navegación de empleados optimizadas

Esta funcionalidad ya está disponible en los entornos de espacio aislado. Para activar esta característica, vaya a **Administración del sistema > vinculos > configuración > Parámetros del sistema > características de vista previa**. Seleccione **Formulario y navegación de trabajador mejorado**. Esto habilitará estos cambios para todos los usuarios. Puede desactivar esta opción en cualquier momento.

Para obtener más información, consulte [Entrada y navegación de empleados optimizadas](./streamlined-employee-entry.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]