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
# <a name="workflow-system"></a><span data-ttu-id="43098-103">Sistema de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="43098-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43098-104">Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="43098-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="43098-105">Notificaciones</span><span class="sxs-lookup"><span data-stu-id="43098-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="43098-106">¿Por qué se reciben varias notificaciones cuando se rechaza un elemento de trabajo?</span><span class="sxs-lookup"><span data-stu-id="43098-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="43098-107">Si se rechaza un elemento de trabajo, ese elemento de trabajo se completa como rechazado.</span><span class="sxs-lookup"><span data-stu-id="43098-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="43098-108">Otro elemento de trabajo se crea y se asigna al originador.</span><span class="sxs-lookup"><span data-stu-id="43098-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="43098-109">Esto significa que hay una notificación al originador del elemento de trabajo rechazado, y una notificación independiente al usuario asignado al nuevo elemento de trabajo de “cambio solicitado”.</span><span class="sxs-lookup"><span data-stu-id="43098-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="43098-110">Cada notificación es para un elemento de trabajo diferente, pero la semejanza puede provocar la confusión.</span><span class="sxs-lookup"><span data-stu-id="43098-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="43098-111">Estamos buscando formas de mejorar esto en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="43098-111">We are looking at ways to improve this in a future release.</span></span>
