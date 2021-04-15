---
title: Solicitud de contratación
description: Este tema describe la entidad Solicitud de contratación para Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: dd2f2fc74261c6eea3033567fe020c4e03c60637
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805187"
---
# <a name="recruiting-request"></a>Solicitud de contratación

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Solicitud de contratación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmrecruitingrequestentity

### <a name="description"></a>Descripción

Describe una solicitud de contratación para un trabajo.

### <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_hiringmanagerpersonnelnumber": "String",
    "mshr_recruiterpartynumber": "String",
    "mshr_status": Int,
    "mshr_description": "String",
    "mshr_recruitingrequestlocationid": "String",
    "mshr_comments": "String",
    "mshr_jobid": "String",
    "mshr_titleid": "String",
    "mshr_jobfunctionid": "String",
    "mshr_defaultfulltimeequivalency": Decimal,
    "mshr_regulatoryjobcategory": Int,
    "mshr_jobtypeid": "String",
    "mshr_exemptstatus": Int,
    "mshr_estimatedstartdate": "Date",
    "mshr_externaldescription": "String",
    "mshr_compensationlevelid": "String",
    "mshr_compensationlowthreshold": Decimal,
    "mshr_compensationcontrolpoint": Decimal,
    "mshr_compensationhighthreshold": Decimal,
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "_mshr_fk_hiringmanager_id_value": "Guid",
    "_mshr_fk_recruiter_id_value": "Guid",
    "_mshr_fk_job_id_value": "Guid",
    "_mshr_fk_title_id_value": "Guid",
    "_mshr_fk_jobtype_id_value": "Guid",
    "_mshr_fk_compensationlevel_id_value": "Guid",
    "mshr_hcmrecruitingrequestentityid": "Guid",
    "_mshr_fk_recruitingrequestlocation_id_value": “Guid”
}
```

### <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de solicitud de contratación**<br>mshr_recruitingrequestid<br>*Cadena* | Solo lectura<br>Obligatorio<br>Generado por el sistema | Identificador único legible por el usuario para la solicitud que se muestra en la aplicación de recursos humanos. Secuencia numérica. |
| **Id. de entidad Solicitud de contratación**<br>mshr_hcmrecruitingrequestentityid<br>*GUID* | Solo lectura<br>Obligatorio<br>Generado por el sistema | Valor GUID generado por el sistema para identificar de forma única la solicitud de contratación. |
| **Id. de área de datos**<br>mshr_dataareaid<br>*Cadena* | Leer/Escribir<br>Opcional<br> | Especifica la entidad jurídica (empresa) para la solicitud de contratación. |
| **Valor de id. de área de datos**<br>_mshr_dataareaid_id_value<br>*GUID*<br> | Solo lectura<br>Opcional<br>Clave externa: entidad cdm_companyid of cdm_company | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa) para la solicitud de contratación. |
| **Número de personal del responsable de contratación**<br>mshr_hiringmanagerpersonnelnumber<br>*Cadena* | Leer/Escribir<br>Opcional | El número de personal del responsable de contratación asociado con esta solicitud de contratación. |
| **Valor de id. del responsable de contratación**<br>_mshr_fk_hiringmanager_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmworkerbaseentityid de la entidad mshr_hcmworkerbaseentity | Valor GUID generado por el sistema para identificar al responsable asociado con la solicitud de contratación. |
| **Número de parte de técnico de selección de personal**<br>mshr_recruiterpartynumber<br>*Cadena* | Leer/Escribir<br>Opcional | El número de persona (parte) del técnico de selección de personal seleccionado para la solicitud. |
| **Valor de id. de técnico de selección de personal**<br>_mshr_fk_recruiter_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_dirpersonentityid de la entidad mshr_dirpersonentity | Valor GUID generado por el sistema para identificar al técnico de selección de personal asociado con la solicitud de contratación. |
| **Estado**<br>mshr_status<br>Conjunto de opciones *RecruitingRequestStatus* | Leer/Escribir<br>Obligatorio<br> | Indica el estado de la solicitud de contratación. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Obligatorio | Describe la solicitud. |
| **Id. de ubicación de la solicitud de contratación**<br>mshr_recruitingrequestlocationid<br>*Cadena* | Leer/Escribir<br>Opcional | Identificador único legible por el usuario de la ubicación del trabajo asociada con esta solicitud. |
| **Valor de id. de ubicación de contratación**<br>_mshr_fk_recruitinglocation_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmrecruitingrequestlocationentityid de la entidad mshr_hcmrecruitingrequestlocationentity | Valor GUID generado por el sistema para identificar la ubicación de solicitud de contratación seleccionada con la solicitud. |
| **Comentarios**<br>mshr_comments<br>*Cadena* | Leer/Escribir<br>Opcional | Comentarios sobre la solicitud de uso para responsables de contratación y técnicos de selección de personal. |
| **Id. de trabajo**<br>mshr_jobid<br>*Cadena* | Escribir una vez<br>Obligatorio |   Identificador único legible por el usuario del trabajo compartido por todos los puestos asociados con esta solicitud. |
| **Valor de id. de trabajo**<br>_mshr_fk_job_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmjobentityid de la entidad mshr_hcmjobentity | Identificador único generado por el sistema del trabajo compartido por todos los puestos asociados con la solicitud de contratación. |
| **Id. de título**<br>mshr_titleid<br>*Cadena* | Solo lectura<br>Obligatorio | Identificador único legible por el usuario del puesto asociado con esta solicitud. |
| **Valor de id. de título**<br>_mshr_fk_title_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmtitleid de la entidad mshr_hcmtitleentity | Identificador único generado por el sistema del puesto seleccionado para la solicitud de contratación. |
| **Id. de puesto**<br>mshr_jobfunctionid<br>*Cadena* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_jobfunctionid de la entidad mshr_hcmjobfunctionentity | Identificador único legible por el usuario del puesto asociado con esta solicitud. |
| **Equivalente de jornada completa predeterminada**<br>mshr_defaultfulltimeequivalency<br>*Doble* | Solo lectura<br>Obligatorio | Valor equivalente a tiempo completo para el trabajo, donde 1.0 representa a un trabajador a tiempo completo. |
| **Categoría de trabajo reglamentaria**<br>mshr_regulatoryjobcategory<br>Conjunto de opciones *RegulatoryJobCategory* | Solo lectura<br>Opcional | La categoría de trabajo EEO del puesto seleccionado para el trabajo. Valores válidos incluidos en el conjunto de opciones HcmRegulatoryJobCategory (mshr_hcmregulatoryjobcategory). |
| **Id. de tipo de trabajo**<br>mshr_jobtypeid<br>*Cadena* | Solo lectura<br>Opcional | Tipo del trabajo asociado al puesto. Los tipos de trabajo son valores definidos por el usuario, disponibles en la entidad mshr_hcmjobtypeentity. |
| **Valor de id. de tipo de trabajo**<br>_mshr_fk_jobtype_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmjobtypeentityid de mshr_hcmjobtypenentity | Identificador único generado por el sistema del tipo de trabajo asociado con el trabajo para la solicitud de contratación. |
| **Estado de exento**<br>mshr_exemptstatus<br>Conjunto de opciones *JobExemptStatus* | Solo lectura<br>Opcional | Estado de exención de FLSA según el tipo de trabajo. |
| **Fecha de inicio estimada**<br>mshr_estimatedstartdate<br>*Fecha* | Leer/Escribir<br>Obligatorio | Fecha estimada en que un candidato comenzaría a trabajar. |
| **Descripción externa**<br>mshr_externaldescription<br>*Cadena* | Leer/Escribir<br>Opcional | Descripción del trabajo/puesto para el candidato. | 
| **Umbral bajo de compensación**<br>mshr_compensationlowthreshold<br>*Doble* | Leer/Escribir<br>Opcional | Límite inferior del nivel de compensación. |
| **Punto de control de compensación**<br>mshr_compensationcontrolpoint<br>*Doble* | Leer/Escribir<br>Opcional | Punto de control para el nivel de compensación. |
| **Umbral alto de compensación**<br>mshr_compensationhighthreshold<br>*Doble* | Leer/Escribir<br>Opcional | Límite superior del nivel de compensación. |
| **Nivel de compensación**<br>mshr_compensationlevelid<br>*Cadena* | Leer/Escribir<br>Opcional | Nivel de compensación del trabajo. Se puede configurar un trabajo con múltiples niveles de compensación. Este atributo indica el nivel de compensación laboral seleccionado para esta solicitud. |
| **Id. de compensación laboral**<br>_mshr_fk_jobcompensation_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmjobcompensationentityid de la entidad mshr_hcmjobcompensationentity | Identificador único generado por el sistema para el nivel de compensación asociado con el trabajo de la solicitud de contratación. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
