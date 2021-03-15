---
title: Aptitud de la persona
description: Este tema describe la entidad Aptitud de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: b6bcbbd1203f4e9e80f6c5264cf4d5ea7d0970fc
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126107"
---
# <a name="person-skill"></a>Aptitud de la persona

Este tema describe la entidad Aptitud de la persona para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpersonskillentity

## <a name="description"></a>Descripción

Esta entidad describe las aptitudes de un candidato.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_certifier": "String",
    "mshr_partynumber": "String",
    "mshr_levelid": "String",
    "mshr_ratinglevelexaminer": "String",
    "mshr_skillid": "String",
    "mshr_ratingid": "String",
    "mshr_leveltype": Int,
    "mshr_yearsofexperience": Decimal,
    "mshr_verified": Int,
    "mshr_leveldate": "Date",
    "mshr_primaryfield": "String",
    "_mshr_fk_certifier_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_ratinglevel_id_value": "Guid",
    "_mshr_fk_ratinglevelexaminer_id_value": "Guid",
    "_mshr_fk_skill_id_value": "Guid",
    "mshr_hcmpersonskillentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de aptitud de la persona**<br>mshr_hcmpersonskillentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro de entidad. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio |   Id. de registro de la parte (persona) asociada. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema de registro de entidad (persona) de la parte. |
| **Certificador**<br>mshr_certifier<br>*Cadena* | Leer/Escribir<br>Opcional | El número de personal del trabajador que certificó esta aptitud. |
| **Valor de id. del certificador**<br>_mshr_fk_certifier_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmworkerentityid de mshr_hcmworkerentity | Identificador único generado por el sistema del registro de trabajador para el trabajador que certificó la aptitud. |
| **Id. de aptitud**<br>mshr_skillid<br>*Cadena* | Leer/Escribir<br>Obligatorio | Identificador de la aptitud definida en Human Resources. |
| **Valor de id. de aptitud**<br>_mshr_fk_skill_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmskillentityid de mshr_hcmskillentity | El identificador generado por el sistema para la aptitud seleccionada. |
| **Años de experiencia**<br>mshr_yearsofexperience<br>*Decimal* | Leer/Escribir<br>Opcional | Los años de experiencia de esta aptitud que tiene el candidato. |
| **Id. de calificación**<br>mshr_ratingid<br>*Cadena* | Leer/Escribir<br>Obligatorio | Tipo de escala de calificación. Para esta entidad, el valor es **Aptitudes**. |
| **Tipo de nivel**<br>mshr_leveltype<br>*Conjunto de opciones mshr_hrmskillleveltype* | Leer/Escribir<br>Obligatorio | Una categorización de tipo para el nivel asignado a la aptitud. |
| **Id. de nivel**<br>mshr_levelid<br>*Cadena* | Leer/Escribir<br>Obligatorio | El id. del nivel de calificación que tiene el candidato para esta aptitud. |
| **Valor de id. de nivel de calificación**<br>_mshr_fk_ratinglevel_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmratinglevelentityid de mshr_hcmratinglevelentity | El identificador generado por el sistema para el nivel de calificación. |
| **Fecha de nivel**<br>mshr_leveldate<br>*Fecha y hora* | Leer/Escribir<br>Obligatorio | La fecha en la que se calificó al candidato en la aptitud. |
| **Examinador de nivel de calificación**<br>mshr_ratinglevelexaminer<br>*Cadena* | Leer/Escribir<br>Opcional | El número de personal del trabajador que calificó al candidato. |
| **Valor de id. de examinador de nivel de calificación**<br>_mshr_fk_ratinglevelexaminer_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmworkerentityid de mshr_hcmworkerentity | Identificador generado por el sistema del trabajador que examinó el nivel que tenía el candidato de la aptitud. |
| **Comprobada**<br>mshr_verified<br>*Conjunto de opciones mshr_noyes* | Leer/Escribir<br>Obligatorio | Indica si se ha comprobado el nivel de aptitud evaluado. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Campo que se utilizará como identificador principal del registro de entidad. Combinación de número de parte, tipo de nivel, id. de aptitud y fecha de nivel. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]