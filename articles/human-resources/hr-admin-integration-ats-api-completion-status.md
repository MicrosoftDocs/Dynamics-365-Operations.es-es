---
title: Estado de finalización
description: Este tema describe el conjunto de opciones de estado de terminación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798378"
---
# <a name="completion-status"></a>Estado de finalización

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe el conjunto de opciones de estado de terminación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmcompletionstatus

Esta enumeración proporciona el conjunto de opciones de valores de estado para el cribado de candidatos. 

| Valor | Etiqueta | Descripción |
| --- | --- | --- |
| 200000000 | Incompleto | El candidato aún no ha completado el cribado. |
| 200000001 | Correcto | El candidato ha superado el cribado. |
| 200000002 | Error | El candidato no ha superado el cribado. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para candidato a contratar](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]