---
title: Solución de problemas de optimización de planificación
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con Optimización de planiicación.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: c3dd0bf262f65aac2359c05ff954bdfbd294353f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436633"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="2de19-103">Solución de problemas de optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="2de19-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2de19-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con Optimización de planiicación.</span><span class="sxs-lookup"><span data-stu-id="2de19-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="2de19-105">La instalación del complemento Optimización de planiicación no se completa</span><span class="sxs-lookup"><span data-stu-id="2de19-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="2de19-106">Optimización de planificación requiere un entorno de alta disponibilidad de Lifecycle Services (LCS) habilitado, nivel 2 o superior (no un entorno OneBox), con Dynamics 365 Supply Chain Management, versión 10.0.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="2de19-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="2de19-107">Si intenta instalar el complemento en un entorno OneBox, la instalación no se completará.</span><span class="sxs-lookup"><span data-stu-id="2de19-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="2de19-108">**Reparar**: cancele la instalación y use un entorno de alta disponibilidad, nivel 2 o superior (no un entorno OneBox).</span><span class="sxs-lookup"><span data-stu-id="2de19-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="2de19-109">La planificación de trabajos por lotes falla cuando está habilitada Optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="2de19-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="2de19-110">Cuando se habilita Optimización de planificación, el motor de planificación maestro incorporado se desactiva automáticamente.</span><span class="sxs-lookup"><span data-stu-id="2de19-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="2de19-111">Los trabajos por lotes de planificación maestros creados para el motor de planificación de Supply Chain Management tendrán errores si se activan mientras está habilitada Optimización de planificación.</span><span class="sxs-lookup"><span data-stu-id="2de19-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="2de19-112">Puede recibir un mensaje de error como *Esta operación activó la planificación maestra que no es compatible cuando la Optimización de planificación está habilitada*.</span><span class="sxs-lookup"><span data-stu-id="2de19-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="2de19-113">**Reparar**: cancele todos los trabajos por lotes de planificación maestra que se crearon para el motor de planificación de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="2de19-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="2de19-114">Los resultados de Optimización de planificación son diferentes de los resultados anteriores</span><span class="sxs-lookup"><span data-stu-id="2de19-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="2de19-115">Optimización de planificación difiere del diseño de planificación maestra incorporado en algunas áreas.</span><span class="sxs-lookup"><span data-stu-id="2de19-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="2de19-116">Esto también pueden provocarlo funciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="2de19-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="2de19-117">**Reparar**: ejecute el análisis de ajuste de Optimización de planificación y luego analice los resultados mientras consulta la documentación relacionada para comprender la incidencia.</span><span class="sxs-lookup"><span data-stu-id="2de19-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="2de19-118">Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="2de19-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="master-planning-doesnt-respect-the-coverage-time-fence"></a><span data-ttu-id="2de19-119">La planificación maestra no respeta el intervalo de tiempo de cobertura</span><span class="sxs-lookup"><span data-stu-id="2de19-119">Master planning doesn't respect the coverage time fence</span></span>

<span data-ttu-id="2de19-120">Esto se debe a una función pendiente de Optimización de planificación.</span><span class="sxs-lookup"><span data-stu-id="2de19-120">This is caused by a pending feature for Planning Optimization.</span></span>

<span data-ttu-id="2de19-121">**Reparar**: hasta que la función pendiente esté disponible, filtre o elimine los pedidos planificados para eliminar sugerencias de suministro fuera del intervalo de tiempo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="2de19-121">**Fix**: Until the pending feature is available, filter or delete planned orders to remove supply suggestions outside of the coverage time fence.</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="2de19-122">No es posible habilitar Optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="2de19-122">Can't enable Planning Optimization</span></span>

<span data-ttu-id="2de19-123">El **Estado de conexión** debe ser **Conectado** antes de poder establecer **Usar Optimización de planificación** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2de19-123">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="2de19-124">Para obtener más información, consulte [Empezar a utilizar la optimización de la planificación](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="2de19-124">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="2de19-125">**Reparar**: asegúrese de que el complemento Optimización de planificación se haya instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2de19-125">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="2de19-126">Se muestra un mensaje de error durante CTP</span><span class="sxs-lookup"><span data-stu-id="2de19-126">Error message is shown during CTP</span></span>

<span data-ttu-id="2de19-127">Si intenta ejecutar Capaz de comprometer (CTP) desde un pedido de ventas cuando la Optimización de planificación está habilitada, recibirá el siguiente mensaje de error: *Esta operación activó la planificación maestra que no es compatible cuando Optimización de planificación está habilitada*.</span><span class="sxs-lookup"><span data-stu-id="2de19-127">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="2de19-128">Esto está relacionado con una función pendiente que está planificada como parte del soporte para pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="2de19-128">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="2de19-129">**Reparar:** Evite los cálculos de CTP cuando la Optimización de planificación esté habilitada hasta que esté disponible el soporte de CTP.</span><span class="sxs-lookup"><span data-stu-id="2de19-129">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2de19-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2de19-130">Additional resources</span></span>

[<span data-ttu-id="2de19-131">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="2de19-131">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="2de19-132">Análisis de idoneidad de optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="2de19-132">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
