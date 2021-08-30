---
title: Solicitud de baja
description: Este tema proporciona detalles y una consulta de ejemplo para la entidad de solicitud de baja en Dynamics 365 Human Resources.
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
ms.openlocfilehash: c6c772c26e8a789a54c9eeb36c1cab576a7f94cb3ede547db46fe18a2e89c8ce
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762031"
---
# <a name="leave-request"></a>Solicitud de baja

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Solicitud de baja para Dynamics 365 Human Resources.

### <a name="description"></a>Descripción

Esta entidad proporciona información para una solicitud de licencia.

Nombre físico: mshr_essleaverequestentity.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de solicitud**</br>mshr_requestid</br>*Cadena* | Solo lectura | El id. de solicitud. |
| **Id. del tipo de baja**</br>mshr_leavetypeid</br>*Cadena* | Solo lectura | Id. del tipo de baja. |
| **Fecha**</br>mshr_leavedate</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha de la solicitud de licencia. |
| **Importe**</br>mshr_amount</br>*Decimal* | Solo lectura | El monto de la solicitud de licencia. |
| **Tipo medio día**</br>mshr_halfdaydefinition</br>*Conjunto de opciones mshr_LeaveHalfDayDefinition* | Solo lectura | El tipo de licencia de medio día. |
| **Comentario**</br>mshr_comment</br>*Cadena* | Solo lectura | Comentario de la solicitud. |
| **Estado**</br>mshr_status</br>*Conjunto de opciones mshr_status* | Solo lectura | El estado de la solicitud. |
| **Fecha**</br>mshr_requestdate</br>*Desplazamineto de fecha y hora* | Solo lectura | La fecha de la solicitud. |
| **Número de personal**</br>mshr_personnelnumber</br>*Cadena* | Solo lectura | El número de personal exclusivo del empleado. |
| **Id. de código de motivo**</br>mshr_reasoncodeid</br>*Cadena* | Solo lectura | Id. de código de motivo. |
| **Id. de área de datos**</br>mshr_dataareaid</br>*Cadena* | Solo lectura | Especifica la entidad jurídica (empresa). |
| **Campo primario**</br>mshr_primaryfield</br>*GUID* | Solo lectura</br>Generado por el sistema | |
| **Entidad de tipo de baja**</br>mshr_essleaverequestentityid</br>*GUID* | Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única la solicitud de baja. |

## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**Respuesta**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
