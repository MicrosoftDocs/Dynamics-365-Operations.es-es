---
title: Estado de posición de solicitud de reclutamiento
description: Este tema describe el conjunto de opciones de estado de puesto de solicitud de contratación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: e287ec4b9b78194b76ef3c993c6ce32f808e26f9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051890"
---
# <a name="recruiting-request-position-status"></a>Estado de posición de solicitud de reclutamiento

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tema describe el conjunto de opciones de estado de puesto de solicitud de contratación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmrecruitingrequestpositionstatus

Esta enumeración proporciona el conjunto de opciones para los valores de estado de cada puesto y una solicitud de contratación en la entidad RecruitingRequestPosition.

| Valor | Etiqueta | Descripción |
| --- | --- | --- |
| 200000000 | Abiertas | El puesto en la solicitud de contratación está abierto para la contratación. Esto no indica que no haya una asignación de puesto activa actualmente para el puesto. Puede haber un empleado en el puesto en el momento de la contratación. Solo indica que el puesto está disponible para contratación en el contexto de la solicitud de contratación. |
| 200000001 | Relleno | Se ha seleccionado un trabajador para asignárselo al puesto. |
| 200000002 | Cancelados | Se ha cancelado la solicitud de contratación para este puesto. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]