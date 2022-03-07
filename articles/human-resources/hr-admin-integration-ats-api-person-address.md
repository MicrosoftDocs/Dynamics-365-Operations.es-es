---
title: Dirección de la persona
description: Este tema describe la entidad Dirección de la persona para Dynamics 365 Human Resources.
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
ms.openlocfilehash: e16966c30ccfadd69e3d53f1259fa7167896e6d1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798162"
---
# <a name="person-address"></a>Dirección de la persona

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Dirección de la persona para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpersonaddressentities

## <a name="description"></a>Descripción

Esta entidad contiene la lista de direcciones postales para los registros de candidatos.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_roles": "String",
    "mshr_countryregionid": "String",
    "mshr_zipcode": "String",
    "mshr_street": "String",
    "mshr_city": "String",
    "mshr_state": "String",
    "mshr_county": "String",
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "_mshr_fk_countryregion_id_value": "Guid",
    "mshr_hcmpersonaddressentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de dirección de la persona**<br>mshr_hcmpersonaddressentityid<br>*Cadena* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro de entidad. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | Id. de registro de la parte (persona) asociada. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema de registro de entidad (persona) de la parte. |
| **Id. de ubicación**<br>mshr_locationid<br>*Cadena* | Leer/Escribir<br>Obligatorio | Id. de ubicación del registro de dirección. Configurado en la entidad mshr_logisticspostaladdresslocationcdsentity. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Obligatorio | Descripción de la dirección del candidato. |
| **Roles**<br>mshr_roles<br>*Cadena* | Leer/Escribir<br>Obligatorio | Roles asignados para esta dirección. Se puede asignar más de un rol. Los roles deben separarse con signos de punto y coma. Valores válidos contenidos en la entidad mshr_logisticslocationroleentity. |
| **Calle**<br>mshr_street<br>*Cadena* | Leer/Escribir<br>Opcional | Número de calle. |
| **Ciudad**<br>mshr_city<br>*Cadena* | Leer/Escribir<br>Opcional | Ciudad de la dirección. Configurado en la entidad mshr_logisticsaddresscityentity. |
| **Estado o provincia**<br>mshr_state<br>*Cadena* | Leer/Escribir<br>Opcional | Estado de la dirección. Configurado en la entidad mshr_logisticsaddressstateentity. |
| **Provincia**<br>mshr_county<br>*Cadena* | Leer/Escribir<br>Opcional | Provincia de la dirección. Configurado en la entidad mshr_logisticsaddresscountyentity. |
| **Código postal**<br>mshr_zipcode<br>*Cadena* | Leer/Escribir<br>Opcional | Código postal de la dirección. Configurado en la entidad mshr_logisticsaddresspostalcodeentity. |
| **Id. de país o región**<br>mshr_countryregionid<br>*Cadena* | Leer/Escribir<br>Opcional | País o región de la dirección. |
| **Valor de id. de país o región**<br>_mshr_fk_countriregion_id_value<br>*GUID* | Solo lectura<br>Opcional<br>Clave externa: mshr_logisticaddresscountryregionentityid de mshr_logisticsaddresscountryregionentity | Identificador único del país o región de la dirección generado por el sistema. |
| **Es principal**<br>mshr_isprimary<br>*Conjunto de opciones mshr_noyes* | Leer/Escribir<br>Obligatorio | Identifica si esta dirección es la dirección principal de la persona del rol definido. |
| **Es privado**<br>mshr_isprivate<br>*Conjunto de opciones mshr_noyes* | Leer/Escribir<br>Obligatorio | Identifica si esta dirección es una dirección privada de la persona. |
| **Campo principal**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Campo utilizado como identificador principal del registro de entidad. Combinación de número de parte e id. de ubicación. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]