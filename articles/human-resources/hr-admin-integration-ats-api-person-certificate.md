---
title: Certificado de la persona
description: Este artículo describe la entidad Certificado de la persona para Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/15/2022
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
ms.openlocfilehash: 1f9d5a8c83d9714a4d10dec16e66ab87b794b074
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887327"
---
# <a name="person-certificate"></a>Certificado de la persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad Certificado de la persona para Dynamics 365 Human Resources.

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

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Description |
| --- | --- | --- |
| **Id. de tipo de certificado**<br>mshr_certificatetypeid<br>*Cadena* | Leer/Escribir<br>Obligatorio |  Identificador del tipo de certificado definido en Human Resources. |
| **Fecha inicial**<br>mshr_startdate<br>*Fecha y hora* | Leer/Escribir<br>Obligatorio | La fecha en la que se emitió el certificado. |
| **Fecha final**<br>mshr_enddate<br>*Fecha y hora* | Leer/Escribir<br>Opcional | La fecha en la que expirará el certificado. |
| **Notas**<br>mshr_notes<br>*Cadena* | Leer/Escribir<br>Opcional | Notas para los técnicos de selección de personal y los responsables de contratación. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | El id. de entidad (persona) del candidato. |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio |  Campo que se utilizará como identificador principal del registro de entidad. Combinación de número de entidad, id. de tipo de certificado y fecha de inicio. |
| **Valor de id. de tipo de certificado**<br>_mshr_fk_certificatetype_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmcertificatetypeentityid de mshr_hcmcertificatetypeentity | Identificador único generado por el sistema del tipo de certificado de la entidad asociada. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema de registro de entidad (persona) de la parte. |
| **Id. de entidad de certificado de la persona**<br>mshr_hcmpersoncertificateentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro de entidad de certificado de la persona. |




## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
