---
title: Resultado de integración de candidatos
description: Este tema describe el conjunto de opciones de resultados de integración del solicitante para Dynamics 365 Human Resources.
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
ms.openlocfilehash: e8e41fe485cc70a668d4610ce6eabba5cd16ac86
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795126"
---
# <a name="applicant-integration-result"></a>Resultado de integración de candidatos

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe el conjunto de opciones de resultados de integración del solicitante para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmapplicantintegrationresult

Esta enumeración proporciona el estado de un registro de candidato.

| Valor | Etiqueta | Descripción |
| --- | --- | --- |
| 200000000 | No procesado | El candidato aún está bajo consideración. |
| 200000001 | Contratado | El candidato ha sido contratado. |
| 200000002 | No contratado | Se tomó la decisión de no contratar al candidato. |
| 200000003 | Descartado | El candidato fue descartado del planteamiento. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]