---
title: Puesto de solicitud de contratación
description: Este tema describe la entidad Puesto de solicitud de contratación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 4892dc0801a47ab7c219df00b997fa469f56b7fc
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464703"
---
# <a name="recruiting-request-position"></a>Puesto de solicitud de contratación

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Puesto de solicitud de contratación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmrecruitingrequestpositionentity

### <a name="description"></a>Descripción

Describe el puesto (o puestos a cubrir) que se van a cubrir para una solicitud de contratación. Es opcional agregar un puesto a la solicitud de contratación. Las propiedades del puesto son de solo lectura, ya que no deben ser diferentes en la solicitud de contratación que en el registro maestro del puesto. Si es necesario cambiar las propiedades, debe hacerlo en el registro maestro del puesto antes de agregar el puesto a la solicitud de contratación.

### <a name="json-representation"></a>Representación JSON
```json
{
    "mshr_recruitingrequestid": "String",
    "mshr_positionid": "String",
    "mshr_description": "String",
    "mshr_positiontypeid": "String",
    "mshr_status": Int,
    "mshr_departmentnumber": "String",
    "mshr_reportstopositionid": "String",
    "mshr_reportstopersonnelnumber": "String",
    "mshr_financialdimension": "String",
    "mshr_dataareaid": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_recruitingrequest_id_value": "Guid",
    "_mshr_fk_position_id_value": "Guid",
    "_mshr_fk_positiontype_id_value": "Guid",
    "_mshr_fk_department_id_value": "Guid",
    "_mshr_fk_reportstoposition_id_value": "Guid",
    "_mshr_fk_reportstoworker_id_value": "Guid",
    "mshr_hcmrecruitingrequestpositionentityid": "Guid"
}
```

### <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad Puesto de solicitud de contratación**<br>mshr_hcmrecruitingrequestpositionentityid<br>*GUID* | Solo lectura<br>Obligatorio |    Identificador generado por el sistema del registro de puesto de solicitud de contratación. |
| **Id. de solicitud de contratación**<br>mshr_recruitingrequestid<br>*Cadena* | Escribir una vez<br>Obligatorio | Identificador único legible por el usuario de la solicitud de contratación. |
| **Valor de id. de solicitud de contratación**<br>_mshr_fk_recruitingrequest_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmrecruitingrequestentityid de la entidad mshr_hcmrecruitingrequestentity | Identificador generado por el sistema de la solicitud de contratación a la que está asignado el puesto. |
| **Id. de puesto**<br>mshr_positionid<br>*Cadena* | Escribir una vez<br>Obligatorio | Identificador único legible por el usuario del puesto. |
| **Valor de id. de posición**<br>_mshr_fk_position_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmpositionv2entityid de la entidad mshr_hcmpositionv2entity | Identificador generado por el sistema para el puesto. |
| **Descripción**<br>mshr_description<br>*Cadena* | Solo lectura<br>Obligatorio | Descripción del puesto. |
| **Id. de tipo de puesto**<br>mshr_positiontypeid<br>*Cadena* | Solo lectura<br>Opcional | Identificador único legible por el usuario del tipo de puesto. |
| **Valor de id. de tipo de puesto**<br>_mshr_fk_positiontype_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmpositiontypeentityid de la entidad mshr_hcmpositiontypeentity | Identificador único generado por el sistema del tipo de puesto. |
| **Estado**<br>mshr_status<br>Conjunto de opciones *RecruitingRequestPositionStatus* | Leer/Escribir<br>Obligatorio | Estado del puesto para la solicitud de contratación. |
| **Número del departamento**<br>mshr_departmentnumber<br>*Cadena* | Solo lectura<br>Opcional<br> | Número de departamento del puesto. |
| **Valor de id. de departamento**<br>_mshr_fk_department_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_omdepartmententityid de la entidad mshr_omdepartmententity | Identificador único generado por el sistema del departamento del puesto. |
| **Id. de Informa al puesto**<br>mshr_reportstopositionid<br>*Cadena* | Solo lectura<br>Obligatorio | Id. legible por el usuario del puesto al que informa el puesto contratado en la jerarquía organizativa. |
| **Valor de id. de Informa al puesto**<br>_mshr_fk_reportstoposition_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmpositionv2entityid de la entidad mshr_hcmpositionv2entity | Id. generado por el sistema del puesto al que informa el puesto contratado. |
| **Informa al número de personal**<br>mshr_reportstopersonnelnumber<br>*Cadena* | Solo lectura<br>Obligatorio | El id. del trabajador al que informará el candidato contratado. |
| **Valor de id. de Informa al trabajador**<br>_mshr_fk_reportstoworker_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmworkerbaseentityid de la entidad mshr_hcmworkerbaseentity | Id. generado por el sistema del trabajador al que informará el candidato contratado. |
| **Dimensión financiera**<br>mshr_financialdimension<br>*Cadena* | Solo lectura<br>Opcional | La dimensión financiera (por ejemplo, centro de coste) asignada al puesto. La dimensión financiera se asigna a cada puesto por entidad jurídica. Los centros de coste que se definen en las dimensiones son accesibles a través de la entidad mshr_dimattributeomcostcenterentity. |
| **Id. de área de datos**<br>mshr_dataareaid<br>*Cadena* | Leer/Escribir<br>Opcional | Especifica la entidad jurídica (empresa) para el puesto de la solicitud de contratación. |
| **Valor de id. de área de datos**<br>_mshr_dataareaid_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: entidad cdm_companyid of cdm_company | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa) para el puesto de la solicitud de contratación. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Concatenación del valor de la solicitud de contratación y el id. de puesto como otro método para identificar de forma única el registro. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]