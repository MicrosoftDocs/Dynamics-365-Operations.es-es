---
title: Configurar integración con tablas de Dataverse
description: En este artículo se describe la integración entre Microsoft Dynamics 365 Human Resources y Dataverse.
author: anschmidt
ms.date: 12/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2022-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63c25020b7026a76ecc6e2c3563f8299627ec8a8
ms.sourcegitcommit: bdee5e642d417a13abdb778c14ec5f2dbbf8dee7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2022
ms.locfileid: "9838632"
---
# <a name="configure-integration-with-dataverse-tables"></a>Configurar integración con tablas de Dataverse

>[!Important]
>La funcionalidad mencionada en este artículo está disponible actualmente para los clientes en Dynamics 365 Human Resources en la infraestructura de Finanzas y operaciones. 


Para integrar Microsoft Dynamics 365 Human Resources con Dataverse, puede usar el [Integrador de datos](/powerapps/administrator/data-integrator). La plantilla Human Resources a Dataverse permite que los datos de puestos, posiciones, trabajadores y otros fluyan de Recursos humanos a Dataverse, y de Dataverse a Human Resources, creando una escritura en ambos sistemas.

## <a name="system-requirements-for-human-resources"></a>Requisitos del sistema para Human Resources

La solución de integración requiere las siguientes versiones de Human Resources y Dynamics 365 Finance: 

- Dynamics 365 Finance versión 7.2 y posteriores
- Entorno de Dynamics CRM donde se ha creado una base de datos y se permiten aplicaciones de Dynamics 365

## <a name="template-and-tasks"></a>Plantilla y tareas

Siga estos pasos para acceder a la plantilla de Human Resources a Finance.

1. Abra el [Centro de administración de Power Apps](https://admin.powerapps.com/). 
2. En su entorno, seleccione **Dynamics 365 Apps** y luego seleccione **Fuente de la aplicación** en la barra de herramientas.
3. Para instalar la plantilla, busque "Recursos humanos de doble escritura" o vaya directamente a la siguiente dirección: <https://appsource.microsoft.com/product/dynamics-365/mscrm.hcm_dualwrite>.
3. Una vez completada la instalación, abra Dynamics 365 Finance.
4. Abra el espacio trabajo **Administración de datos**. 
5. Seleccione **Doble escritura**. 
6. Siga el proceso de vinculación de su entorno para al menos una empresa de su organización. 
7. Cuando haya terminado de configurar un vínculo a su entorno de Dataverse, seleccione **Aplicar solución**. Se aplica la solución y las asignaciones se instalan en la aplicación del integrador.

## <a name="template-mappings"></a>Asignaciones de plantilla

En las siguientes tablas de asignación de plantillas, el nombre de la tarea indica las entidades utilizadas en cada aplicación. Finanzas está a la izquierda y Dataverse a la derecha.

### <a name="bank-account-disbursements-dual-write-to-bank-account-disbursement"></a>Desembolsos de cuenta bancaria (doble escritura) a desembolso de cuenta bancaria

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATIONID        | cdm\_bankaccountid.cdm\_accountidentification        |
| IMPORTE                         | cdm\_amount                                         |
| PRIORITY                       | cdm\_disbursementpriority                           |
| NÚMERO PERSONAL                | cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber    |
| REMAINDER                      | cdm\_isremainder                                    |

### <a name="benefit-calculation-rate-detail-dual-write-to-benefit-calculation-rate-detail"></a>Detalle del índice de cálculo de la prestación (doble escritura) del índice de cálculo de la prestación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CONTRIBUTIONMETHOD             | cdm\_contributionmethod                             |
| EFFECTIVE                      | cdm\_effective                                      |
| EMPLOYERCONTRIBUTION           | cdm\_employercontribution                           |
| EXPIRATION                     | cdm\_expiration                                     |
| WORKERDEDUCTION                | cdm\_workerdeduction                                |
| NOMBRE                           | cdm\_calculationrateid.cdm\_name                     |

### <a name="benefit-calculation-rate-header-to-benefit-calculation-rate"></a>Encabezado del índice de cálculo de la prestación del índice de cálculo de la prestación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| NOMBRE                           | cdm\_name                                           |
| TIERTYPE                       | cdm\_tiertype                                       |

### <a name="benefit-option-to-benefit-option"></a>Opción de beneficio para Opción de beneficio

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ALLOWBENEFICIARYDESIGNATIONS   | cdm\_allowbeneficiarydesignations                   |
| ALLOWDEPENDENTCOVERAGE         | cdm\_allowdependentcoverage                         |
| BENEFITOPTIONID                | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| ISWAIVE                        | cdm\_iswaived                                       |

### <a name="benefit-type-to-benefit-type"></a>Tipo de beneficio para Tipo de beneficio

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| BENEFITTYPEID                  | cdm\_name                                           |
| CONCURRENTENROLLMENT           | cdm\_concurrentenrollment                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| PAYROLLCATEGORY                | cdm\_payrollcategory                                |

### <a name="business-calendar-to-business-process-calendar"></a>Calendario comercial para Calendario de procesos comerciales

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| NOMBRE                           | cdm\_calendarname                                   |
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| ISOPENMONDAY                   | cdm\_ismondayopen                                   |
| ISOPENTUESDAY                  | cdm\_istuesdayopen                                  |
| ISOPENWEDNESDAY                | cdm\_iswednesdayopen                                |
| ISOPENTHURSDAY                 | cdm\_isthursdayopen                                 |
| ISOPENFRIDAY                   | cdm\_isfridayopen                                   |
| ISOPENSATURDAY                 | cdm\_issaturdayopen                                 |
| ISOPENSUNDAY                   | cdm\_issundayopen                                   |

### <a name="business-process-to-business-process-header"></a>Proceso de negocio para el encabezado de proceso de negocio

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processid                                      |
| PROCESSTYPE                    | cdm\_processtype                                    |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NOMBRE                           | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| ESTADO                         | cdm\_status                                         |
| TARGETDATE                     | cdm\_targetdate                                     |
| STARTDATETIME                  | cdm\_startdatetime                                  |
| ENDDATETIME                    | cdm\_enddatetime                                    |
| RESOLVEDBYPERSONNELNUMBER      | cdm\_resolvedbyid.cdm\_workernumber                  |
| PROCESSOWNERPERSONNELNUMBER    | cdm\_processownerid.cdm\_workernumber                |
| SOURCETEMPLATENAME             | cdm\_sourcetemplateid.cdm\_name                      |
| SOURCETEMPLATEPROCESSTYPE      | cdm\_sourcetemplateid.cdm\_businessprocesstype       |
| SOURCETEMPLATEGENERICSUBTYPE   | cdm\_sourcetemplateid.cdm\_genericsubtype            |

### <a name="business-process-library-task-group-to-business-process-library-task-group"></a>Grupo de tareas de la biblioteca de procesos empresariales a Grupo de tareas de la biblioteca de procesos empresariales

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_processtype                                    |
| NOMBRE                           | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |

### <a name="business-process-stage-to-business-process-stage"></a>Etapa de proceso de negocio para la etapa de proceso de negocio

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| NOMBRE                           | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| SEQUENCENUMBER                 | cdm\_sequencenumber                                 |

### <a name="business-process-task-to-business-process-task"></a>Tarea de proceso de negocio para la tarea de proceso de negocio

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| DUEDATE                        | cdm\_duedate                                        |
| TASKID                         | cdm\_taskid                                         |
| INSTRUCTIONS                   | cdm\_instructions                                   |
| COMPLETIONDATETIME             | cdm\_completiondatetime                             |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| NOMBRE                           | cdm\_name                                           |
| ESTADO                         | cdm\_status                                         |
| RESOLVEDBY\_PERSONNELNUMBER     | cdm\_resolvedbyid.cdm\_workernumber                  |
| TEMPLATETASKID                 | cdm\_templatetaskid.cdm\_taskid                      |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedposition.cdm\_jobpositionnumber         |

### <a name="business-process-template-to-checklist-template-header"></a>Plantilla de proceso empresarial para encabezado de plantilla de lista de verificación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSTYPE                    | cdm\_businessprocesstype                            |
| GENERICSUBTYPE                 | cdm\_genericsubtype                                 |
| NOMBRE                           | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| CALENDARID                     | cdm\_businessprocesscalendarid.cdm\_name             |
| NÚMERO PERSONAL                | cdm\_processownerid.cdm\_workernumber                |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="business-process-template-task-to-checklist-template-task"></a>Tarea de plantilla de proceso empresarial para tarea de plantilla de lista de verificación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TASKID                         | cdm\_taskid                                         |
| NOMBRE                           | cdm\_name                                           |
| TEMPLATEHEADER\_PROCESSTYPE     | cdm\_businessprocesstemplateheaderid.cdm\_businessprocesstype |
| TEMPLATEHEADER\_GENERICSUBTYPE  | cdm\_businessprocesstemplateheaderid.cdm\_genericsubtype |
| TEMPLATEHEADER\_NAME            | cdm\_businessprocesstemplateheaderid.cdm\_name       |
| DESCRIPCIÓN                    | cdm\_description                                    |
| DUEDATEOFFSETDAYS              | cdm\_duedateoffsetdays                              |
| MENUITEMTYPE                   | cdm\_tasklinktype                                   |
| MENUITEM                       | cdm\_tasklink                                       |
| CONTACTPERSON\_PERSONNELNUMBER  | cdm\_contactpersonid.cdm\_workernumber               |
| ASSIGNMENTTYPE                 | cdm\_assignmenttype                                 |
| ASSIGNEDWORKER\_PERSONNELNUMBER | cdm\_assignedworkerid.cdm\_workernumber              |
| ASSIGNEDPOSITION\_POSITIONID    | cdm\_assignedpositionid.cdm\_jobpositionnumber       |
| ASSIGNEDGROUP\_NAME             | cdm\_assignedgroupid.cdm\_name                       |
| ISOPTIONAL                     | cdm\_isoptional                                     |
| INSTRUCTIONS                   | cdm\_instructions                                   |

### <a name="calculation-frequency-to-benefit-calculation-frequency"></a>Frecuencia de cálculo para frecuencia de cálculo de prestación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| FREQUENCY                      | cdm\_name                                           |
| FREQUENCYCONTROL               | cdm\_frequencycontrol                               |
| ISIMMUTABLE                    | cdm\_isimmutable                                    |

### <a name="calculation-frequency-pay-period-to-benefit-calculation-frequency-pay-period"></a>Periodo de pago de frecuencia de cálculo para el periodo de pago de la frecuencia de cálculo de la prestación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALCULATIONFREQUENCYID         | cdm\_benefitcalculationfrequencyid.cdm\_name         |
| PERIODSTARTDATE                | cdm\_payperiodid.cdm\_periodstartdate                |
| PAYCYCLEID                     | cdm\_payperiodid.cdm\_paycycleid.cdm\_name            |

### <a name="calendar-to-work-calendar"></a>Calendario para calendario de trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARID                     | cdm\_name                                           |
| CALENDARNAME                   | cdm\_description                                    |
| WORKCALENDARHOLIDAYID          | cdm\_workcalendarholidayid.cdm\_name                 |

### <a name="compensation-fixed-action-table-to-fixed-compensation-event"></a>Tabla de acción fija de compensación para evento de compensación fija

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACTION                         | cdm\_name                                           |
| ACTIVE                         | cdm\_isactive                                       |
| DESCRIPCIÓN                    | cdm\_description                                    |
| TIPO                           | cdm\_eventtype                                      |

### <a name="compensation-fixed-plan-to-compensation-fixed-plan"></a>Plan de compensación fija para el plan de compensación fija

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PLAN                           | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| TIPO                           | cdm\_type                                           |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| DIVISA                       | cdm\_transactioncurrencyid.isocurrencycode          |
| PAYFREQUENCY                   | cdm\_payfrequency.cdm\_name                          |
| HIRERULE                       | cdm\_hirerule                                       |
| OUTOFRANGETOLERANCE            | cdm\_outofrangetolerance                            |
| RECOMMENDATIONALLOWED          | cdm\_recommendationallowed                          |
| COMPENSATIONSTRUCTURE          | cdm\_compensationgrid.cdm\_name                      |
| REFPOINTSETUPID                | cdm\_referencepointsetupline.cdm\_referencepointsetupid.cdm\_name |
| CONTROLPOINT                   | cdm\_referencepointsetupline.cdm\_name               |

### <a name="compensation-grids-to-compensation-grid"></a>Cuadrículas de compensación para cuadrícula de compensación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| GRIDID                         | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| REFERENCESETUP                 | cdm\_referencepointsetupid.cdm\_name                 |
| TIPO                           | cdm\_type                                           |
| DIVISA                       | cdm\_transactioncurrencyid.isocurrencycode          |

### <a name="compensation-job-function-to-job-function"></a>Función de trabajo de compensación para función de trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBFUNCTIONID                  | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |

### <a name="compensation-job-type-to-job-type"></a>Tipo de trabajo de commpensación para tipo de trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBTYPEID                      | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| EXEMPTSTATUS                   | cdm\_exemptstatus                                   |

### <a name="compensation-pay-frequency-to-compensation-pay-frequency"></a>Frecuencia de pago de compensación para Frecuencia de pago de compensación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYRATECONVERSION              | cdm\_name                                           |
| PERIOD                         | cdm\_period                                         |
| DESCRIPCIÓN                    | cdm\_description                                    |
| ANNUALCONVERSIONFACTOR         | cdm\_annualconversionfactor                         |
| HOURLYCONVERSIONFACTOR         | cdm\_hourlyconversionfactor                         |
| MONTHLYCONVERSIONFACTOR        | cdm\_monthlyconversionfactor                        |
| WEEKLYCONVERSIONFACTOR         | cdm\_weeklyconversionfactor                         |

### <a name="compensation-regions-to-compensation-region"></a>Regiones de compensación para Región de compensación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| UBICACIÓN                       | cdm\_name                                           |

### <a name="compensation-variable-plan-v2-to-compensation-variable-plan"></a>Plan de compensación variable V2 para el plan de compensación variable

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VARIABLEAWARDBASIS             | cdm\_awardbasis                                     |
| AWARDBASISCALCULATION          | cdm\_awardbasiscalculation                          |
| CALCULATIONTYPE                | cdm\_calculationtype                                |
| DESCRIPCIÓN                    | cdm\_description                                    |
| ENABLEENROLLMENT               | cdm\_enableenrollment                               |
| ENABLELEVELS                   | cdm\_enablelevels                                   |
| ENABLERECOMMENDATION           | cdm\_enablerecommendation                           |
| HIRERULE                       | cdm\_hirerule                                       |
| LEVERAGE100PERCENT             | cdm\_leverage100percent                             |
| LEVERAGEMAXIMUM                | cdm\_leveragemaximum                                |
| LEVERAGEMINIMUM                | cdm\_leverageminimum                                |
| LEVERAGEOVEROBJECTIVE          | cdm\_leverageoverobjective                          |
| LEVERAGEUNDEROBJECTIVE         | cdm\_leverageunderobjective                         |
| PERCENTOFBASIS                 | cdm\_percentofbasis                                 |
| PLANID                         | cdm\_name                                           |
| VARIABLECOMPENSATIONTYPE       | cdm\_variablecompensationtypeid.cdm\_name            |
| UNITCURRENCYCODE               | transactioncurrencyid.isocurrencycode              |
| UNITRELATIONSHIP               | cdm\_unitrelationship                               |
| UNITVALUE                      | cdm\_unitvalue                                      |
| NUMBEROFUNITSREAL              | cdm\_numberofunits                                  |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| VESTINGRULE                    | cdm\_vestingruleid.cdm\_name                         |
| LEVERAGETOLERANCEMAX           | cdm\_leveragetolerancemax                           |
| LEVERAGETOLERANCEMIN           | cdm\_leveragetolerancemin                           |

### <a name="compensation-variable-type-to-compensation-variable-plan-type"></a>Tipo de compensación variable para tipo de plan de compensación variable

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| TIPO                           | cdm\_awardtype                                      |
| VARIABLECOMPENSATIONTYPE       | cdm\_name                                           |

### <a name="compensation-vesting-rules-to-vesting-rule"></a>Reglas de otorgamiento de compensación para la regla de otorgamiento

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| NOTA                           | cdm\_notes                                          |
| VESTINGRULE                    | cdm\_name                                           |

### <a name="department-v2-to-department"></a>Departamento V2 para departamento

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| OPERATINGUNITNUMBER            | cdm\_departmentnumber                               |
| NOMBRE                           | cdm\_name                                           |
| SEARCHNAME                     | cdm\_description                                    |
| PARTYTYPE                      | cdm\_partytype                                      |

### <a name="dual-write-tax-region-to-tax-region"></a>Región fiscal de doble escritura para región fiscal

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CITY                           | cdm\_city                                           |
| COUNTRYORREGION                | cdm\_countryorregion                                |
| COUNTY                         | cdm\_county                                         |
| STATE                          | cdm\_stateorprovince                                |
| TAXREGIONNAME                  | cdm\_name                                           |

### <a name="dual-write-worker-identification-to-worker-person-identification-number"></a>Número de identificación de trabajador de doble escritura para número de identificación de persona trabajadora

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| ENTRYTYPE                      | cdm\_entrytype                                      |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| IDENTIFICATIONNUMBER           | cdm\_identificationnumber                           |
| IDENTIFICATIONTYPEID           | cdm\_identificationtypeid.cdm\_name                  |
| ISPRIMARY                      | cdm\_isprimary                                      |
| ISSUEDATE                      | cdm\_issuedate                                      |
| ISSUINGAGENCYID                | cdm\_issuingagencyid.cdm\_name                       |
| WORKERNUMBER                   | cdm\_workerid.cdm\_workernumber                      |

### <a name="compensation-structure-to-compensation-structure"></a>Estructura de compensación para estructura de compensación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IMPORTE                         | cdm\_amount                                         |
| GRID                           | cdm\_compensationgridid.cdm\_name                    |
| LEVELID                        | cdm\_compensationlevelid.cdm\_name                   |
| REFERENCEPOINTLINENUMBER       | cdm\_referencepointid.cdm\_linenumber                |
| REFERENCESETUP                 | cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name |
| REFERENCEPOINT                 | cdm\_referencepointid.cdm\_name                      |

### <a name="earning-code-to-payroll-earning-code"></a>Código de ganancias para código de ganancias de nómina

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EARNINGCODE                    | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| INCLUDEINPAYMENTTYPE           | cdm\_includeinpaymenttype                           |
| QUANTITYUNIT                   | cdm\_quantityunit                                   |
| TRACKFMLAHOURS                 | cdm\_trackfmlahours                                 |
| ISPRODUCTIVE                   | cdm\_isproductive                                   |

### <a name="employee-fixed-compensation-to-worker-fixed-compensation"></a>Remuneración fija del empleado para Remuneración fija del trabajador

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| TIPO                           | cdm\_compensationtype                               |
| EFFECTIVEDATE                  | cdm\_effectivedate                                  |
| EXPIRATIONDATE                 | cdm\_expirationdate                                 |
| LINENUMBER                     | cdm\_linenumber                                     |
| PAYFREQUENCY                   | cdm\_payfrequencyid.cdm\_name                        |
| PAYRATE                        | cdm\_payrate                                        |
| PLAN                           | cdm\_planid.cdm\_name                                |
| POSITIONID                     | cdm\_positionid.cdm\_jobpositionnumber               |
| PROCESSTYPE                    | cdm\_processtype                                    |
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |
| ACTION                         | cdm\_eventid.cdm\_name                               |
| STEP                           | cdm\_referencepointsetuplineid.cdm\_name             |
| REFPOINTSETUPID                | cdm\_referencepointsetuplineid.cdm\_referencepointsetupid.cdm\_name |

### <a name="employment-per-company-to-employment"></a>Empleo por empresa para Empleo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| EMPLOYMENTENDDATE              | cdm\_employmentenddate                              |
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |
| EMPLOYMENTSTARTDATE            | cdm\_employmentstartdate                            |
| WORKERTYPE                     | cdm\_workertype                                     |
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| ADJUSTEDWORKERSTARTDATE        | cdm\_adjustedworkerstartdate                        |
| EMPLOYERNOTICEAMOUNT           | cdm\_employernoticeamount                           |
| EMPLOYERUNITOFNOTICE           | cdm\_employerunitofnotice                           |
| WORKERUNITOFNOTICE             | cdm\_workerunitofnotice                             |
| WORKERNOTICEAMOUNT             | cdm\_workernoticeamount                             |
| LASTDATEWORKED                 | cdm\_lastdateworked                                 |
| PROBATIONENDDATE               | cdm\_probationenddate                               |
| TRANSITIONDATE                 | cdm\_transitiondate                                 |
| TRANSITIONREASONCODENAME       | cdm\_transitionreasoncode.cdm\_name                  |
| WORKERSTARTDATE                | cdm\_workerstartdate                                |
| VALIDTO                        | cdm\_validto                                        |
| VALIDFROM                      | cdm\_validfrom                                      |

### <a name="ethnic-origins-to-ethnic-origin"></a>Orígenes étnicos para el origen étnico

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ETHNICORIGINID                 | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |

### <a name="group-assignment-to-business-process-group-assignment"></a>Asignación de grupo para Asignación de grupo de procesos empresariales

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NOMBRE                           | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| ISACTIVE                       | cdm\_isactive                                       |

### <a name="identification-type-to-worker-person-identification-type"></a>Tipo de identificación para el Tipo de identificación de la persona del trabajador

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| IDENTIFICATIONTYPEID           | cdm\_name                                           |
| ALLOWEDVALUES                  | cdm\_allowedvalues                                  |
| FIXEDLENGTH                    | cdm\_fixedlength                                    |
| IDENTIFICATIONNUMBERFORMAT     | cdm\_identificationnumberformat                     |

### <a name="issuing-agency-to-person-identification-issuing-agency"></a>Agencia emisora para Agencia emisora de identificación de personas

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CORREO ELECTRÓNICO                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| ISSUINGAGENCY                  | cdm\_name                                           |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| NOMBRE                           | cdm\_description                                    |
| PAGER                          | cdm\_pager                                          |
| SMS                            | cdm\_sms                                            |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telex                                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |

### <a name="job-positions-dual-write-to-job-position"></a>Puestos de trabajo de doble escritura para Puesto de trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONID                     | cdm\_jobpositionnumber                              |
| ACTIVATION                     | cdm\_activation                                     |
| AVAILABLEFORASSIGNMENT         | cdm\_availableforassignment                         |
| COMPENSATIONREGIONID           | cdm\_compensationregionid.cdm\_name                  |
| DEPARTMENTID                   | cdm\_departmentid.cdm\_departmentnumber              |
| DESCRIPCIÓN                    | cdm\_description                                    |
| FULLTIMEEQUIVALENT             | cdm\_fulltimeequivalent                             |
| JOBID                          | cdm\_jobid.cdm\_name                                 |
| PARENTPOSITIONID               | cdm\_parentjobpositionid.cdm\_jobpositionnumber      |
| POSITIONTYPEID                 | cdm\_positiontypeid.cdm\_name                        |
| JUBILACIÓN                     | cdm\_retirement                                     |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |

### <a name="jobs-dual-write-to-job"></a>Trabajos de doble escritura para Trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| JOBID                          | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| JOBDESCRIPTION                 | cdm\_jobdescription                                 |
| ALLOWUNLIMITEDPOSITIONS        | cdm\_allowunlimitedpositions                        |
| MAXIMUMNUMBEROFPOSITIONS       | cdm\_maximumnumberofpositions                       |
| JOBFUNCTIONID                  | cdm\_jobfunctionid.cdm\_name                         |
| JOBTYPEID                      | cdm\_jobtypeid.cdm\_name                             |
| TITLEID                        | cdm\_titleid.cdm\_name                               |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| DEFAULTFULLTIMEEQUIVALENCY     | cdm\_defaultfulltimeequivalent                      |

### <a name="language-codes-to-language"></a>Códigos de idioma para Idioma

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LANGUAGECODEID                 | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |

### <a name="leave-and-absence-bank-transaction-v2-to-leave-bank-transaction"></a>Transacción bancaria de baja y ausencia V2 para Transacción bancaria de baja

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IMPORTE                         | cdm\_amount                                         |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TRANSACTIONDATE                | cdm\_transactiondate                                |
| TRANSACTIONNUMBER              | cdm\_transactionnumber                              |
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |
| TRANSACTIONTYPE                | cdm\_transactiontype                                |

### <a name="leave-and-absence-enrollment-v2-to-leave-enrollment"></a>Inscripción de bajas y ausencias V2 para Inscripción de bajas

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_startdate                                      |
| ENDDATE                        | cdm\_enddate                                        |
| CUSTOMDATE                     | cdm\_customdate                                     |
| ACCRUALSTARTDATE               | cdm\_accrualstartdate                               |
| ACCRUALDATEBASIS               | cdm\_accrualdatebasis                               |
| ISACCRUALSUSPENDED             | cdm\_isaccrualsuspended                             |
| LEAVEPLANID                    | cdm\_leaveplanid.cdm\_name                           |
| TIERBASIS                      | cdm\_tierbasis                                      |
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |

### <a name="leave-and-absence-plan-v2-to-leave-plan"></a>Plan de bajas y ausencias V2 para plan de bajas

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCRUALFREQUENCY               | cdm\_accrualfrequency                               |
| NOMBRE                           | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| STARTDATE                      | cdm\_startdate                                      |
| LEAVETYPEID                    | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-and-absence-type-to-leave-type"></a>Tipo de baja y ausencia para Tipo de baja

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| TIPO                           | cdm\_type                                           |
| EARNINGCODEID                  | cdm\_earningcodeid.cdm\_name                         |

### <a name="leave-and-absence-type-reason-code-to-leave-type-reason-code"></a>Código de motivo de tipo de baja y ausencia para Código de motivo de tipo de baja

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| LEAVETYPE                      | cdm\_typeid.cdm\_type                                |
| REASONCODEID                   | cdm\_reasoncodeid.cdm\_name                          |

### <a name="leave-time-off-request-detail-to-leave-request-detail"></a>Detalle de solicitud de disponibilidad por baja para Detalle de solicitud de baja

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| IMPORTE                         | cdm\_amount                                         |
| LEAVEDATE                      | cdm\_leavedate                                      |
| REQUESTID                      | cdm\_leaverequestid.cdm\_leaverequestnumber          |
| TIPO                           | cdm\_leavetypeid.cdm\_type                           |

### <a name="leave-time-off-request-header-to-leave-request"></a>Encabezado de solicitud de disponibilidad por baja para Solicitud de baja

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REQUESTID                      | cdm\_leaverequestnumber                             |
| REQUESTDATE                    | cdm\_requestdate                                    |
| ESTADO                         | cdm\_status                                         |
| COMMENT                        | cdm\_comment                                        |
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |

### <a name="levels-to-compensation-level"></a>Niveles para Nivel de compensación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TIPO                           | cdm\_type                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| LEVEL                          | cdm\_name                                           |

### <a name="onboarding-process-header-to-onboard-process-header"></a>Encabezado del proceso de incorporación para encabezado de proceso de incorporación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PROCESSID                      | cdm\_processheaderid.cdm\_processid                  |
| ONBOARDEDEMPLOYEEPERSONNELNUMBER | cdm\_onboardedemployeeid.cdm\_workernumber           |
| EMPLOYMENTPERSONNELNUMBER      | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| LEGALENTITYID                  | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |
| EMPLOYMENTSTARTDATE            | cdm\_employmentid.cdm\_employmentstartdate           |

### <a name="pay-cycle-to-pay-cycle"></a>Ciclo de pago para ciclo de pago

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| PAYCYCLEFREQUENCY              | cdm\_frequency                                      |

### <a name="pay-period-to-pay-period"></a>Período de pago para período de pago

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| COMMENTS                       | cdm\_description                                    |
| DEFAULTPAYMENTDATE             | cdm\_defaultpaymentdate                             |
| PAYCYCLEID                     | cdm\_paycycleid.cdm\_name                            |
| PERIODENDDATE                  | cdm\_periodenddate                                  |
| PERIODSTARTDATE                | cdm\_periodstartdate                                |
| ESTADO                         | cdm\_status                                         |

### <a name="payroll-details-for-positions-to-payroll-position-detail"></a>Detalles de nómina para posiciones para Detalle de posición de nómina

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| PAYCYCLEID                     | cdm\_paycycle.cdm\_name                              |
| POSITIONID                     | cdm\_position.cdm\_jobpositionnumber                 |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| ANNUALREGULARHOURS             | cdm\_annualregularhours                             |
| PAIDBYLEGALENTITY              | cdm\_paidby.cdm\_companycode                         |

### <a name="position-default-dimensions-dual-write-to-job-position-dimension"></a>Dimensiones predeterminadas de posición de doble escritura para Dimensión de puesto de trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DIMENSIONDISPLAYVALUE          | cdm\_dimensiondisplayvalue                          |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |

### <a name="position-type-to-position-type"></a>Tipo de puesto para Tipo de puesto

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| POSITIONTYPEID                 | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| CLASSIFICATION                 | cdm\_classification                                 |

### <a name="position-worker-assignments-v2-to-position-worker-assignment"></a>Asignaciones de trabajador del puesto V2 para Asignación del trabajador del puesto

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |
| POSITIONID                     | cdm\_jobpositionid.cdm\_jobpositionnumber            |
| VALIDFROM                      | cdm\_validfrom                                      |
| VALIDTO                        | cdm\_validto                                        |
| IsPrimaryPosition              | cdm\_isprimaryposition                              |

### <a name="reason-codes-to-reason-code"></a>Códigos de motivo para Código de motivo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REASONCODEID                   | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| ISABSENCEAPPLICABLE            | cdm\_isabsenceapplicable                            |
| ISAPPLICATIONAPPLICABLE        | cdm\_isapplicationapplicable                        |
| ISCOMPENSATIONAPPLICABLE       | cdm\_iscompensationapplicable                       |
| ISCREATENEWPOSITIONAPPLICABLE  | cdm\_iscreatenewpositionapplicable                  |
| ISEDITPOSITIONAPPLICABLE       | cdm\_iseditpositionapplicable                       |
| ISHIREAPPLICABLE               | cdm\_ishireapplicable                               |
| ISSKILLMAPPINGAPPLICABLE       | cdm\_isskillmappingapplicable                       |
| ISTERMINATIONAPPLICABLE        | cdm\_isterminationapplicable                        |
| ISTRANSFERAPPLICABLE           | cdm\_istransferapplicable                           |

### <a name="reference-point-setup-line-dual-write-to-compensation-reference-point-setup-line"></a>Línea de configuración del punto de referencia (doble escritura) para Línea de configuración del punto de referencia de compensación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| DESCRIPCIÓN                    | cdm\_description                                    |
| LINENUM                        | cdm\_linenumber                                     |
| REFPOINTID                     | cdm\_name                                           |
| REFPOINTSETUPID                | cdm\_referencepointsetupid.cdm\_name                 |

### <a name="reference-point-setups-to-compensation-reference-point-setup"></a>Configuraciones de punto de referencia para Configuración de punto de referencia de compensación

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| REFERENCESETUP                 | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| TIPO                           | cdm\_compensationtype                               |

### <a name="skill-types-to-skill-type"></a>Tipos de habilidad para Tipo de habilidad

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| SKILLTYPE                      | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |

### <a name="titles-to-title"></a>Títulos para título

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| TITLEID                        | cdm\_name                                           |

### <a name="variable-compensation-level-v2-to-compensation-variable-plan-level"></a>Nivel de compensación variable V2 para el nivel del plan de compensación variable

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| AWARDAMOUNT                    | cdm\_awardamount                                    |
| AWARDPERCENT                   | cdm\_awardpercent                                   |
| AWARDUNITSREAL                 | cdm\_awardunits                                     |
| COMPENSATIONLEVELID            | cdm\_compensationlevelid.cdm\_name                   |
| PLANID                         | cdm\_compensationvariableplanid.cdm\_name            |

### <a name="veteran-status-to-veteran-status"></a>Estado de veterano para Estado de veterano

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| VETERANSTATUSID                | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |
| ISPROTECTEDVETERAN             | cdm\_isprotectedveteran                             |

### <a name="work-calendar-enrollments-to-work-calendar-enrollment"></a>Inscripciones de calendario laboral para Inscripción del calendario laboral

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| STARTDATE                      | cdm\_employmentid.cdm\_employmentstartdate           |
| NÚMERO PERSONAL                | cdm\_employmentid.cdm\_workerid.cdm\_workernumber     |
| CALENDARID                     | cdm\_workcalendarid.cdm\_name                        |
| COMPANYID                      | cdm\_employmentid.cdm\_companyid.cdm\_companycode     |

### <a name="work-calendar-holiday-to-work-calendar-holiday"></a>Vacaciones del calendario laboral para Vacaciones del calendario laboral

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ID                             | cdm\_name                                           |
| DESCRIPCIÓN                    | cdm\_description                                    |

### <a name="work-calendar-holiday-line-to-work-calendar-holiday-line"></a>Línea del calendario laboral para Línea del calendario laboral

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| HOLIDAYID                      | cdm\_workcalendarholidayid.cdm\_name                 |
| NOMBRE                           | cdm\_name                                           |
| HOLIDAYDATE                    | cdm\_holidaydate                                    |

### <a name="worker-to-worker"></a>Trabajador para Trabajador

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO PERSONAL                | cdm\_workernumber                                   |
| FIRSTNAME                      | cdm\_firstname                                      |
| MIDDLENAME                     | cdm\_middlename                                     |
| LASTNAME                       | cdm\_lastname                                       |
| WORKERTYPE                     | cdm\_type                                           |
| WORKERSTATUS                   | cdm\_status                                         |
| PRIMARYCONTACTEMAIL            | cdm\_primaryemailaddress                            |
| PRIMARYCONTACTPHONE            | cdm\_primarytelephone                               |
| PRIMARYCONTACTFACEBOOK         | cdm\_facebookidentity                               |
| PRIMARYCONTACTTWITTER          | cdm\_twitteridentity                                |
| PRIMARYCONTACTLINKEDIN         | cdm\_linkedinidentity                               |
| PRIMARYCONTACTURL              | cdm\_websiteurl                                     |
| GENDER                         | cdm\_gender                                         |
| BIRTHDATE                      | cdm\_birthdate                                      |
| NOMBRE                           | cdm\_fullname                                       |

### <a name="worker-bank-accounts-to-worker-bank-account"></a>Cuentas bancarias de trabajadores para Cuenta bancaria de trabajador

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ACCOUNTIDENTIFICATION          | cdm\_accountidentification                          |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONID         | cdm\_countryorregion                                |
| ADDRESSCOUNTY                  | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_addressdescription                             |
| ADDRESSDISTRICTNAME            | cdm\_districtname                                   |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |
| BANKACCOUNTNUMBER              | cdm\_bankaccountnumber                              |
| BANKACCOUNTTYPE                | cdm\_bankaccounttype                                |
| CORREO ELECTRÓNICO                          | cdm\_email                                          |
| EXTENSION                      | cdm\_extension                                      |
| FAX                            | cdm\_fax                                            |
| INTERNETADDRESS                | cdm\_websiteurl                                     |
| MOBILEPHONE                    | cdm\_mobilephone                                    |
| ROUTINGNUMBER                  | cdm\_routingnumber                                  |
| TELEPHONE                      | cdm\_telephone                                      |
| TELEXNUMBER                    | cdm\_telexnumber                                    |
| BANKIBAN                       | cdm\_iban                                           |
| SWIFTNO                        | cdm\_swiftcode                                      |
| BANKLOCATIONCODE               | cdm\_banklocationcode                               |
| BRANCHNAME                     | cdm\_branchname                                     |
| BRANCHNUMBER                   | cdm\_branchnumber                                   |
| ROUTINGNUMBERTYPE              | cdm\_routingnumbertype                              |
| ACCOUNTHOLDER                  | cdm\_accountholder                                  |
| NAMEOFPERSON                   | cdm\_nameofperson                                   |
| NOMBRE                           | cdm\_description                                    |
| ADDRESSSTREET                  | cdm\_line1                                          |
| ADDRESSSTREETNUMBER            | cdm\_line2                                          |

### <a name="worker-personal-details-to-worker-personal-detail"></a>Datos personales del trabajador para Detalles personales del trabajador

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |
| BIRTHDATE                      | cdm\_birthdate                                      |
| PERSONBIRTHCITY                | cdm\_birthcity                                      |
| GENDER                         | cdm\_gender                                         |
| EXPATRIATEENDDATE              | cdm\_expatriateenddate                              |
| EXPATRIATESTARTDATE            | cdm\_expatriatestartdate                            |
| DISABLEDVETERAN                | cdm\_isdisabledveteran                              |
| DECEASEDDATE                   | cdm\_deceaseddate                                   |
| DISABLEDVERIFICATIONDATE       | cdm\_disabledveteranverificationdate                |
| EDUCATION                      | cdm\_education                                      |
| ETHNICORIGINID                 | cdm\_ethnicoriginid.cdm\_name                        |
| ISDISABLED                     | cdm\_isdisabled                                     |
| ISFULLTIMESTUDENT              | cdm\_isfulltimestudent                              |
| ISEXPATRIATERULINGAPPLICABLE   | cdm\_isexpatriaterulingapplicable                   |
| MARITALSTATUS                  | cdm\_maritalstatus                                  |
| MILITARYSERVICESTARTDATE       | cdm\_militaryservicestartdate                       |
| MILITARYSERVICEENDDATE         | cdm\_militaryserviceenddate                         |
| NUMBEROFDEPENDENTS             | cdm\_numberofdependents                             |
| NATIVELANGUAGEID               | cdm\_nativelanguageidid.cdm\_name                    |
| NATIONALITYCOUNTRYREGION       | cdm\_nationalitycountryregion                       |
| PERSONBIRTHCOUNTRYREGION       | cdm\_birthcountryregion                             |
| FATHERBIRTHCOUNTRYREGION       | cdm\_fatherbirthcountryregion                       |
| MOTHERBIRTHCOUNTRYREGION       | cdm\_motherbirthcountryregion                       |
| CITIZENSHIPCOUNTRYREGION       | cdm\_citizenshipcountryregion                       |
| VETERANSTATUSID                | cdm\_veteranstatusid.cdm\_name                       |

### <a name="worker-postal-addresses-dual-write-to-worker-address"></a>Direcciones postales del trabajador de doble escritura para Dirección del trabajador

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| NÚMERO PERSONAL                | cdm\_workerid.cdm\_workernumber                      |
| ADDRESSLOCATIONID              | cdm\_addressnumber                                  |
| ADDRESSLOCATIONROLES           | cdm\_addresstype                                    |
| EFFECTIVE                      | cdm\_effectivedate                                  |
| EXPIRATION                     | cdm\_expirationdate                                 |
| ADDRESSSTREET                  | cdm\_street                                         |
| ADDRESSSTREETNUMBER            | cdm\_streetnumber                                   |
| ADDRESSCITY                    | cdm\_city                                           |
| ADDRESSCOUNTRYREGIONISOCODE    | cdm\_countryregion                                  |
| ADDRESSSTATE                   | cdm\_stateorprovince                                |
| ADDRESSCOUNTYID                | cdm\_county                                         |
| ADDRESSDESCRIPTION             | cdm\_description                                    |
| ADDRESSLATITUDE                | cdm\_latitude                                       |
| ADDRESSLONGITUDE               | cdm\_longitude                                      |
| ADDRESSZIPCODE                 | cdm\_postalcode                                     |
| ADDRESSPOSTBOX                 | cdm\_postofficebox                                  |
| ISPRIMARY                      | cdm\_ispreferred                                    |

### <a name="working-time-to-work-calendar-time-interval"></a>Tiempo de trabajo para Intervalo de tiempo de calendario de trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| ENDTIME                        | cdm\_endtime                                        |
| STARTTIME                      | cdm\_starttime                                      |
| WORKCALENDARDATE               | cdm\_workcalendardayid.cdm\_calendardate             |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKCALENDARID                 | cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name  |

### <a name="working-times-to-work-calendar-day"></a>Horarios de trabajo para día de calendario de trabajo

| Entidad financiera                 | Tabla de Dataverse                                    | 
|--------------------------------|----------------------------------------------------|
| CALENDARDATE                   | cdm\_calendardate                                   |
| WORKCALENDARID                 | cdm\_workcalendarid.cdm\_name                        |
| WORKINGDAYDEFINITION           | cdm\_status                                         |

## <a name="integration-considerations"></a>Consideraciones de integración

- Todos los cambios que se realicen en los datos de cualquiera de los sistemas estarán sujetos a la validación del otro sistema. Si ocurre una falla, los datos no se escribirán en ninguno de los sistemas. 
- Todas las escrituras están sujetas a valores predeterminados de datos (si se produce una lógica personalizada en Finanzas).
- La aplicación integradora de escritura dual usa claves de integración para mapear entre los dos sistemas. A veces, es difícil elegir la clave de integración correcta, especialmente si varias claves de integración cumplen los requisitos. Para ayudar con esta elección, la siguiente tabla enumera las claves de integración sugeridas para sus asignaciones.

| Tabla de Dataverse                          | Claves de integración |
|------------------------------------------|------------------|
| Desembolso de cuenta bancaria                | cdm\_bankaccountid.cdm\_accountidentification, cdm\_bankaccountid.cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Frecuencia de cálculo de la prestación            | cdm\_name |
| Período de pago de la frecuencia de cálculo de prestación | cdm\_payperiodid.cdm\_periodstartdate, cdm\_payperiodid.cdm\_paycycleid.cdm\_name, cdm\_benefitcalculationfrequencyid.cdm\_name |
| Índice de cálculo de la prestación                 | cdm\_name |
| Detalle de índice de cálculo de la prestación          | cdm\_workerdeduction, cdm\_effective, cdm\_calculationrateid.cdm\_name |
| Opción de prestación                           | cdm\_name |
| Tipo de prestación                             | cdm\_name |
| Calendario de proceso de negocio                | cdm\_name |
| Asignación de grupo de procesos empresariales        | cdm\_name |
| Encabezado del proceso de negocio                  | cdm\_processid |
| Grupo de tareas de biblioteca de procesos empresariales      | cdm\_processtype, cdm\_name |
| Etapa de proceso empresarial                   | cdm\_name, cdm\_businessprocesstype, cdm\_companyid.cdm\_companycode |
| Tarea de proceso de negocio                    | cdm\_taskid |
| Unidad de negocio                            | |
| Encabezado de plantilla de lista de comprobación                | cdm\_businessprocesstype, cdm\_name, cdm\_genericsubtype |
| Tarea de plantilla de lista de comprobación                  | cdm\_taskid |
| Empresa                                  | cdm\_companycode |
| Plan fijo de compensación                  | cdm\_name, cdm\_company.cdm\_companycode |
| Cuadrícula de compensación                        | cdm\_name, cdm\_companyid.cdm\_companycode |
| Nivel de compensación                       | cdm\_name |
| Frecuencia de pago de compensación               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Configuración de puntos de referencia de compensación       | cdm\_name, cdm\_companyid.cdm\_companycode |
| Línea de configuración de puntos de referencia de compensación  | cdm\_name, cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode |
| Región de compensación                      | cdm\_name |
| Estructura de compensación                   | cdm\_compensationlevelid.cdm\_name, cdm\_referencepointid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_name, cdm\_referencepointid.cdm\_referencepointsetupid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_compensationgridid.cdm\_name, cdm\_compensationgridid.cdm\_companyid.cdm\_companycode |
| Plan de compensación variable               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Nivel de plan de compensación variable         | cdm\_companyid.cdm\_companycode, cdm\_compensationvariableplanid.cdm\_name, cdm\_compensationvariableplanid.cdm\_companyid.cdm\_companycode, cdm\_compensationlevelid.cdm\_name |
| Tipo de plan de compensación variable          | cdm\_name, cdm\_companyid.cdm\_companycode |
| Divisa                                 | isocurrencycode |
| Departamento                               | cdm\_departmentnumber |
| Empleo                               | cdm\_employmentstartdate, cdm\_workerid.cdm\_workernumber, cdm\_companyid.cdm\_companycode |
| Origen étnico                            | cdm\_name |
| Evento de compensación fija                 | cdm\_name, cdm\_companyid.cdm\_companycode |
| Puesto                                      | cdm\_name |
| Función de trabajo                             | cdm\_name |
| Puesto de trabajo                             | cdm\_jobpositionnumber |
| Dimensión de puesto de trabajo                   | cdm\_jobpositionid.cdm\_jobpositionnumber, cdm\_companyid.cdm\_companycode |
| Tipo de trabajo                                 | cdm\_name |
| Idioma                                 | cdm\_name |
| Transacción bancaria de bajas                   | cdm\_transactiondate, cdm\_transactiontype, cdm\_transactionnumber, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Inscripción de baja                         | cdm\_startdate, cdm\_leaveplanid.cdm\_name, cdm\_leaveplanid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workerid.cdm\_workernumber |
| Plan de bajas                               | cdm\_name, cdm\_companyid.cdm\_companycode |
| Solicitud de baja                            | cdm\_leaverequestnumber, cdm\_companyid.cdm\_companycode |
| Detalles de solicitud de baja                     | cdm\_leavedate, cdm\_leavetypeid.cdm\_type, cdm\_leavetypeid.cdm\_companyid.cdm\_companycode, cdm\_leaverequestid.cdm\_leaverequestnumber, cdm\_leaverequestid.cdm\_companyid.cdm\_companycode |
| Tipo de baja                               | cdm\_type, cdm\_companyid.cdm\_companycode |
| Código de auditoría de tipo de baja                   | cdm\_reasoncodeid.cdm\_name, cdm\_typeid.cdm\_type, cdm\_typeid.cdm\_companyid.cdm\_companycode |
| Encabezado del proceso de incorporación                   | cdm\_processheaderid.cdm\_processid |
| Organización                             | |
| Ciclo de pago                                | cdm\_name |
| Período de pago                               | cdm\_periodstartdate, cdm\_paycycleid.cdm\_name, cdm\_periodenddate |
| Código de ganancias de nómina                     | cdm\_name |
| Detalle de puesto de nómina                  | cdm\_validfrom, cdm\_validto, cdm\_position.cdm\_jobpositionnumber |
| Agencia emisora de identificación de personas     | cdm\_name |
| Tipo de puesto                            | cdm\_name |
| Asignación del trabajador del puesto               | cdm\_validfrom, cdm\_jobpositionid.cdm\_jobpositionnumber |
| Código de motivo                              | cdm\_name |
| Tipo de aptitud                               | cdm\_name |
| Región de impuestos                               | cdm\_stateorprovince, cdm\_name, cdm\_countryorregion, cdm\_county, cdm\_city |
| Equipo                                     | azureactivedirectoryobjectid, membershiptype |
| Título                                    | cdm\_name |
| User                                     | azureactivedirectoryobjectid |
| Regla de atribución                             | cdm\_name, cdm\_companyid.cdm\_companycode |
| Estado de excombatiente                           | cdm\_name |
| Calendario de trabajo                            | cdm\_name, cdm\_companyid.cdm\_companycode |
| Día de calendario de trabajo                        | cdm\_calendardate, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Inscripción de calendario de trabajo                 | cdm\_employmentid.cdm\_employmentstartdate, cdm\_employmentid.cdm\_workerid.cdm\_workernumber, cdm\_employmentid.cdm\_companyid.cdm\_companycode |
| Vacaciones calendario de trabajo                    | cdm\_name |
| Línea de festivo del calendario de trabajo               | cdm\_holidaydate, cdm\_workcalendarholidayid.cdm\_name |
| Intervalo de tiempo del calendario de trabajo              | cdm\_starttime, cdm\_workcalendardayid.cdm\_calendardate, cdm\_workcalendardayid.cdm\_companyid.cdm\_companycode, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_name, cdm\_workcalendardayid.cdm\_workcalendarid.cdm\_companyid.cdm\_companycode, cdm\_companyid.cdm\_companycode, cdm\_workcalendarid.cdm\_name, cdm\_workcalendarid.cdm\_companyid.cdm\_companycode |
| Trabajador                                   | cdm\_workernumber |
| Dirección del trabajador                           | cdm\_addressnumber, cdm\_addresstype, cdm\_workerid.cdm\_workernumber |
| Cuenta bancaria de trabajador                      | cdm\_accountidentification, cdm\_workerid.cdm\_workernumber |
| Compensación fija de trabajador                | cdm\_linenumber, cdm\_effectivedate, cdm\_companyid.cdm\_companycode, cdm\_positionid.cdm\_jobpositionnumber, cdm\_workerid.cdm\_workernumber, cdm\_eventid.cdm\_name, cdm\_eventid.cdm\_companyid.cdm\_companycode, cdm\_planid.cdm\_name, cdm\_planid.cdm\_company.cdm\_companycode |
| Número de identificación de persona del trabajador      | cdm\_identificationnumber, cdm\_workerid.cdm\_workernumber, cdm\_identificationtypeid.cdm\_name |
| Tipo de identificación de persona del trabajador        | cdm\_name |
| Detalle personal del trabajador                   | cdm\_workerid.cdm\_workernumber |
