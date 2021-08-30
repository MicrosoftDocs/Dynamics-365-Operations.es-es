---
title: Plan de compensación variable con nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de plan de compensación variable de nóminas en Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-15
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 96a644bf129de6dd3f78098bcb6415d17058d6decbd7d904a99bb6f050d3a9e0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730451"
---
# <a name="payroll-variable-compensation-plan"></a>Plan de compensación variable con nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad del plan de compensación variable de nómina para Dynamics 365 Human Resources.

### <a name="description"></a>Descripción

Esta entidad proporciona el plan de compensación variable asignado para un puesto determinado de un empleado.

Nombre físico: mshr_payrollvariablecompensationawardentity.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura</br>Obligatorio |El número de personal exclusivo del empleado.  |
| **Fecha de prima**</br>mshr_awarddate</br>*Desplazamineto de fecha y hora* | Solo lectura</br>Obligatorio | Fecha de la prima. |
| **Tipo de prima**</br>mshr_awardtype</br>*[Conjunto de opciones mshr_HrmCompVarAwardEmplType](hr-admin-integration-payroll-api-award-type.md)* | Solo lectura</br>Obligatorio | El tipo de prima definido para el plan de compensación variable seleccionado. |
| **Divisa**</br>mshr_unitcurrencycode</br>*Cadena* | Solo lectura </br>Obligatorio |La moneda definida para el plan de compensación variable.   |
| **Id. de plan de compensación fija**</br>mshr_fixedplanid</br>*Cadena* | Solo lectura | El plan de compensación fijo utilizado como base para el cálculo de la prima. |
| **Valor de unidad**</br>mshr_awardamount</br>*Decimal* | Solo lectura | El valor de la unidad |
| **Tipo de proceso**</br>mshr_processtype</br>*[Conjunto de opciones mshr_hrmCompProcessType](hr-admin-integration-payroll-api-process-type.md)* | Solo lectura | El tipo de proceso. |
| **Tipo de plan de compensación variable**</br>Cadena</br>*mshr_typeid* | Solo lectura | El tipo de plan de compensación variable. |
| **Id. de plan de compensación variable**</br>Cadena</br>*mshr_planid* | Solo lectura | Id. del plan de compensación variable. |
| **Campo primario**</br>mshr_primaryfield</br>*GUID* | Solo lectura</br>Generado por el sistema. | |
| **Id. de empleado**</br>mshr_fk_employee_id_value</br>*GUID* | Solo lectura</br>Obligatorio</br>Clave externa: mshr_Employee_id of mshr_payrollemployeeentity entity  | Id. de empleado. |
| **Entidad de plan de compensación variable con nómina**</br>mshr_payrollvariablecompensationawardentityid</br>*GUID* | Obligatorio</br>Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única el plan de compensación. |


## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollvariablecompensationawardentities?$filter=mshr_personnelnumber eq '000001'
```

**Respuesta**

```json
{
    "mshr_personnelnumber": "000001",
    "mshr_awarddate": "2015-01-15T00:00:00Z",
    "mshr_awardtype": 200000000,
    "mshr_unitcurrencycode": "USD",
    "mshr_fixedplanid": "",
    "mshr_awardamount": 1,
    "mshr_processtype": 200000003,
    "mshr_typeid": "Bonus",
    "mshr_planid": "MgBonus",
    "mshr_primaryfield": "000001 | MgBonus | Bonus | 1/15/2015",
    "_mshr_fk_employee_id_value": "00000655-0000-0000-adff-004105000000",
    "mshr_payrollvariablecompensationawardentityid": "000001a1-0000-0000-adff-004105000000",
    "_mshr_fk_fixedcomp_id_value": null
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
