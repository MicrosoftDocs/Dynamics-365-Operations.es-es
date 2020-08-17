---
title: Novedades o cambios en Dynamics 365 Human Resources (08 de julio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 07/08/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c4382aa7473e2b67201ac00753ac9abe11b3c646
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614371"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Novedades o cambios en Dynamics 365 Human Resources (8 de julio de 2020)

Este tema describe las funciones que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3382. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="database-logging"></a>Registro de base de datos

El registro de la base de datos le permite determinar qué tablas y campos se supervisan. También le permite determinar los eventos que deberían activar el seguimiento de cambios. Utiliza las capacidades de registro de bases de datos para ver estos cambios a lo largo del tiempo. Para más información, vea [Configurar y administrar el registro de bases de datos](hr-admin-database-logging.md).

## <a name="configure-the-name-of-employee-self-service"></a>Configurar el nombre del Autoservicio para empleados

En **Parámetros de Human Resources**, ahora puede cambiar el nombre del espacio de trabajo **Autoservicio para empleados** a **Autoservicio**. Para más información, consulte [Cambiar el nombre del espacio de trabajo Autoservicio para empleados](hr-employee-self-service-workspace-name.md)

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>Acceso a inscripción abierta de administración de prestaciones fuera del período

Esta versión corrige un error por el cual los empleados podían acceder a la inscripción directa de prestaciones fuera del período de inscripción o sin un evento de vida. Como resultado, si necesita hacer una inscripción abierta de demostración en el autoservicio del empleado, debe ajustar las fechas de inscripción abiertas a hoy (o antes) para que sea accesible. Puede cambiar esta configuración en **Gestión de prestaciones > Reglas y períodos de opciones**.

## <a name="email-employee-enrollment-confirmation"></a>Confirmación de inscripción del empleado por correo electrónico

Ahora puede enviar correos electrónicos a los empleados después de que completen su selección de prestaciones. Puede enviar un mensaje predeterminado o utilizar una plantilla de correo electrónico de la organización. Estas configuraciones están en **Parámetros de recursos humanos> Gestión de prestaciones**.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>La baja cancelada aún aparece en el próximo tiempo libre del espacio de trabajo de Personas (441358)

La baja cancelada ya no se muestra como próximo tiempo libre en las tarjetas de bajas del espacio de trabajo **Personas**.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>No se puede usar la propiedad de entidad de departamento en la entidad PositionV2 (456486)

Ahora puede agregar un departamento sin crear una relación duplicada.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity solo debe usar el campo calculado para los planes de jubilación (459779)

Al exportar la entidad **PayrollWorkerEnrolledBenefitDetailEntity**, la exportación determina si debe usar un campo calculado basado en una tabla de tasas o usar el campo **ContribuciónAmountCur** en la tabla de apoyo. La lógica utilizada por la entidad de datos utiliza la tabla de tasas en situaciones donde la aplicación normalmente no lo hace. Esta lógica hace que las exportaciones de la entidad devuelvan un valor cero para esta columna, porque no hay una tabla de tasas de cálculo y el producto no permite que el cliente especifique una.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Traducciones confusas al checo en Gestión de personal y Autoservicio de empleados (400276)

Esta versión corrige las traducciones para **Directorio de empresa**, **Próximo curso registrado**, **Trabajo** y **Posición**.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>La tabla WorkCalendarEmployment no tiene habilitados los campos del sistema creados y modificados (460171)

Los campos del sistema creados y modificados están habilitados ahora en la table **WorkCalendarEmployment** de Human Resources.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Excepción de referencia nula para Contratar y agregar detalles para el futuro empleado (455475)

Esta versión corrige un error (referencia nula) en la entrada simplificada de empleados cuando contrata a un empleado usando la opción **Contratar y agregar detalles**.

## <a name="changes-made-in-the-common-data-service-worker-entity-dont-reflect-in-human-resources-455652"></a>Los cambios realizados en la entidad de trabajadores de Common Data Service no se reflejan en Human Resources (455652)

Los cambios realizados en los siguientes campos de la entidad **Trabajador** en Common Data Service ahora aparecerán en Human Resources:

- **Trabaja en casa**
- **Antigüedad**
- **Fecha de aniversario**
- **Fecha de contratación original**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>El nivel de compensación correcto no se basa por defecto en el trabajo asignado al puesto (394136)

Con este cambio, el nivel de compensación correcto predeterminado se basa en los registros de **Fecha de vigencia** de los **Detalles de posición** y la **Fecha de inicio** de la **Asignación del plan de compensación**.

## <a name="in-preview"></a>En vista previa

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

Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de bajas y ausencias. Esta capacidad proporciona transparencia para el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas. Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).

## <a name="add-attachments-to-time-off-requests"></a>Agregar archivos adjuntos a las solicitudes de permisos

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

## <a name="checklist-entities-included-in-common-data-service"></a>Lista de entidades incluidas en Common Data Service

Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Common Data Service.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)
