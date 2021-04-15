---
title: Ubicación de la solicitud de contratación
description: Este tema describe la entidad Ubicación de solicitud de contratación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: f22926292690cb23d9d19cf3887a005b71d44c8d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5789669"
---
# <a name="recruiting-request-location"></a>Ubicación de la solicitud de contratación

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Ubicación de solicitud de contratación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmrecruitingrequestlocationentity

### <a name="description"></a>Descripción

La lista de ubicaciones definidas como ubicaciones en las que los empleados trabajarán tras su contratación. Son ubicaciones creadas en entidades jurídicas.

### <a name="json-representation"></a>Representación JSON

```
{
    "mshr_recruitingrequestlocationid": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_telephone": "String",
    "mshr_email": "String",
    "mshr_internetaddress": "String",
    "_mshr_dataareaid_id_value": "Guid",
    "mshr_dataareaid": "String",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmrecruitingrequestlocationentityid": "Guid"
}
```

### <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de ubicación**<br>mshr_locationid<br>*Cadena* | Escribir una vez<br>Obligatorio | Identificador de la ubicación de contratación generado por el sistema y legible para el usuario. |
| **Ubicación de la solicitud de contratación**<br>mshr_recruitingrequestlocationid<br>*Cadena* | Escribir una vez<br>Obligatorio | Identificador único definido por el usuario para la ubicación de contratación. |
| **Id. de entidad Ubicación de solicitud de contratación**<br>mshr_hcmrecruitingrequestlocationentityid<br>*GUID* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro Ubicación de solicitud de contratación. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Obligatorio | Descripción de la ubicación. |
| **Id. de país o región**<br>mshr_countryregionid<br>*Cadena* | Solo lectura<br>Opcional | Especifica el país o la región donde el candidato tiene la ciudadanía. |
| **Valor de id. de país o región**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_logisticaddresscountryregionentityid de mshr_logisticsaddresscountryregionentity | Identificador único del país o región de la dirección generado por el sistema. |
| **ZipCode**<br>mshr_zipcode<br>*Cadena* | Solo lectura<br>Opcional | Código postal. |
| **Calle**<br>mshr_street<br>*Cadena* | Solo lectura<br>Opcional | Dirección postal. |
| **Ciudad**<br>mshr_city<br>*Cadena* | Solo lectura<br>Opcional | Ciudad. |
| **Estado o provincia**<br>mshr_state<br>*Cadena* | Solo lectura<br>Opcional | Comunidad autónoma o provincia. |
| **Provincia**<br>mshr_county<br>*Cadena* | Solo lectura<br>Opcional | Provincia. |
| **Teléfono**<br>mshr_telephone<br>*Cadena* | Leer/Escribir<br>Opcional | Número de teléfono de la ubicación. |
| **Correo**<br>mshr_email<br>*Cadena* | Leer/Escribir<br>Opcional | Dirección de correo electrónico. |
| **Dirección de Internet**<br>mshr_internetaddress<br>*Cadena* | Leer/Escribir<br>Opcional | URL del sitio web de la ubicación. |
| **Id. de área de datos**<br>mshr_dataareaid<br>*Cadena* | Leer/Escribir<br>Opcional | Especifica la entidad jurídica (empresa). |
| **Valor de id. de área de datos**<br>_mshr_dataareaid_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: entidad cdm_companyid of cdm_company | Valor GUID generado por el sistema que identifica a la entidad jurídica (empresa). |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]