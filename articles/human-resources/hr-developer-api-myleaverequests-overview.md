---
title: Visión general de MyLeaveRequests
description: La entidad MyLeaveRequests en Microsoft Dynamics 365 Human Resources proporciona la lista de Solicitudes de licencia en el sistema, con ámbito (limitada) a las solicitudes accesibles para el usuario actual que consulta la entidad.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4bf3b298af9eb39e03514a4005afb43a42908e47
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420347"
---
# <a name="myleaverequests-overview"></a>Visión general de MyLeaveRequests

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