---
title: Plan de prestaciones de trabajadores en nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de plan de prestaciones de trabajadores en nómina en Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1805f7efaf2efc48d5996776f3aa27d75606886f
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068443"
---
# <a name="payroll-worker-benefit-plan"></a>Plan de prestaciones de trabajadores en nómina


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad del plan de prestaciones de trabajadores en nómina para Dynamics 365 Human Resources.

Nombre físico: mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>Descripción

Esta entidad proporciona información sobre el plan de prestacione para un trabajador determinado.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura</br>Obligatorio | El número de personal exclusivo del empleado. |
| **Id. de entidad jurídica**</br>mshr_legalentityID</br>*Cadena* | Solo lectura | Especifica la entidad jurídica (empresa). |
| **Id. de período**</br>mshr_periodid</br>*Cadena* | Solo lectura | El identificador del período. |
| **Id. de plan**</br>mshr_planid</br>*Cadena* | Solo lectura | El identificador del plan. |
| **Opción de cobertura**</br>mshr_coverageoptionid</br>*Cadena* | Solo lectura | Identificación de la opción de cobertura. |
| **Fecha inicial de la deducción**</br>mshr_deductionstartdatetime</br>*Desplazamineto de fecha y hora* | Solo lectura | Fecha inicial de la deducción. |
| **Fecha final de la deducción**</br>mshr_deductionenddatetime</br>*Desplazamineto de fecha y hora* | Solo lectura | Fecha final de la deducción. |
| **Estado**</br>mshr_status</br>*[Conjunto de opciones de estado del plan de prestaciones para empleados](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | Solo lectura | Estado del plan de prestaciones. |
| **Válido desde**</br>mshr_validfrom</br>*Desplazamineto de fecha y hora* | Solo lectura | La hora de inicio de la validez de este registro. |
| **Válido hasta**</br>mshr_validto</br>*Desplazamineto de fecha y hora* |  Solo lectura | La hora final de la validez de este registro. |
| **Id. del tipo de plan**</br>mshr_plantypeid</br>*Cadena* | Solo lectura | El identificador del tipo de plan. |
| **Código de tipo de plan**</br>mshr_plantypecode</br>*[Conjunto de opciones de cobertura del tipo de plan de prestaciones](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | Solo lectura | Especificación del tipo de plan. |
| **Número de períodos de pago**</br>mshr_payperiod</br>*Entero* | Solo lectura | El número de períodos de pago que representa la frecuencia con la que se paga al proveedor de beneficios o a los empleados. Esta cantidad se utilizará para calcular el importe del salario de beneficio anual del empleado. |
| **Importe del empleado**</br>mshr_amountemployee</br>*Decimal* | Solo lectura | Cantidad de empleados o porcentaje. |
| **Importe de la empresa**</br>mshr_amountemployer</br>*Decimal* | Solo lectura | Cantidad de empleadores o porcentaje. |
| **Campo primario**</br>mshr_primaryfield</br>*Cadena* | Generado por el sistema | Campo primario. |
| **Valor de identificación del trabajador** </br>_mshr_fk_worker_id_value</br>*GUID* | Clave extranjera: mshr_hcmworkerbaseentityid de la entidad mshr_hcmworkerbaseentity. | Identificador único generado por el sistema para el trabajador. |
| **Valor del id. del período**</br> _mshr_fk_period_id_value</br>*GUID* | Clave extranjera: mshr_benefitperiodentityid de la entidad mshr_benefitperiodentity. | Identificador único generado por el sistema para el período. |
| **Valor del id. del plan**</br> _mshr_fk_plan_id_value</br>*GUID* | Clave extranjera: mshr_benefitplanentityid de la entidad mshr_benefitplanentity. | Identificador único generado por el sistema para el plan. |
| **Valor de id. de tipo de plan**</br> _mshr_fk_plantype_id_value</br>*GUID* | Clave extranjera: mshr_benefitplantypeentityid de la entidad mshr_benefitplantypeentity. | Identificador único generado por el sistema para el plan. |
| **Valor del id. de opción de cobertura**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | Clave extranjera: mshr_benefitcoverageoptionentityid de la entidad mshr_benefitcoverageoptionentity. | Identificador único generado por el sistema para el plan. |
| **Valor de id. de entidad del plan de prestaciones para trabajadores en nómina**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | Solo lectura </br> Generado por el sistema | Identificador único generado por el sistema para el registro. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>Consulta de ejemplo para el plan de beneficios de trabajadores en nómina

**Solicitud**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**Respuesta**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
