---
title: Contacto de parte
description: Este tema describe la entidad de contacto de parte para Dynamics 365 Human Resources.
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
ms.openlocfilehash: fe25e37025a9f7945121a2a999c164a273e803fed750cc258e1ad30e33fc709b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6727194"
---
# <a name="party-contact"></a>Contacto de parte

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad de contacto de parte para Dynamics 365 Human Resources.

Nombre físico: mshr_dirpartycontactentities

## <a name="description"></a>Descripción

Esta entidad describe la información de contacto del candidato, incluidas las cuentas de teléfono, correo electrónico y redes sociales.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_partynumber": "String",
    "mshr_locationid": "String",
    "mshr_description": "String",
    "mshr_type": Int,
    "mshr_countryregioncode": "String",
    "mshr_locator": "String",
    "mshr_locatorextension": "String",
    "mshr_purpose": "String",
    "mshr_ismobilephone": Int,
    "mshr_isinstantmessage": Int,
    "mshr_isprimary": Int,
    "mshr_isprivate": Int,
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "String",
    "mshr_dirpartycontactentityid": "String"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de contacto del grupo**<br>mshr_dirpartycontactentityid<br>*Cadena* | Solo lectura<br>Obligatorio | Identificador único generado por el sistema para el registro de entidad. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | Id. de registro de la parte (persona) asociada. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema de registro de entidad (persona) de la parte. |
| **Id. de ubicación**<br>mshr_locationid<br>*Cadena* | Leer/Escribir<br>Obligatorio | Id. de ubicación del registro de dirección. Configurado en la entidad mshr_logisticspostaladdresslocationcdsentity. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Obligatorio | La descripción de los detalles de contacto. |
| **Tipo**<br>mshr_type<br>*Conjunto de opciones mshr_logisticselectronicaddressmethodtype* | Leer/Escribir<br>Obligatorio | El tipo de detalle de contacto. |
| **Código país o región**<br>mshr_countryregioncode<br>*Cadena* | Leer/Escribir<br>Opcional | País o región de la dirección. |
| **Localizador**<br>mshr_locator<br>*Cadena* | Leer/Escribir<br>Opcional | Los detalles de contacto. Por ejemplo, si el tipo es **Dirección de correo electrónico**, este campo contiene la dirección de correo electrónico del candidato. |
| **Extensión del localizador**<br>mshr_locatorextension<br>*Cadena* | Leer/Escribir<br>Opcional | La extensión del localizador. Por ejemplo, si el tipo es **Teléfono**, entonces esta propiedad contendría la extensión del número de teléfono. |
| **Es móvil**<br>mshr_ismobile<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Obligatorio | Especifica si el teléfono es un número de teléfono móvil. |
| **Es mensaje instantáneo**<br>mshr_isinstantmessage<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Obligatorio | Especifica si el teléfono está habilitado para mensajería instantánea. |
| **Es principal**<br>mshr_isprimary<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Obligatorio | Determina el contacto principal del tipo de contacto. Debe haber solo un registro principal por tipo de contacto. |
| **Es privado**<br>mshr_isprivate<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Obligatorio | Identifica si esta dirección es una dirección privada de la persona. |
| **Propósito**<br>mshr_purpose<br>*Cadena* | Leer/Escribir<br>Opcional | La finalidad o el rol de los detalles de contacto. |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* | Solo lectura<br>Obligatorio | Campo utilizado como identificador principal del registro de entidad. Combinación de número de parte, tipo, descripción y localizador. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]