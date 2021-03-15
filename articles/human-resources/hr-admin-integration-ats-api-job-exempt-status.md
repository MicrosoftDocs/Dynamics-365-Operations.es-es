---
title: Estado de exención de trabajo
description: Este tema describe el conjunto de opciones de estado de exención de trabajo para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125578"
---
# <a name="job-exempt-status"></a>Estado de exención de trabajo

Este tema describe el conjunto de opciones de estado de exención de trabajo para Dynamics 365 Human Resources.

Nombre físico: cdm_jobexemptstatus

Esta enumeración especifica el conjunto de opciones para valores de estado de exención de trabajo FLSA. Esto se ofrece en el conjunto de opciones cdm_jobexemptstatus existente.

| Valor | Etiqueta | Descripción |
| --- | --- | --- |
| 200000000 | Exento | El trabajo tiene un estado de exención según las pautas de la FLSA. |
| 200000001 | NonExempt | El trabajo tiene un estado de no exención según las pautas de la FLSA. |
| 200000002 | No aplicable | Las pautas de estado de la FLSA no se aplican al trabajo. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]