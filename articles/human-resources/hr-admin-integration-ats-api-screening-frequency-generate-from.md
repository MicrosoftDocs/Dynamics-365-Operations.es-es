---
title: Origen de generación de la frecuencia de cribado
description: Este tema describe la frecuencia de cribado generada a partir del conjunto de opciones para Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 238cd5da750d815c904090cc9002e3d1a5d2bcc7
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464583"
---
# <a name="screening-frequency-generate-from"></a>Origen de generación de la frecuencia de cribado

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