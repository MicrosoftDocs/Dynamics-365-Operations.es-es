---
title: Preguntas frecuentes de flujo de trabajo
description: Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "773231"
---
# <a name="workflow-system"></a>Sistema de flujo de trabajo

[!include [banner](../includes/banner.md)]

Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notificaciones

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>¿Por qué se reciben varias notificaciones cuando se rechaza un elemento de trabajo?
Si se rechaza un elemento de trabajo, ese elemento de trabajo se completa como rechazado. Otro elemento de trabajo se crea y se asigna al originador. Esto significa que hay una notificación al originador del elemento de trabajo rechazado, y una notificación independiente al usuario asignado al nuevo elemento de trabajo de “cambio solicitado”. 

Cada notificación es para un elemento de trabajo diferente, pero la semejanza puede provocar la confusión. Estamos buscando formas de mejorar esto en una versión futura.
