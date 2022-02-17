---
title: Aptitud de solicitud de contratación
description: Este tema describe la entidad Aptitud de solicitud de contratación para Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 245b9a1ff4f140b9288b79c70820204f3082568b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068618"
---
# <a name="recruiting-request-skill"></a>Aptitud de solicitud de contratación


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Aptitud de solicitud de contratación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmrecruitingrequestskillentity

### <a name="description"></a>Descripción

Describe los requisitos de aptitudes para una solicitud de contratación.

### <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_skillid": "String",
    "mshr_skilldescription": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_ratingleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratingmodel_id_value": "Guid",
    "mshr_hcmrecruitingrequestskillentityid": "Guid"
}
```

### <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad Aptitud de solicitud de contratación**<br>mshr_hcmrecruitingrequestskillentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro **Aptitud de solicitud de contratación**. |
| **Id. de solicitud de contratación**<br>mshr_recruitingrequestid<br>*Cadena* | Escribir una vez<br>Obligatorio | Identificador único legible por el usuario de la solicitud de contratación asociada. |
| **Valor de id. de solicitud de contratación**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br> Clave externa: mshr_hcmrecruitingrequestentityid de la entidad mshr_hcmrecruitingrequestentity | Identificador único generado por el sistema de la solicitud de contratación asociada. |
| **Id. de aptitud**<br>mshr_skillid<br>*Cadena*<br> | Escribir una vez<br>Obligatorio | Identificador único legible por el usuario de la aptitud requerida. |
| **Valor de id. de aptitud**<br>_mshr_fk_skill_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmskillentityid de la entidad mshr_hcmskillentity | El identificador único generado por el sistema de la aptitud requerida. |
| **Id. de nivel de calificación**<br>mshr_ratinglevelid<br>*Cadena* | Escribir una vez<br>Opcional | El valor del nivel de aptitud requerido seleccionado para el trabajo, según el modelo de calificación asignado a la aptitud. |
| **Valor de id. de nivel de calificación**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmratinglevelentityid de la entidad mshr_hcmratinglevelentity | Identificador único generado por el sistema para el nivel. |
| **Descripción de la aptitud**<br>mshr_skilldescription<br>*Cadena* | Solo lectura<br>Obligatorio | Descripción de la aptitud. |
| **Descripción del nivel de calificación**<br>mshr_ratingleveldescription<br>*Cadena* | Solo lectura<br>Opcional | Descripción del nivel de aptitud seleccionado. |
| **Id. de área de datos**<br>mshr_dataareaid<br>*Cadena* | Leer/Escribir<br>Opcional | Especifica la entidad jurídica (empresa). |
| **Valor de id. de área de datos**<br>_mshr_dataareaid_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: entidad cdm_companyid of cdm_company | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa). |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Concatenación del valor de la solicitud de contratación y el id. de aptitud como otro método para identificar de forma única el registro. |
| **Id. de modelo de calificación**<br>mshr_ratingmodelid<br>*Cadena* | Leer/Escribir<br>Obligatorio | El modelo de calificación utilizado para calificar la aptitud. |
| **Valor de id. de modelo de calificación**<br>_mshr_fk_hcmratingmodel_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmratingmodelentityid de la entidad mshr_hcmratingmodelentity | Identificador único generado por el sistema del modelo de calificación utilizado para calificar la aptitud. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
