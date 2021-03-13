---
title: Novedades o cambios en Dynamics 365 Human Resources (25 de junio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 23 de junio de 2020.
author: andreabichsel
manager: tfehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ad80e53c0a24d602ac446d3e0765f397dd0fc2d9
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127506"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Novedades o cambios en Dynamics 365 Human Resources (23 de junio de 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3347. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>Cuando una inscripción expira para un empleado despedido, el tipo de baja, el saldo y la cantidad se borran en el formulario de inscripción de licencia (444867)

Los valores en **Tipo de baja**, **Saldo** y **Cantidad** ahora se mantienen en lugar de borrarse al hacer esta selección.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>Saldo pronosticado incorrecto cuando se habilita la nueva función (Dejar acumulación para una sola compañía o un solo plan) (456553)

El saldo pronosticado correcto ahora aparece cuando la acumulación de baja para una sola compañía o un solo plan se han habilitado.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>Entidades con relaciones que dan como resultado propiedades de navegación duplicadas (456486)

Esta versión corrige un problema con las propiedades de navegación (relación) de varias entidades. Se detectan relaciones duplicadas. Todos estos escenarios han sido corregidos.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>Comentarios entre empresas sobre la evaluación del rendimiento (455536)

Los comentarios entre empresas ahora son visibles en las revisiones de rendimiento con esta solución. Este cambio corrige la vista de los comentarios de los revisores que se introdujeron en diferentes compañías para la misma revisión de rendimiento.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>Inconsistencia en mostrar datos de gestión de compensación (432562)

Ahora se mantiene una vista coherente de los datos de compensación en el autoservicio de Manager. Dependiendo de cómo navegue a los **Detalles de compensación** de un trabajador, los datos de compensación ahora se muestran constantemente a los gerentes.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>La fecha de vigencia fija del plan de compensación es la fecha de hoy (411994)

La fecha de inicio de la compensación ahora se basa en la fecha de inicio del puesto asignado al empleado.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>El formulario de baja y ausencia Habilitar la definición de medio día se desactiva cuando se abre el formulario (452607)

Con este cambio, **Habilitar definición de medio día** se habilitará hasta que existan nuevas transacciones de baja. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>No se puede publicar en HcmDiscussionEntity a través de Excel; Error de campo TotalRatingScore (453899)

Ahora puede actualizar el campo **TotalRatingScore** usando **HCMDiscussionEntity** en el diseñador de libros de Excel.

## <a name="in-preview"></a>En vista previa

## <a name="database-logging"></a>Registro de base de datos

El registro de la base de datos le permite determinar qué tablas y campos se supervisan. También le permite determinar los eventos que deberían activar el seguimiento de cambios. Utiliza las capacidades de registro de bases de datos para ver estos cambios a lo largo del tiempo. Para más información, vea [Configurar y administrar el registro de bases de datos](hr-admin-database-logging.md).

## <a name="mandatory-fields"></a>Campos obligatorios 

Ahora puede hacer que los campos sean obligatorios utilizando las capacidades de personalización de Human Resources. Esta característica requiere **Vistas guardadas**.

## <a name="human-resources-application-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para más información, consulte [Aplicación de recursos humanos en Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades del marco de gestión de datos (DMF) para la gestión de ventajas
 
Las entidades de gestión de ventajas se están lanzando. Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas. Una plantilla de gestión de ventajas estará disponible para mover datos. La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.

## <a name="buy-and-sell-leave"></a>Comprar y vender bajas 

Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja. Este proceso a menudo se gestiona manualmente. Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos. Agiliza el proceso de gestión de bajas y ayuda a eliminar errores. Para obtener más información, consulte:

- [Gestionar directivas de compra y venta de bajas](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar y vender bajas](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Acumulación de bajas para una sola compañía o plan único

Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de licencia y ausencias. Esta capacidad proporciona transparencia en el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas. Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Agregar archivos adjuntos a las solicitudes de tiempo libre

La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19. Los empleados ahora pueden agregar estos archivos adjuntos. También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja. Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Agregar código de razón a las suspensiones acumuladas 

Se han agregado códigos de motivo a la suspensión acumulada.

## <a name="carry-forward-rules"></a>Transferir reglas 

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspender la acumulación de bajas para los tipos de baja especificados

Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas. La baja no remunerada puede ser un tipo, pero no tiene por qué serlo. Puede suspender cualquier baja basada en otro tipo de baja.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidad DMF disponible para suspensiones acumuladas 

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="coming-soon"></a>Próximamente

## <a name="configure-the-name-of-employee-self-service"></a>Configurar el nombre de Autoservicio para empleados

Una nueva opción estará disponible en los **parámetros de Human Resources** para actualizar el nombre del espacio de trabajo de autoservicio del empleado a Autoservicio.

## <a name="checklist-entities-included-in-dataverse"></a>Lista de entidades incluidas en Dataverse

Las entidades de lista de verificación para los procesos de incorporación, retirada, transferencias y negocios estarán disponibles pronto dentro de Dataverse.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)