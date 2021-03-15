---
title: Estado de solicitud de contratación
description: Este tema describe el conjunto de opciones de estado de solicitud de contratación para Dynamics 365 Human Resources.
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
ms.openlocfilehash: 55ed9c391a1b5f86c3c443b9fceeee5c2301444d
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125963"
---
# <a name="recruiting-request-status"></a>Estado de solicitud de contratación

Este tema describe el conjunto de opciones de estado de solicitud de contratación para Dynamics 365 Human Resources.

Nombre físico: mshr_hcmrecruitingrequeststatus

Esta enumeración proporciona el conjunto de opciones de los valores de estado de una solicitud de contratación.

| Valor | Etiqueta | Descripción |
| --- | --- | --- |
| 200000000 | Borrador | La solicitud está en estado de borrador. No está lista para la contratación activa. |
| 200000001 | En revisión | Se ha enviado la solicitud y se está enrutando para su aprobación por flujo de trabajo. Solo está disponible cuando el flujo de trabajo está habilitado. |
| 200000002 | Pendientes | La solicitud está pendiente de una acción de flujo de trabajo. Solo está disponible cuando el flujo de trabajo está habilitado. |
| 200000003 | Cancelados | Se ha cancelado la solicitud. Solo está disponible cuando el flujo de trabajo está habilitado. |
| 200000004 | Denegada | Se ha denegado la solicitud. Solo está disponible cuando el flujo de trabajo está habilitado. |
| 200000005 | Activa | Se ha completado y aprobado cualquier flujo de trabajo, y la solicitud está lista para la contratación activa. |
| 200000006 | Cerradas | La solicitud de contratación se ha cerrado. |

## <a name="see-also"></a>Consulte también

[Introducción a la API de integración del sistema de seguimiento de candidatos](hr-admin-integration-ats-api-introduction.md)<br>
[Consulta de ejemplo para solicitud de contratación](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]