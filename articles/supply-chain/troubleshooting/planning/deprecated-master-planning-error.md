---
title: Recibe un error al ejecutar el motor de planificación maestra integrado
description: Cuando ejecuta el motor de planificación maestra integrado en desuso, recibe un mensaje de error.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294174"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a><span data-ttu-id="d3ff7-103">Recibe un error al ejecutar el motor de planificación maestra integrado</span><span class="sxs-lookup"><span data-stu-id="d3ff7-103">You receive an error when running the built-in master planning engine</span></span>

<span data-ttu-id="d3ff7-104">Código de error: ReqCalcScheduleItemTablePlanningOptimizationFitError</span><span class="sxs-lookup"><span data-stu-id="d3ff7-104">Error code: ReqCalcScheduleItemTablePlanningOptimizationFitError</span></span>

## <a name="symptoms"></a><span data-ttu-id="d3ff7-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d3ff7-105">Symptoms</span></span>

<span data-ttu-id="d3ff7-106">Cuando ejecuta la planificación maestra con el motor de planificación maestra integrado en desuso, recibe el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="d3ff7-106">When you run master planning by using the deprecated built-in master planning engine, you receive the following error message:</span></span>

> <span data-ttu-id="d3ff7-107">Recibe este mensaje de error porque el motor de planificación maestro integrado se utilizó para escenarios compatibles con Optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-107">You receive this error message because the built-in master planning engine was used for scenarios supported by Planning Optimization.</span></span> <span data-ttu-id="d3ff7-108">Debe migrar a Optimización de la planificación ahora, ya que la planificación maestra incorporada actual quedará obsoleta.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-108">You should migrate to Planning Optimization now, as the current built-in master planning will be deprecated.</span></span> <span data-ttu-id="d3ff7-109">Tenga en cuenta que esta ejecución de planificación maestra se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-109">Note that this master planning run did complete successfully.</span></span> <span data-ttu-id="d3ff7-110">En caso de que su migración tenga una fuerte dependencia de las características pendientes, se puede solicitar una excepción al uso continuo del motor de planificación maestro integrado.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-110">In case your migration has strong dependencies on pending features, an exception to continued usage of the built-in master planning engine can be requested.</span></span> <span data-ttu-id="d3ff7-111">Complete el siguiente cuestionario para comenzar y, si es relevante, solicite una excepción de la migración a Optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-111">Please complete the following questionnaire to get started and, if relevant, request an exception from migration to Planning Optimization.</span></span> [<span data-ttu-id="d3ff7-112">Cuestionario de excepción y migración de Planning Optimization</span><span class="sxs-lookup"><span data-stu-id="d3ff7-112">Planning Optimization migration and exception questionnaire</span></span>](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a><span data-ttu-id="d3ff7-113">Causa</span><span class="sxs-lookup"><span data-stu-id="d3ff7-113">Cause</span></span>

<span data-ttu-id="d3ff7-114">Si ejecuta la planificación y no usa las funciones de control de producción, debería considerar migrar a Planning Optimization.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-114">If you run planning and don't use production control features, you should consider migrating to Planning Optimization.</span></span> <span data-ttu-id="d3ff7-115">El motor de planificación maestro integrado está en desuso.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-115">The built-in master planning engine is being deprecated.</span></span> <span data-ttu-id="d3ff7-116">Por lo tanto, si desea continuar usándolo sin recibir el mensaje de error, debe solicitar una excepción de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3ff7-116">Therefore, if you want to continue to use it without receiving the error message, you must apply for an exception from Microsoft.</span></span>

## <a name="resolution"></a><span data-ttu-id="d3ff7-117">Resolución</span><span class="sxs-lookup"><span data-stu-id="d3ff7-117">Resolution</span></span>

<span data-ttu-id="d3ff7-118">Para obtener más información sobre cómo migrar a Planning Optimization, o cómo solicitar una excepción para poder seguir utilizando el motor de planificación integrado en desuso, consulte [Migración a la optimización de la planificación para la planificación maestra](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span><span class="sxs-lookup"><span data-stu-id="d3ff7-118">For more information about how to migrate to Planning Optimization, or how to apply for an exception so that you can continue to use the deprecated built-in planning engine instead, see [Migration to Planning Optimization for master planning](/dynamics365/supply-chain/master-planning/new-master-planning-engine).</span></span>
