---
title: Tablas de Dataverse
description: Microsoft Dynamics 365 Human Resources usa Dataverse para habilitar escenarios de extensibilidad e integración.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2f075a8e96af55b1363d2d51db377c5b25c38775
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114186"
---
# <a name="dataverse-tables"></a>Tablas de Dataverse

Microsoft Dynamics 365 Human Resources usa Dataverse para habilitar escenarios de extensibilidad e integración.

> [!NOTE]
> Las entidades de Human Resources se corresponden con tablas de Dataverse. Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)

Están disponibles las siguientes entidades de Dataverse basadas en entidades de Human Resources.

## <a name="benefit-tables"></a>Tablas de prestaciones

| Nombre | Tabla |
| --- | --- |
| Frecuencia de cálculo de la prestación | cdm_benefitcalculationfrequency |
| Período de pago de la frecuencia de cálculo de prestación | cdm_benefitcalculationfrequencypayperiod |
| Índice de cálculo de la prestación | cdm_benefitcalculationrate |
| Detalle de índice de cálculo de la prestación | cdm_benefitcalculationratedetail |
| Opción de prestación | cdm_benefitoption |
| Plan de prestaciones | cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados) |
| Tipo de prestación | cdm_benefittype |

## <a name="business-process-tasks-tables"></a>Tablas de tareas de procesos de negocio

| Nombre | Tabla |
| --- | --- |
| Calendario de proceso de negocio | cdm_businessprocesscalendar |
| Asignación de grupo de procesos empresariales | cdm_businessprocessgroupassignment |
| Grupo de tareas de biblioteca de procesos empresariales | cdm_businessprocesslibrarytaskgroup |
| Etapa de proceso empresarial | cdm_businessprocessstage |
| Encabezado de plantilla de lista de comprobación | cdm_businessprocesstemplateheader |
| Tarea de plantilla de lista de comprobación | cdm_businessprocesstemplatetask |

## <a name="compensation-tables"></a>Tablas de compensación

| Nombre | Tabla |
| --- | --- |
| Plan fijo de compensación | cdm_compensationfixedplan |
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
| Evento de compensación fija | cdm_fixedcompensationevent |
| Regla de atribución | cdm_vestingrule |
| Compensación fija de trabajador | cdm_workerfixedcompensation |

## <a name="organization-tables"></a>Tablas de organización

| Nombre | Tabla |
| --- | --- |
| Departamento | cdm_department |
| Empleo | cdm_employment |
| Empresa | cdm_company |
| Puesto | cdm_job |
| Función de trabajo | cdm_jobfunction |
| Puesto de trabajo | cdm_jobposition |
| Tipo de puesto | cdm_positiontype |
| Asignación del trabajador del puesto | cdm_positionworkerassignmentmap |
| Dimensión de puesto de trabajo | cdm_jobpositiondimension|
| Tipo de trabajo | cdm_jobtype |
| Idioma | cdm_language |
| Cargo | cdm_title |

> [!NOTE]
> Dimensiones financieras para **Tipo de puesto**, **Asignación de puesto de trabajador** y **Empleo** proporcionan integración unidireccional a Dataverse. Actualmente las actualizaciones de dimensiones financieras no se pueden sincronizar desde Dataverse a Human Resources. 

## <a name="leave-and-absence-tables"></a>Tablas de permisos y ausencias

| Nombre | Tabla |
| --- | --- |
| Transacción bancaria de bajas | cdm_leavebanktransaction |
| Inscripción de baja | cdm_leaveenrollment |
| Plan de bajas | cdm_leaveplan |
| Solicitud de baja | cdm_leaverequest |
| Detalles de solicitud de baja | cdm_leaverequestdetail |
| Tipo de baja | cdm_leavetype |
| Código de auditoría de tipo de baja | cdm_leavetypereasoncode |

## <a name="payroll-tables"></a>Tablas de nómina

| Nombre | Tabla |
| --- | --- |
| Ciclo de pago | cdm_paycycle |
| Período de pago | cdm_payperiod |
| Código de ganancias de nómina | cdm_payrollearningcode |
| Desembolso de cuenta bancaria | cdm_bankaccountdisbursement |
| Región de impuestos | cdm_taxregion |

## <a name="worker-tables"></a>Tablas de trabajador

| Nombre | Tabla |
| --- | --- |
| Trabajador | cdm_worker |
| Dirección del trabajador | cdm_workeraddress |
| Detalle personal del trabajador | cdm_workerpersonaldetail |
| Número de identificación de persona del trabajador | cdm_workerpersonidentificationnumber |
| Tipo de identificación de persona del trabajador | cdm_workerpersonidentificationtype |
| Calendario de trabajo | cdm_workcalendar |
| Día de calendario de trabajo | cdm_workcalendarday |
| Vacaciones calendario de trabajo |cdm_workcalendarholiday |
| Línea de festivo del calendario de trabajo | cdm_workcalendarholidayline |
| Intervalo de tiempo del calendario de trabajo | cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados) |
| Cuenta bancaria de trabajador | cdm_workerbankaccount |

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

![Trabajador](./media/HCMCommon-worker-entity-diagram.png)

### <a name="job-and-job-position"></a>Trabajo y puesto de trabajo

![Trabajo y puesto de trabajo](./media/HCMCommon-job-and-job-position-entity-diagram.png)

### <a name="benefits"></a>Prestaciones

![Prestaciones](./media/HCMCommon-benefits-entity-diagram.png)

### <a name="compensation"></a>Compensación

![Compensación](./media/HCMCommon-compensation-entity-diagram.png)

### <a name="leave"></a>Dejar

![Dejar](./media/HCMCommon-leave-entity-diagram.png)

### <a name="work-calendar"></a>Calendario de trabajo

![Calendario de trabajo](./media/HCMCommon-work-calendar-entity-diagram.png)

## <a name="see-also"></a>Consulte también

[Elegir una tecnología de integración de datos](hr-admin-integration-choose-technology.md)<br>
[Configurar la integración de Dataverse](hr-admin-integration-common-data-service.md)<br>
[Configurar tablas virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Preguntas frecuentes sobre tablas virtuales para Human Resources](hr-admin-virtual-entity-faq.md)<br>
[¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)<br>
[Actualizaciones de terminología](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates)


[!INCLUDE[footer-include](../includes/footer-banner.md)]