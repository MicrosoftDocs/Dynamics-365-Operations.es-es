---
title: Nivel educativo de solicitud de contratación
description: Este tema describe la entidad Nivel educativo de solicitud de contratación para Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: efc5c4813f8abd869e8137052c4aeb356a930d0b
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465975"
---
# <a name="recruiting-request-education"></a>Nivel educativo de solicitud de contratación

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Nivel educativo de solicitud de contratación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmrecruitingrequesteducationentity

### <a name="description"></a>Descripción

Describe los requisitos educativos para una RecruitingRequest.

### <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_educationdisciplineid": "String",
    "mshr_educationdisciplinedescription": "String",
    "mshr_educationlevelid": "String",
    "mshr_educationleveldescription": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequesteducationentityid": "Guid"
}
```

### <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad Nivel educativo de solicitud de contratación**<br>mshr_hcmrecruitingrequesteducationentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro Nivel educativo de solicitud de contratación. |
| **Id. de solicitud de contratación**<br>mshr_recruitingrequestid<br>*Cadena* | Escribir una vez<br>Obligatorio | Identificador único legible por el usuario de la solicitud de contratación relacionada. |
| **Valor de id. de solicitud de contratación**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmrecruitingrequestentityid de mshr_hcmrecruitingrequestentity | Identificador único generado por el sistema de la solicitud de contratación relacionada. |
| **Id. de nivel de formación**<br>mshr_educationlevelid<br>*Cadena* | Escribir una vez<br>Obligatorio | El nivel educativo requerido. |
| **Valor de id. de nivel de formación**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: entidad mshr_hcmeducationlevelentityid de mshr_hcmeducationlevelentity | Identificador único generado por el sistema del nivel de formación requerido. |
| **Descripción del nivel de formación**<br>mshr_educationleveldescription<br>*Cadena* | Solo lectura<br>Obligatorio | Descripción del nivel requerido para la aptitud. |
| **Id. de disciplina de formación**<br>mshr_educationdisciplinedescription<br>*Cadena* | Escribir una vez<br>Obligatorio | Ámbito de la disciplina de formación. |
| **Valor de id. de disciplina de formación**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmeducationdisciplineentityid de mshr_hcmeducationdisciplineentity | Identificador único generado por el sistema del ámbito de la disciplina de formación. |
| **Descripción de la disciplina de formación**<br>mshr_educationdisciplinedescription<br>Cadena | Solo lectura<br>Obligatorio | Descripción del ámbito de la disciplina de formación. |
| **Id. de área de datos**<br>mshr_dataareaid<br>*Cadena* | Leer/Escribir<br>Opcional | Especifica la entidad jurídica (empresa).|
| **Valor de id. de área de datos**<br>_mshr_dataareaid_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: entidad cdm_companyid of cdm_company | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa). |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Concatenación del valor de la solicitud de contratación, el id. de nivel de formación y el id, de disciplina de formación como otro método para identificar de forma única el registro. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]