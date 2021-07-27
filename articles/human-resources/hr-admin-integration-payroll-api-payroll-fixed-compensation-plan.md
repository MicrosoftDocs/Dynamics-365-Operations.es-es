---
title: Plan de compensación fija con nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de plan de compensación fija de nóminas en Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
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
ms.openlocfilehash: 24f8af4d691c3085c36018c574fa3b917a3d6953
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314222"
---
# <a name="payroll-fixed-compensation-plan"></a>Plan de compensación fija con nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad del plan de compensación fija de nómina para Dynamics 365 Human Resources.

### <a name="description"></a>Descripción

Esta entidad proporciona el plan de compensación fija asignado para un puesto determinado de un empleado.

Nombre físico: mshr_payrollfixedcompensationplanentity.

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de empleado**<br>mshr_fk_employee_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_Employee_id of mshr_payrollemployeeentity entity  | Id. de empleado |
| **Índice salarial**<br>mshr_payrate<br>*Decimal* | Solo lectura<br>Obligatorio | Tasa de pago definida en el plan de compensación fijo. |
| **Id. de plan**<br>mshr_planid<br>*Cadena* | Solo lectura<br>Obligatorio |Especifica el plan de compensación.  |
| **Válido desde**<br>mshr_validfrom<br>*Desplazamineto de fecha y hora* |  Solo lectura<br>Obligatorio |Fecha de inicio de la validez de la compensación fija del empleado.  |
| **Entidad de plan de compensación fija con nómina**<br>mshr_payrollfixedcompensationplanentityid<br>*GUID* | Obligatorio<br>Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única el plan de compensación. |
| **Frecuencia de pago**<br>mshr_payfrequency<br>*Cadena* | Solo lectura<br>Obligatorio |La frecuencia con la que se pagará al empleado.  |
| **Válido hasta**<br>mshr_validto<br>*Desplazamineto de fecha y hora* | Solo lectura <br>Obligatorio | Fecha de finalización de la validez de la compensación fija del empleado. |
| **Id. de puesto**<br>mshr_positionid<br>*Cadena* | Solo lectura <br>Obligatorio | ID de puesto asociado con el empleado y la inscripción al plan de compensación fija. |
| **Divisa**<br>mshr_currency<br>*Cadena* | Solo lectura <br>Obligatorio |La moneda definida para el plan de compensación fijo   |
| **Número de personal**<br>mshr_personnelnumber<br>*Cadena* | Solo lectura<br>Obligatorio |El número de personal exclusivo del empleado.  |

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
