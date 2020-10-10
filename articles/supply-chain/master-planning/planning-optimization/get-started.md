---
title: Introducción a la optimización de la planificación
description: Este tema explica cómo empezar a usar la función de optimización de la planificación.
author: ChristianRytt
manager: tfehr
ms.date: 05/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 04b39469ccf4f088bb33bdfc73ce40eece6f5f2e
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "3887273"
---
# <a name="get-started-with-planning-optimization"></a><span data-ttu-id="c33fd-103">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="c33fd-103">Get started with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c33fd-104">La funcionalidad de optimización de la planificación no admite actualmente todas las características disponibles en el motor de planificación que se incorpora en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c33fd-104">The Planning Optimization functionality doesn't currently support all the features that are available in the planning engine that is built into Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c33fd-105">Por lo tanto, es importante que evalúe si la función que están disponible actualmente en la optimización de la planificación cumplirá sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="c33fd-105">Therefore, it's important that you evaluate whether the feature set that is currently available in Planning Optimization will meet your requirements.</span></span> <span data-ttu-id="c33fd-106">De forma predeterminada, la funcionalidad de optimización de la planificación no está activada Dynamics Lifecycle Services (LCS) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c33fd-106">By default, the Planning Optimization functionality isn't turned on in Dynamics Lifecycle Services (LCS) by default.</span></span> <span data-ttu-id="c33fd-107">Por lo tanto, tiene una oportunidad de realizar la evaluación antes de que se active.</span><span class="sxs-lookup"><span data-stu-id="c33fd-107">Therefore, you have an opportunity to do your evaluation before it's turned on.</span></span>

<span data-ttu-id="c33fd-108">Finalmente, la optimización de la planificación reemplazará al motor de planificación de Supply Chain Management integrado.</span><span class="sxs-lookup"><span data-stu-id="c33fd-108">Eventually, Planning Optimization will replace the existing built-in Supply Chain Management planning engine.</span></span>

<span data-ttu-id="c33fd-109">Antes de activar o desactivar la planificación de optimización, se recomienda encarecidamente que evalúe los resultados del análisis de aptitud de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="c33fd-109">Before you turn on Planning Optimization, we strongly recommend that you evaluate the results of the Planning Optimization fit analysis.</span></span> <span data-ttu-id="c33fd-110">Para obtener más información, consulte [Análisis de aptitud de optimización de la planificación](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="c33fd-110">For more information, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

### <a name="availability"></a><span data-ttu-id="c33fd-111">Disponibilidad</span><span class="sxs-lookup"><span data-stu-id="c33fd-111">Availability</span></span>
<span data-ttu-id="c33fd-112">Optimización de planificación está disponible actualmente en las siguientes geografías de Azure: Estados Unidos, Canadá, Europa, Reino Unido y Australia.</span><span class="sxs-lookup"><span data-stu-id="c33fd-112">Planning Optimization is currently available in the following Azure geographies: United States, Canada, Europe, United Kingdom, and Australia.</span></span> <span data-ttu-id="c33fd-113">Si intenta instalar el complemento desde otra región geográfica, LCS mostrará un mensaje que indica que esta ubicación geográfica no es compatible.</span><span class="sxs-lookup"><span data-stu-id="c33fd-113">If you try to install the add-in from another geographic region, then LCS will show a message that this geographic is not supported.</span></span>

<span data-ttu-id="c33fd-114">Tenga en cuenta que Optimización de planificación no admite implementaciones locales de Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c33fd-114">Note that Planning Optimization does not support on-premises deployments of Dynamics 365 Supply Chain Management.</span></span>

### <a name="licensing"></a><span data-ttu-id="c33fd-115">Licencias</span><span class="sxs-lookup"><span data-stu-id="c33fd-115">Licensing</span></span>

<span data-ttu-id="c33fd-116">Si puede ejecutar con la planificación maestra con su licencia actual, no es necesario comprar una licencia adicional de empezar a usar la optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="c33fd-116">If you can run master planning by using your current license, you don't have to buy an additional license to start to use Planning Optimization.</span></span>

### <a name="install-the-add-in"></a><span data-ttu-id="c33fd-117">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="c33fd-117">Install the add-in</span></span>

<span data-ttu-id="c33fd-118">Para usar la optimización de la planificación, instale el complemento de optimización de la planificación para Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c33fd-118">To use Planning Optimization, install the Planning Optimization Add-in for Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c33fd-119">Puede obtener acceso al complemento desde su proyecto de LCS y activar la funcionalidad de optimización de la planificación desde la interfaz de usuario (IU) de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c33fd-119">You can access the add-in from your LCS project and turn on the Planning Optimization functionality from the Supply Chain Management user interface (UI).</span></span>

> [!NOTE]
> <span data-ttu-id="c33fd-120">El requisito para Optimización de la planificación es un entorno de alta disponibilidad habilitado para LCS, nivel 2 o superior (no un entorno OneBox), con Dynamics 365 Supply Chain Management, versión 10.0.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="c33fd-120">The requirement for Planning Optimization is an LCS enabled high-availability environment, tier 2 or higher (not a OneBox environment), with Dynamics 365 Supply Chain Management version 10.0.7 or later.</span></span> <span data-ttu-id="c33fd-121">Si intenta instalar el complemento en un entorno OneBox, la instalación no se completará y deberá cancelarla.</span><span class="sxs-lookup"><span data-stu-id="c33fd-121">If you try to install the add-in on a OneBox environment, the installation will not complete and you will need to cancel the installation.</span></span>

1. <span data-ttu-id="c33fd-122">Inicie sesión en LCS y abra el entorno deseado.</span><span class="sxs-lookup"><span data-stu-id="c33fd-122">Sign in to LCS, and open the desired environment.</span></span>
1. <span data-ttu-id="c33fd-123">Vaya a **Detalles completos**.</span><span class="sxs-lookup"><span data-stu-id="c33fd-123">Go to **Full details**.</span></span>
1. <span data-ttu-id="c33fd-124">Desplácese hacia abajo hasta la ficha desplegable **Complementos del entorno**.</span><span class="sxs-lookup"><span data-stu-id="c33fd-124">Scroll down to the **Environment add-ins** FastTab.</span></span>
1. <span data-ttu-id="c33fd-125">Seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="c33fd-125">Select **Install a new add-in**.</span></span>
1. <span data-ttu-id="c33fd-126">Seleccione **optimización de la planificación**.</span><span class="sxs-lookup"><span data-stu-id="c33fd-126">Select **Planning Optimization**.</span></span>
1. <span data-ttu-id="c33fd-127">Siga la guía de instalación y acepte los términos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="c33fd-127">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="c33fd-128">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="c33fd-128">Select **Install**.</span></span>
1. <span data-ttu-id="c33fd-129">En la ficha desplegable **Complementos del entorno** debería ver que se está instalando Planning Optimization.</span><span class="sxs-lookup"><span data-stu-id="c33fd-129">On the **Environment add-ins** FastTab you should see that Planning Optimization is installing.</span></span>
1. <span data-ttu-id="c33fd-130">Después de unos minutos, **Instalando** debería cambiar a **Instalado** (es posible que deba actualizar la página).</span><span class="sxs-lookup"><span data-stu-id="c33fd-130">After a few minutes **Installing** should change to **Installed** (you may need to refresh the page).</span></span> <span data-ttu-id="c33fd-131">Cuando está instalado, está listo para activar la Optimización de planificación en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c33fd-131">When installed, you are ready to activate Planning Optimization in Dynamics 365 Supply Chain Management.</span></span>

### <a name="planning-optimization-integration"></a><span data-ttu-id="c33fd-132">Integración de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="c33fd-132">Planning Optimization integration</span></span>

<span data-ttu-id="c33fd-133">Para configurar si el complemento de optimización de la planificación se debe usar para la planificación maestra, vaya **Planificación maestra** \> **Configuración** \> **Parámetros de optimización de la planificación**.</span><span class="sxs-lookup"><span data-stu-id="c33fd-133">To configure whether the Planning Optimization Add-in should be used for master planning, go to **Master planning** \> **Setup** \> **Planning Optimization parameters**.</span></span>

#### <a name="connection-status"></a><span data-ttu-id="c33fd-134">Estado de conexión</span><span class="sxs-lookup"><span data-stu-id="c33fd-134">Connection status</span></span>

<span data-ttu-id="c33fd-135">El estado de la conexión indica el estado actual de la conexión entre Supply Chain Management y el servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="c33fd-135">The connection status indicates the current status of the connection between Supply Chain Management and the Planning Optimization service.</span></span> <span data-ttu-id="c33fd-136">La tabla siguiente muestra los posibles valores.</span><span class="sxs-lookup"><span data-stu-id="c33fd-136">The following table shows the possible values.</span></span>

| <span data-ttu-id="c33fd-137">Estado de conexión</span><span class="sxs-lookup"><span data-stu-id="c33fd-137">Connection status</span></span> | <span data-ttu-id="c33fd-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="c33fd-138">Description</span></span> | <span data-ttu-id="c33fd-139">¿Se puede usar optimización de la planificación?</span><span class="sxs-lookup"><span data-stu-id="c33fd-139">Can Planning Optimization be used?</span></span> |
|---|---|---|
| <span data-ttu-id="c33fd-140">Conectada</span><span class="sxs-lookup"><span data-stu-id="c33fd-140">Connected</span></span> | <span data-ttu-id="c33fd-141">Una conexión se ha establecido entre el servicio de optimización de la planificación y Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c33fd-141">A connection has been established between the Planning Optimization service and Supply Chain Management.</span></span> | <span data-ttu-id="c33fd-142">Sí</span><span class="sxs-lookup"><span data-stu-id="c33fd-142">Yes</span></span> |
| <span data-ttu-id="c33fd-143">Habilitando conexión</span><span class="sxs-lookup"><span data-stu-id="c33fd-143">Enabling connection</span></span> | <span data-ttu-id="c33fd-144">Una petición para activar la conexión al servicio de optimización de la planificación está actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="c33fd-144">A request to turn on the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="c33fd-145">No</span><span class="sxs-lookup"><span data-stu-id="c33fd-145">No</span></span> |
| <span data-ttu-id="c33fd-146">Desconectado</span><span class="sxs-lookup"><span data-stu-id="c33fd-146">Disconnected</span></span> | <span data-ttu-id="c33fd-147">No hay conexión al servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="c33fd-147">There is no connection to the Planning Optimization service.</span></span> <span data-ttu-id="c33fd-148">La conexión se puede cambiar desde LCS, según lo descrito antes en este tema.</span><span class="sxs-lookup"><span data-stu-id="c33fd-148">The connection can be turned on from LCS, as described earlier in this topic.</span></span> | <span data-ttu-id="c33fd-149">No</span><span class="sxs-lookup"><span data-stu-id="c33fd-149">No</span></span> |
| <span data-ttu-id="c33fd-150">Deshabilitando conexión</span><span class="sxs-lookup"><span data-stu-id="c33fd-150">Disabling connection</span></span> | <span data-ttu-id="c33fd-151">Una petición para desactivar la conexión al servicio de optimización de la planificación está actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="c33fd-151">A request to turn off the connection to the Planning Optimization service is currently in progress.</span></span> | <span data-ttu-id="c33fd-152">No</span><span class="sxs-lookup"><span data-stu-id="c33fd-152">No</span></span> |
| <span data-ttu-id="c33fd-153">Obteniendo estado</span><span class="sxs-lookup"><span data-stu-id="c33fd-153">Getting status</span></span> | <span data-ttu-id="c33fd-154">El sistema está esperando por la información del estado del servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="c33fd-154">The system is waiting for status information from the Planning Optimization service.</span></span> | <span data-ttu-id="c33fd-155">No</span><span class="sxs-lookup"><span data-stu-id="c33fd-155">No</span></span> |

#### <a name="the-use-planning-optimization-option"></a><span data-ttu-id="c33fd-156">La opción de optimización de la planificación de uso</span><span class="sxs-lookup"><span data-stu-id="c33fd-156">The Use Planning Optimization option</span></span>

<span data-ttu-id="c33fd-157">Si se establece la opción **optimización de la planificación de uso** se determina el motor de planificación que se usa para la planificación maestra:</span><span class="sxs-lookup"><span data-stu-id="c33fd-157">The setting of the **Use Planning Optimization** option determines which planning engine is used for master planning:</span></span>

- <span data-ttu-id="c33fd-158">**Sí**: la optimización de la planificación se utiliza para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="c33fd-158">**Yes** – Planning Optimization is used for master planning.</span></span>
- <span data-ttu-id="c33fd-159">**No**: el motor de planificación de Supply Chain Management integrado se utiliza para la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="c33fd-159">**No** – The built-in Supply Chain Management planning engine is used for master planning.</span></span>

> [!NOTE]
> <span data-ttu-id="c33fd-160">Si se activan los trabajos por lotes existentes de planificación creados para el motor de planificación de Supply Chain Management integrado se activan mientras que la opción **optimización de la planificación de uso** está establecida en **Sí**, estos trabajos fallarán.</span><span class="sxs-lookup"><span data-stu-id="c33fd-160">If existing planning batch jobs that were created for the built-in Supply Chain Management planning engine are triggered while the **Use Planning Optimization** option is set to **Yes**, those jobs will fail.</span></span>

### <a name="integration-with-the-setup"></a><span data-ttu-id="c33fd-161">Integración con la configuración</span><span class="sxs-lookup"><span data-stu-id="c33fd-161">Integration with the setup</span></span>

<span data-ttu-id="c33fd-162">Si la vista previa de optimización de la planificación está activada, la planificación maestra se realiza mediante el complemento de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="c33fd-162">If the Planning Optimization preview is turned on, master planning is done by using the Planning Optimization Add-in.</span></span> <span data-ttu-id="c33fd-163">En este caso, se ven afectados los resultados y las características de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="c33fd-163">In this case, master planning results and features are affected.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c33fd-164">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c33fd-164">Additional resources</span></span>

[<span data-ttu-id="c33fd-165">Términos y condiciones de la vista previa</span><span class="sxs-lookup"><span data-stu-id="c33fd-165">Terms and conditions for the preview</span></span>](https://go.microsoft.com/fwlink/?linkid=2015274)

[<span data-ttu-id="c33fd-166">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="c33fd-166">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="c33fd-167">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="c33fd-167">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="c33fd-168">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="c33fd-168">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="c33fd-169">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="c33fd-169">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="c33fd-170">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="c33fd-170">Cancel a planning job</span></span>](cancel-planning-job.md)
