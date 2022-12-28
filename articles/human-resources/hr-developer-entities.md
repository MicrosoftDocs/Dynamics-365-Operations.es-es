---
title: Tablas de Dataverse
description: Microsoft Dynamics 365 Human Resources usa Dataverse para habilitar escenarios de extensibilidad e integración.
author: twheeloc
ms.date: 12/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be30f10c8e5f5e962f54f720f66c712a785835
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838592"
---
# <a name="dataverse-tables"></a>Tablas de Dataverse


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Microsoft Dynamics 365 Human Resources usa Dataverse para habilitar escenarios de extensibilidad e integración.

> [!NOTE]
> Las entidades de Human Resources se corresponden con tablas de Dataverse. Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

Están disponibles las siguientes entidades de Dataverse basadas en entidades de Human Resources.

Para obtener más información sobre los problemas conocidos, consulte [Búsqueda de problemas en Lifecycle Services (LCS)](/dev-itpro/lifecycle-services/issue-search-lcs).

## <a name="benefit-tables"></a>Tablas de prestaciones

| Name | Tabla | Problemas conocidos  | Status |
| --- | --- |    --------|----------  |
| Frecuencia de cálculo de la prestación | cdm_benefitcalculationfrequency |     |     |
| Período de pago de la frecuencia de cálculo de prestación | cdm_benefitcalculationfrequencypayperiod |     |     |
| Índice de cálculo de la prestación | cdm_benefitcalculationrate |    |     |
| Detalle de índice de cálculo de la prestación | cdm_benefitcalculationratedetail |753225 | Resuelto  |
| Opción de prestación | cdm_benefitoption |    |     |
| Plan de prestaciones | cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados) |    |     |
| Tipo de prestación | cdm_benefittype |    |     |

## <a name="business-process-tasks-tables"></a>Tablas de tareas de procesos de negocio

| Name | Tabla |Problemas conocidos  | Status |
| --- | --- |   --------|----------   |
| Calendario de proceso de negocio | cdm_businessprocesscalendar | 751867 | Resuelto |
| Asignación de grupo de procesos empresariales | cdm_businessprocessgroupassignment | 751869  751863 | Activa|
| Grupo de tareas de biblioteca de procesos empresariales | cdm_businessprocesslibrarytaskgroup |751866 | Cerrada |
| Etapa de proceso empresarial | cdm_businessprocessstage |      |     |
| Encabezado de plantilla de lista de comprobación | cdm_businessprocesstemplateheader |     |     |
| Tarea de plantilla de lista de comprobación | cdm_businessprocesstemplatetask |      |     |

## <a name="compensation-tables"></a>Tablas de compensación

| Name | Tabla |Problemas conocidos  | Status |
| --- | --- | ----------      | -------    |
| Plan fijo de compensación | cdm_compensationfixedplan |754453 | Cerrada |
| Cuadrícula de compensación | cdm_compensationgrid |             |     |
| Nivel de compensación | cdm_compensationlevel |           |     |
| Frecuencia de pago de compensación | cdm_compensationpayfrequency |                  |     |
| Configuración de puntos de referencia de compensación | cdm_compensationreferencepointsetup |               |     |
| Línea de configuración de puntos de referencia de compensación | cdm_compensationreferencepointsetupline |             |     |
| Región de compensación | cdm_compensationregion |                   |     |
| Estructura de compensación | cdm_compensationstructure |    754456        | Cerrada    |
| Plan de compensación variable | cdm_compensationvariableplan |               |     |
| Nivel de plan de compensación variable | cdm_compensationvariableplanlevel |                |     |
| Tipo de plan de compensación variable | cdm_compensationvariableplantype |               |     |
| Evento de compensación fija | cdm_fixedcompensationevent |               |     |
| Regla de atribución | cdm_vestingrule |              |     |
| Compensación fija de trabajador | cdm_workerfixedcompensation |              |     |

## <a name="organization-tables"></a>Tablas de organización

| Name | Tabla |Problemas conocidos  | Status |
| --- | --- | ----------      | -------    |
| Departamento | cdm_department |  752194    | Cerrada    |
| Empleo | cdm_employment | 762414  |  Cerrada  |
| Empresa | cdm_company |  |     |
| Puesto | cdm_job |  |     |
| Función de trabajo | cdm_jobfunction |        |     |
| Puesto de trabajo | cdm_jobposition | 752214      | Cerrada    |
| Tipo de puesto | cdm_positiontype |            |     |
| Asignación del trabajador del puesto | cdm_positionworkerassignmentmap | 752224    |  Cerrada   |
| Dimensión de puesto de trabajo | cdm_jobpositiondimension|       |     |
| Tipo de trabajo | cdm_jobtype |      |     |
| Idioma | cdm_language |        |     |
| Cargo | cdm_title |       |     |

> [!NOTE]
> Dimensiones financieras para **Tipo de puesto**, **Asignación de puesto de trabajador** y **Empleo** proporcionan integración unidireccional a Dataverse. Actualmente las actualizaciones de dimensiones financieras no se pueden sincronizar desde Dataverse a Human Resources. 

## <a name="leave-and-absence-tables"></a>Tablas de permisos y ausencias

| Name | Tabla | Problemas conocidos  | Status |
| --- | --- |   ----------      | -------    |
| Transacción bancaria de bajas | cdm_leavebanktransaction |  752252    |    Resuelto |
| Inscripción de baja | cdm_leaveenrollment |  752934    |Cerrada     |
| Plan de bajas | cdm_leaveplan |   752232   |   Cerrada  |
| Solicitud de baja | cdm_leaverequest | 753207     | Cerrada    |
| Detalles de solicitud de baja | cdm_leaverequestdetail | 753207     |   Cerrada  |
| Tipo de baja | cdm_leavetype |      |     |
| Código de auditoría de tipo de baja | cdm_leavetypereasoncode |         |     |

>[!NOTE]
>La integración de escritura dual que usa tablas de Dataverse para licencias y ausencias solo está disponible cuando la función **Configurar varios tipos de licencias en un solo plan de licencias** está habilitada en Microsoft Dynamics 365 Finance usando **Administración de características**. 

## <a name="payroll-tables"></a>Tablas de nómina

| Name | Tabla |Problemas conocidos  | Status |
| --- | --- |  ----------      | -------    |
| Ciclo de pago | cdm_paycycle |    |     |
| Período de pago | cdm_payperiod |          |     |
| Código de ganancias de nómina | cdm_payrollearningcode |   754458        |   Cerrada  |
| Desembolso de cuenta bancaria | cdm_bankaccountdisbursement |    751904     |   Cerrada  |
| Región de impuestos | cdm_taxregion |          |     |

## <a name="worker-tables"></a>Tablas de trabajador

| Name | Tabla |Problemas conocidos  | Status |
| --- | --- |----------      | -------    |
| Trabajador | cdm_worker |    751906    |    Cerrada |
| Dirección del trabajador | cdm_workeraddress |   754465     |Cerrada     |
| Detalle personal del trabajador | cdm_workerpersonaldetail |   751906     |   Cerrada  |
| Número de identificación de persona del trabajador | cdm_workerpersonidentificationnumber |  766704      |   Cerrada  |
| Tipo de identificación de persona del trabajador | cdm_workerpersonidentificationtype |        |     |
| Calendario de trabajo | cdm_workcalendar |        |     |
| Día de calendario de trabajo | cdm_workcalendarday |        |     |
| Vacaciones calendario de trabajo |cdm_workcalendarholiday |        |     |
| Línea de festivo del calendario de trabajo | cdm_workcalendarholidayline |        |     |
| Intervalo de tiempo del calendario de trabajo | cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados) |        |     |
| Cuenta bancaria de trabajador | cdm_workerbankaccount |        |     |

## <a name="worker-setup-tables"></a>Tablas de configuración de trabajador

| Nombre | Tabla |
| --- | --- |
| Estado de excombatiente | cdm_veteranstatus |
| Origen étnico | cdm_ethnicorigin |
| Código de motivo | cdm_reasoncode |
| Agencia emisora de identificación de personas | cdm_personidentificationissuingagency |

## <a name="competency-tables"></a>Tablas de competencia

| Nombre | Tabla |
| --- | --- |
| Tipo de aptitud | cdm_skilltype |

## <a name="table-relationship-models"></a>Modelos de relación de tabla

### <a name="worker"></a>Trabajador

![Trabajador.](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Trabajo y puesto de trabajo

![Trabajo y puesto de trabajo.](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Beneficios

![Beneficios.](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Compensación

![Compensación.](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Salir

![Bajas y ausencias.](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendario de trabajo

![Calendario de trabajo.](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Consulte también

[Elegir una tecnología de integración de datos](hr-admin-integration-choose-technology.md)<br>
[Configurar la integración de Dataverse](hr-admin-integration-common-data-service.md)<br>
[Configurar tablas virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Preguntas frecuentes sobre tablas virtuales para Human Resources](hr-admin-virtual-entity-faq.md)<br>
[¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Actualizaciones de terminología](/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
