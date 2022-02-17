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
ms.openlocfilehash: 2bbb234d2f51391ea65e3d6153d6cee250f3c6dc
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069816"
---
# <a name="payroll-position"></a>Puesto de nómina


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Puestos de nómina en Dynamics 365 Human Resources.

Nombre físico: mshr_payrollpositionentity.

### <a name="description"></a>Descripción

Esta entidad proporciona información relacionada con el puesto para un empleado dado.

Nombre físico: mshr_payrollpositionentity.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de puesto**</br>mshr_positionid</br>*Cadena* | Solo lectura | El id. del puesto. |
| **Id. de ciclo de pago**</br>mshr_paycycleid</br>*Cadena* | Solo lectura | El ciclo de pago que se define en la posición. |
| **Horas ordinarias anuales**</br>Horas regulares anuales</br>*Decimal* | Solo lectura | Las horas regulares anuales que se definen en el puesto. |
| **Pagado por la entidad jurídica**</br>paidbylegalentity</br>*Cadena* | Solo lectura | La entidad legal que se define en el puesto y responsable de emitir el pago. |
| **Válido hasta**</br>validto</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha hasta la que son válidos los detalles del puesto. |
| **Válido desde**</br>validfrom</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha desde la que son válidos los detalles del puesto. |
| **Campo primario**</br>mshr_primaryfield</br>*Cadena* | Generado por el sistema | El campo primario. |
| **Id de entidad de detalle de puesto de nómina**</br>Nómina posicióndetallesentidadid</br>*Guid* | Obligatorio</br>Generado por el sistema. | Un valor de identificador único global (GUID) generado por el sistema para identificar de forma exclusiva el puesto. |

## <a name="relations"></a>Relaciones

| Valor de la propiedad | Entidad relacionada | Propiedad de navegación | Tipo de recopilación |
| --- | --- | --- | --- |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_PayrollPosition |
| _mshr_fk_hcmpositionhierarchy_id_value | mshr_hcmpositionhierarchyentity | mshr_FK_HcmPositionHierarchy_id | No aplicable |
| _mshr_fk_job_id_value | mshr_payrollpositionjobentity | mshr_FK_Job_id | mshr_FK_PayrollPositionJobEntity_Payroll |
| _mshr_fk_positionassignmentv2_id_value | mshr_hcmpositionworkerassignmentv2entity | mshr_FK_PositionAssignmentV2_id | No aplicable |

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
