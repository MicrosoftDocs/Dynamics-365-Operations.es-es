---
title: Detalles de nómina para puestos
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de detalles de nóminas par las posiciones en Dynamics 365 Human Resources.
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
ms.openlocfilehash: e13a6b3608802eb7bb2bc00686c2e914cc765587
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314174"
---
# <a name="payroll-position"></a>Puesto de nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Puestos de nómina en Dynamics 365 Human Resources.

Nombre físico: mshr_payrollpositionentity.

### <a name="description"></a>Descripción

Esta entidad proporciona información relacionada con el puesto para un empleado dado.

Nombre físico: 

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Horas ordinarias anuales**<br>Horas regulares anuales<br>*Decimal* | Solo lectura<br>Obligatorio | Horas regulares anuales definidas en el puesto.  |
| **Id de entidad de detalle de puesto de nómina**<br>Nómina posicióndetallesentidadid<br>*Guid* | Obligatorio<br>Generado por el sistema. | Valor GUID generado por el sistema para identificar el puesto de forma única.  |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* | Obligatorio<br>Generado por el sistema |  |
| **Valor de id. de trabajo de puesto**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_PayrollPositionJobEntity de la mshr_payrollpositionjobentity |Id. del trabajo asociado al puesto.|
| **Valor de id. de plan de compensación fijo**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | Id. del plan de compensación fijo asociado al puesto. |
| **Id. de ciclo de pago**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | El ciclo de pago definido en la posición. |
| **Pagado por la entidad jurídica**<br>paidbylegalentity<br>*Cadena* | Solo lectura<br>Obligatorio | La entidad legal definida en el puesto responsable de emitir el pago. |
| **Id. de puesto**<br>mshr_positionid<br>*Cadena* | Solo lectura<br>Obligatorio | El id. del puesto. |
| **Válido hasta**<br>validto<br>*Desplazamineto de fecha y hora* | Solo lectura<br>Obligatorio |La fecha desde la que son válidos los detalles del puesto.  |
| **Válido desde**<br>validfrom<br>*Desplazamineto de fecha y hora* | Solo lectura<br>Obligatorio |La fecha hasta la que son válidos los detalles del puesto.  |

## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionentities?$filter=mshr_positionid eq @positionid and mshr_validfrom le @asofdate and mshr_validto ge @asofdate&@positionid='000276'&@asofdate=2021-04-01
```

**Respuesta**

```json
{
    "mshr_positionid": "000276",
    "mshr_paycycleid": "w",
    "mshr_annualregularhours": 3000,
    "mshr_paidbylegalentity": "USMF",
    "mshr_validfrom": "2021-03-14T00:00:00Z",
    "mshr_validto": "2154-12-31T00:00:00Z",
    "mshr_primaryfield": "000276 | 3/14/2021",
    "_mshr_fk_job_id_value": "00010094-0000-0000-df00-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollpositionentityid": "00010097-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
