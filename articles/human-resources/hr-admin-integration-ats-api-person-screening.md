---
title: Filtrado de persona
description: Este artículo describe la entidad Cribado de la persona para Dynamics 365 Human Resources.
author: jaredha
ms.date: 12/05/2022
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
ms.openlocfilehash: 3c316e0381f4d407ed7c4c39b5949717b71477bd
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "9831900"
---
# <a name="person-screening"></a>Filtrado de persona


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artículo describe la entidad Cribado de la persona para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmpersonscreeningentity

## <a name="description"></a>Descripción

Esta entidad describe los cribados que un candidato ha superado o debe superar para conseguir el empleo.

## <a name="json-representation"></a>Representación JSON

```json
{
    "mshr_note": "String",
    "mshr_requiredby": "Date",
    "mshr_status": Int,
    "mshr_partynumber": "String",
    "mshr_screeningtypeid": "String",
    "_mshr_fk_screeningtype_id_value": "Guid",
    "mshr_primaryfield": "String",
    "_mshr_fk_person_id_value": "Guid",
    "mshr_hcmpersonscreeningentityid": "Guid",
    "mshr_completeddate": "Date"
}
```

## <a name="properties"></a>Propiedades

| Propiedad<br>**Nombre físico**<br>**_Tipo_** | Utilizar | Description |
| --- | --- | --- |
| **Notas**<br>mshr_note<br>*Cadena* | Leer/Escribir<br>Opcional | Notas para los técnicos de selección de personal y los responsables de contratación. |
| **Requerido antes del**<br>mshr_requiredby<br>*Fecha y hora* | Leer/Escribir<br>Opcional | La fecha en la que debe estar completada la evaluación. |
| **Estado**<br>mshr_status<br>*Conjunto de opciones mshr_hcmcompletionstatus*|Leer/Escribir<br>Obligatorio | Proporciona el estado del candidato para el cribado. |
| **Número de parte**<br>mshr_partynumber<br>*Cadena* | Leer/Escribir<br>Obligatorio | El número de entidad (persona) asociado con el candidato. |
| **Id. de tipo de cribado**<br>mshr_screeningtypeid<br>*Cadena* | Leer/Escribir<br>Obligatorio<br>Clave externa: ScreeningType | Identificador del tipo de cribado definido en Human Resources. |
| **Valor de id. de tipo de cribado**<br>_mshr_fk_screeningtype_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_hcmscreeningtypeentityid de mshr_hcmscreeningtypeentity | Identificador único generado por el sistema para el registro de tipo de cribado en la entidad asociada. |
| **Campo primario**<br>mshr_primaryfield<br>*Cadena* |  Solo lectura<br>Obligatorio | Campo que se utilizará como identificador principal del registro de entidad. |
| **Valor de id. de persona**<br>_mshr_fk_person_id_value<br>*GUID* | Solo lectura<br>Obligatorio<br>Clave externa: mshr_dirpersonentityid de mshr_dirpersonentity | Identificador único generado por el sistema de registro de entidad (persona) de la parte. |
| **Id. de entidad de cribado de la persona**<br>mshr_hcmpersonscreeningentityid<br>*GUID* | Solo lectura<br>Obligatorio<br>Generado por el sistema| Identificador principal único del registro de cribado de la persona. |
| **Fecha de finalización**<br>mshr_completeddate<br>*Fecha y hora* | Leer/Escribir<br>Opcional | La fecha en que se completó el cribado. |


## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
