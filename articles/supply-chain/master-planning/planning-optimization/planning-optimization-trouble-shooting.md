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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-5-7
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 39583c244f09f54551d560e8b1dd9f1a5a1590cc
ms.sourcegitcommit: 72f70c81176e86cda714a4712525f73514c895b7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "5457338"
---
# <a name="troubleshoot-planning-optimization"></a><span data-ttu-id="01c45-103">Solución de problemas de optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="01c45-103">Troubleshoot Planning Optimization</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01c45-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al trabajar con Optimización de planiicación.</span><span class="sxs-lookup"><span data-stu-id="01c45-104">This topic describes how to fix common issues that you might encounter while working with Planning Optimization.</span></span>

## <a name="installation-of-the-planning-optimization-add-in-doesnt-complete"></a><span data-ttu-id="01c45-105">La instalación del complemento Optimización de planiicación no se completa</span><span class="sxs-lookup"><span data-stu-id="01c45-105">Installation of the Planning Optimization add-in doesn't complete</span></span>

<span data-ttu-id="01c45-106">Optimización de planificación requiere un entorno de alta disponibilidad de Lifecycle Services (LCS) habilitado, nivel 2 o superior (no un entorno OneBox), con Dynamics 365 Supply Chain Management, versión 10.0.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="01c45-106">Planning Optimization requires a Lifecycle Services (LCS) enabled, high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="01c45-107">Si intenta instalar el complemento en un entorno OneBox, la instalación no se completará.</span><span class="sxs-lookup"><span data-stu-id="01c45-107">If you try to install the add-in on a OneBox environment, the installation won't complete.</span></span>

<span data-ttu-id="01c45-108">**Reparar**: cancele la instalación y use un entorno de alta disponibilidad, nivel 2 o superior (no un entorno OneBox).</span><span class="sxs-lookup"><span data-stu-id="01c45-108">**Fix**: Cancel the installation and use a high-availability environment, tier 2 or higher (not a OneBox environment).</span></span>

## <a name="planning-of-batch-jobs-fails-when-planning-optimization-is-enabled"></a><span data-ttu-id="01c45-109">La planificación de trabajos por lotes falla cuando está habilitada Optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="01c45-109">Planning of batch jobs fails when Planning Optimization is enabled</span></span>

<span data-ttu-id="01c45-110">Cuando se habilita Optimización de planificación, el motor de planificación maestro incorporado se desactiva automáticamente.</span><span class="sxs-lookup"><span data-stu-id="01c45-110">When you enable Planning Optimization, the built-in master planning engine is automatically disabled.</span></span> <span data-ttu-id="01c45-111">Los trabajos por lotes de planificación maestros creados para el motor de planificación de Supply Chain Management tendrán errores si se activan mientras está habilitada Optimización de planificación.</span><span class="sxs-lookup"><span data-stu-id="01c45-111">Master planning batch jobs that were created for the built-in Supply Chain Management planning engine will fail if they are triggered while Planning Optimization is enabled.</span></span> <span data-ttu-id="01c45-112">Puede recibir un mensaje de error como *Esta operación activó la planificación maestra que no es compatible cuando la Optimización de planificación está habilitada*.</span><span class="sxs-lookup"><span data-stu-id="01c45-112">You may receive an error message such as *This operation triggered master planning that isn't supported when Planning Optimization is enabled*.</span></span>

<span data-ttu-id="01c45-113">**Reparar**: cancele todos los trabajos por lotes de planificación maestra que se crearon para el motor de planificación de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="01c45-113">**Fix**: Cancel all master planning batch jobs that were created for the built-in Supply Chain Management planning engine.</span></span>

## <a name="planning-optimization-results-are-different-from-earlier-results"></a><span data-ttu-id="01c45-114">Los resultados de Optimización de planificación son diferentes de los resultados anteriores</span><span class="sxs-lookup"><span data-stu-id="01c45-114">Planning Optimization results are different from earlier results</span></span>

<span data-ttu-id="01c45-115">Optimización de planificación difiere del diseño de planificación maestra incorporado en algunas áreas.</span><span class="sxs-lookup"><span data-stu-id="01c45-115">Planning Optimization differs from the built-in master planning design in some areas.</span></span> <span data-ttu-id="01c45-116">Esto también pueden provocarlo funciones pendientes.</span><span class="sxs-lookup"><span data-stu-id="01c45-116">This can also be caused by pending features.</span></span>

<span data-ttu-id="01c45-117">**Reparar**: ejecute el análisis de ajuste de Optimización de planificación y luego analice los resultados mientras consulta la documentación relacionada para comprender la incidencia.</span><span class="sxs-lookup"><span data-stu-id="01c45-117">**Fix**: Run Planning Optimization fit analysis and then analyze the results while referring to the related documentation to understand the impact.</span></span> <span data-ttu-id="01c45-118">Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="01c45-118">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

## <a name="cant-enable-planning-optimization"></a><span data-ttu-id="01c45-119">No es posible habilitar Optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="01c45-119">Can't enable Planning Optimization</span></span>

<span data-ttu-id="01c45-120">El **Estado de conexión** debe ser **Conectado** antes de poder establecer **Usar Optimización de planificación** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="01c45-120">The **Connection status** must be **Connected** before you can set **Use Planning Optimization** to **Yes**.</span></span> <span data-ttu-id="01c45-121">Para obtener más información, consulte [Empezar a utilizar la optimización de la planificación](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="01c45-121">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="01c45-122">**Reparar**: asegúrese de que el complemento Optimización de planificación se haya instalado correctamente.</span><span class="sxs-lookup"><span data-stu-id="01c45-122">**Fix**: Make sure that the Planning Optimization add-in was installed successfully.</span></span>

## <a name="error-message-is-shown-during-ctp"></a><span data-ttu-id="01c45-123">Se muestra un mensaje de error durante CTP</span><span class="sxs-lookup"><span data-stu-id="01c45-123">Error message is shown during CTP</span></span>

<span data-ttu-id="01c45-124">Si intenta ejecutar Capaz de comprometer (CTP) desde un pedido de ventas cuando la Optimización de planificación está habilitada, recibirá el siguiente mensaje de error: *Esta operación activó la planificación maestra que no es compatible cuando Optimización de planificación está habilitada*.</span><span class="sxs-lookup"><span data-stu-id="01c45-124">If you try to run capable to promise (CTP) from a sales order when Planning Optimization is enabled, you will receive the following error message: *This operation triggered master planning that isn't supported when the Planning Optimization is enabled*.</span></span>

<span data-ttu-id="01c45-125">Esto está relacionado con una función pendiente que está planificada como parte del soporte para pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="01c45-125">This is related to a pending feature that is planned as part of the support for production orders.</span></span>

<span data-ttu-id="01c45-126">**Reparar:** Evite los cálculos de CTP cuando la Optimización de planificación esté habilitada hasta que esté disponible el soporte de CTP.</span><span class="sxs-lookup"><span data-stu-id="01c45-126">**Fix:** Avoid CTP calculations when Planning Optimization is enabled until CTP support is available.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01c45-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="01c45-127">Additional resources</span></span>

[<span data-ttu-id="01c45-128">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="01c45-128">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="01c45-129">Análisis de idoneidad de optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="01c45-129">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]