---
title: Nivel de evaluación
description: Este artículo describe la entidad Nivel de calificación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: dcd366632456c186eca9682d79a0c8690772e8bc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893885"
---
# <a name="rating-level"></a>Nivel de evaluación


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad Nivel de calificación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmratinglevelentity

## <a name="description"></a>Descripción

Esta entidad proporciona los niveles de calificación disponibles para las aptitudes. Los niveles de calificación se aplican a todas las entidades jurídicas.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_description": "String",
    "mshr_factor": Int,
    "mshr_note": "String",
    "mshr_ratinglevelid": "String",
    "mshr_ratingmodelid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_ratingmodelentity_id_value": "Guid",
    "mshr_hcmratinglevelentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de nivel de calificación**<br>mshr_hcmratinglevelentityid<br>*GUID* | Solo lectura<br>Obligatorio<br>Generado por el sistema | El identificador único generado por el sistema para el nivel. |
| **Id. de nivel de calificación**<br>mshr_ratinglevelid<br>*Cadena* | Leer/Escribir<br>Obligatorio | Identificador único legible por el usuario para el nivel. |
| **Id. de modelo de calificación**<br>mshr_ratingmodelid<br>*Cadena* | Leer/Escribir<br>Obligatorio | El modelo de calificación al que pertenece el nivel de calificación. |
| **Id. de entidad de modelo de calificación**<br>_mshr_fk_ratingmodelentity_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmratingmodelentityid de mshr_hcmratingmodelentity | El identificador generado por el sistema para el modelo de calificación al que pertenece el nivel de calificación. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Obligatorio | La descripción del nivel de calificación. |
| **Factor**<br>mshr_factor<br>*Entero* | Leer/Escribir<br>Obligatorio | Factor para el nivel de calificación. Cuando se comparan elementos con un número diferente de niveles de calificación, el factor se emplea para normalizar puntuaciones. El valor debe ser un número entero entre 0 y 9. |
| **Nota**<br>mshr_note<br>*Cadena* | Leer/Escribir<br>Opcional | Las notas asociadas al nivel de calificación. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Campo que se utilizará como identificador principal del registro de entidad. Combinación del id. de nivel de calificación y el id. de modelo de calificación. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
