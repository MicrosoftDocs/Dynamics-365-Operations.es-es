---
title: Certificado de la persona
description: Este tema describe la entidad Certificado de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5cdd742d6d36ccd7136f95e416507ed6e5e5a75a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055205"
---
# <a name="person-certificate"></a>Certificado de la persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Certificado de la persona para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpersoncertificateentity

## <a name="description"></a>Descripción

Esta entidad describe los certificados profesionales de un candidato.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_certificatetypeid": "String",
    "mshr_startdate": "Date",
    "mshr_enddate": "Date",
    "mshr_notes": "String",
    "mshr_partynumber": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_certificatetype_id_value": "Guid",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersoncertificateentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de certificado de la persona**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro de entidad de certificado de la persona. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | El id. de entidad (persona) del candidato. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema de registro de entidad (persona) de la parte. |
| **Id. de tipo de certificado**<br>mshr_certificatetypeid<br>*Cadena* | Leer/Escribir<br>Obligatorio |  Identificador del tipo de certificado definido en Human Resources. |
| **Valor de id. de tipo de certificado**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmcertificatetypeentityid de mshr_hcmcertificatetypeentity | Identificador único generado por el sistema del tipo de certificado de la entidad asociada. |
| **Fecha inicial**<br>mshr_startdate<br>*Fecha y hora* | Leer/Escribir<br>Obligatorio | La fecha en la que se emitió el certificado. |
| **Fecha final**<br>mshr_enddate<br>*Fecha y hora* | Leer/Escribir<br>Opcional | La fecha en la que expirará el certificado. |
| **Notas**<br>mshr_notes<br>*Cadena* | Leer/Escribir<br>Opcional | Notas para los técnicos de selección de personal y los responsables de contratación. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio |  Campo que se utilizará como identificador principal del registro de entidad. Combinación de número de entidad, id. de tipo de certificado y fecha de inicio. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]