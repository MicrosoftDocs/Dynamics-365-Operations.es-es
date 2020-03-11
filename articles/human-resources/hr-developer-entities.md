---
title: Entidades de Common Data Service
description: Microsoft Dynamics 365 Human Resources usa Common Data Service para habilitar escenarios de extensibilidad e integración.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.openlocfilehash: 6879a45dd1fcc1ba718747aaaf0d7936c2eac49f
ms.sourcegitcommit: 3cad15f8ecc257d3a45c1bc1fada7c094ff4bcec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087355"
---
# <a name="common-data-service-entities"></a>Entidades de Common Data Service

Microsoft Dynamics 365 Human Resources usa Common Data Service para habilitar escenarios de extensibilidad e integración.

Para obtener más información acerca de Common Data Service, consulte [¿Qué es Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).

Las siguientes entidades de Recursos Humanos están disponibles en Common Data Service.

## <a name="benefit-entities"></a>Entidades de prestación

| Nombre | Entidad |
| --- | --- |
| Frecuencia de cálculo de la prestación | cdm_benefitcalculationfrequency |
| Período de pago de la frecuencia de cálculo de prestación | cdm_benefitcalculationfrequencypayperiod |
| Índice de cálculo de la prestación | cdm_benefitcalculationrate |
| Detalle de índice de cálculo de la prestación | cdm_benefitcalculationratedetail |
| Opción de prestación | cdm_benefitoption |
| Plan de prestaciones | cdm_benefitplan (No habilitada para la compatibilidad de campos personalizados) |
| Tipo de prestación | cdm_benefittype |

## <a name="business-process-tasks-entities"></a>Entidades de tareas de procesos de negocio

| Nombre | Entidad |
| --- | --- |
| Calendario de proceso de negocio | cdm_businessprocesscalendar |
| Asignación de grupo de procesos empresariales | cdm_businessprocessgroupassignment |
| Grupo de tareas de biblioteca de procesos empresariales | cdm_businessprocesslibrarytaskgroup |
| Etapa de proceso empresarial | cdm_businessprocessstage |
| Encabezado de plantilla de lista de comprobación | cdm_businessprocesstemplateheader |
| Tarea de plantilla de lista de comprobación | cdm_businessprocesstemplatetask |

## <a name="compensation-entities"></a>Entidades de compensación

| Nombre | Entidad |
| --- | --- |
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
| Evento de compensación fija | cdm_fixedcompensationevent |
| Regla de atribución | cdm_vestingrule |
| Compensación fija del trabajador | cdm_workerfixedcompensation |

## <a name="organization-entities"></a>Entidades de la organización

| Nombre | Entidad |
| --- | --- |
| Departamento | cdm_department |
| Empleo | cdm_employment |
| Compañía | cdm_company |
| Puesto | cdm_job |
| Función de trabajo | cdm_jobfunction |
| Puesto de trabajo | cdm_jobposition |
| Tipo de puesto | cdm_positiontype |
| Asignación del trabajador del puesto | cdm_positionworkerassignmentmap |
| Tipo de trabajo | cdm_jobtype |
| Idioma | cdm_language |

## <a name="leave-and-absence-entities"></a>Entidades de permisos y ausencias

| Nombre | Entidad |
| --- | --- |
| Transacciones bancaria de bajas | cdm_leavebanktransaction |
| Inscripción en baja | cdm_leaveenrollment |
| Plan de bajas | cdm_leaveplan |
| Solicitud de baja | cdm_leaverequest |
| Detalles de solicitud de baja | cdm_leaverequestdetail |
| Tipo de baja | cdm_leavetype |
| Código de auditoría de tipo de baja | cdm_leavetypereasoncode |

## <a name="payroll-entities"></a>Entidades de nómina

| Nombre | Entidad |
| --- | --- |
| Ciclo de pago | cdm_paycycle |
| Período de pago | cdm_payperiod |
| Código de ganancia de nómina | cdm_payrollearningcode |
| Desembolso de cuenta bancaria | cdm_bankaccountdisbursement |
| Región de impuestos | cdm_taxregion |

## <a name="worker-entities"></a>Entidades del trabajador

| Nombre | Entidad |
| --- | --- |
| Trabajador | cdm_worker |
| Dirección de trabajador | cdm_workeraddress |
| Detalle personal del trabajador | cdm_workerpersonaldetail |
| Número de identificación de persona del trabajador | cdm_workerpersonidentificationnumber |
| Tipo de identificación de persona del trabajador | cdm_workerpersonidentificationtype |
| Calendario de trabajo | cdm_workcalendar |
| Día de calendario de trabajo | cdm_workcalendarday |
| Vacaciones calendario de trabajo |cdm_workcalendarholiday |
| Línea de festivo del calendario de trabajo | cdm_workcalendarholidayline |
| Intervalo de tiempo del calendario de trabajo | cdm_workcalendartimeinterval (No habilitada para la compatibilidad de campos personalizados) |
| Cuenta bancaria del trabajador | cdm_workerbankaccount |

## <a name="worker-setup-entities"></a>Configurar entidades del trabajador

| Nombre | Entidad |
| --- | --- |
| Estado de veterano | cdm_veteranstatus |
| Origen étnico | cdm_ethnicorigin |
| Código de motivo | cdm_reasoncode |
| Agencia emisora de identificación de personas | cdm_personidentificationissuingagency |

## <a name="competency-entities"></a>Entidades de competencia

| Nombre | Entidad |
| --- | --- |
| Tipo de aptitud | cdm_skilltype |

## <a name="entity-relationship-models"></a>Modelos de relación de entidad

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

[Elegir una tecnología de integración de datos](hr-admin-integration-choose-technology.md)</br>
[Configurar la integración de Common Data Service](hr-admin-integration-common-data-service.md)