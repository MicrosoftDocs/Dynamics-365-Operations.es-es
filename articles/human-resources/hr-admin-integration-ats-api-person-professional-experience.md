---
title: Experiencia profesional de la persona
description: Este tema describe la entidad Experiencia profesional de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 51dd993e2d43174e96c062e142021cc0f6e3a288
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125290"
---
# <a name="person-professional-experience"></a>Experiencia profesional de la persona

Este tema describe la entidad Experiencia profesional de la persona para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpersonprofessionalexperienceentity

## <a name="description"></a>Descripción

Esta entidad describe la experiencia profesional o el historial laboral de un candidato.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_employerposition": "String",
    "mshr_startdate": "Date",
    "mshr_allowcontactemployer": Int,
    "mshr_employerlocation": "String",
    "mshr_employername": "String",
    "mshr_enddate": "Date",
    "mshr_note": "String",
    "mshr_phone": "String",
    "mshr_url": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonprofessionalexperienceentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de la entidad Experiencia profesional de la persona**<br>mshr_hcmpersonprofessionalexperienceentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro de entidad. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | Identificador único del registro de persona para el candidato. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema del registro de entidad de la persona. |
| **Puesto de la empresa**<br>mshr_employerposition<br>*Cadena* | Leer/Escribir<br>Obligatorio | El cargo que ocupaba el candidato en su empleo. |
| **Nombre de la empresa**<br>mshr_employername<br>*Cadena* | Leer/Escribir<br>Obligatorio | Nombre de la empresa. |
| **Ubicación de la empresa**<br>mshr_employerlocation<br>*Cadena* | Leer/Escribir<br>Opcional | Ubicación de la empresa. Longitud máxima: 60. No se ha definido ni se requiere ningún formato específico. |
| **Teléfono**<br>mshr_phone<br>*Cadena* | Leer/Escribir<br>Opcional | Número de teléfono de la empresa. |
| **URL**<br>mshr_url<br>*Cadena* | Leer/Escribir<br>Opcional | URL del sitio web de la empresa. |
| **Fecha inicial**<br>mshr_startdate<br>*Fecha y hora* | Leer/Escribir<br>Obligatorio | La fecha de inicio del empleo del candidato. |
| **Fecha final**<br>mshr_enddate<br>*Fecha y hora* | Leer/Escribir<br>Opcional | La fecha de finalización del empleo del candidato, o nulo si el candidato sigue trabajando aquí. |
| **Permitir contacto con empresa**<br>mshr_allowcontactemployer<br>*Conjunto de opciones mshr_hrmblankyesno* | Leer/Escribir<br>Opcional | Indica si el candidato permite ponerse en contacto con su empresa anterior. |
| **Notas**<br>mshr_note<br>*Cadena* | Leer/Escribir<br>Opcional | Notas para el técnico de selección de personal o el responsable de contratación. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Campo utilizado como identificador principal del registro de entidad. Combinación de número de parte, fecha de inicio, puesto de la empresa empleador y nombre de la empresa. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

