---
title: Preguntas frecuentes de flujo de trabajo
description: Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: f6240b1b5136937aa47f455547fed6f0c7c08e2c
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1509300"
---
# <a name="workflow-system"></a>Sistema de flujo de trabajo

[!include [banner](../includes/banner.md)]

Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Notificaciones

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>¿Por qué se reciben varias notificaciones cuando se rechaza un elemento de trabajo?
Si se rechaza un elemento de trabajo, ese elemento de trabajo se completa como rechazado. Otro elemento de trabajo se crea y se asigna al originador. Esto significa que hay una notificación al originador del elemento de trabajo rechazado, y una notificación independiente al usuario asignado al nuevo elemento de trabajo de “cambio solicitado”. 

Cada notificación es para un elemento de trabajo diferente, pero la semejanza puede provocar la confusión. Estamos buscando formas de mejorar esto en una versión futura.

### <a name="why-are-my-workflow-exports-failing"></a>¿Por qué mis exportaciones del flujo de trabajo están fallando?
Existen actualmente un límite en la función de exportación del flujo de trabajo que impide que los nombres del flujo de trabajo pasen de 48 caracteres. Usar un nombre que sea más largo de 48 caracteres puede resultar en un error “El servidor no puede autenticar la solicitud” y/o evitar que se exporte un archivo sin un tipo de archivo. La siguiente entrada del blog proporciona más detalles [Solución de problemas de exportación del flujo de trabajo](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).
