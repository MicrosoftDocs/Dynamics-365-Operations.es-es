---
title: Novedades y cambios en Dynamics 365 Human Resources (28 de mayo de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 28 de mayo de 2020.
author: andreabichsel
ms.date: 05/28/2020
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
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 624201841b512b01daf94d13e3d9fe7c381f5c11b328d57e22fbd73e1066bf88
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741390"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (28 de mayo de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3287. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>La entidad LeaveRequest no funciona cuando se habilitan varios tipos por plan de baja (447498)

Con este cambio, **LeaveEnrollmentV2Entity** ya está disponible para corregir el error que ocurre cuando habilita varios tipos de licencia.

## <a name="batch-contention-reduction-feature-preview-446619"></a>Función de reducción de contención por lotes (vista previa) (446619)

Cuando habilita esta característica, puede esperar una reducción en el bloqueo de las tablas del marco de trabajo por lotes al seleccionar tareas y finalizar trabajos.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>UpdateConflict al guardar el trabajador impide editar un registro en Personas (427915)

Este cambio corrige un error al agregar un nuevo trabajador, actualizar la información de la dirección y cambiar las preferencias de idioma. En este escenario único, apareció un error que indica que el registro no se pudo actualizar. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>No se puede agregar un archivo adjunto a una solicitud de baja aprobada para volver a enviarla (425407)

Este cambio ahora permite adjuntos con las solicitudes de baja aprobadas.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>El usuario puede introducir una compensación para un empleado en un formulario de entidad legal diferente (409529)

Este cambio desactiva las opciones de compensación para evitar la entrada accidental de registros de compensación para la entidad jurídica incorrecta.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>Error cuando se transfiere a un empleado y la fecha de asignación del puesto de trabajador es anterior a la duración del puesto (429402)

Los mensajes de error al transferir a un empleado en este escenario se han actualizado para describir mejor los cambios necesarios para corregir el problema.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Capacidades de archivos adjuntos en la inscripción de beneficios de autoservicio para empleados
 
Ahora puede agregar archivos adjuntos durante el proceso de inscripción de beneficios para cada plan en el que se inscribe el empleado. Entonces puede ver los archivos adjuntos dentro del formulario **Ventaja de trabajador inscrito**.

## <a name="in-preview"></a>En vista previa

## <a name="human-resources-application-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para más información, consulte [Aplicación de recursos humanos en Teams](./hr-admin-teams-leave-app.md). 

## <a name="leave-suspension"></a>Dejar suspensión

Puede suspender la baja y la ausencia en Human Resources para un empleado. La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados. Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la licencia crea un ajuste prorrateado al saldo de licencia del empleado. Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Actualizar la experiencia del usuario para indicar que la acumulación está suspendida (429550)

La experiencia del usuario ahora indica que la acumulación se ha suspendido para un plan.

## <a name="coming-soon"></a>Próximamente

## <a name="database-logging-in-preview-in-june"></a>Registro de base de datos (en vista previa en junio)

La característica de registro de la base de datos le permite determinar qué tabla y campos se deben monitorizar. También le permite determinar los eventos que deberían activar el seguimiento de cambios. Las capacidades de consulta están disponibles para ver estos cambios a lo largo del tiempo.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>Comprar y vender baja (en vista previa el 1 de junio)

Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja. Este proceso a menudo se gestiona manualmente. Esta característica proporciona una forma más automatizada de gestionar políticas y solicitudes para el departamento de recursos humanos, y ayuda a eliminar errores al tiempo que simplifica el proceso de gestión de bajas. Para obtener más información, consulte:

- [Gestionar directivas de compra y venta de bajas](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar y vender bajas](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades del marco de gestión de datos (DMF) para la gestión de ventajas
 
Las entidades de gestión de ventajas se están lanzando. Las entidades DMF permiten importar y exportar datos para configurar fácilmente la gestión de ventajas. Una plantilla de gestión de ventajas también estará disponible para mover datos. La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>Agregar código de razón a las suspensiones acumuladas (1 de junio)

Se han agregado códigos de motivo a la suspensión acumulada.

## <a name="carry-forward-rules-june-1"></a>Reglas de transferencia (1 de junio)

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>Suspender la acumulación de bajas para los tipos de baja especificados (1 de junio)

En este comunicado, RR. HH. puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas. La baja no remunerada puede ser un tipo, pero no tiene por qué serlo. Puede suspender cualquier baja basada en otro tipo de baja.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>Entidad DMF disponible para suspensiones acumuladas (1 de junio)

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]