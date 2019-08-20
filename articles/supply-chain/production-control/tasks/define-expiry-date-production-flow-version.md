---
title: Definir una fecha de vencimiento para una versión del flujo de producción
description: Para finalizar la validez y el procesamiento de una versión de flujo de producción en una fecha concreta, o planificar la sustitución de una versión activa por una versión nueva, necesita establecer una fecha de vencimiento en la versión.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10260290fba02ebf9313d0d1355c9aa28e3509d7
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843706"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="6393d-103">Definir una fecha de vencimiento para una versión del flujo de producción</span><span class="sxs-lookup"><span data-stu-id="6393d-103">Define an expiry date for a production flow version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6393d-104">Para finalizar la validez y el procesamiento de una versión de flujo de producción en una fecha concreta, o planificar la sustitución de una versión activa por una versión nueva, necesita establecer una fecha de vencimiento en la versión.</span><span class="sxs-lookup"><span data-stu-id="6393d-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="6393d-105">No es necesario desactivar la versión.</span><span class="sxs-lookup"><span data-stu-id="6393d-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="6393d-106">Establecer una fecha de vencimiento para finalizar una versión del flujo de producción</span><span class="sxs-lookup"><span data-stu-id="6393d-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="6393d-107">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="6393d-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="6393d-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6393d-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="6393d-109">Seleccione cualquier flujo de producción que tenga una versión ya definida.</span><span class="sxs-lookup"><span data-stu-id="6393d-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="6393d-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6393d-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="6393d-111">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="6393d-111">Click Edit.</span></span>
5. <span data-ttu-id="6393d-112">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6393d-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="6393d-113">En el campo Fecha de vencimiento, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="6393d-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="6393d-114">Para la fecha de vencimiento, no se iniciará ni se activará una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="6393d-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="6393d-115">Tampoco no será posible crear o iniciar trabajos para este flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="6393d-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="6393d-116">Podrá completar los trabajos después de la fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="6393d-116">You can still complete started jobs after the expiration date.</span></span>  

