---
title: Saldo de bajas
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de saldo de bajas en Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ab136e9b40de280387dc3c5207a08a6bb357941feb3a8c736d9671f7850f2bf8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6782692"
---
# <a name="leave-balance"></a>Saldo de bajas

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad de saldo de bajas para Dynamics 365 Human Resources.

### <a name="description"></a>Descripción

Esta entidad proporciona el saldo de la licencia por tipo de licencia para un empleado determinado.

Nombre físico: mshr_essleavebalanceentities.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura | El número de personal exclusivo del empleado. |
| **Saldo actual**</br>mshr_balanceavailable</br>*Decimal* | Solo lectura | El saldo actual del empleado. |
| **Tipo**</br>mshr_balanceavailable</br>*Cadena* | Solo lectura | Id. del tipo de baja. |
| **Tasa de acumulación**</br>mshr_accrualratedescription</br> | Solo lectura | La tasa de acumulación. |
| **ÚIltimo importe transferible**</br>mshr_lastcarryforwardamount</br>*Decimal* | Solo lectura | El último importe de transferencia. |
| **Tomado este año**</br>mshr_takenthisyear</br>*Decimal* | Solo lectura | La cantidad de vacaciones que se tomaron este año. |
| **Total de este año**</br>mshr_totalthisyear</br>*Decimal* | Solo lectura | Importe total de las entregas este año. |
| **Id. de área de datos**</br>mshr_dataareaid_id</br>*Cadena* | Solo lectura | Especifica la entidad jurídica (empresa). |
| **Campo primario**</br>mshr_primaryfield</br>*GUID* | Solo lectura</br>Generado por el sistema | |
| **Id. del tipo de baja**</br>_mshr_fk_leavetype_id_value</br>*GUID* | Solo lectura</br>Clave externa: mshr_essleavetypeentityid de mshr_essleavetypeentity entity  | Id. del tipo de baja |
| **Entidad de saldo de bajas**</br>mshr_essleavebalanceentityid</br>*GUID* | Generado por el sistema | Valor GUID generado por el sistema para identificar el saldo. |

## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**Respuesta**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
