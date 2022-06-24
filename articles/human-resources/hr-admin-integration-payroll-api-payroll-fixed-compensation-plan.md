---
title: Plan de compensación fija con nómina
description: Este artículo proporciona detalles y una consulta de ejemplo para la entidad de plan de compensación fija de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 83fa8aeb38cc44191242cf029022939cefb22cb8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909857"
---
# <a name="payroll-fixed-compensation-plan"></a>Plan de compensación fija con nómina


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad del plan de compensación fija de nómina para Dynamics 365 Human Resources.

### <a name="description"></a>Descripción

Esta entidad proporciona el plan de compensación fija asignado para un puesto determinado de un empleado.

Nombre físico: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de plan**</br>mshr_planid</br>*Cadena* | Solo lectura | Especifica el plan de compensación.  |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura | El número de personal exclusivo del empleado. |
| **Índice salarial**</br>mshr_payrate</br>*Decimal* | Solo lectura | Tasa de pago definida en el plan de compensación fijo. |
| **Id. de puesto**</br>mshr_positionid</br>*Cadena* | Solo lectura | ID de puesto asociado con el empleado y la inscripción al plan de compensación fija. |
| **Válido desde**</br>mshr_validfrom</br>*Desplazamineto de fecha y hora* |  Solo lectura | Fecha de inicio de la validez de la compensación fija del empleado.  |
| **Válido hasta**</br>mshr_validto</br>*Desplazamineto de fecha y hora* | Solo lectura | Fecha de finalización de la validez de la compensación fija del empleado. |
| **Frecuencia de pago**</br>mshr_payfrequency</br>*Cadena* | Solo lectura | El identificador de la [frecuencia de pago de compensación](hr-admin-integration-payroll-api-compensation-pay-frequency.md) para la tarifa de pago dada. |
| **Divisa**</br>mshr_currency</br>*Cadena* | Solo lectura | La moneda definida para el plan de compensación fijo. |
| **Entidad de plan de compensación fija con nómina**</br>mshr_payrollfixedcompensationplanentityid</br>*GUID* | Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única el plan de compensación. |

## <a name="relations"></a>Relaciones

|Valor de la propiedad | Entidad relacionada | Propiedad de navegación | Tipo de recopilación |
| --- | --- | --- | --- |
| _mshr_fk_employee_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Employee_id | mshr_FK_PayrollEmployeeEntity_FixedCompPlan |
| _mshr_fk_job_id_value | [mshr_payrollpositionjobentity](hr-admin-integration-payroll-api-payroll-position-job.md) | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_FixedCompPlan |
| _mshr_fk_payrollposition_id_value | [mshr_payrollpositionentity](hr-admin-integration-payroll-api-payroll-position.md) | mshr_FK_PayrollPosition_id | mshr_FK_PayrollPositionEntity_FixedCompPlan |
| _mshr_fk_plan_id_value | mshr_hcmcompfixedplantableentity | mshr_FK_Plan_id | - |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_FixedComp |

## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollfixedcompensationplanentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Respuesta**

```json
{
    "mshr_planid": "GradeC",
    "mshr_personnelnumber": "000041",
    "mshr_payrate": 75200,
    "mshr_positionid": "000276",
    "mshr_validfrom": "2011-04-05T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_payfrequency": "Annual",
    "mshr_currency": "USD",
    "_mshr_fk_employee_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_fk_plan_id_value": "0000070c-0000-0000-b328-fef003000000",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "mshr_payrollfixedcompensationplanentityid": "0000029f-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": null
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
