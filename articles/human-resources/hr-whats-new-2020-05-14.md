---
title: Novedades y cambios en Dynamics 365 Human Resources (14 de mayo de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 14 de mayo de 2020.
author: andreabichsel
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2c5ae1078e3490fef3383fc6d637df70128683e7
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051026"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-14-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (14 de mayo de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3244. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte para referencia de Lifecycle Services (LCS).

## <a name="platform-changes"></a>Cambios de plataforma

Los cambios de plataforma están incluidos en la versión de esta semana. Para obtener más información, consulte [Actualizaciones de platforma para la versión 10.0.10 de aplicaciones de Finance and Operations (mayo de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-34.md). Esta versión incluye correcciones de errores y cambios en las vistas guardadas.
 
## <a name="ensure-dataverse-picklists-are-consistent-with-leave-enums-436343"></a>Asegurar que las listas de selección de Dataverse sean consistentes con las enumeraciones de bajas (436343)

Las listas de selección de Dataverse ya son consistentes con las enumeraciones de bajas.

## <a name="allow-users-to-configure-leave-request-workflow-based-on-the-request-amount-300044"></a>Permitir a los usuarios configurar el flujo de trabajo de solicitud de baja en función del importe de la solicitud (300044)

Los usuarios pueden configurar los flujos de trabajo de solicitudes de baja en función de los importes de la solicitud.
 
## <a name="new-worker-form-exposes-data-through-the-view-menu-when-advanced-security-is-enabled-403185"></a>El nuevo formulario de trabajador expone datos a través del menú Ver cuando la seguridad avanzada está habilitada (403185)

Esta versión corrige cómo funciona la visualización de trabajadores en entidades jurídicas cuando se habilita el acceso avanzado y se puede acceder a los trabajadores de otras empresas.

## <a name="allow-running-leave-accruals-for-a-single-plan-or-a-single-company-318844"></a>Permitir realizar bajas acumuladas para un solo plan o una sola empresa (318844)

Con este cambio, puede ejecutar acumulaciones para una empresa o un plan.
 
## <a name="show-the-positions-full-time-equivalent-fte-in-the-enrolled-workers-form-414658"></a>Mostrar el equivalente a tiempo completo del puesto (FTE) en el formulario Trabajadores inscritos (414658)

El valor FTE de la posición de un trabajador determina la tasa de acumulación de un trabajador cuando la opción FTE está habilitada en el tipo de baja. Este campo ahora está incluido en el formulario **Trabajadores inscritos** y el diálogo **Inscripción masiva**.

## <a name="add-leave-balance-expiration-batch-job-431266"></a>Agregar trabajo por lotes de vencimiento de saldo de bajas (431266)

Ahora hay disponible un nuevo trabajo por lotes que se ejecuta diariamente. Disminuye el saldo restante cuando las fechas de vencimiento se actualizan.

## <a name="exporting-personal-contacts-for-an-employee-using-the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-the-parent-relationship-type-345893"></a>La exportación de contactos personales para un empleado utilizando la entidad de persona de contacto personal del trabajador no exporta contactos personales con el tipo de relación principal (345893)

La entidad de datos **Persona de contacto personal del trabajador** (**HcmPersonalContactPersonEntity** en DMF y **PersonalContactPerson** en OData) no pudo exportar contactos personales que tienen un tipo de relación **Principal**. Este problema está solucionado para contactos personales creados después de este cambio. Los contactos personales existentes de tipo **Principal** se solucionarán en una versión posterior.

## <a name="reason-codes-display-across-different-scenarios-when-theyre-marked-as-leave-and-absence-and-the-streamlined-employee-form-is-enabled-434163"></a>Los códigos de motivo se muestran en diferentes escenarios cuando están marcados como Baja y ausencia y el formulario de empleado optimizado está habilitado (434163)

Este cambio restringe los códigos de motivo a solo códigos de Baja y ausencia cuando habilita la entrada optimizada de empleados.

## <a name="the-preview-feature-assign-a-leave-plan-to-employees-in-the-future-displays-error-433555"></a>La característica de vista previa Asignar un plan de bajas a los empleados en el futuro muestra el error (433555)

Este cambio corrige un error cuando un plan de bajas tiene dos tipos de bajas asignados e intenta asignar un empleado.

## <a name="getting-started-banner-appears-for-all-users-441731"></a>El banner de inicio aparece para todos los usuarios (441731)

Con este cambio, el banner Introducción está oculto para los usuarios que no sean administradores del sistema o administradores de administración de datos. 

## <a name="the-dataverse-worker-address-entity-works-differently-in-terms-of-date-time-effective-dates-in-human-resources-425071"></a>La entidad Dirección del trabajador en Dataverse funciona de manera diferente en términos de fechas de vigencia en Recursos Humanos (425071)

Este cambio mantiene la información de la dirección alineada en ciertos escenarios, según las fechas de la dirección.

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-425407"></a>No se puede agregar un archivo adjunto a una solicitud de baja aprobada (425407)

Con la versión de esta semana, puede agregar archivos adjuntos a las solicitudes de baja aprobadas sin cambiar la solicitud de baja.

## <a name="in-preview"></a>En vista previa

## <a name="leave-suspension"></a>Dejar suspensión

Puede suspender la baja y la ausencia en Human Resources para un empleado. La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados. Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la licencia crea un ajuste prorrateado al saldo de licencia del empleado. Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Actualizar la experiencia del usuario para indicar que la acumulación está suspendida (429550)

La experiencia del usuario ahora indica que la acumulación se ha suspendido para un plan.

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a>Suspender la acumulación de bajas para los tipos de baja especificados (272447)

En este comunicado, RR. HH. puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas. La baja no remunerada puede ser un tipo, pero no tiene por qué serlo. Puede suspender cualquier baja basada en otro tipo de baja.

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a>Entidad DMF disponible para suspensiones acumuladas (429549)

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="add-reason-code-to-accrual-suspensions-429547"></a>Agregar código de razón a las suspensiones acumuladas (429547)

Se han agregado códigos de motivo a la suspensión acumulada.

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a>Comenzar la transición desde los parámetros de Recursos Humanos a los parámetros de baja y ausencia

Esta versión comienza a combinar los parámetros de Recursos Humanos con los parámetros de Baja y ausencia.

## <a name="carry-forward-rules"></a>Transferir reglas

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]