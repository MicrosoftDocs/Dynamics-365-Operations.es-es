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
# <a name="workflow-system"></a><span data-ttu-id="2a339-103">Sistema de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2a339-103">Workflow system</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2a339-104">Este tema responde a las preguntas frecuentes acerca del sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2a339-104">This topic answers frequently asked questions about the workflow system in Microsoft Dynamics 365 for Finance and Operations.</span></span>

## <a name="notifications"></a><span data-ttu-id="2a339-105">Notificaciones</span><span class="sxs-lookup"><span data-stu-id="2a339-105">Notifications</span></span>

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a><span data-ttu-id="2a339-106">¿Por qué se reciben varias notificaciones cuando se rechaza un elemento de trabajo?</span><span class="sxs-lookup"><span data-stu-id="2a339-106">Why are multiple notifications received when a work item is rejected?</span></span>
<span data-ttu-id="2a339-107">Si se rechaza un elemento de trabajo, ese elemento de trabajo se completa como rechazado.</span><span class="sxs-lookup"><span data-stu-id="2a339-107">When a work item is rejected, that work item is completed as rejected.</span></span> <span data-ttu-id="2a339-108">Otro elemento de trabajo se crea y se asigna al originador.</span><span class="sxs-lookup"><span data-stu-id="2a339-108">Another work item is created and assigned to the originator.</span></span> <span data-ttu-id="2a339-109">Esto significa que hay una notificación al originador del elemento de trabajo rechazado, y una notificación independiente al usuario asignado al nuevo elemento de trabajo de “cambio solicitado”.</span><span class="sxs-lookup"><span data-stu-id="2a339-109">This means that there is a notification to the originator for the rejected work item, and a separate notification to the user assigned to the new "change requested" work item.</span></span> 

<span data-ttu-id="2a339-110">Cada notificación es para un elemento de trabajo diferente, pero la semejanza puede provocar la confusión.</span><span class="sxs-lookup"><span data-stu-id="2a339-110">Each notification is for a different work item, but the similarity can cause confusion.</span></span> <span data-ttu-id="2a339-111">Estamos buscando formas de mejorar esto en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="2a339-111">We are looking at ways to improve this in a future release.</span></span>

### <a name="why-are-my-workflow-exports-failing"></a><span data-ttu-id="2a339-112">¿Por qué mis exportaciones del flujo de trabajo están fallando?</span><span class="sxs-lookup"><span data-stu-id="2a339-112">Why are my workflow exports failing?</span></span>
<span data-ttu-id="2a339-113">Existen actualmente un límite en la función de exportación del flujo de trabajo que impide que los nombres del flujo de trabajo pasen de 48 caracteres.</span><span class="sxs-lookup"><span data-stu-id="2a339-113">There is currently a limitation in the workflow export feature that prevents workflow names from exceeding 48 characters.</span></span> <span data-ttu-id="2a339-114">Usar un nombre que sea más largo de 48 caracteres puede resultar en un error “El servidor no puede autenticar la solicitud” y/o evitar que se exporte un archivo sin un tipo de archivo.</span><span class="sxs-lookup"><span data-stu-id="2a339-114">Using a name that is longer than 48 characters can result in a "Server failed to authenticate the request" error and/or prevent a file to be exported  without a file type.</span></span> <span data-ttu-id="2a339-115">La siguiente entrada del blog proporciona más detalles [Solución de problemas de exportación del flujo de trabajo](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="2a339-115">The following blog post provides more details [Workflow Export Troubleshooting](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).</span></span>
