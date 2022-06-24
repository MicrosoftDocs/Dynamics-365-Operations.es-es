---
title: Frecuencia de pago de compensación
description: Este artículo proporciona detalles y una consulta de ejemplo para la entidad de frecuencia de pago de compensación en Dynamics 365 Human Resources.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9afe27776797b2355a32226bbd7fa514b5c5d962
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894625"
---
# <a name="compensation-pay-frequency"></a>Frecuencia de pago de compensación


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad de frecuencia de pago de compensación en Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpayrateconversionentity.

### <a name="description"></a>Descripción

Esta entidad proporciona información sobre la conversión de la tasa de pago para una frecuencia de pago de compensación determinada.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Conversión de tasa de pago anual**</br>mshr_annualconversionfactor</br>*Decimal* | Solo lectura | El factor de conversión anual para la frecuencia de pago. |
| **Descripción**</br>mshr_description</br>*Cadena* | Solo lectura | La descripción de la tasa de conversión. |
| **Conversión de tasa de pago horaria**</br>mshr_hourlyconversionfactor</br>*Decimal* | Solo lectura | El factor de conversión horaria para la frecuencia de pago. |
| **Conversión de tasa de pago mensual**</br>mshr_monthlyconversionfactor</br>*Decimal* | Solo lectura | El factor de conversión mensual para la frecuencia de pago. |
| **Conversión de índice salarial**</br>mshr_payrateconversion</br>*Cadena* | Solo lectura | Una cadena única para identificar la tasa de conversión. |
| **Periodo**</br>mshr_period</br>*conjunto de opciones de período* | Solo lectura | El período principal para la conversión de la tasa de pago dada. |
| **Conversión de tasa de pago semanal**</br>mshr_weeklyconversionfactor</br>*Decimal* | Solo lectura | El factor de conversión semanal para la frecuencia de pago. |
| **Identificación de área de datos**</br>mshr_dataareaid</br>*Cadena* | Solo lectura | La entidad jurídica (empresa). |
| **Identificación de entidad de frecuencia de pago de compensación**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Generado por el sistema | Un valor de identificador único global (GUID) generado por el sistema para identificar de forma exclusiva el registro. |

## <a name="example-query-for-payroll-employee"></a>Consulta de ejemplo para empleado de nómina

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_hcmpayrateconversionentities?$filter=mshr_payrateconversion eq 'Annual' and mshr_dataareaid eq 'usmf'
```

**Respuesta**

```json
{
    "mshr_annualconversionfactor": 1,
    "mshr_description": "Annual",
    "mshr_hourlyconversionfactor": 0.0004807692,
    "mshr_monthlyconversionfactor": 0.0833333333,
    "mshr_payrateconversion": "Annual",
    "mshr_period": 200000000,
    "mshr_weeklyconversionfactor": 0.0192307692,
    "mshr_dataareaid": "usmf",
    "mshr_hcmpayrateconversionentityid": "0000056e-0000-0000-b027-fef003000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
