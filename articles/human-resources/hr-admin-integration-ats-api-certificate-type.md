---
title: Tipo de certificado
description: Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.
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
ms.openlocfilehash: b8e979f242eb689b730b7f8a8684b3e697adbee6
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054701"
---
# <a name="certificate-type"></a>Tipo de certificado

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la entidad Tipo de certificado para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmcertificatetypeentity

## <a name="description"></a>Descripción

Esta entidad define la lista de tipos de certificados profesionales configurados en Recursos Humanos. La entidad no es específica de una entidad jurídica (empresa).

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de tipo de certificado**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | Solo lectura<br>Obligatorio 
Generado por el sistema | Identificador primario único del tipo de certificado. |
| **Tipo de certificado**<br>mshr_certificatetype<br>*Cadena* | Leer/Escribir<br>Obligatorio | Identificador único legible por el usuario del tipo de certificado. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Obligatorio | Descripción del tipo de certificado. |
| **Requiere renovación**<br>mshr_requirerenewal<br>*Opción mshr_noyes establecida* | Leer/Escribir<br>Opcional | Indica si se requiere renovación para el certificado. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]