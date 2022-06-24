---
title: Formación de la persona
description: Este artículo describe la entidad Formación de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0fbbb467852d2aeb070c7732c9aa3108fd504de0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893914"
---
# <a name="person-education"></a>Formación de la persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad Formación de la persona para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpersoneducationentity

## <a name="description"></a>Descripción

Esta entidad contiene el historial educativo de la persona candidata. La formación está vinculada al registro de la persona, lo que permite asociarla a cualquier otro rol creado para la persona, además del registro de candidato (trabajador, contratista, etc.).

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_creditbasis": Int,
    "mshr_creditscompleted": Decimal,
    "mshr_creditsearned": Decimal,
    "mshr_creditsneeded": Decimal,
    "mshr_description": "String",
    "mshr_duration": Decimal,
    "mshr_durationunit": Int,
    "mshr_educationdisciplineid": "String",
    "mshr_educationinstitutionid": "String",
    "mshr_educationlevelid": "String",
    "mshr_enddate": "Date",
    "mshr_gradepointaverage": Decimal,
    "mshr_gradescale": "String",
    "mshr_notes": "String",
    "mshr_secondaryemphasis": "String",
    "mshr_startdate": "Date",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_educationdiscipline_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_educationinstitution_id_value": "Guid",
    "_mshr_fk_educationlevel_id_value": "Guid",
    "mshr_hcmpersoneducationentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de formación de la persona**<br>mshr_hcmpersoneducationentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema del registro de entidad de formación de la persona. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | Identificador único del registro de parte (persona) para el candidato. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema para el registro de persona del candidato. |
| **Base de créditos**<br>mshr_creditbasis<br>*Conjunto de opciones mshr_hcmeducationcreditbasis* | Leer/Escribir<br>Opcional | Base de créditos del título educativo. |
| **Créditos completados**<br>mshr_creditscompleted<br>*Decimal* | Leer/Escribir<br>Opcional | Número de créditos completados para la formación. |
| **Créditos obtenidos**<br>mshr_creditsearned<br>*Decimal* | Leer/Escribir<br>Opcional | Número de créditos obtenidos por el expediente educativo de un título en curso. |
| **Créditos necesarios**<br>mshr_creditsneeded<br>*Decimal* | Leer/Escribir<br>Opcional | Número de créditos necesarios para un título en curso. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción del título del candidato. |
| **Id. de nivel de formación**<br>mshr_educationlevelid<br>*Cadena* | Leer/Escribir<br>Opcional | Id. del nivel educativo. | 
| **Valor de id. de nivel educativo**<br>_mshr_fk_educationlevel_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmeducationdegreeentityid de la entidad mshr_hcmeducationdegreeentity | Identificador generado por el sistema para el expediente del título educativo. Este identificador proporciona los títulos y niveles educativos definidos para la organización. |
| **Id. de disciplina de formación**<br>mshr_educationdisciplineid<br>*Cadena* | Leer/Escribir<br>Obligatorio<br>Clave externa: EducationDiscipline | Id. de la disciplina de formación. |
| **Valor de id. de disciplina de formación**<br>_mshr_fk_educationdiscipline_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmeducationdisciplineentityid de mshr_hcmeducationdisciplineentity | Identificador único generado por el sistema para la disciplina de formación del registro de formación. |
| **Énfasis secundario**<br>mshr_secondaryemphasis<br>*Cadena* | Leer/Escribir<br>Opcional | Énfasis secundario del título obtenido. |
| **Id. de institución educativa**<br>mshr_educationinstitutionid<br>*Cadena* | Leer/Escribir<br>Opcional | Id. de la institución educativa a la que asistió. |
| **Valor de id. de institución educativa**<br>_mshr_fk_educationinstitution_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmeducationinstitutionentityid de mshr_hcmeducationinstitutionentity | Identificador generado por el sistema para la institución educativa. |
| **Fecha inicial**<br>mshr_startdate<br>*Fecha y hora* | Leer/Escribir<br>Opcional | Fecha de inicio de la formación para el título obtenido. |
| **Fecha final**<br>mshr_enddate<br>*Fecha y hora* | Leer/Escribir<br>Obligatorio | Fecha de emisión de la credencial. |
| **Duración**<br>mshr_duration<br>*Decimal* | Leer/Escribir<br>Opcional | Duración del registro de formación. |
| **Unidad de duración**<br>mshr_durationunit<br>*Conjunto de opciones mshr_periodunit* | Leer/Escribir<br>Opcional | Unidad de tiempo asociada con la duración del registro de formación. |
| **Nota media**<br>mshr_gradepointaverage<br>*Decimal* | Leer/Escribir<br>Opcional | Nota media obtenida para el título. |
| **Escala de calificaciones**<br>mshr_gradescale<br>*Cadena* | Leer/Escribir<br>Opcional | Escala usada para la nota media. |
| **Notas**<br>mshr_notes<br>*Cadena* | Leer/Escribir<br>Opcional | Notas para el técnico de selección de personal o el responsable de contratación. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Campo utilizado como otro identificador principal del registro de entidad. Combinación de número de parte, id. de disciplina de formación, id. de institución educativa e id de nivel de formación. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
