---
title: Número de identificación de la persona
description: Este tema describe la entidad Número de identificación de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: a8fa924898472302e67dd4e32251ca0c94da0ea9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798090"
---
# <a name="person-identification-number"></a>Número de identificación de la persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Número de identificación de la persona para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpersonidentificationnumberentity

## <a name="description"></a>Descripción

Esta entidad describe los números de identificación para el candidato. Permite al consumidor de API escribir en el registro del candidato números de identificación, como números del seguro social o números de pasaporte. Los números de identificación aparecen en el registro del trabajador, pero no en el registro del candidato. Una aplicación de integración puede escribir los valores en la base de datos de Human Resources, pero los números no serán visibles en Human Resources hasta que se cree el registro de trabajador del candidato.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_entrytype": "String",
    "mshr_description": "String",
    "mshr_expirationdate": "Datetime",
    "mshr_isprimary": Int,
    "mshr_identificationnumber": "String",
    "mshr_partynumber": "String",
    "mshr_identificationtypeid": "String",
    "mshr_issuingagencyid": "String",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_issuingagency_id_value": "Guid",
    "_mshr_fk_identificationtype_id_value": "Guid",
    "mshr_hcmpersonidentificationnumberentityid": "Guid",
    "mshr_issueddate": "Datetime"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de la entidad Número de identificación de la persona**<br>mshr_hcmpersonidentificationnumberentityid<br>*GUID* | Solo lectura<br>Obligatorio<br>Generado por el sistema | Identificador principal único del registro de número de identificación de la persona. |
| **Tipo de entrada**<br>mshr_entrytype<br>*Cadena* | Leer/Escribir<br>Opcional | Valor libre para hacer referencia al tipo de entrada del número de identificación. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Opcional | La descripción del número de identificación. |
| **Fecha de vencimiento**<br>mshr_expirationdate<br>*Fecha y hora* | Leer/Escribir<br>Opcional | La fecha en la que caduca el número de identificación o el documento asociado. |
| **Es principal**<br>mshr_isprimary<br>*Conjunto de opciones mshr_noyes* | Leer/Escribir<br>Opcional | Define si el número de identificación es el registro principal de la persona para este tipo de identificación. |
| **Número de identificación**<br>mshr_identificationnumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | El número de identificación. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | El identificador de la parte (persona) que posee el número de identificación. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de la entidad mshr_dirpersonentity | Identificador único de la parte (persona). |
| **Id. de tipo de identificación**<br>mshr_identificationtypeid<br>*Cadena* | Leer/Escribir<br>Obligatorio | Tipo del número de identificación. |
| **Valor de id. de tipo de identificación**<br>_mshr_fk_identificationtype_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmidentificationtypeentityid de la entidad mshr_hcmidentificationtypeentity | Identificador único generado por el sistema del tipo de identificación. |
| **Id. de agencia emisora**<br>mshr_issuingagencyid<br>*Cadena* | Leer/Escribir<br>Opcional | Agencia u organización que emite el número de identificación. |
| **Valor de id. de agencia emisora**<br>_mshr_fk_issuingagency_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_hcmissuingagencyentityid de la entidad mshr_hcmissuingagencyentity | Identificador único generado por el sistema de la agencia que emite el número de identificación. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Campo que se utilizará como identificador principal del registro de entidad. Combinación del número de parte, el id. de tipo de identificación y el número de identificación. |
| **Fecha de emisión**<br>mshr_issuedate<br>*Fecha* | Leer/Escribir<br>Opcional | Fecha de emisión del número de identificación. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]