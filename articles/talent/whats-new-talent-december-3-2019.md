---
title: Novedades y cambios en Dynamics 365 Talent (3 de diciembre de 2019)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 12/03/2019
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
ms.search.validFrom: 2019-12-03
ms.dyn365.ops.version: Talent
ms.openlocfilehash: bf1ad4ca2e0ab18aaa35a7410d80a54e7a2160ce
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528702"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-december-3-2019"></a>Novedades y cambios en Dynamics 365 Talent (3 de diciembre de 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Cambios en Attract

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Cambios en Onboard

Este lanzamiento incluye correcciones de errores de menor importancia para Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Cambios en Core HR

Los cambios que se describen en esta sección se aplican a la compilación número 8.1.2646. Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en Microsoft Dynamics Lifecycle Services (LCS).

### <a name="feature-management-workspace"></a>Espacio de trabajo Administración de características.

El espacio de trabajo **Administración de características** proporciona una lista de características entregadas en cada versión. De forma predeterminada, las nuevas características están desactivadas. Puede usar el espacio de trabajo para activarlas y ver su documentación. Para obtener más información acerca de la administración de características, consulte [Visión general de la Administración de características](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todas las características nuevas siguen en versión preliminar durante al menos 30 días como mínimo, y normalmente 30-60 días. Las características más importantes están disponibles en octubre y abril de cada año tras el periodo de prueba preliminar. En cuanto vea características nuevas en el espacio de trabajo **Administración de características**, puede activarlas. Algunas características pueden estar activadas de forma predeterminada.
 
A veces, una característica entera estará activada de forma predeterminada y no se puede desactivar (por ejemplo, el espacio de trabajo **Administración de características**).
 
Cuando una característica esté disponible, se puede activar y desactivar en los entornos de producción. El espacio de trabajo **Administración de características** indica cuando una característica de versión preliminar pasará a ser obligatoria. Esta fecha es un el 1 de octubre o el 1 de abril para que se corresponda con los planes semestrales de publicación. No pueden desactivar características obligatorias. Hasta que llegue a ser obligatoria, se puede activar y desactivar una característica en todos los entornos.

### <a name="add-automatic-scheduling-of-batch-job-history-cleanup-332528"></a>Adición de programación automática de limpieza de historial de trabajos por lotes (332528)

Con este cambio, el **Historial de trabajo por lotes** se ejecuta todas las noches y elimina los elementos del historial de trabajos por lotes que tengan más de 30 días.

### <a name="talent-doesnt-respond-in-worker-actions-when-identification-number-length-doesnt-match-the-identification-type-390971"></a>Talent no responde en las acciones de trabajador cuando la longitud del número de identificación no coincide con el tipo de identificación (390971)

Esta versión corrige el problema que ocurre cuando la longitud del número de identificación no coincide con la definición en el tipo de identificación. 

### <a name="fixed-compensation-doesnt-update-level-with-changes-to-position-details--348085"></a>La compensación fija no actualiza el nivel con cambios en los detalles de puesto (348085)

En la versión de esta semana, **Fecha inicial de compensación** determina el trabajo asociado con el puesto en ese momento al crear un nuevo registro de compensación fija para un empleado.

### <a name="workers-employees-and-contractors-lists-show-worker-type-as-both-when-they-should-only-be-worker-or-contractor-384473"></a>Las listas de trabajadores, empleados y contratistas muestran Ambos como Tipo de trabajador cuando debería ser solo Trabajador o Contratista (384473)

Este cambio refleja con precisión el tipo de trabajador especificado (contratista o empleado).

### <a name="email-notifications-for-new-hire-actions-dont-contain-name-information-due-to-security-policies-383402"></a>Las notificaciones por correo electrónico para nuevas acciones de contratación no contienen información sobre el nombre por las directivas de seguridad (383402)

Este cambio corrige la información que se muestra en los campos de nombre o apellido dentro de los marcadores de posición para el flujo de trabajo cuando la seguridad avanzada está habilitada.

### <a name="system-allows-two-full-day-leave-requests-for-the-same-day-379284"></a>El sistema permite dos solicitudes de licencia de día completo para el mismo día (379284)

Con este cambio, no se pueden emitir dos solicitudes de licencia para el mismo día. 

### <a name="address-changes-list-should-be-sorted-by-effective-date-352798"></a>La lista de cambios de dirección se debe ordenar por Fecha de vigencia (352798)

Con este cambio, ahora la lista de cambio de dirección se ordena por **Fecha de vigencia**.

### <a name="leave-requests-should-allow-deletes-from-common-data-service-to-talent-376999"></a>Las solicitudes de licencia deben permitir a Talent realizar eliminaciones de Common Data Service (376999)

Con este cambio, las solicitudes de licencia en estado de borrador o canceladas se pueden eliminar primero de Common Data Service y después de Talent.

### <a name="delete-earning-codes-is-allowed-when-the-same-earning-code-is-assigned-to-an-employee-371792"></a>Se permite eliminar códigos de ganancias cuando se asigna el mismo código de ganancias a un empleado (371792)

En esta versión primero debe eliminar el código de ganancias del empleado antes de eliminar el código de ganancias del sistema.

### <a name="leave-and-absence-workflow-with-two-approval-stages-fails-to-complete--391116"></a>El flujo de trabajo de bajas y ausencias con dos etapas de aprobación no se completa (391116)

Con este cambio, el flujo de trabajo de bajas y ausencias continúa durante todos los pasos cuando hay más de una etapa de aprobación configurada para la solicitud.

### <a name="issue-date-doesnt-sync-to-common-data-service-when-updated-or-entered-in-talent-397361"></a>La fecha de emisión no se sincroniza con Common Data Service cuando se actualiza o introduce en Talent (397361)

Este cambio corrige un problema por el que la fecha de emisión de registros de **Identificación de persona** no se sincronizaba con Common Data Service desde Talent

### <a name="hierarchy-circular-reference-error-issued-when-assigning-a-manager-to-a-position-386659"></a>Error de referencia circular de jerarquía emitido al asignar un director a un puesto (386659)

Este cambio corrige un escenario único en el que aparece un error de referencia circular al asignar un director nuevo a un puesto.

### <a name="common-data-service-entities-that-now-support-custom-fields"></a>Entidades de Common Data Service que ahora admiten campos personalizados

Ahora las siguientes entidades de Common Data Service admiten campos personalizados:

| Nombre | Entidad |
| --- | --- |
| Desembolso de cuenta bancaria | cdm_bankaccountdisbursement |
| Frecuencia de cálculo de la prestación | cdm_benefitcalculationfrequency |
| Período de pago de la frecuencia de cálculo de prestación | cdm_benefitcalculationfrequencypayperiod |
| Índice de cálculo de la prestación | cdm_benefitcalculationrate |
| Detalle de índice de cálculo de la prestación | cdm_benefitcalculationratedetail |
| Opción de prestación | cdm_benefitoption |
| Plan de prestaciones | cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados) |
| Tipo de prestación | cdm_benefittype |
| Calendario de proceso de negocio | cdm_businessprocesscalendar |
| Asignación de grupo de procesos empresariales | cdm_businessprocessgroupassignment |
| Grupo de tareas de biblioteca de procesos empresariales | cdm_businessprocesslibrarytaskgroup |
| Etapa de proceso empresarial | cdm_businessprocessstage |
| Encabezado de plantilla de lista de comprobación | cdm_businessprocesstemplateheader |
| Tarea de plantilla de lista de comprobación | cdm_businessprocesstemplatetask |
| Compañía | cdm_company |
| Plan de compensación fija | cdm_compensationfixedplan |
| Cuadrícula de compensación | cdm_compensationgrid |
| Nivel de compensación | cdm_compensationlevel |
| Frecuencia de pago de compensación | cdm_compensationpayfrequency |
| Configuración de puntos de referencia de compensación | cdm_compensationreferencepointsetup |
| Línea de configuración de puntos de referencia de compensación | cdm_compensationreferencepointsetupline |
| Región de compensación | cdm_compensationregion |
| Estructura de compensación | cdm_compensationstructure |
| Plan de compensación variable | cdm_compensationvariableplan |
| Nivel de plan de compensación variable | cdm_compensationvariableplanlevel |
| Tipo de plan de compensación variable | cdm_compensationvariableplantype |
| Departamento | cdm_department |
| Empleo | cdm_employment |
| Origen étnico | cdm_ethnicorigin |
| Evento de compensación fija | cdm_fixedcompensationevent |
| Puesto | cdm_job |
| Función de trabajo | cdm_jobfunction |
| Puesto de trabajo | cdm_jobposition |
| Tipo de trabajo | cdm_jobtype |
| Idioma | cdm_language |
| Transacciones bancaria de bajas | cdm_leavebanktransaction |
| Inscripción en baja | cdm_leaveenrollment |
| Plan de bajas | cdm_leaveplan |
| Solicitud de baja | cdm_leaverequest |
| Detalles de solicitud de baja | cdm_leaverequestdetail |
| Tipo de baja | cdm_leavetype |
| Código de auditoría de tipo de baja | cdm_leavetypereasoncode |
| Ciclo de pago | cdm_paycycle |
| Período de pago | cdm_payperiod |
| Código de ganancia de nómina | cdm_payrollearningcode |
| Agencia emisora de identificación de personas | cdm_personidentificationissuingagency |
| Tipo de puesto | cdm_positiontype |
| Asignación del trabajador del puesto | cdm_positionworkerassignmentmap |
| Código de motivo | cdm_reasoncode |
| Tipo de aptitud | cdm_skilltype |
| Región de impuestos | cdm_taxregion |
| Regla de atribución | cdm_vestingrule |
| Estado de veterano | cdm_veteranstatus |
| Calendario de trabajo | cdm_workcalendar |
| Día de calendario de trabajo | cdm_workcalendarday |
| Vacaciones calendario de trabajo |cdm_workcalendarholiday |
| Línea de festivo del calendario de trabajo | cdm_workcalendarholidayline |
| Intervalo de tiempo del calendario de trabajo | cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados) |
| Trabajador | cdm_worker |
| Dirección de trabajador | cdm_workeraddress |
| Cuenta bancaria del trabajador | cdm_workerbankaccount |
| Compensación fija del trabajador | cdm_workerfixedcompensation |
| Detalle personal del trabajador | cdm_workerpersonaldetail |
| Número de identificación de persona del trabajador | cdm_workerpersonidentificationnumber |
| Tipo de identificación de persona del trabajador | cdm_workerpersonidentificationtype |

## <a name="in-preview"></a>En vista previa

Las características de vista previa solo están disponibles en entornos de **Espacio aislado**.

### <a name="print-performance-reviews"></a>Imprimir evaluaciones del rendimiento

Consulte [Imprimir evaluaciones del rendimiento](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) en el plan de la oleada 2 de la versión Dynamics 365: 2019.


[!INCLUDE[footer-include](../includes/footer-banner.md)]