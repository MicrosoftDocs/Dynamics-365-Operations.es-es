--- 
title: "Desactivar una versión de flujo de producción"
description: "Cuando ya no se necesita una versión del flujo de producción activa, se puede desactivar."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 8db4b2857e9a7c99ee6fa4ef397f7ed99335faba
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="4c587-103">Desactivar una versión de flujo de producción</span><span class="sxs-lookup"><span data-stu-id="4c587-103">Deactivate a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4c587-104">Cuando ya no se necesita una versión del flujo de producción activa, se puede desactivar.</span><span class="sxs-lookup"><span data-stu-id="4c587-104">When an active production flow version is no longer needed, it can be deactivated.</span></span> <span data-ttu-id="4c587-105">Debe usar esta opción únicamente si todas las reglas kanban y las actividades han terminado y no están activadas de nuevo.</span><span class="sxs-lookup"><span data-stu-id="4c587-105">You should only use this option if all kanban rules and activities have ended and will not be activated again.</span></span> <span data-ttu-id="4c587-106">Tenga en cuenta que la fecha de caducidad de todas las reglas kanban relacionadas con esta versión del flujo de producción se actualizarán con la fecha y hora actuales.</span><span class="sxs-lookup"><span data-stu-id="4c587-106">Note that the expiry date of all kanban rules related to this production flow version will be updated with the current date and time.</span></span> 

<span data-ttu-id="4c587-107">Para modificar una versión de flujo de producción activa, considere configurar una fecha de vencimiento para la versión activa y cree una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="4c587-107">To modify an active production flow version, consider setting an expiry date for the active version and create a new version.</span></span> <span data-ttu-id="4c587-108">Esto le permitirá continuar con sus operaciones de producción mientras prepara la nueva versión y las reglas kanban relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4c587-108">This will allow you to continue your production operations while preparing the new version and related kanban rules.</span></span> 

<span data-ttu-id="4c587-109">Para que una versión del flujo de producción activa expire, deberá establecer una fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="4c587-109">To expire an active production flow version, you need to set an expiry date.</span></span> <span data-ttu-id="4c587-110">En ese sentido, la desactivación es más bien una excepción que una regla.</span><span class="sxs-lookup"><span data-stu-id="4c587-110">In that sense, deactivation is more like an exception than a rule.</span></span> 

<span data-ttu-id="4c587-111">Para este procedimiento necesita un flujo de producción con una versión que se pueda desactivar.</span><span class="sxs-lookup"><span data-stu-id="4c587-111">For this procedure you need a production flow with a version that can be deactivated.</span></span> <span data-ttu-id="4c587-112">No intente esto en un entorno de producción salvo que totalmente convencido de que la versión que está completamente obsoleta.</span><span class="sxs-lookup"><span data-stu-id="4c587-112">Do not try this in a production environment unless you are 100% positive that the version is fully obsolete.</span></span>


## <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="4c587-113">Desactivar una versión de flujo de producción</span><span class="sxs-lookup"><span data-stu-id="4c587-113">Deactivate a production flow version</span></span>
1. <span data-ttu-id="4c587-114">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="4c587-114">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="4c587-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4c587-115">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="4c587-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4c587-116">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="4c587-117">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4c587-117">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="4c587-118">Haga clic en Desactivar.</span><span class="sxs-lookup"><span data-stu-id="4c587-118">Click Deactivate.</span></span>
    * <span data-ttu-id="4c587-119">No continúe si no está convencido de que esta versión del flujo de producción está obsoleta.</span><span class="sxs-lookup"><span data-stu-id="4c587-119">Do not proceed if you are not 100% positive that this production flow version is obsolete.</span></span> <span data-ttu-id="4c587-120">Haciendo clic en Acepar expirarán todas las reglas kanban activas y se pondrá fin de forma inmediata a todas las actividades de producción y de reabastecimiento de esta versión del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="4c587-120">Clicking Ok will expire all active kanban rules and put an immediate stop to all production and replenishment activities of this production flow version.</span></span>  
6. <span data-ttu-id="4c587-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4c587-121">Click OK.</span></span>


