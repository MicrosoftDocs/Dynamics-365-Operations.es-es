---
title: Empleado con nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad Empleado de nóminas en Dynamics 365 Human Resources.
author: jcart
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7f43476cd044a9cc2e11412aac4af1cff2f9e511
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559542"
---
# <a name="payroll-employee"></a>Empleado con nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad empleado de nómina para Dynamics 365 Human Resources.

Nombre físico: mshr_payrollemployeeentity.

### <a name="description"></a>Descripción

Esta entidad proporciona información sobre el empleado. Debes configurar los [parámetros de integración de nómina](hr-admin-integration-payroll-api-parameters.md) antes de usar esta entidad.

>[!IMPORTANT] 
>**FirstName**, **MiddleName**, **LastName**, **NameValidFrom** y **NameValidTo** ya no están disponibles en esta entidad. Esto garantiza que solo haya una fuente de datos con fecha de vigencia que respalde esta entidad.
>Estos campos estarán disponibles en el **DirPersonNameHistoricalEntity**, que se publicó en la Platform update 43. Hay una relación OData de **PayrollEmployeeEntity** a **DirPersonNameHistoricalEntity**. 

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad jurídica**</br>mshr_legalentityid</br>*Cadena* | Solo lectura | Especifica la entidad jurídica (empresa). |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura | El número de personal exclusivo del empleado. |
| **Fecha inicial del empleo**</br>mshr_employmentstartdate</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha de inicio del empleo del empleado. |
| **Fecha final del empleo**</br>mshr_employmentenddate</br>*Desplazamineto de fecha y hora* | Solo lectura |La fecha de finalización del empleo del empleado.  |
| **Fecha de nacimiento**</br>mshr_birthdate</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha de nacimiento del empleado. |
| **Género**</br>mshr_gender</br>[Opción mshr_hcmpersongender establecida](hr-admin-integration-payroll-api-gender.md) | Solo lectura | El sexo del empleado. |
| **Tipo de empleo**</br>mshr_employmenttype</br>[Conjunto de opciones mshr_hcmemploymenttype](hr-admin-integration-payroll-api-hcmemploymenttype.md) | Solo lectura | Tipo de empleo. |
| **Id. de tipo de identificación**</br>mshr_identificationtypeid</br>*Cadena* |Solo lectura | El tipo de identificación definido para el empleado. |
| **El número de identificación para**</br>mshr_identificationnumber</br>*Cadena* | Solo lectura |El número de identificación definido para el empleado. |
| **Listo para pagar**</br>mshr_readytopay</br>[Conjunto de opciones mshr_noyes](hr-admin-integration-payroll-api-no-yes.md) | Solo lectura | Indica si el empleado está marcado como listo para pagar. |
| **ID de entidad de empleado de nómina**</br>mshr_payrollemployeeentityid</br>*GUID* | Generado por el sistema | Un valor de identificador único global (GUID) generado por el sistema para identificar de forma exclusiva el empleado. |

## <a name="relations"></a>Relaciones

|Valor de la propiedad | Entidad relacionada | Propiedad de navegación | Tipo de recopilación |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>Consulta de ejemplo para empleado de nómina

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
```

**Respuesta**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
