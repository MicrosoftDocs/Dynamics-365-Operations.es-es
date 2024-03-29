---
title: Tipo de baja
description: Este artículo proporciona detalles y una consulta de ejemplo para la entidad de tipo de baja en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 6e7905989df92e943b86f86194c87dcb2a7b1446
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893797"
---
# <a name="leave-type"></a>Tipo de baja


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad de tipo de baja para Dynamics 365 Human Resources.

### <a name="description"></a>Description

Esta entidad proporciona información para un tipo de baja dado.

Nombre físico: mshr_essleavetypeentity.

## <a name="properties"></a>Propiedades

| Propiedad</br>**Nombre físico**</br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. del tipo de baja**</br>mshr_leavetypeid</br>*Cadena* | Solo lectura | Id. del tipo de baja. |
| **Descripción**</br>mshr_description</br>*Cadena* | Solo lectura | Una descripción del tipo de baja. |
| **Categoría**</br>mshr_category</br>*Conjunto de opciones mshr_LeaveTypeCategory* | Solo lectura | Categoría del tipo de baja. |
| **Código de motivo requerido**</br>mshr_isreasoncoderequired</br>*Conjunto de opciones mshr_NoYes* | Solo lectura | Define si se requiere un código de motivo para el tipo de licencia. |
| **Unidad de baja**</br>mshr_leaveamountunit</br>*Conjunto de opciones mshr_LeaveAmountUnit* | Solo lectura | La unidad de este tipo de licencia. |
| **Habilitar medio día**</br>mshr_enablehalfdaydefinition</br>*Conjunto de opciones mshr_NoYes* | Define si medio día está habilitado para el tipo de licencia. |
| **Id. de área de datos**</br>mshr_dataareaid_id</br>*Cadena* | Solo lectura | Especifica la entidad jurídica (empresa). |
| **Entidad de tipo de baja**</br>mshr_essleavetypeentityid</br>*GUID* | Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única el tipo de baja. |

## <a name="example-query"></a>Consulta de ejemplo

**Solicitud**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**Respuesta**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración de nóminas](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
