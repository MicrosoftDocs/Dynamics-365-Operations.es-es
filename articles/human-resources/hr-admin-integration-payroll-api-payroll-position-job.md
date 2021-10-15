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
ms.openlocfilehash: c0b70411e6535b22d698545438dcb0b16935e731
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559592"
---
# <a name="payroll-position-job"></a>Trabajo de puesto de nómina

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Puesto de nómina para Dynamics 365 Human Resources.

### <a name="description"></a>Descripción

Esta entidad proporciona la relación entre el puesto y un trabajo para un plan de compensación fijo dado.

Nombre físico: mshr_payrollpositionjobentity.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de puesto**</br>mshr_positionid</br>*Cadena* | Solo lectura | El id. del puesto. |
| **Válido desde**</br>mshr_validto</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha desde la que es válida el puesto y la relación laboral. |
| **Válido hasta**</br>mshr_validto</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha hasta la que es válida el puesto y la relación laboral. |
| **Id. de trabajo**</br>mshr_jobid</br>*Cadena* | Solo lectura | El id. de trabajo. |
| **Campo primario**</br>mshr_primaryfield</br>*Cadena* | Generado por el sistema | El campo primario. |
| **Id. de entidad de trabajo de puesto de nómina**</br>mshr_payrollpositionjobentityid</br>*Guid* | Generado por el sistema. | Un valor de identificador único global (GUID) generado por el sistema para identificar de forma exclusiva el trabajo. |

## <a name="relations"></a>Relaciones

| Valor de la propiedad | Entidad relacionada | Propiedad de navegación | Tipo de recopilación |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | mshr_payrollfixedcompensationplanentity | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Job |
| _mshr_fk_jobdetail_id_value | mshr_hcmjobdetailentity | mshr_FK_JobDetail_id | No aplicable |
| _mshr_fk_payroll_id_value | mshr_payrollpositionentity | mshr_FK_Payroll_id | mshr_FK_PayrollPositionEntity_Job |

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
