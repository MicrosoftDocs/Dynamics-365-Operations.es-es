---
title: Tipos de filtrado
description: Este artículo describe la entidad Tipos de cribado para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 95f4a3dce6851c7080ac665f5922e3b5877fa9f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880549"
---
# <a name="screening-types"></a>Tipos de filtrado


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad Tipos de cribado para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmscreeningtypeentity

## <a name="description"></a>Descripción

Esta entidad describe los tipos de cribado establecidos por la empresa para los procesos de cribado de empleados previo a la contratación y en curso.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Descripción |
| --- | --- | --- |
| **Id. de entidad de tipo de cribado**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | Solo lectura<br>Obligatorio<br>Generado por el sistema | Identificador principal único del registro de tipo de cribado. |
| **Id. de tipo de cribado**<br>mshr_screeningtypeid<br>*Cadena* | Leer/Escribir<br>Obligatorio | Identificador único definido por el usuario para el tipo de cribado. |
| **Descripción**<br>mshr_description<br>*Cadena* | Leer/Escribir<br>Obligatorio | La descripción del tipo de cribado. |
| **Unidad de frecuencia**<br>mshr_frequencyunit<br>*Conjunto de opciones mshr_hcmfrequencyunit* | Leer/Escribir<br>Obligatorio | Describe la frecuencia con la que se debe completar el cribado para la persona asignada. |
| **Generar desde**<br>mshr_generatefrom<br>*Conjunto de opciones mshr_hcmfrequencygeneratefrom* | Leer/Escribir<br>Obligatorio | Si el valor de Frecuencia es distinto de "Solo una vez", el valor de GenerateFrom determina la fecha a partir de la cual se calculará el siguiente evento de cribado. |
| **Intervalo de frecuencia**<br>mshr_frequencyinterval<br>*Entero* | Leer/Escribir<br>Obligatorio | Si el valor de Frecuencia es distinto de "Solo una vez", debe definir un intervalo para las unidades de tiempo entre cada evento de cribado. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
