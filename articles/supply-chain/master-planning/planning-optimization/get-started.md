---
title: Introducción a la optimización de la planificación
description: Este tema explica cómo empezar a usar la función de optimización de la planificación.
author: ChristianRytt
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 37c2acb2397b2a0ad69272c0645bd200a8d7910d
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774043"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="d575c-103">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="d575c-103">Get started with Planning Optimization</span></span>

<span data-ttu-id="d575c-104">La funcionalidad de optimización de la planificación no admite actualmente todas las características disponibles en el motor de planificación que se incorpora en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d575c-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d575c-105">Por lo tanto, es importante que evalúe si la función que están disponible actualmente en la optimización de la planificación cumplirá sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="d575c-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="d575c-106">De forma predeterminada, la funcionalidad de optimización de la planificación no está activada Dynamics Lifecycle Services (LCS) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d575c-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="d575c-107">Por lo tanto, tiene una oportunidad de realizar la evaluación antes de que se active.</span><span class="sxs-lookup"><span data-stu-id="d575c-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="d575c-108">Finalmente, la optimización de la planificación reemplazará al motor de planificación de Supply Chain Management integrado.</span><span class="sxs-lookup"><span data-stu-id="d575c-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="d575c-109">Antes de activar o desactivar la planificación de optimización, se recomienda encarecidamente que evalúe los resultados del análisis de aptitud de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d575c-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="d575c-110">Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="d575c-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="d575c-111">Licencias</span><span class="sxs-lookup"><span data-stu-id="d575c-111">Licensing</span></span>

<span data-ttu-id="d575c-112">Si puede ejecutar con la planificación maestra con su licencia actual, no es necesario comprar una licencia adicional de empezar a usar la optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d575c-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="d575c-113">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="d575c-113">Install the add-in</span></span>

<span data-ttu-id="d575c-114">Para usar la optimización de la planificación, instale el complemento de optimización de la planificación para Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d575c-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="d575c-115">Puede obtener acceso al complemento desde su proyecto de LCS y activar la funcionalidad de optimización de la planificación desde la interfaz de usuario (IU) de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d575c-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

1. <span data-ttu-id="d575c-116">Inicie sesión en LCS y abra el entorno deseado.</span><span class="sxs-lookup"><span data-stu-id="d575c-116">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="d575c-117">Vaya a **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="d575c-117">Go to **Full details**.</span></span>
1. <span data-ttu-id="d575c-118">Seleccione **Mantener** o descienda hasta la ficha desplegable **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="d575c-118">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="d575c-119">Seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="d575c-119">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="d575c-120">Seleccione **optimización de la planificación**.</span><span class="sxs-lookup"><span data-stu-id="d575c-120">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="d575c-121">Siga la guía de instalación y acepte los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="d575c-121">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="d575c-122">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d575c-122">Select **Install**.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="d575c-123">Integración de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="d575c-123">Planning Optimization integration</span></span>

<span data-ttu-id="d575c-124">Para configurar si el complemento de optimización de la planificación se debe usar para la planificación maestra, vaya **Planificación maestra** \> **Configuración** \> **Integración de la optimización de la planificación** \> **Parámetros de integración**.</span><span class="sxs-lookup"><span data-stu-id="d575c-124">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization integration** \> **Integration parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="d575c-125">Estado de conexión</span><span class="sxs-lookup"><span data-stu-id="d575c-125">Connection status</span></span>

<span data-ttu-id="d575c-126">El estado de la conexión indica el estado actual de la conexión entre Supply Chain Management y el servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d575c-126">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="d575c-127">La tabla siguiente muestra los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="d575c-127">The following table shows the possible values.</span></span>

| <span data-ttu-id="d575c-128">Estado de conexión</span><span class="sxs-lookup"><span data-stu-id="d575c-128">Connection status</span></span> | <span data-ttu-id="d575c-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="d575c-129">Description</span></span> | <span data-ttu-id="d575c-130">¿Se puede usar optimización de la planificación?</span><span class="sxs-lookup"><span data-stu-id="d575c-130">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="d575c-131">Conectada</span><span class="sxs-lookup"><span data-stu-id="d575c-131">Connected</span></span> | <span data-ttu-id="d575c-132">Una conexión se ha establecido entre el servicio de optimización de la planificación y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d575c-132">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="d575c-133">Sí</span><span class="sxs-lookup"><span data-stu-id="d575c-133">Yes</span></span> |
| <span data-ttu-id="d575c-134">Habilitando conexión</span><span class="sxs-lookup"><span data-stu-id="d575c-134">Enabling connection</span></span> | <span data-ttu-id="d575c-135">Una petición para activar la conexión al servicio de optimización de la planificación está actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="d575c-135">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="d575c-136">No</span><span class="sxs-lookup"><span data-stu-id="d575c-136">No</span></span> |
| <span data-ttu-id="d575c-137">Desconectado</span><span class="sxs-lookup"><span data-stu-id="d575c-137">Disconnected</span></span> | <span data-ttu-id="d575c-138">No hay conexión al servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d575c-138">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="d575c-139">La conexión se puede cambiar desde LCS, según lo descrito antes en este tema.</span><span class="sxs-lookup"><span data-stu-id="d575c-139">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="d575c-140">No</span><span class="sxs-lookup"><span data-stu-id="d575c-140">No</span></span> |
| <span data-ttu-id="d575c-141">Deshabilitando conexión</span><span class="sxs-lookup"><span data-stu-id="d575c-141">Disabling connection</span></span> | <span data-ttu-id="d575c-142">Una petición para desactivar la conexión al servicio de optimización de la planificación está actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="d575c-142">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="d575c-143">No</span><span class="sxs-lookup"><span data-stu-id="d575c-143">No</span></span> |
| <span data-ttu-id="d575c-144">Obteniendo estado</span><span class="sxs-lookup"><span data-stu-id="d575c-144">Getting status</span></span> | <span data-ttu-id="d575c-145">El sistema está esperando por la información del estado del servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d575c-145">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="d575c-146">No</span><span class="sxs-lookup"><span data-stu-id="d575c-146">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="d575c-147">La opción de optimización de la planificación de uso</span><span class="sxs-lookup"><span data-stu-id="d575c-147">The Use Planning Optimization option</span></span>

<span data-ttu-id="d575c-148">Si se establece la opción **optimización de la planificación de uso** se determina el motor de planificación que se usa para la planificación maestra:</span><span class="sxs-lookup"><span data-stu-id="d575c-148">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="d575c-149">**Sí**: la optimización de la planificación se utiliza para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="d575c-149">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="d575c-150">**No**: el motor de planificación de Supply Chain Management integrado se utiliza para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="d575c-150">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="d575c-151">Si se activan los trabajos por lotes existentes de planificación creados para el motor de planificación de Supply Chain Management integrado se activan mientras que la opción **optimización de la planificación de uso** está establecida en **Sí**, estos trabajos fallarán.</span><span class="sxs-lookup"><span data-stu-id="d575c-151">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="d575c-152">Integración con la configuración</span><span class="sxs-lookup"><span data-stu-id="d575c-152">Integration with the setup</span></span>

<span data-ttu-id="d575c-153">Si la vista previa de optimización de la planificación está activada, la planificación maestra se realiza mediante el complemento de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="d575c-153">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="d575c-154">En este caso, se ven afectados los resultados y las características de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="d575c-154">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="d575c-155">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="d575c-155">Related resources</span></span>

[<span data-ttu-id="d575c-156">Términos y condiciones de la vista previa</span><span class="sxs-lookup"><span data-stu-id="d575c-156">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="d575c-157">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="d575c-157">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="d575c-158">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="d575c-158">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="d575c-159">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="d575c-159">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="d575c-160">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="d575c-160">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="d575c-161">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="d575c-161">Cancel a planning job</span></span>](cancel-planning-job.md)
