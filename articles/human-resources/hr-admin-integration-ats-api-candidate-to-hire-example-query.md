---
title: Consulta de ejemplo para candidato a contratar
description: Este artículo proporciona una consulta de ejemplo para la entidad Candidato a contratar en Dynamics 365 Human Resources.
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
ms.openlocfilehash: 2dd744665d4f0b6c64f4ee45a01c237081018514
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848354"
---
# <a name="example-query-for-candidate-to-hire"></a>Consulta de ejemplo para candidato a contratar


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo proporciona una consulta de ejemplo para la entidad Candidato a contratar en Dynamics 365 Human Resources.

Este artículo proporciona un ejemplo que demuestra cómo puede utilizar *inserciones profundas* para crear todos los detalles de un nuevo registro de candidato en una sola operación de API. Para obtener más información sobre inserciones profundas, consulte [Crear registros de entidad relacionados en una operación](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).

La entidad **mshr_hcmcandidatetohireentity** es única debido a su relación con la entidad **mshr_dirpersonentity**. Muchas de las propiedades de **mshr_hcmcandidatetohireentity** (por ejemplo, **mshr_firstname**, **mshr_lastname** y **mshr_birthdate**) se derivan del registro **mshr_dirpersonentity**. Si publica un nuevo registro de candidato en **mshr_hcmcandidatetohireentity** sin utilizar inserciones profundas, puede definir valores para estas propiedades directamente en el registro **mshr_hcmcandidatetohireentity**. El registro **mshr_dirpersonentity** asociado se crea implícitamente con los valores definidos para las propiedades. Luego, puede crear cualquier otro registro de entidad relacionado (como habilidades o educación) como llamadas API separadas.

Sin embargo, si desea utilizar inserciones profundas para crear todas las entidades relacionadas en una operación, las propiedades específicas de la entidad **mshr_dirpersonentity** debe definirse en ese nivel anidado de la operación.

Este ejemplo muestra cómo puede crear un registro de candidato, el registro de la persona asociada y las habilidades y la educación de la persona en tres niveles anidados, utilizando inserciones profundas en una única operación de API.

> [!NOTE]
> El ejemplo no incluye todas las propiedades de cada una de las entidades API. Está simplificado a efectos de demostración.

**Solicitud**

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

**Respuesta**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
