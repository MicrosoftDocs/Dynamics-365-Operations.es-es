---
title: Configurar la integración con Finance
description: Este artículo describe la funcionalidad disponible para la integración de Dynamics 365 Human Resources y Dynamics 365 Finance.
author: andreabichsel
manager: tfehr
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 132d0bb72662e538dd4451800eb5b11b4f1988cd
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465255"
---
# <a name="configure-integration-with-finance"></a>Configurar la integración con Finance

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Para integrar Dynamics 365 Human Resources con Dynamics 365 Finance, puede usar la plantilla Human Resources a Finance en [Integrador de datos](https://docs.microsoft.com/powerapps/administrator/data-integrator). La plantilla de Human Resources a Finance permite el flujo de datos para trabajos, puestos y trabajadores. La plantilla permite que los datos fluyan de Human Resources a Finance, pero no permite que los datos fluyan de Finance a Human Resources.

![Flujo de integración de Human Resources a Finance](./media/hr-admin-integration-finance-flow.png)

La solución Human Resources a Finance proporciona los siguientes tipos de sincronización de datos:

- Mantener trabajos en Human Resources y sincronizarlos de Human Resources a Finance
- Mantener puestos y asignaciones de puestos en Human Resources y sincronizarlos de Human Resources a Finance
- Mantener empleos en Human Resources y sincronizarlos de Human Resources a Finance
- Mantener trabajadores y direcciones de trabajadores en Human Resources y sincronizarlos de Human Resources a Finance

## <a name="system-requirements-for-human-resources"></a>Requisitos del sistema para Human Resources

La solución de integración requiere las siguientes versiones de Human Resources y Finance: 

- Dynamics 365 Human Resources en Dataverse
- Dynamics 365 Finance versión 7.2 y posteriores

## <a name="template-and-tasks"></a>Plantilla y tareas

Para acceder a la plantilla de Human Resources a Finance.

1. Abra el [Centro de administración de Power Apps](https://admin.powerapps.com/). 

2. Seleccione **Proyectos** y luego seleccione **Nuevo proyecto** en la esquina superior derecha. Crear un nuevo proyecto para cada entidad jurídica que desee integrar en Finance.

3. Seleccione **Human Resources (Human Resources Dataverse a Finance)** para sincronizar registros de Human Resources a Finance.

La plantilal usa las siguientes tareas subyacentes para sincronizar registros de Human Resources con Finance:

- **Funciones de trabajo con la función de trabajo de compensación**
- **Departamentos con unidad operativa**
- **Tipos de trabajo con tipo de trabajo de compensación**
- **Trabajos con trabajos**
- **Trabajos con detalles del trabajo**
- **Tipos de puesto con tipo de puesto**
- **Puestos de trabajo con puesto base**
- **Puestos de trabajo con detalles del puesto**
- **Puestos de trabajo con duraciones de puestos de trabajo**
- **Puestos de trabajo con jerarquías de puestos de trabajo**
- **Trabajadores con Trabajador**
- **Empleos con empleo**
- **Empleos con detalles del empleo**
- **Asignación del trabajador del puesto con asignaciones del trabajador del puesto**
- **Direcciones del trabajador con dirección postal del trabajador V2**

## <a name="template-mappings"></a>Asignaciones de plantilla

En las siguientes tablas de asignación de plantillas, el nombre de la tarea contiene las entidades utilizadas en cada aplicación. El origen (Human Resources) está a la izquierda y el destino (Finance) está a la derecha.

### <a name="job-functions-to-compensation-job-function"></a>Funciones de trabajo con la función de trabajo de compensación

| Tabla de Dataverse (origen) | Entidad de Finance (destino) |
|-------------------------------------|---------------------------------------------|
| cdm_name (cdm_Job   Function Name)  | JOBFUNCTIONID   (JOBFUNCTIONID)            |
| cdm_description   (cdm_description) | DESCRIPTION   (DESCRIPTION)                 |

### <a name="departments-to-operating-unit"></a>Departamentos con unidad operativa

| Tabla de Dataverse (origen)           | Entidad de Finance (destino) |
|-----------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                           | NAME (NAME)                                 |
| cdm_departmentnumber   (cdm_departmentnumber) | OPERATINGUNITNUMBER   (OPERATINGUNITNUMBER) |
|                                               | OPERATINGUNITTYPE   (OPERATINGUNITTYPE)     |
| cdm_description   (cdm_description)           | NAMEALIAS   (NAMEALIAS)                     |

### <a name="job-types-to-compensation-job-type"></a>Tipos de trabajo con tipo de trabajo de compensación

| Tabla de Dataverse (origen)   | Entidad de Finance (destino) |
|---------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                   | JOBTYPEID   (JOBTYPEID)                     |
| cdm_description   (cdm_description)   | DESCRIPTION   (DESCRIPTION)                 |
| cdm_exemptstatus   (cdm_exemptstatus) | EXEMPTSTATUS   (EXEMPTSTATUS)               |

### <a name="jobs-to-jobs"></a>Trabajos con trabajos

| Tabla de Dataverse (origen)                           | Entidad de Finance (destino)           |
|---------------------------------------------------------------|-------------------------------------------------------|
| cdm_name (cdm_name)                                           | JOBID (JOBID)                                         |
| cdm_maximumnumberofpositions   (cdm_maximumnumberofpositions) | MAXIMUMNUMBEROFPOSITIONS   (MAXIMUMNUMBEROFPOSITIONS) |
| cdm_allowedunlimitedpositions   (cdm_allowunlimitedpositions) | ALLOWUNLIMITEDPOSITIONS   (ALLOWUNLIMITEDPOSITIONS)   |
| cdm_description   (cdm_description)                           | DESCRIPTION   (DESCRIPTION)                           |
| cdm_jobdescription   (cdm_jobdescription)                     | JOBDESCRIPTION   (JOBDESCRIPTIONS)                    |

### <a name="jobs-to-job-detail"></a>Trabajos con detalles del trabajo

| Tabla de Dataverse (origen)                             | Entidad de Finance (destino) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                                             | JOBID (JOBID)                               |
| cdm_jobtypeid.cdm_name   (Tipo de trabajo (Nombre del tipo de trabajo))             | JOBTYPEID   (JOBTYPEID)                     |
| cdm_jobfunctionid.cdm_name   (Función de trabajo (Nombre de función de trabajo)) | FUNCTIONID   (FUCNTIONID)                   |
| cdm_validfrom   (Válido desde)                                    | VALIDFROM   (VALIDFROM)                     |
| cdm_validto   (Válido hasta)                                        | VALIDTO (VALIDTO)                           |
| cdm_defaultfulltimeequivalent   (Equivalente predeterminado a tiempo completo)   | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)   |

### <a name="position-types-to-position-type"></a>Tipos de puesto con tipo de puesto

| Tabla de Dataverse (origen)       | Entidad de Finance (destino) |
|-------------------------------------------|---------------------------------------------|
| cdm_name (cdm_name)                       | POSITIONTYPEID   (POSITIONTYPEID)           |
| cdm_description   (cdm_description)       | DESCRIPTION   (DESCRIPTION)                 |
| cdm_classification   (cdm_classification) | CLASSIFICATION   (CLASSIFICATION)           |

### <a name="job-positions-to-base-position"></a>Puestos de trabajo con puesto base

| Tabla de Dataverse (origen)           | Entidad de Finance (destino) |
|-----------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número de puesto de trabajo) | POSITIONID (POSITIONID)                      |

### <a name="job-positions-to-position-details"></a>Puestos de trabajo con detalles del puesto

| Tabla de Dataverse (origen)              | Entidad de Finance (destino)       |
|--------------------------------------------------------------------------|---------------------------------------------------|
| cdm_jobpositionnumber  (Número de puesto de trabajo)                            | POSITIONID (POSITIONID)                             |
| cdm_jobid.cdm_name   (Trabajo (Nombre))                                        | JOBID (JOBID)                                    |
| cdm_description   (cdm_description)                                        | DESCRIPTION   (DESCRIPTION)                       |
| cdm_departmentid.cdm_departmentnumber   (Departamento (número de departamento)) | DEPARTMENTNUMBER   (DEPARTMENTNUMBER)             |
| cdm_positiontypeid.cdm_name   (Tipo de posición (Nombre))                     | POSITIONTYPEID   (POSITIONTYPEID)                 |
| cdm_avaialableforassignment   (Disponible para asignación)                 | AVAILABLEFORASSIGNMENT   (AVAILABLEFORASSIGNMENT) |
| cdm_validfrom   (Válido desde)                                            | VALIDFROM   (VALIDFROM)                           |
| cdm_validto   (Válido hasta)                                                 | VALIDTO (VALIDTO)                               |
| cdm_fulltimeequivalent   (Equivalente a tiempo completo)                           | FULLTIMEEQUIVALENT   (FULLTIMEEQUIVALENT)         |

### <a name="job-positions-to-position-durations"></a>Puestos de trabajo con duraciones de puestos de trabajo

| Tabla de Dataverse (origen)             | Entidad de Finance (destino) |
|-------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número de puesto de trabajo)   | POSITIONID (POSITIONID)                      |
| Activación calculada (Activación calculada) | VALIDFROM (VALIDFROM)                        |
| Jubilación calculada (Jubilación calculada) | VALIDTO (VALIDTO)                         |

### <a name="job-positions-to-position-hierarchies"></a>Puestos de trabajo con jerarquías de puestos de trabajo

| Tabla de Dataverse (origen)        | Entidad de Finance (destino) |
|-----------------------------------------------------------------------------------------------|---------------------------------------------|
| cdm_jobpositionnumber   (Número de puesto de trabajo)                                                 | POSITIONID(POSITIONID)                      |
| cdm_parentjobpositionid.cdmjobpositionnumber   (cdm_parentjobpositionid.cdmjobpositionnumber) | PARENTPOSITIONID (PARENTPOSITIONID)         |
| cdm_validfrom   (Válido desde)                                                                  | VALIDFROM   (VALIDFROM)                     |
| cdm_validto (Válido hasta)                                                                      | VALIDTO (VALIDTO)                           |
| HIERARCHYTYPENAME   (HIERARCHYTYPENAME)                                                       | HIERARCHYTYPENAME   (HIERARCHYTYPENAME)     |


### <a name="workers-to-worker"></a>Trabajadores con Trabajador
| Tabla de Dataverse (origen)           | Entidad de Finance (destino)       |
|-----------------------------------------------|---------------------------------------------------|
| cdm_birthdate   (cdm_birthdate)               | BIRTHDATE   (BIRTHDATE)                           |
| cdm_gender   (cdm_gender)                     | GENDER (GENDER)                                   |
| cdm_primaryaddress   (cdm_primaryaddress)     | PRIMARYCONTACTEMAIL   (PRIMARYCONTACTEMAIL )      |
| cdm_primarytelephone   (cdm_primarytelephone) | PRIMARYCONTACTPHONE   (PRIMARYCONTACTPHONE)       |
| cdm_facebookidentity   (cdm_facebookidentity) | PRIMARYCONTACTFACEBOOK   (PRIMARYCONTACTFACEBOOK) |
| cdm_twitteridentity   (cdm_twitteridentity)   | PRIMARYCONTACTTWITTER   (PRIMARYCONTACTTWITTER)   |
| cdm_linkedinIdentity   (cdm_linkedinIdentity) | PRIMARYCONTACTLINKEDIN   (PRIMARYCONTACTLINKEDIN) |
| cdm_websiteurl   (cdm_websiteurl)             | PRIMARYCONTACTURL   (PRIMARYCONTACTURL)           |
| cdm_firstname   (cdm_firstname)               | FIRSTNAME   (FIRSTNAME)                           |
| cdm_middlename   (cdm_middlename)             | MIDDLENAME   (MIDDLENAME)                         |
| cdm_lastname   (cdm_lastname)                 | LASTNAME (LASTNAME)                               |
| cdm_workernumber   (cdm_workernumber)         | PERSONNELNUMBER   (PERSONNELNUMBER)               |
| cdm_type (cdm_type)                           | WORKERTYPE   (WORKERTYPE)                         |
| cdm_state   (cdm_state)                       | WORKSTATUS   (WORKERSTATUS)                       |

### <a name="employments-to-employment"></a>Empleos con empleo

| Tabla de Dataverse (origen)                             | Entidad de Finance (destino) |
|-----------------------------------------------------------------|---------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE) |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)     |
| cdm_workertype   (cdm_workertype)                               | WORKERTYPE   (WORKERTYPE)                   |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)         |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)             |

### <a name="employments-to-employment-detail"></a>Empleos con detalles del empleo

| Tabla de Dataverse (origen)                             | Entidad de Finance (destino)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_employmentstartdate   (cdm_employmentstartdate)             | EMPLOYMENTSTARTDATE   (EMPLOYMENTSTARTDATE)   |
| cdm_employmentenddate   (cdm_employmentenddate)                 | EMPLOYMENTENDDATE   (EMPLOYMENTENDDATE)       |
| cdm_validfrom   (Válido desde)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto (Válido hasta)                                        | VALIDTO (VALIDTO)                             |
| cdm_workerstartdate   (cdm_workerstartdate)                     | WORKERSTARTDATE   (WORKERSTARTDATE)           |
| cdm_lastdateworked   (cdm_lastdateworked)                       | LASTDATEWORKED   (LASTDATEWORKED)             |
| cdm_transitiondate   (cdm_transitiondate)                       | TRANSITIONDATE   (TRANSITIONDATE)             |
| cdm_employerunitofnotice   (cdm_employerunitofnotice)           | EMPLOYERUNITOFNOTICE   (EMPLOYERUNITOFNOTICE) |
| cdm_workerunitofnotice   (cdm_workerunitofnotice)               | WORKERUNITOFNOTICE   (WORKERUNITOFNOTICE)     |
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_companyid.cdm_companycode   (cdm_companyid.cdm_companycode) | LEGALENTITYID   (LEGALENTITYID)               |
| cdm_employernoticeamount   (cdm_employernoticeamount)           | EMPLOYERNOTICEAMOUNT   (EMPLOYERNOTICEAMOUNT) |
| cdm_workernoticeamount   (cdm_workernoticeamount )              | WORKERNOTICEAMOUNT   (WORKERNOTICEAMOUNT)     |

### <a name="position-worker-assignment-to-position-worker-assignments"></a>Asignación del trabajador del puesto con asignaciones del trabajador del puesto

| Tabla de Dataverse (origen)                             | Entidad de Finance (destino)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_jobpositionnumber   (Número de puesto de trabajo)                   | POSITIONID(POSITIONID)                        |
| cdm_validfrom   (Válido desde)                                    | VALIDFROM   (VALIDFROM)                       |
| cdm_validto   (Válido hasta)                                        | VALIDTO (VALIDTO)                             |

### <a name="worker-addresses-to-worker-postal-address-v2"></a>Direcciones del trabajador con dirección postal del trabajador V2

| Tabla de Dataverse (origen)                             | Entidad de Finance (destino)   |
|-----------------------------------------------------------------|-----------------------------------------------|
| cdm_workerid.cdm_workernumber   (cdm_workerid.cdm_workernumber) | PERSONNELNUMBER   (PERSONNELNUMBER)           |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSLOCATIONROLES   (ADDRESSLOCATIONROLES) |
| cdm_line1   (cdm_line1)                                         | ADDRESSSTREET   (ADDRESSSTREET)               |
| cdm_city (cdm_city)                                             | ADDRESSCITY   (ADDRESSCITY)                   |
| cdm_stateorprovince   (cdm_stateorprovince)                     | ADDRESSSTATE   (ADDRESSSTATE)                 |
| cdm_postalcode   (cdm_postalcode)                               | ADDRESSZIPCODE(ADDRESSZIPCODE)                |
| cdm_countryregion   (cdm_countryregion)                         | ADDRESSCOUNTRYREGION(ADDRESSCOUNTRYREGION)    |
| cdm_addressnumber   (cdm_addressnumber)                         | ADDRESSLOCATIONID(ADDRESSLOCATIONID)          |
| cdm_ispreferred   (cdm_ispreferred)                             | ISPRIMARY   (ISPRIMARY)                       |
| cdm_county   (cdm_county)                                       | ADDRESSCOUNTYID(ADDRESSCOUNTYID)              |
| cdm_addresstype   (cdm_addresstype)                             | ADDRESSDESCRIPTION(ADDRESSDESCRIPTION)        |

## <a name="integration-considerations"></a>Consideraciones de integración

La integración de Human Resources con Finance intentará hacer coincidir los registros según el id. Si los registros coinciden, el integrador de datos sobrescribirá los datos en Finance con los valores en Human Resources. Sin embargo, puede ocurrir un problema si lógicamente estos son registros diferentes y se generó el mismo id. en Human Resources o Finance en función de la secuencia numérica respectiva.

Este problema puede ocurrir con **Trabajador**, que usa **Número personal** para hacer la coincidencia y **Puestos**. Los trabajos no usan secuencias numéricas. Como resultado, si la misma ID de trabajo existe tanto en Human Resources como en Finance, la información de Human Resources sobrescribe la información de Dynamics 365 Finance. 

Para evitar problemas con los id. duplicados, puede agregar un prefijo en la [secuencia numérica](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/number-sequence-overview?toc=/dynamics365/unified-operations/talent/toc.json) o establecer un número inicial en la secuencia numérica que esté más allá del rango del otro sistema. 

El id. de ubicación utilizado para la dirección del trabajador no forma parte de una secuencia numérica. Al integrar una dirección de trabajador de Human Resources con Finance, si la dirección de trabajador ya existe en Finance, se puede crear un registro de dirección duplicado. 

La siguiente ilustración muestra un ejemplo de una asignación de plantilla en el integrador de datos. 

![Asignación de plantillas](./media/IntegrationMapping.png)

[!INCLUDE[footer-include](../includes/footer-banner.md)]