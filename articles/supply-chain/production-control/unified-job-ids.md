---
title: Secuencia numérica unificada para id. de trabajo
description: Esta función proporciona una secuencia numérica única y unificada que genera identificaciones de trabajo para los módulos de control de producción, ejecución de fabricación y tiempo y asistencia.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824951"
---
# <a name="unified-number-sequence-for-job-ids"></a><span data-ttu-id="69093-103">Secuencia numérica unificada para id. de trabajo</span><span class="sxs-lookup"><span data-stu-id="69093-103">Unified number sequence for job IDs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69093-104">Esta función proporciona una secuencia numérica única y unificada que genera identificaciones de trabajo para los módulos de control de producción, ejecución de fabricación y tiempo y asistencia.</span><span class="sxs-lookup"><span data-stu-id="69093-104">This feature provides a single, unified number sequence that generates job IDs for the Production control, Manufacturing execution, and Time and attendance modules.</span></span> <span data-ttu-id="69093-105">Anteriormente, podía elegir una secuencia de números diferente para cada uno de estos módulos, lo que podría resultar en identificación de trabajo en conflicto si dos o más de estas secuencias usaban un formato idéntico.</span><span class="sxs-lookup"><span data-stu-id="69093-105">Previously, you were able to choose a different number sequence for each of these modules, which could result in conflicting job IDs if two or more of these sequences used an identical format.</span></span> <span data-ttu-id="69093-106">Tal conflicto puede provocar daños en los datos.</span><span class="sxs-lookup"><span data-stu-id="69093-106">Such a conflict can cause data corruption.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="69093-107">Activar esta función para su sistema</span><span class="sxs-lookup"><span data-stu-id="69093-107">Turn on this feature for your system</span></span>

<span data-ttu-id="69093-108">Si su sistema aún no incluye la función descrita en este tema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la característica *Secuencia numérica unificada para identificaciones de trabajo*.</span><span class="sxs-lookup"><span data-stu-id="69093-108">If your system doesn't already include the feature described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Unified number sequence for job IDs* feature.</span></span>

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a><span data-ttu-id="69093-109">Configurar la secuencia numérica unificada para id. de trabajo</span><span class="sxs-lookup"><span data-stu-id="69093-109">Set up the unified number sequence for job IDs</span></span>

<span data-ttu-id="69093-110">Después de habilitar esta función, la configuración **Identificación de trabajo** de secuencia numérica ubicada en las páginas de parámetros para los módulos Control de producción, Ejecución de fabricación y Tiempo y asistencia quedará obsoleta y se añadirá un campo nuevo **Identificación de trabajo unificado**.</span><span class="sxs-lookup"><span data-stu-id="69093-110">After enabling this feature, the existing **Job identification** number-sequence settings located on the parameters pages for the Production control, Manufacturing execution, and Time and attendance modules will be deprecated and a new **Unified job ID** field will be added.</span></span> <span data-ttu-id="69093-111">El valor **ID de trabajo unificado** es compartido por los tres módulos, asegurando así que todos los módulos hagan referencia a la misma secuencia numérica.</span><span class="sxs-lookup"><span data-stu-id="69093-111">The **Unified job ID** value is shared by all three modules, thus ensuring that all modules reference the same number sequence.</span></span> <span data-ttu-id="69093-112">Por lo tanto, los identificadores de trabajo serán únicos en los tres módulos y nunca se producirá un conflicto.</span><span class="sxs-lookup"><span data-stu-id="69093-112">Job IDs will therefore be unique across all three modules and a conflict will never occur.</span></span>

<span data-ttu-id="69093-113">Para configurar la secuencia numérica unificada para id. de trabajo:</span><span class="sxs-lookup"><span data-stu-id="69093-113">To set up the unified number sequence for job IDs:</span></span>

1. <span data-ttu-id="69093-114">Active la función como se describe en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="69093-114">Turn on the feature as described in the previous section.</span></span>
1. <span data-ttu-id="69093-115">Identifique la secuencia numérica que desea utilizar para sus id. de trabajo unificados o cree una nueva.</span><span class="sxs-lookup"><span data-stu-id="69093-115">Either identify the number sequence you want to use for your unified job IDs, or create a new one.</span></span> <span data-ttu-id="69093-116">Para obtener más información, consulte [Información general de secuencias numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="69093-116">For more information, see [Number sequences overview](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span></span>
1. <span data-ttu-id="69093-117">Vaya a la página **Parámetros de control de producción**, **Parámetros de ejecución de fabricación**, o **Parámetros de tiempo y asistencia**.</span><span class="sxs-lookup"><span data-stu-id="69093-117">Go to the **Production control parameters**, **Manufacturing execution parameters**, or **Time and attendance parameters** page.</span></span> <span data-ttu-id="69093-118">No importa cuál elija porque cuando realiza esta configuración en cualquiera de esas páginas, todas las demás páginas se actualizarán automáticamente.</span><span class="sxs-lookup"><span data-stu-id="69093-118">It doesn't matter which one you choose because when you make this setting on any of those pages, all of the other pages will update automatically.</span></span>
1. <span data-ttu-id="69093-119">Abra la pestaña **Secuencias numéricas** en la página de parámetros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="69093-119">Open the **Number sequences** tab on your selected parameters page.</span></span>
1. <span data-ttu-id="69093-120">Asigne el **Código de secuencia numérica** que identificó previamente a la fila de la cuadrícula **Id. de trabajo unificados**.</span><span class="sxs-lookup"><span data-stu-id="69093-120">Assign the **Number sequence code** that you identified previously to the **Unified job IDs** row of the grid.</span></span>
