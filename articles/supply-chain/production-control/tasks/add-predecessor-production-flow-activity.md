---
title: Agregar un predecesor a una actividad de flujo de producción
description: En una versión de flujo de producción, todas las actividades deben estar secuenciadas.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d76ec6ac928228011f42355bebd553576bcfd275
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255454"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="30922-103">Agregar un predecesor a una actividad de flujo de producción</span><span class="sxs-lookup"><span data-stu-id="30922-103">Add a predecessor to a production flow activity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="30922-104">En una versión de flujo de producción, todas las actividades deben estar secuenciadas.</span><span class="sxs-lookup"><span data-stu-id="30922-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="30922-105">Una actividad puede tener uno o múltiples predecesores o sucesores.</span><span class="sxs-lookup"><span data-stu-id="30922-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="30922-106">Este procedimiento muestra cómo asociar un predecesor a una actividad.</span><span class="sxs-lookup"><span data-stu-id="30922-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="30922-107">Para realizar esta tarea, se necesita un flujo de producción que tenga la versión Borrador con al menos dos actividades que se puedan conectar.</span><span class="sxs-lookup"><span data-stu-id="30922-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="30922-108">Para obtener más información, lea el documento “Los flujos de producción y las actividades en lean manufacturing”.</span><span class="sxs-lookup"><span data-stu-id="30922-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="30922-109">Encuentre el flujo de producción y la versión.</span><span class="sxs-lookup"><span data-stu-id="30922-109">Find the production flow and version</span></span>
1. <span data-ttu-id="30922-110">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="30922-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="30922-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="30922-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="30922-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="30922-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="30922-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="30922-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="30922-114">Haga clic en Actividades.</span><span class="sxs-lookup"><span data-stu-id="30922-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="30922-115">Seleccione una actividad y agregue un predecesor</span><span class="sxs-lookup"><span data-stu-id="30922-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="30922-116">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="30922-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="30922-117">Haga clic en Agregar un predecesor.</span><span class="sxs-lookup"><span data-stu-id="30922-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="30922-118">En el campo Actividad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="30922-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="30922-119">En campo Coeficiente de tiempo de ciclo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="30922-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="30922-120">La proporción de tiempo de ciclo predeterminado de una relación de actividad es 1.</span><span class="sxs-lookup"><span data-stu-id="30922-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="30922-121">Esto supone que las actividades se ejecutan en el mismo paso o el ritmo de producción.</span><span class="sxs-lookup"><span data-stu-id="30922-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="30922-122">Si el predecesor se ejecuta a un ritmo más alto (un ritmo de producción inferior), la proporción debe ser inferior a 1, si el predecesor se ejecuta a un ritmo más lento (un ritmo de producción más alto), el tiempo de ciclo es mayor que 1.</span><span class="sxs-lookup"><span data-stu-id="30922-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="30922-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="30922-123">Click OK.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]