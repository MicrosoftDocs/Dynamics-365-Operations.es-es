---
title: Introducción a la optimización de la planificación
description: Este tema explica cómo empezar a usar la función de optimización de la planificación.
author: ChristianRytt
manager: AnnBe
ms.date: 02/10/2020
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
ms.openlocfilehash: 3e64699005387adcc92e2e7c9fefad68a9de85c0
ms.sourcegitcommit: a688c864fc609e35072ad8fd2c01d71f6a5ee7b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "3076141"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="70a1d-103">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="70a1d-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

<span data-ttu-id="70a1d-104">La funcionalidad de optimización de la planificación no admite actualmente todas las características disponibles en el motor de planificación que se incorpora en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="70a1d-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="70a1d-105">Por lo tanto, es importante que evalúe si la función que están disponible actualmente en la optimización de la planificación cumplirá sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="70a1d-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="70a1d-106">De forma predeterminada, la funcionalidad de optimización de la planificación no está activada Dynamics Lifecycle Services (LCS) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="70a1d-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="70a1d-107">Por lo tanto, tiene una oportunidad de realizar la evaluación antes de que se active.</span><span class="sxs-lookup"><span data-stu-id="70a1d-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="70a1d-108">Finalmente, la optimización de la planificación reemplazará al motor de planificación de Supply Chain Management integrado.</span><span class="sxs-lookup"><span data-stu-id="70a1d-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="70a1d-109">Antes de activar o desactivar la planificación de optimización, se recomienda encarecidamente que evalúe los resultados del análisis de aptitud de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="70a1d-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="70a1d-110">Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="70a1d-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="licensing"></a><span data-ttu-id="70a1d-111">Licencias</span><span class="sxs-lookup"><span data-stu-id="70a1d-111">Licensing</span></span>

<span data-ttu-id="70a1d-112">Si puede ejecutar con la planificación maestra con su licencia actual, no es necesario comprar una licencia adicional de empezar a usar la optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="70a1d-112">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="70a1d-113">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="70a1d-113">Install the add-in</span></span>

<span data-ttu-id="70a1d-114">Para usar la optimización de la planificación, instale el complemento de optimización de la planificación para Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="70a1d-114">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="70a1d-115">Puede obtener acceso al complemento desde su proyecto de LCS y activar la funcionalidad de optimización de la planificación desde la interfaz de usuario (IU) de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="70a1d-115">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="70a1d-116">El requisito para la optimización de la planificación es un entorno de alta disponibilidad habilitado para LCS (no un entorno OneBox), con Dynamics 365 Supply Chain Management versión 10.0.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="70a1d-116">The requirement for Planning Optimization is an LCS enabled high-availability environment (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span>

1. <span data-ttu-id="70a1d-117">Inicie sesión en LCS y abra el entorno deseado.</span><span class="sxs-lookup"><span data-stu-id="70a1d-117">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="70a1d-118">Vaya a **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="70a1d-118">Go to **Full details**.</span></span>
1. <span data-ttu-id="70a1d-119">Desplácese hacia abajo hasta la ficha desplegable **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="70a1d-119">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="70a1d-120">Seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="70a1d-120">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="70a1d-121">Seleccione **optimización de la planificación**.</span><span class="sxs-lookup"><span data-stu-id="70a1d-121">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="70a1d-122">Siga la guía de instalación y acepte los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="70a1d-122">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="70a1d-123">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="70a1d-123">Select **Install**.</span></span>
1. <span data-ttu-id="70a1d-124">En la ficha desplegable **Complementos del entorno** debería ver que se está instalando Planning Optimization.</span><span class="sxs-lookup"><span data-stu-id="70a1d-124">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="70a1d-125">Después de unos minutos, **Instalando** debería cambiar a **Instalado** (es posible que deba actualizar la página).</span><span class="sxs-lookup"><span data-stu-id="70a1d-125">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="70a1d-126">Cuando está instalado, está listo para activar la Optimización de planificación en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="70a1d-126">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="70a1d-127">Integración de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="70a1d-127">Planning Optimization integration</span></span>

<span data-ttu-id="70a1d-128">Para configurar si el complemento de optimización de la planificación se debe usar para la planificación maestra, vaya **Planificación maestra** \> **Configuración** \> **Parámetros de optimización de la planificación**.</span><span class="sxs-lookup"><span data-stu-id="70a1d-128">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="70a1d-129">Estado de conexión</span><span class="sxs-lookup"><span data-stu-id="70a1d-129">Connection status</span></span>

<span data-ttu-id="70a1d-130">El estado de la conexión indica el estado actual de la conexión entre Supply Chain Management y el servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="70a1d-130">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="70a1d-131">La tabla siguiente muestra los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="70a1d-131">The following table shows the possible values.</span></span>

| <span data-ttu-id="70a1d-132">Estado de conexión</span><span class="sxs-lookup"><span data-stu-id="70a1d-132">Connection status</span></span> | <span data-ttu-id="70a1d-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="70a1d-133">Description</span></span> | <span data-ttu-id="70a1d-134">¿Se puede usar optimización de la planificación?</span><span class="sxs-lookup"><span data-stu-id="70a1d-134">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="70a1d-135">Conectada</span><span class="sxs-lookup"><span data-stu-id="70a1d-135">Connected</span></span> | <span data-ttu-id="70a1d-136">Una conexión se ha establecido entre el servicio de optimización de la planificación y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="70a1d-136">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="70a1d-137">Sí</span><span class="sxs-lookup"><span data-stu-id="70a1d-137">Yes</span></span> |
| <span data-ttu-id="70a1d-138">Habilitando conexión</span><span class="sxs-lookup"><span data-stu-id="70a1d-138">Enabling connection</span></span> | <span data-ttu-id="70a1d-139">Una petición para activar la conexión al servicio de optimización de la planificación está actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="70a1d-139">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="70a1d-140">No</span><span class="sxs-lookup"><span data-stu-id="70a1d-140">No</span></span> |
| <span data-ttu-id="70a1d-141">Desconectado</span><span class="sxs-lookup"><span data-stu-id="70a1d-141">Disconnected</span></span> | <span data-ttu-id="70a1d-142">No hay conexión al servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="70a1d-142">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="70a1d-143">La conexión se puede cambiar desde LCS, según lo descrito antes en este tema.</span><span class="sxs-lookup"><span data-stu-id="70a1d-143">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="70a1d-144">No</span><span class="sxs-lookup"><span data-stu-id="70a1d-144">No</span></span> |
| <span data-ttu-id="70a1d-145">Deshabilitando conexión</span><span class="sxs-lookup"><span data-stu-id="70a1d-145">Disabling connection</span></span> | <span data-ttu-id="70a1d-146">Una petición para desactivar la conexión al servicio de optimización de la planificación está actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="70a1d-146">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="70a1d-147">No</span><span class="sxs-lookup"><span data-stu-id="70a1d-147">No</span></span> |
| <span data-ttu-id="70a1d-148">Obteniendo estado</span><span class="sxs-lookup"><span data-stu-id="70a1d-148">Getting status</span></span> | <span data-ttu-id="70a1d-149">El sistema está esperando por la información del estado del servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="70a1d-149">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="70a1d-150">No</span><span class="sxs-lookup"><span data-stu-id="70a1d-150">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="70a1d-151">La opción de optimización de la planificación de uso</span><span class="sxs-lookup"><span data-stu-id="70a1d-151">The Use Planning Optimization option</span></span>

<span data-ttu-id="70a1d-152">Si se establece la opción **optimización de la planificación de uso** se determina el motor de planificación que se usa para la planificación maestra:</span><span class="sxs-lookup"><span data-stu-id="70a1d-152">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="70a1d-153">**Sí**: la optimización de la planificación se utiliza para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="70a1d-153">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="70a1d-154">**No**: el motor de planificación de Supply Chain Management integrado se utiliza para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="70a1d-154">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="70a1d-155">Si se activan los trabajos por lotes existentes de planificación creados para el motor de planificación de Supply Chain Management integrado se activan mientras que la opción **optimización de la planificación de uso** está establecida en **Sí**, estos trabajos fallarán.</span><span class="sxs-lookup"><span data-stu-id="70a1d-155">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="70a1d-156">Integración con la configuración</span><span class="sxs-lookup"><span data-stu-id="70a1d-156">Integration with the setup</span></span>

<span data-ttu-id="70a1d-157">Si la vista previa de optimización de la planificación está activada, la planificación maestra se realiza mediante el complemento de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="70a1d-157">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="70a1d-158">En este caso, se ven afectados los resultados y las características de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="70a1d-158">In this case, master planning results and features are affected.</span></span>

## <a name="related-resources"></a><span data-ttu-id="70a1d-159">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="70a1d-159">Related resources</span></span>

[<span data-ttu-id="70a1d-160">Términos y condiciones de la vista previa</span><span class="sxs-lookup"><span data-stu-id="70a1d-160">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="70a1d-161">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="70a1d-161">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="70a1d-162">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="70a1d-162">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="70a1d-163">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="70a1d-163">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="70a1d-164">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="70a1d-164">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="70a1d-165">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="70a1d-165">Cancel a planning job</span></span>](cancel-planning-job.md)
