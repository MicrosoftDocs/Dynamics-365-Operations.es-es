---
title: Origen de generación de la frecuencia de cribado
description: Este tema describe la frecuencia de cribado generada a partir del conjunto de opciones para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 27c6c62f3ac312ee502df969f25f1b16761cba03
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067813"
---
# <a name="screening-frequency-generate-from"></a>Origen de generación de la frecuencia de cribado


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe la frecuencia de cribado generada a partir del conjunto de opciones para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmfrequencygeneratefrom

Esta enumeración proporciona el conjunto de opciones de valores para determinar la fecha de inicio del cálculo para el siguiente cribado necesario.

| Valor | Etiqueta | Descripción |
| --- | --- | --- |
| 200000000 No seleccionado | No se ha seleccionado ningún valor. |
| 200000001 Fecha de finalización | El cálculo se realiza a partir de la última fecha de cribado completada. |
| 200000002 Fecha es obligatoria | El cálculo se realiza a partir de la última fecha de cribado obligatoria. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
