---
title: Novedades y cambios en Dynamics 365 Human Resources (06 de agosto de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 6 de agosto de 2020.
author: andreabichsel
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a8058c1acdde20a1b48130fa1e8b75aa415bafce
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691985"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Novedades y cambios en Dynamics 365 Human Resources (06 de agosto de 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources. Los cambios se aplican al número de compilación 8.1.3444. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.

## <a name="platform-update-1001236-is-now-available"></a>La Platform update 10.0.12(36) ya está disponible.

Para obtener más información, consulte [Platform updates para la versión 10.0.12 de aplicaciones de finanzas y operaciones (agosto de 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md).

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>Entidades del marco de gestión de datos (DMF) para la gestión de ventajas
 
Las entidades de gestión de ventajas se están lanzando. Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas. Una plantilla de gestión de ventajas estará disponible para mover datos. La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos. Para obtener más información, consulte:

- [Compatibilidad con la entidad DMF](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
- [Visión general de la administración de datos](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire crea un flujo de trabajo para comprar y vender solicitudes de licencia (446557)

Para obtener más información, consulte:

- [Permitir que los empleados compren y vendan licencias](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) en el plan de la segunda ola de lanzamiento de Dynamics 365 en 2020
- [Gestionar directivas de compra y venta de bajas](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar y vender bajas](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>La entidad Direcciones postales de los trabajadores V2 tiene acceso a través de entidades legales con acceso restringido (459126)

Con este cambio, la entidad **Dirección postal de trabajador V2** estará limitada en función del acceso de entidad jurídica otorgado al usuario.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>El hipervínculo del correo electrónico de flujo de trabajo no abre las revisiones relevantes (437398)

Ahora, cuando usa el marcador de posición para abrir una revisión de rendimiento en el flujo de trabajo de revisión, el hipervínculo generado en el correo electrónico abre el registro seleccionado.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>Nuevas entidades para comprar y vender solicitudes de licencia (473180)

Ahora las entidades del marco de administración de datos están disponibles para la compra y venta de licencias. Para más información, consulte [Información general sobre la administración de datos](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>Al ver información de registros y utilizar filtros avanzados, un usuario puede obtener acceso a los registros de otros empleados (472490)

Con este cambio, los usuarios de autoservicio para empleados solo pueden acceder a sus propios registros mientras utilizan el autoservicio para empleados. Ver información de registro mientras se cambia la opción de filtrado ya no expone datos adicionales.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>Los análisis de gestión de personal incluyen registros de trabajadores que se han ido (382893)

En esta versión, los análisis de administración de personal solo incluyen a los trabajadores activos. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>No se puede procesar un aumento por méritos para un empleado (473125)

Este cambio permite introducir aumentos por méritos al cambiar la fecha de vigencia del nuevo aumento por méritos.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>El flujo de trabajo de revisión se puede iniciar más de una vez (467541)

Con este cambio, el flujo de trabajo de revisión del rendimiento solo puede iniciar una vez. El estado del supervisor ya no muestra la opción de iniciar la revisión.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>El flujo de trabajo de solicitud de baja finaliza por error al cancelar una solicitud de baja aprobada (472063)

En esta versión, al cancelar una solicitud de baja aprobada, el estado de la solicitud ya no permanece aprobado y el flujo de trabajo continuará.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>El sistema sugiere trabajadores que se han ido al crear un nuevo formulario de revisión a partir de la plantilla (460624)

Con este cambio, los trabajadores que se han ido ya no estarán disponibles al crear nuevas revisiones a partir de una plantilla. No se pueden crear revisiones para empleados que están fuera de las fechas de su empleo.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>Detección de referencia circular de jerarquía de puestos (415879)

Con este cambio, la detección de referencia circular de la jerarquía de puestos se limita a un solo punto en el tiempo. Puede ejecutar la detección de referencias circulares para diferentes fechas a fin de comprobar que no haya referencias circulares en la estructura jerárquica.

## <a name="buy-and-sell-leave"></a>Comprar y vender bajas 

Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja. Este proceso a menudo se gestiona manualmente. Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos. Agiliza el proceso de gestión de bajas y ayuda a eliminar errores. Para obtener más información, consulte:

- [Permitir que los empleados compren y vendan licencias](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) en el plan de la segunda ola de lanzamiento de Dynamics 365 en 2020
- [Gestionar directivas de compra y venta de bajas](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Comprar y vender bajas](./hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Acumulación de bajas para una sola compañía o plan único

Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de bajas y ausencias. Esta capacidad proporciona transparencia para el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas. Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Agregar archivos adjuntos a las solicitudes de permisos

La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19. Los empleados ahora pueden agregar estos archivos adjuntos. También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja. Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Agregar código de razón a las suspensiones acumuladas 

Se han agregado códigos de motivo a la suspensión acumulada.

## <a name="carry-forward-rules"></a>Transferir reglas 

Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan. Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días. Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Suspender la acumulación de bajas para los tipos de baja especificados

Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas. La baja no remunerada puede ser un tipo, pero no tiene por qué serlo. Puede suspender cualquier baja basada en otro tipo de baja.

## <a name="in-preview"></a>En vista previa

### <a name="mandatory-fields"></a>Campos obligatorios

Ahora puede hacer que los campos sean obligatorios mediante las características de personalización de Recursos Humanos. Esta característica requiere **Vistas guardadas**. Para obtener más información sobre las vistas guardadas, consulte:

- [Vistas guardadas: disponibilidad general](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) en el plan del segundo lanzamiento de versiones de Dynamics 365 en 2020
- [Crear formularios que usan completamente las vistas guardadas](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Aplicación Human Resources en Teams

Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams. Pueden interactuar con un bot para crear solicitudes de baja. Para obtener más información, consulte:

- [Experiencia de bajas y ausencias de empleados en Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020
- [Aplicación Human Resources en Teams](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidad DMF disponible para suspensiones acumuladas

Ahora está disponible una entidad DMF para suspensiones acumuladas.

## <a name="coming-soon"></a>Próximamente

## <a name="checklist-entities-included-in-dataverse"></a>Lista de entidades incluidas en Dataverse

Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.

## <a name="known-issues"></a>Problemas conocidos

Es posible que el espacio de trabajo **Administración de características** muestre características que están deshabilitadas como características en versión preliminar cuando estén disponibles de forma generalizada. A continuación se muestra una lista de características disponibles de forma generalizada que indican un estado incorrecto. 

1.  Administración de prestaciones
2.  Gestión de casos
3.  Registro de base de datos (auditoría)
4.  Acumulación de bajas para una sola empresa o un solo plan
5.  Suspensión de acumulación de permisos y ausencias
6.  Código de motivo de ajuste de saldo y comentario
7.  Comprar y vender bajas
8.  Calendario de bajas y ausencias
9.  Reglas transferibles de baja
10. Auditoría de acumulación de bajas
11. Eliminación de acumulaciones de bajas
12. Redondeo de acumulación de bajas
13. Configurar varios tipos de baja en un solo plan de bajas
14. Actualizar mejoras de permiso
15. Usar FTE de un empleado para acumulaciones
16. Vista de compensación entre empresas
17. Imprimir evaluaciones del rendimiento
18. Correcciones de vacaciones de acumulación de bajas

## <a name="see-also"></a>Consulte también

[Novedades y cambios en Human Resources](hr-admin-whats-new.md)</br>
[Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Actualizar proceso](hr-admin-setup-update-process.md)</br>
[Administrar características](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]