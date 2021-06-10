---
title: Visión general de MyLeaveRequests
description: La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f29d5cf1469b58b4ea1837dc82b9513f5c002609
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054965"
---
# <a name="myleaverequests-overview"></a>Visión general de MyLeaveRequests

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.

## <a name="key"></a>Clave

  | Nombre de la propiedad | Tipo de datos |
  |---------------|-----------|
  | dataAreaId    | Cadena    |
  | RequestId     | Cadena    |
  | LeaveType     | Cadena    |
  | LeaveDate     | Fecha      |
  
## <a name="properties"></a>Propiedades

  | Nombre de la propiedad     | Tipo de datos | Requerido |
  |-------------------|-----------|----------|
  | dataAreaId        | Cadena    | X        |
  | RequestId         | Cadena    | X        |
  | LeaveType         | Cadena    | X        |
  | LeaveDate         | Fecha      | X        |
  | ReasonCodeId      | Cadena    |          |
  | PersonnelNumber   | Cadena    | X        |
  | RequestDate       | Fecha      | X        |
  | Comentar           | Cadena    |          |
  | Estado            | Enumeración      | X        |
  | Importe            | Real      |          |
  | HalfDayDefinition | Enumeración      |          |

## <a name="actions"></a>Acciones 

 | Nombre de acción                               | Descripción                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [enviar](hr-developer-api-myleaverequests-submit.md)   | Envíe la solicitud para que la procese el flujo de trabajo. |

## <a name="see-also"></a>Consulte también

- [Enviar una solicitud de baja al flujo de trabajo](hr-developer-api-myleaverequests-submit.md)
- [Autenticación](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]