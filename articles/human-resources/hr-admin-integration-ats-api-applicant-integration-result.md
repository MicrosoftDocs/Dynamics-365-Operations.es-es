---
title: Resultado de integración de candidatos
description: Este tema describe el conjunto de opciones de resultados de integración del solicitante para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 425fc78edc933b79879c330284ef911c6fd4fd1c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066377"
---
# <a name="applicant-integration-result"></a>Resultado de integración de candidatos


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
