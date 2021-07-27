---
title: Trabajo de puesto de nómina
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de trabajo de puesto de nóminas en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 842c459acd8b5e1a8b6074243b3afa18dc6a13c5
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314246"
---
# <a name="payroll-position-job"></a>Trabajo de puesto de nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Puesto de nómina para Dynamics 365 Human Resources.

### <a name="description"></a>Descripción

Esta entidad proporciona la relación entre el puesto y un trabajo para un plan de compensación fijo dado.

Nombre físico: mshr_payrollpositionjobentity.

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de trabajo**<br>mshr_jobid<br>*Cadena* | Solo lectura<br>Obligatorio |El id. de trabajo. |
| **Válido desde**<br>mshr_validto<br>*Desplazamineto de fecha y hora* | Solo lectura <br>Obligatorio | Fecha desde la que es válida el puesto y la relación laboral. |
| **Válido hasta**<br>mshr_validto<br>*Desplazamineto de fecha y hora* | Solo lectura <br>Obligatorio | Fecha hasta la que es válido el puesto y la relación laboral.  |
| **Id. de puesto**<br>mshr_positionid<br>*Cadena* | Solo lectura<br>Obligatorio | El id. del puesto. |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* | Obligatorio<br>Generado por el sistema |  |
| **Valor de id. de trabajo de puesto**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_PayrollPositionJobEntity de la mshr_payrollpositionjobentity |Id. del trabajo asociado al puesto.|
| **Valor de id. de plan de compensación fijo**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | Id. del plan de compensación fijo asociado al puesto. |
| **Id. de entidad de trabajo de puesto de nómina**<br>mshr_payrollpositionjobentityid<br>*Guid* | Obligatorio<br>Generado por el sistema. | Valor GUID generado por el sistema para identificar de forma única el trabajo.  |

## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollpositionjobentities?$filter=mshr_positionid eq '000276'
```

**Respuesta**

```json
{
    "mshr_positionid": "000276",
    "mshr_validfrom": "2016-07-06T18:11:33Z",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_jobid": "Accountant",
    "mshr_primaryfield": "000276 | Accountant | 7/6/2016 06:11:33 pm",
    "_mshr_fk_jobdetail_id_value": "00000b8d-0000-0000-b0ff-004105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000058a-0000-0000-d5ff-004105000000",
    "_mshr_fk_payroll_id_value": "00000427-0000-0000-df00-014105000000",
    "mshr_payrollpositionjobentityid": "00000906-0000-0000-df00-014105000000"
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
