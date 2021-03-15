---
title: Candidato a contratar
description: Este tema describe la entidad Candidato a contratar para Dynamics 365 Human Resources.
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
ms.openlocfilehash: eb16f9f46e3f5c58854ec06c3b89ec72dd7bae00
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125746"
---
# <a name="candidate-to-hire"></a>Candidato a contratar

Este tema describe la entidad Candidato a contratar para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmcandidatetohireentity

## <a name="description"></a>Descripción

Esta entidad proporciona detalles del candidato que se utilizan para crear un trabajador en Dynamics 365 Human Resources. Se utiliza para leer todos los registros de candidatos y crear registros de candidatos internos y externos, lo que le permite crear detalles personales para el nuevo candidato.

Cuando crea un registro de candidato externo que será un nuevo registro de persona en el sistema, no debe definir un número de parte (persona) si registra un nuevo registro de candidato. El nuevo registro de entidad de persona se crea con el nuevo registro de candidato.

Cuando crea un registro de candidato interno (un candidato para el puesto que ya tiene un registro de empleado en la empresa), defina el número de parte (persona) del registro que ya existe para la persona para la propiedad mshr_partynumber en el registro de candidato en lugar de definir la información personal (como nombre, sexo o fecha de nacimiento) que se usaría para crear un nuevo registro de persona.

## <a name="json-representation"></a>Representación JSON

```json
        {
            "mshr_candidateid": "String",
            "mshr_partynumber": "String",
            "mshr_partytype": "String",
            "mshr_recruitingrequestid": "String",
            "mshr_positionid": "String",
            "mshr_firstname": "String",
            "mshr_middlename": "String",
            "mshr_lastnameprefix": "String",
            "mshr_lastname": "String",
            "mshr_gender": Int,
            "mshr_birthdate": "Date",
            "mshr_citizenshipcountrycode": "String",
            "mshr_veteranstatusid": "String",
            "mshr_isdisabledveteran": Int,
            "mshr_availabilitydate": "Date",
            "mshr_iswillingtorelocate": Int,
            "mshr_comments": "String",
            "mshr_applicantintegrationresult": Int,
            "mshr_donothirereasoncodeid": "String",
            "mshr_dataareaid": "String",
            "_mshr_dataareaid_id_value": "Guid",
            "_mshr_fk_person_id_value": "Guid",
            "_mshr_fk_recruitingrequest_id_value": "Guid",
            "_mshr_fk_position_id_value": "Guid",
            "mshr_hcmcandidatetohireentityid": "Guid",
            "_mshr_fk_veteranstatus_id_value": "Guid",
            "_mshr_fk_reasoncode_id_value": "Guid",
            "mshr_militaryserviceenddate": "Guid",
            "mshr_militaryservicestartdate": "Guid"
        }
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de candidato a contratar**<br>mshr_hcmcandidatetohireentityid<br>GUID | Solo lectura<br>Obligatorio<br>Generado por el sistema | Identificador único generado por el sistema para el registro de entidad. |
| **Id. de candidato**<br>mshr_candidateid<br>Cadena | Solo lectura<br>Obligatorio<br>Generado por el sistema | Un identificador único para la entidad. |
| **Número de parte**<br>mshr_partynumber<br>Cadena | Solo lectura<br>Obligatorio | El número de parte (persona) del registro personal del candidato. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>GUID | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_direpersonentity | El identificador único generado por el sistema para el registro de parte (persona) del candidato. |
| **Tipo de parte**<br>mshr_partytype<br>Opción mshr_dirpartytype establecida | Solo lectura<br>Obligatorio | El tipo de parte del registro, como se define en el conjunto de opciones mshr_dirpartytype. Para esta entidad, el tipo siempre será “Persona”. |
| **Id. de solicitud de contratación**<br>mshr_recruitingrequestid<br>Cadena | Escribir una vez<br>Opcional | Referencias de la Solicitud de reclutamiento que rellena este candidato. |
| **Valor de id. de solicitud de contratación**<br>_mshr_fk_recruitingrequest_id_value<br>GUID | Leer/Escribir<br>Opcional<br>Clave externa: mshr_hcmrecruitingrequestentityid de mshr_hcmrecruitingrequestentity | El identificador único generado por el sistema para la solicitud de contratación que rellena el candidato. |
| **Id. de puesto**<br>mshr_positionid<br>Cadena | Leer/Escribir<br>Opcional | El id. del puesto para el que se está considerando al candidato. |
| **Valor de id. de posición**<br>_mshr_fk_position_if_value<br>GUID | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmpositionv2entityid de mshr_hcmpositionv2entity | Identificador generado por el sistema del puesto para el que se está considerando al candidato. |
| **Nombre**<br>mshr_firstname<br>Cadena | Leer/Escribir<br>Obligatorio | Nombre del candidato. |
| **Segundo nombre**<br>mshr_middlename<br>Cadena | Leer/Escribir<br>Opcional | Segundo nombre del candidato. |
| **Prefijo de apellido**<br>mshr_lastnameprefix<br>Cadena | Leer/Escribir<br>Opcional | Prefijo de apellido del candidato. |
| **Apellidos**<br>mshr_lastname<br>Cadena | Leer/Escribir<br>Opcional | Apellido del candidato. |
| **Género**<br>mshr_gender<br>Opción mshr_hcmpersongender establecida | Leer/Escribir<br>Opcional | El sexo del candidato. |
| **Fecha de nacimiento**<br>mshr_birthdate<br>Fecha y hora | Leer/Escribir<br>Opcional | La fecha de nacimiento del candidato. |
| **Código de país de ciudadanía**<br>mshr_citizenshipcountrycode<br>Cadena | Leer/Escribir<br>Opcional | Especifica el país donde el candidato tiene la ciudadanía. Los códigos de país válidos se encuentran en mshr_logisticaddresscountryregionentity. |
| **Id. de estado de veterano**<br>mshr_veteranstatusid<br>Cadena | Leer/Escribir<br>Opcional | Indica el estado de veterano del candidato. |
| **Valor de id. de estado de veterano**<br>_mshr_fk_veteranstatus_id_value<br>GUID | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmveteranstatusentityid de mshr_hcmveteranstatusentity | Identificador único generado por el sistema para el registro de entidad de estado de veterano. |
| **Fecha inicial del servicio militar**<br>mshr_militaryservicestartdate<br>Fecha y hora | Leer/Escribir<br>Opcional | La fecha de inicio del servicio militar del candidato. |
| **Fecha final del servicio militar**<br>mshr_militaryserviceenddate<br>Fecha y hora | Leer/Escribir<br>Opcional | La fecha de finalización del servicio militar del candidato. |
| **Es un excombatiente discapacitado**<br>mshr_isdisabledveteran<br>Opción mshr_noyes establecida | Leer/Escribir<br>Opcional | Indica si el candidato tiene deshabilitado el estado de veterano. |
| **Fecha de disponibilidad**<br>mshr_availabilitydate<br>Fecha y hora | Leer/Escribir<br>Opcional | La fecha más temprana en que el candidato estaría disponible para trabajar. |
| **Está dispuesto a reubicarse**<br>mshr_iswillingtorelocate<br>Opción mshr_noyes establecida | Leer/Escribir<br>Opcional | Indica si el candidato está dispuesto a reubicarse para el puesto. |
| **Comentarios**<br>mshr_comments<br>Cadena | Leer/Escribir<br>Opcional | Comentarios que utilizará el reclutador o el gerente de contratación. |
| **Resultado de integración de la aplicación**<br>mshr_applcantintegrationresult<br>Opción mshr_applicantintegrationresult establecida | Leer/Escribir<br>Obligatorio | El estado del candidato en el proceso de contratación relacionado con la integración. |
| **Id. de código de motivo de no contratar**<br>mshr_donothirereasoncodeid<br>Cadena | Leer/Escribir<br>Opcional | Un código de motivo que se proporciona opcionalmente cuando el estado (resultado de integración de la aplicación) se establece en “No contratado”. |
| **Valor de id. de código de motivo**<br>_mshr_fk_reasoncode_id_value<br>GUID | Solo lectura<br>Opcional<br>Clave externa: entidad mmshr_hcmreasoncodeentityid de mshr_hcmreasoncodeentity | Identificador único generado por el sistema para el código de motivo **No contratar**. |
| **Id. de área de datos**<br>mshr_dataareaid<br>Cadena | Leer/Escribir<br>Opcional |  Especifica la entidad jurídica (empresa). |
| **Valor de id. de área de datos**<br>_mshr_dataareaid_id_value<br>GUID | Solo lectura<br>Opcional<br>Clave externa: entidad cdm_companyid of cdm_company | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa). |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]