---
title: Proporcionar guías de realidad mixta para trabajadores en producción
description: Este tema explica cómo integrar el módulo de gestión de producción en Microsoft Dynamics 365 Supply Chain Management con Dynamics 365 Guides.
author: cabeln
manager: tfehr
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkGuidesManufacturing
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 61943
ms.assetid: a3847f07-fca4-4140-a26f-d83c6ac68dde
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: cabeln
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 14645f592275d07a6b633146bb6da35b89c1bf77
ms.sourcegitcommit: 6d2fc497c8a7f49c48e7662995e27b5f8cc10296
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000987"
---
# <a name="provide-mixed-reality-guides-for-workers-in-production"></a><span data-ttu-id="f2610-103">Proporcionar guías de realidad mixta para trabajadores en producción</span><span class="sxs-lookup"><span data-stu-id="f2610-103">Provide mixed-reality Guides for workers in production</span></span>

<span data-ttu-id="f2610-104">Los trabajadores en los procesos de producción se beneficiarán de las instrucciones pertinentes que se brindan en el momento adecuado en el contexto de su trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-104">Workers in production processes will benefit from relevant instructions that are provided at the right time in the context of their work.</span></span> <span data-ttu-id="f2610-105">Hay *instrucciones* aplicables en varios dominios de trabajo, que incluyen: montaje, servicio, operaciones, certificación y seguridad.</span><span class="sxs-lookup"><span data-stu-id="f2610-105">*Instructions* apply in several domains of work, including: assembly, service, operations, certification, and safety.</span></span> <span data-ttu-id="f2610-106">En todas estas funciones comerciales básicas, las instrucciones de capacitación continua pueden ayudar a capacitar a los trabajadores para que logren más y trabajen mejor.</span><span class="sxs-lookup"><span data-stu-id="f2610-106">Across all of these core business functions, ongoing training instructions can help empower workers to achieve more and work better.</span></span>

## <a name="introduction"></a><span data-ttu-id="f2610-107">Introducción</span><span class="sxs-lookup"><span data-stu-id="f2610-107">Introduction</span></span>

<span data-ttu-id="f2610-108">Puede proporcionar instrucciones de diferentes formas.</span><span class="sxs-lookup"><span data-stu-id="f2610-108">You can provide instructions in different ways.</span></span> <span data-ttu-id="f2610-109">Un sistema eficiente que se envía fuera de la caja utiliza [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span><span class="sxs-lookup"><span data-stu-id="f2610-109">One efficient system that ships out of the box uses [Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/).</span></span>

<span data-ttu-id="f2610-110">Dynamics 365 Guides puede ayudar a capacitar a sus empleados con el aprendizaje práctico.</span><span class="sxs-lookup"><span data-stu-id="f2610-110">Dynamics 365 Guides can help empower your employees with hands-on learning.</span></span> <span data-ttu-id="f2610-111">Puede definir procesos estandarizados con instrucciones paso a paso que guíen a sus empleados hacia las herramientas y piezas que necesitan y les muestren cómo utilizar estas herramientas en situaciones de trabajo reales.</span><span class="sxs-lookup"><span data-stu-id="f2610-111">You can define standardized processes with step-by-step instructions that guide your employees to the tools and parts they need and show employees how to use these tools in real work situations.</span></span>

<span data-ttu-id="f2610-112">Puede adjuntar guías a varios aspectos del control de producción, que incluyen:</span><span class="sxs-lookup"><span data-stu-id="f2610-112">You can attach guides to various aspects of production control including:</span></span>

- [<span data-ttu-id="f2610-113">Recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-113">Resources</span></span>](#resources)
- [<span data-ttu-id="f2610-114">Grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-114">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="f2610-115">Productos emitidos</span><span class="sxs-lookup"><span data-stu-id="f2610-115">Released products</span></span>](#released-products)
- [<span data-ttu-id="f2610-116">Fórmulas </span><span class="sxs-lookup"><span data-stu-id="f2610-116">Formulas</span></span>](#formulas)
- [<span data-ttu-id="f2610-117">Versiones de fórmula</span><span class="sxs-lookup"><span data-stu-id="f2610-117">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="f2610-118">Listas de materiales (LMAT)</span><span class="sxs-lookup"><span data-stu-id="f2610-118">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="f2610-119">Versiones de listas de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-119">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="f2610-120">Rutas</span><span class="sxs-lookup"><span data-stu-id="f2610-120">Routes</span></span>](#routes)
- [<span data-ttu-id="f2610-121">Versiones de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-121">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="f2610-122">Relaciones de operación de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-122">Route operation relations</span></span>](#route-operation-relations)

> [!NOTE]
> <span data-ttu-id="f2610-123">También puede adjuntar guías con Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="f2610-123">You can also attach Guides with Asset Management.</span></span> <span data-ttu-id="f2610-124">Para obtener más información sobre esa opción, consulte [Integrar Dynamics 365 Supply Chain Management (Administración de activos) con Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span><span class="sxs-lookup"><span data-stu-id="f2610-124">For more information about that option, see [Integrate Dynamics 365 Supply Chain Management (Asset Management) with Dynamics 365 Guides](../asset-management/asset-management-guides-integration.md).</span></span>

<span data-ttu-id="f2610-125">Cuando un trabajador de primera línea elige un trabajo en el piso de producción a través de Supply Chain Management, el trabajador puede ver [las guías relevantes](#logic) en la tarjeta de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-125">When a first-line worker chooses a job on the shop floor through Supply Chain Management, the worker can see [the relevant guides](#logic) on the job card.</span></span> <span data-ttu-id="f2610-126">Cuando el trabajador elige una guía específica, se muestra un código QR para esa guía en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="f2610-126">When the worker chooses a specific guide, a QR code for that guide is shown on the screen.</span></span> <span data-ttu-id="f2610-127">El trabajador luego usa su HoloLens para escanear el código QR, que inicia Guías y muestra las instrucciones necesarias.</span><span class="sxs-lookup"><span data-stu-id="f2610-127">The worker then uses their HoloLens to scan the QR code, which launches Guides and shows the required instructions.</span></span>

<span data-ttu-id="f2610-128">Las siguientes subsecciones describen algunos escenarios seleccionados en los que las empresas de todas las industrias pueden ver el mayor valor al usar Guías para presentar instrucciones para la fabricación.</span><span class="sxs-lookup"><span data-stu-id="f2610-128">The following subsections describe a few selected scenarios where companies across industries can see the biggest value when using Guides to present instructions for manufacturing.</span></span>

### <a name="assembly"></a><span data-ttu-id="f2610-129">Ensamblado</span><span class="sxs-lookup"><span data-stu-id="f2610-129">Assembly</span></span>

<span data-ttu-id="f2610-130">![Utilizar guías en tareas de montaje](media/instruction-guides-hero-assembly.png "Utilizar guías en tareas de servicio")</span><span class="sxs-lookup"><span data-stu-id="f2610-130">![Use Guides in assembly tasks](media/instruction-guides-hero-assembly.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="f2610-131">Las instrucciones en las operaciones de montaje muestran a los trabajadores las herramientas y piezas que necesitan y cómo utilizarlas en situaciones de trabajo reales.</span><span class="sxs-lookup"><span data-stu-id="f2610-131">Instructions in assembly operations show workers the tools and parts they need and how to use them in real work situations.</span></span>

<span data-ttu-id="f2610-132">Los gerentes de producción pueden crear y asignar guías, por ejemplo, para [rutas de producción](routes-operations.md), [relaciones de operación](routes-operations.md#operation-relations) o [listas de materiales](bill-of-material-bom.md).</span><span class="sxs-lookup"><span data-stu-id="f2610-132">Production managers can create and assign Guides, for example, for [production routes](routes-operations.md), [operation relations](routes-operations.md#operation-relations), or [bills of material](bill-of-material-bom.md).</span></span> <span data-ttu-id="f2610-133">Los trabajadores encontrarán las instrucciones relevantes sobre la experiencia de operación respectiva en el piso de producción.</span><span class="sxs-lookup"><span data-stu-id="f2610-133">Workers will find the relevant instructions on the respective operation experience on the shop floor.</span></span>

### <a name="service"></a><span data-ttu-id="f2610-134">Servicio</span><span class="sxs-lookup"><span data-stu-id="f2610-134">Service</span></span>

<span data-ttu-id="f2610-135">![Utilizar guías en tareas de servicio](media/instruction-guides-hero-service.png "Utilizar guías en tareas de servicio")</span><span class="sxs-lookup"><span data-stu-id="f2610-135">![Use Guides in service tasks](media/instruction-guides-hero-service.png "Use Guides in service tasks")</span></span>

<span data-ttu-id="f2610-136">Equipe a los técnicos con instrucciones guiadas en el lugar de trabajo, eliminando la necesidad de programar visitas adicionales.</span><span class="sxs-lookup"><span data-stu-id="f2610-136">Equip technicians with guided instructions at the job site, eliminating the need to schedule additional visits.</span></span>

<span data-ttu-id="f2610-137">Los gerentes de servicio pueden asignar guías, por ejemplo, a [productos](../../commerce/product.md) que recorren rutinas de evaluación de la calidad.</span><span class="sxs-lookup"><span data-stu-id="f2610-137">Service managers can assign Guides, for example, to specific [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="quality"></a><span data-ttu-id="f2610-138">Calidad</span><span class="sxs-lookup"><span data-stu-id="f2610-138">Quality</span></span>

<span data-ttu-id="f2610-139">![Utilice guías en tareas de aseguramiento de la calidad](media/instruction-guides-hero-quality.png "Utilice guías en tareas de aseguramiento de la calidad")</span><span class="sxs-lookup"><span data-stu-id="f2610-139">![Use Guides in quality assurance tasks](media/instruction-guides-hero-quality.png "Use Guides in quality assurance tasks")</span></span>

<span data-ttu-id="f2610-140">Implemente nuevos procesos y garantice una mayor coherencia al convertir el conocimiento de los empleados en una herramienta repetible.</span><span class="sxs-lookup"><span data-stu-id="f2610-140">Rollout new processes and ensure increased consistency by turning employee knowledge into a repeatable tool.</span></span>

<span data-ttu-id="f2610-141">Los gerentes de control de calidad pueden asignar guías, por ejemplo, a [productos](../../commerce/product.md) que recorren rutinas de evaluación de la calidad.</span><span class="sxs-lookup"><span data-stu-id="f2610-141">Quality assurance managers can assign guides, for example, to [products](../../commerce/product.md) that walk through routines of quality assessment.</span></span>

### <a name="certifications"></a><span data-ttu-id="f2610-142">Certificaciones</span><span class="sxs-lookup"><span data-stu-id="f2610-142">Certifications</span></span>

<span data-ttu-id="f2610-143">![Utilice guías para tareas relacionadas con la certificación](media/instruction-guides-hero-certification.png "Utilice guías para tareas relacionadas con la certificación")</span><span class="sxs-lookup"><span data-stu-id="f2610-143">![Use Guides for certification related tasks](media/instruction-guides-hero-certification.png "Use Guides for certification related tasks")</span></span>

<span data-ttu-id="f2610-144">Asegúrese de que cada empleado cumpla con altos estándares identificando rápidamente quién necesita ayuda y dónde.</span><span class="sxs-lookup"><span data-stu-id="f2610-144">Ensure every employee meets high standards by quickly identifying who needs help and where.</span></span>

### <a name="safety"></a><span data-ttu-id="f2610-145">Seguridad</span><span class="sxs-lookup"><span data-stu-id="f2610-145">Safety</span></span>

<span data-ttu-id="f2610-146">![Utilice guías en las instrucciones de seguridad laboral](media/instruction-guides-hero-safety.png "Utilice guías en las instrucciones de seguridad laboral")</span><span class="sxs-lookup"><span data-stu-id="f2610-146">![Use Guides in work safety instructions](media/instruction-guides-hero-safety.png "Use Guides in work safety instructions")</span></span>

<span data-ttu-id="f2610-147">Proporcione instrucciones que recorran los procedimientos peligrosos virtualmente antes de intentarlo en el entorno físico.</span><span class="sxs-lookup"><span data-stu-id="f2610-147">Provide instructions that walk through dangerous procedures virtually before attempting in the physical environment.</span></span> <span data-ttu-id="f2610-148">Con un enfoque de realidad mixta, los trabajadores pueden experimentar procedimientos peligrosos de forma virtual.</span><span class="sxs-lookup"><span data-stu-id="f2610-148">With a mixed reality approach, workers can experience dangerous procedures virtually.</span></span>

<span data-ttu-id="f2610-149">Los gerentes de producción pueden proporcionar instrucciones de manejo dedicadas para el manejo de materiales peligrosos o procedimientos de manejo delicado al asignar instrucciones a [artículos del producto](../../commerce/product.md), [rutas](routes-operations.md) y [operaciones](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="f2610-149">Production managers can provide dedicated handling instructions for hazardous material handling or delicate handling procedures by assigning instructions to [product items](../../commerce/product.md), [routes](routes-operations.md), and [operations](routes-operations.md#operation-relations).</span></span>

## <a name="get-started-with-instructions-and-guides"></a><span data-ttu-id="f2610-150">Empiece con instrucciones y guías</span><span class="sxs-lookup"><span data-stu-id="f2610-150">Get started with instructions and Guides</span></span>

<span data-ttu-id="f2610-151">Para habilitar las instrucciones en los procesos de producción, Supply Chain Management proporciona una integración lista para usar con Dynamics 365 Guides.</span><span class="sxs-lookup"><span data-stu-id="f2610-151">To enable instructions in production processes, Supply Chain Management provides an out-of-the-box integration with Dynamics 365 Guides.</span></span> <span data-ttu-id="f2610-152">Se requiere una instancia de aplicación instalada y con licencia de Guides para crear, mantener y asignar instrucciones de realidad mixta a los activos y el trabajo de producción.</span><span class="sxs-lookup"><span data-stu-id="f2610-152">A licensed and installed application instance of Guides is required to build, maintain, and assign mixed reality instructions to production assets and work.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="f2610-153">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f2610-153">Prerequisites</span></span>

<span data-ttu-id="f2610-154">Para utilizar esta función, su sistema debe incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2610-154">To use this feature, your system must include the following:</span></span>

- <span data-ttu-id="f2610-155">Dynamics 365 Supply Chain Management versión 10.0.15 o posterior</span><span class="sxs-lookup"><span data-stu-id="f2610-155">Dynamics 365 Supply Chain Management version 10.0.15 or later</span></span>
- <span data-ttu-id="f2610-156">[Escritura dual](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) para las aplicaciones de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f2610-156">[Dual-write](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write) for Supply Chain Management apps.</span></span>
- <span data-ttu-id="f2610-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) versión 400.0.1.48 o posterior</span><span class="sxs-lookup"><span data-stu-id="f2610-157">[Dynamics 365 Guides](https://docs.microsoft.com/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 400.0.1.48 or later</span></span>

### <a name="turn-on-the-feature"></a><span data-ttu-id="f2610-158">Activar la característica</span><span class="sxs-lookup"><span data-stu-id="f2610-158">Turn on the feature</span></span>

<span data-ttu-id="f2610-159">Para que la función esté disponible en su sistema, debe habilitar sus claves de configuración.</span><span class="sxs-lookup"><span data-stu-id="f2610-159">To make the feature available on your system, you must enable its configuration keys.</span></span> <span data-ttu-id="f2610-160">Solo necesita hacer esto una vez.</span><span class="sxs-lookup"><span data-stu-id="f2610-160">You only need to do this once.</span></span> <span data-ttu-id="f2610-161">Para hacer esto, un administrador debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f2610-161">To do this, an administrator must do the following:</span></span>

1. <span data-ttu-id="f2610-162">Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f2610-162">Place your system into maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
1. <span data-ttu-id="f2610-163">Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.</span><span class="sxs-lookup"><span data-stu-id="f2610-163">Go to **System administration \> Setup \> License configuration**.</span></span>
1. <span data-ttu-id="f2610-164">Amplíe la sección **Realidad mixta** y luego seleccione la casilla **Guía de realidad mixta**.</span><span class="sxs-lookup"><span data-stu-id="f2610-164">Expand the **Mixed reality** section and then select the **Mixed reality guide** check box.</span></span>
1. <span data-ttu-id="f2610-165">Amplíe la sección **Gestión de producción** y luego seleccione la casilla **Instrucciones de producción**.</span><span class="sxs-lookup"><span data-stu-id="f2610-165">Expand the **Production management** section and then select the **Production instructions** check box.</span></span>
1. <span data-ttu-id="f2610-166">Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span><span class="sxs-lookup"><span data-stu-id="f2610-166">Turn off maintenance mode as described in [Maintenance mode](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).</span></span>
  
## <a name="configure-how-guides-appear-on-the-shop-floor"></a><span data-ttu-id="f2610-167">Configurar cómo aparecen las guías en el taller</span><span class="sxs-lookup"><span data-stu-id="f2610-167">Configure how Guides appear on the shop floor</span></span>

<span data-ttu-id="f2610-168">Para configurar cómo aparecen las guías en el taller, vaya a **Realidad mixta \> Dynamics 365 Guides \> Configurar la integración de guías**.</span><span class="sxs-lookup"><span data-stu-id="f2610-168">To configure how Guides appear on the shop floor, go to **Mixed Reality \> Dynamics 365 Guides \> Configure Guides integration**.</span></span>

<span data-ttu-id="f2610-169">![Configurar la integración de guías para la fabricación](media/instruction-guides-configure-integration.png "Configurar la integración de guías para la fabricación")</span><span class="sxs-lookup"><span data-stu-id="f2610-169">![Configure Guide integration for manufacturing](media/instruction-guides-configure-integration.png "Configure Guide integration for manufacturing")</span></span>

<span data-ttu-id="f2610-170">Establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f2610-170">Set the following fields:</span></span>

- <span data-ttu-id="f2610-171">**Subdominio de Common Data Service** : este campo ya debería mostrar un valor.</span><span class="sxs-lookup"><span data-stu-id="f2610-171">**Common Data Service subdomain** - This field should already show a value.</span></span> <span data-ttu-id="f2610-172">Este campo contiene el subdominio del entorno de Common Data Service en el que crea sus Guías.</span><span class="sxs-lookup"><span data-stu-id="f2610-172">This field holds the subdomain for the Common Data Service environment where you create your Guides.</span></span> <span data-ttu-id="f2610-173">El subdominio es la primera parte de la URL y normalmente lleva el nombre de su organización.</span><span class="sxs-lookup"><span data-stu-id="f2610-173">The subdomain is the first part of the URL and is typically named after your organization.</span></span> <span data-ttu-id="f2610-174">Por ejemplo, si su URL de Common Data Service es "contoso.crm4.dynamics.com", debe ingresar *contoso* aquí.</span><span class="sxs-lookup"><span data-stu-id="f2610-174">For example, if your Common Data Service URL is "contoso.crm4.dynamics.com", you should enter *contoso* here.</span></span> <span data-ttu-id="f2610-175">Este valor se utiliza para componer direcciones para sus guías y se codificará en los códigos QR.</span><span class="sxs-lookup"><span data-stu-id="f2610-175">This value is used to compose addresses for your guides and will be encoded into the QR codes.</span></span>
- <span data-ttu-id="f2610-176">**Tamaño del código QR** - Establezca el tamaño del código QR renderizado.</span><span class="sxs-lookup"><span data-stu-id="f2610-176">**QR code size** - Set the size of the rendered QR code.</span></span> <span data-ttu-id="f2610-177">Recomendamos elegir un tamaño que llene la mayor parte de la pantalla, pero no más.</span><span class="sxs-lookup"><span data-stu-id="f2610-177">We recommend choosing a size that will fill most of your display screen, but not more.</span></span> <span data-ttu-id="f2610-178">Típicamente, *15* es un buen valor.</span><span class="sxs-lookup"><span data-stu-id="f2610-178">Typically, *15* is a good value.</span></span>
- <span data-ttu-id="f2610-179">**Nivel de corrección de errores del código QR** - Establecer la granularidad del código QR.</span><span class="sxs-lookup"><span data-stu-id="f2610-179">**QR code error correction level** - Set the granularity of the QR code.</span></span> <span data-ttu-id="f2610-180">Una mayor granularidad puede ayudar a aumentar la confiabilidad del código, pero su **Tamaño de código QR** debe ser lo suficientemente grande para admitir el nivel de detalle requerido por el nivel de corrección seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f2610-180">Higher granularity can help increase the code's reliability, but your **QR code size** must be large enough to support the level of detail required by your selected correction level.</span></span>


> [!TIP]
> - <span data-ttu-id="f2610-181">Los tamaños de códigos QR que son demasiado grandes para su pantalla tardarán un poco más en renderizarse y luego se reducirán para adaptarse a su pantalla.</span><span class="sxs-lookup"><span data-stu-id="f2610-181">QR codes sizes that are too large for your display will take a bit longer to render and then be scaled down to fit your display.</span></span> <span data-ttu-id="f2610-182">Estos no proporcionan ningún beneficio.</span><span class="sxs-lookup"><span data-stu-id="f2610-182">These do not provide a benefit.</span></span>
> - <span data-ttu-id="f2610-183">Los tamaños de código QR que son demasiado pequeños pueden disminuir la capacidad de HoloLens para leer el código correctamente en algunos entornos.</span><span class="sxs-lookup"><span data-stu-id="f2610-183">QR code sizes that are too small may decrease the ability of HoloLens to read the code properly in some environments.</span></span>
> - <span data-ttu-id="f2610-184">Le recomendamos que pruebe la configuración de cada dispositivo que mostrará códigos QR para usuarios de HoloLens.</span><span class="sxs-lookup"><span data-stu-id="f2610-184">We recommend that you test the settings for each device that will display QR codes for HoloLens users.</span></span> <span data-ttu-id="f2610-185">Elija configuraciones que proporcionen suficiente legibilidad en el entorno de su taller.</span><span class="sxs-lookup"><span data-stu-id="f2610-185">Choose settings that provide sufficient readability in your shop floor environment.</span></span>  

## <a name="get-an-overview-of-all-guide-assignments"></a><span data-ttu-id="f2610-186">Obtenga una descripción general de todas las asignaciones de guías</span><span class="sxs-lookup"><span data-stu-id="f2610-186">Get an overview of all Guide assignments</span></span>

<span data-ttu-id="f2610-187">Utilice la página **Todas las guías** para ver la lista de todas las Guías disponibles en su organización y todas las asignaciones a sus procesos y recursos de producción.</span><span class="sxs-lookup"><span data-stu-id="f2610-187">Use the **All Guides** page to see the list of all available Guides in your organization and all assignments to your production processes and resources.</span></span> <span data-ttu-id="f2610-188">Para abrirlo, vaya a **Realidad mixta \> Guías \> Todas las guías**.</span><span class="sxs-lookup"><span data-stu-id="f2610-188">To open it, go to **Mixed reality \> Guides \> All Guides**.</span></span> <span data-ttu-id="f2610-189">La lista en la parte superior muestra todas las guías disponibles y puede usar el campo aquí para filtrar la lista.</span><span class="sxs-lookup"><span data-stu-id="f2610-189">The list at the top shows all the available Guides and you can use the field here to filter the list.</span></span> <span data-ttu-id="f2610-190">La lista en la parte inferior muestra todas las asignaciones de la Guía y proporciona una barra de herramientas para administrarlas.</span><span class="sxs-lookup"><span data-stu-id="f2610-190">The list at the bottom shows all Guide assignments and provides a toolbar for managing them.</span></span>

<span data-ttu-id="f2610-191">![Administrar guías](media/instruction-guides-allguides.png "Administrar guías")</span><span class="sxs-lookup"><span data-stu-id="f2610-191">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

<span data-ttu-id="f2610-192">Las siguientes secciones describen los tipos de objetos a los que puede asignar guías.</span><span class="sxs-lookup"><span data-stu-id="f2610-192">The following sections describe the types of objects that you can assign Guides to.</span></span> <span data-ttu-id="f2610-193">Cada guía asignada proporciona instrucciones que se adjuntan automáticamente a los respectivos trabajos de producción y estarán disponibles en el taller.</span><span class="sxs-lookup"><span data-stu-id="f2610-193">Each assigned guide provides instructions that are automatically attached to the respective production jobs and will be available on the shop floor.</span></span>

## <a name="associate-a-guide-to-a-resource"></a><a name="resources"></a><span data-ttu-id="f2610-194">Asociar una guía a un recurso</span><span class="sxs-lookup"><span data-stu-id="f2610-194">Associate a Guide to a resource</span></span>

<span data-ttu-id="f2610-195">Agregar una guía a un [recurso](operations-resources.md) para ofrecer la Guía en el contexto de trabajos de producción relevantes.</span><span class="sxs-lookup"><span data-stu-id="f2610-195">Add a Guide to a [resource](operations-resources.md) to offer the Guide in the context of relevant production jobs.</span></span>

### <a name="typical-scenario-using-resources"></a><span data-ttu-id="f2610-196">Escenario típico con recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-196">Typical scenario using resources</span></span>

<span data-ttu-id="f2610-197">Por ejemplo, puede adjuntar una guía con seguridad general de la máquina o instrucciones de manejo a un recurso de tipo máquina.</span><span class="sxs-lookup"><span data-stu-id="f2610-197">For example, you could attach a Guide with general machine security or handling instructions to a resource of type machine.</span></span> <span data-ttu-id="f2610-198">Luego, la Guía estará disponible en cada trabajo que se realice en la máquina.</span><span class="sxs-lookup"><span data-stu-id="f2610-198">Then, the Guide will be available on every job that is performed on the machine.</span></span>

### <a name="add-a-guide-to-a-resource"></a><span data-ttu-id="f2610-199">Agregar una guía a un recurso</span><span class="sxs-lookup"><span data-stu-id="f2610-199">Add a Guide to a resource</span></span>

<span data-ttu-id="f2610-200">Para agregar una guía a un recurso:</span><span class="sxs-lookup"><span data-stu-id="f2610-200">To add a Guide to a resource:</span></span>

1. <span data-ttu-id="f2610-201">Vaya a **Control de producción \> Configuración \> Recursos \> Capacidades de recursos**.</span><span class="sxs-lookup"><span data-stu-id="f2610-201">Go to **Production control \> Setup \> Resources \> Resources**.</span></span>
1. <span data-ttu-id="f2610-202">En el panel de lista, seleccione el recurso al que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-202">From the list pane, select the resource you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-203">Amplíe la ficha desplegable **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-203">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="f2610-204">Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-204">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="f2610-205">Se agrega una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-205">A new line is added to the grid.</span></span>
1. <span data-ttu-id="f2610-206">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-206">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="f2610-207">Si tiene una gran cantidad de guías, puede filtrar la lista para encontrar la que está buscando.</span><span class="sxs-lookup"><span data-stu-id="f2610-207">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="f2610-208">![Administrar guías](media/instruction-guides-allguides.png "Administrar guías")</span><span class="sxs-lookup"><span data-stu-id="f2610-208">![Manage Guides](media/instruction-guides-allguides.png "Manage Guides")</span></span>

## <a name="associate-a-guide-to-a-resource-group"></a><a name="resource-groups"></a><span data-ttu-id="f2610-209">Asociar una guía a un grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-209">Associate a Guide to a resource group</span></span>

<span data-ttu-id="f2610-210">Puede agregar una guía a [grupos de recursos](tasks/define-discrete-manufacturing-resource-group.md) si los usa para administrar grupos de máquinas, líneas de producción o celdas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-210">You can add a guide to [resource groups](tasks/define-discrete-manufacturing-resource-group.md) if you use them to manage groups of machines, production lines, or work cells.</span></span>

### <a name="typical-scenarios-using-resource-groups"></a><span data-ttu-id="f2610-211">Escenarios típicos con grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-211">Typical scenarios using resource groups</span></span>

<span data-ttu-id="f2610-212">**Ejemplo 1:** Ha definido un grupo de recursos para varias máquinas del mismo modelo.</span><span class="sxs-lookup"><span data-stu-id="f2610-212">**Example 1:** You have defined a resource group for several machines of the same model.</span></span> <span data-ttu-id="f2610-213">En lugar de asignar la guía de instrucciones de manejo relevante para el modelo de máquina a cada recurso relevante, podría asignar la Guía al grupo de recursos que refleja ese modelo de máquina.</span><span class="sxs-lookup"><span data-stu-id="f2610-213">Instead of assigning the relevant handling instruction guide for the machine model to every relevant resource, you could instead assign the Guide to the resource group that reflects that machine model.</span></span>

<span data-ttu-id="f2610-214">**Ejemplo 2:** Ha definido un grupo de recursos para una celda de trabajo que contiene diferentes máquinas y tiene una guía que proporciona instrucciones generales sobre cómo mantener la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-214">**Example 2:** You have defined a resource group for a work cell that contains different machines and you have a Guide that provides general instructions for how to maintain the work cell.</span></span> <span data-ttu-id="f2610-215">La Guía se aplica a cualquier actividad de producción en esta celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-215">The Guide applies to any production activity in this work cell.</span></span>

### <a name="add-a-guide-to-a-resource-group"></a><span data-ttu-id="f2610-216">Agregar una guía a un grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-216">Add a Guide to a resource group</span></span>

<span data-ttu-id="f2610-217">Para agregar una guía a un grupo de recursos:</span><span class="sxs-lookup"><span data-stu-id="f2610-217">To add a Guide to a resource group:</span></span>

1. <span data-ttu-id="f2610-218">Vaya a **Control de producción \> Configuración \> Recursos \> Grupos de recursos**.</span><span class="sxs-lookup"><span data-stu-id="f2610-218">Go to **Production control \> Setup \> Resources \> Resource groups**.</span></span>
1. <span data-ttu-id="f2610-219">En el panel de lista, seleccione el grupo de recursos al que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-219">From the list pane, select the resource group you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-220">Amplíe la ficha desplegable **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-220">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="f2610-221">Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-221">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="f2610-222">Se agrega una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-222">A new line is added to the grid.</span></span>
1. <span data-ttu-id="f2610-223">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-223">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="f2610-224">Si tiene una gran cantidad de guías, puede filtrar la lista para encontrar la que está buscando.</span><span class="sxs-lookup"><span data-stu-id="f2610-224">If you have a large number of Guides, then you can filter the list to find the one you are looking for.</span></span>
    <span data-ttu-id="f2610-225">![Agregar una guía a un grupo de recursos](media/instruction-guides-resourcegroup.png "Agregar una guía a un grupo de recursos")</span><span class="sxs-lookup"><span data-stu-id="f2610-225">![Adding a Guide to a resource group](media/instruction-guides-resourcegroup.png "Adding a Guide to a resource group")</span></span>

## <a name="associate-a-guide-to-a-released-product"></a><a name="released-products"></a><span data-ttu-id="f2610-226">Asociar una guía a un producto liberado</span><span class="sxs-lookup"><span data-stu-id="f2610-226">Associate a Guide to a released product</span></span>

<span data-ttu-id="f2610-227">Puede agregar una guía a cualquier [producto lanzado](../pim/tasks/create-released-product-single-company.md).</span><span class="sxs-lookup"><span data-stu-id="f2610-227">You can add a guide to any [released product](../pim/tasks/create-released-product-single-company.md).</span></span>

### <a name="typical-scenario-using-released-products"></a><span data-ttu-id="f2610-228">Escenario típico con productos lanzados</span><span class="sxs-lookup"><span data-stu-id="f2610-228">Typical scenario using released products</span></span>

<span data-ttu-id="f2610-229">Las guías a nivel de producto ayudan a los trabajadores del taller con instrucciones relevantes para operar o manipular un producto o artículo específico liberado.</span><span class="sxs-lookup"><span data-stu-id="f2610-229">Product-level Guides help shop floor workers with instructions relevant to operating or handling a specific released product or item.</span></span>

### <a name="add-a-guide-to-a-released-product"></a><span data-ttu-id="f2610-230">Agregar una guía a un producto liberado</span><span class="sxs-lookup"><span data-stu-id="f2610-230">Add a Guide to a released product</span></span>

<span data-ttu-id="f2610-231">Para agregar una guía a un producto liberado:</span><span class="sxs-lookup"><span data-stu-id="f2610-231">To add a Guide to a released product:</span></span>

1. <span data-ttu-id="f2610-232">Vaya a **Gestión de información de producción \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="f2610-232">Go to **Production information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="f2610-233">Abra el producto al que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-233">Open the product you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-234">En el panel Acción, abra la pestaña **Ingeniero** y, desde el grupo **Ver** , seleccione **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-234">On the Action Pane, open the **Engineer** tab and from the **View** group, select **Associated Guides**.</span></span>
1. <span data-ttu-id="f2610-235">La página **Guías asociadas** se abre para el producto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f2610-235">The **Associated Guides** page opens for your selected product.</span></span>
1. <span data-ttu-id="f2610-236">En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-236">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="f2610-237">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-237">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="f2610-238">![Agregar una guía a un producto liberado](media/instruction-guides-ReleasedProduct-AddGuides.png "Agregar una guía a un producto liberado")</span><span class="sxs-lookup"><span data-stu-id="f2610-238">![Adding a Guide to a released product](media/instruction-guides-ReleasedProduct-AddGuides.png "Adding a Guide to a released product")</span></span>

## <a name="associate-a-guide-to-a-formula"></a><a name="formulas"></a><span data-ttu-id="f2610-239">Asociar una guía a una fórmula</span><span class="sxs-lookup"><span data-stu-id="f2610-239">Associate a Guide to a formula</span></span>

<span data-ttu-id="f2610-240">Puede agregar una guía a cualquier [fórmula](bill-of-material-bom.md#formulas-co-products-and-by-products).</span><span class="sxs-lookup"><span data-stu-id="f2610-240">You can add a guide to any [formula](bill-of-material-bom.md#formulas-co-products-and-by-products).</span></span>

### <a name="typical-scenario-using-formulas"></a><span data-ttu-id="f2610-241">Escenario típico con fórmulas</span><span class="sxs-lookup"><span data-stu-id="f2610-241">Typical scenario using formulas</span></span>
  
<span data-ttu-id="f2610-242">Las guías a nivel de fórmula proporcionan a los trabajadores del taller instrucciones de manejo guiadas en el contexto de una fórmula o receta.</span><span class="sxs-lookup"><span data-stu-id="f2610-242">Formula-level Guides provide shop floor workers with guided handling instructions in the context of a formula or recipe.</span></span> <span data-ttu-id="f2610-243">Las guías también se pueden asignar a versiones de una fórmula.</span><span class="sxs-lookup"><span data-stu-id="f2610-243">Guides can also be assigned to versions of a formula.</span></span>

> [!NOTE]
> <span data-ttu-id="f2610-244">Puede asignar una guía relevante para los procesos de producción basada en una fórmula a una ruta, versión de ruta o relaciones de operación de ruta.</span><span class="sxs-lookup"><span data-stu-id="f2610-244">You can assign guidance relevant for production processes based on a formula to a route, route version, or route operation relations.</span></span>  

> <span data-ttu-id="f2610-245">Actualmente, las guías no se pueden adjuntar a líneas de fórmula individuales.</span><span class="sxs-lookup"><span data-stu-id="f2610-245">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula"></a><span data-ttu-id="f2610-246">Agregar una guía a una fórmula</span><span class="sxs-lookup"><span data-stu-id="f2610-246">Add a Guide to a formula</span></span>

<span data-ttu-id="f2610-247">Para agregar una guía a una fórmula:</span><span class="sxs-lookup"><span data-stu-id="f2610-247">To add a Guide to a formula:</span></span>

1. <span data-ttu-id="f2610-248">Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-248">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="f2610-249">Abra la fórmula a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-249">Open the formula you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-250">Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.</span><span class="sxs-lookup"><span data-stu-id="f2610-250">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="f2610-251">Amplíe la ficha desplegable **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-251">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="f2610-252">Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-252">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="f2610-253">Se agrega una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-253">A new line is added to the grid.</span></span>
1. <span data-ttu-id="f2610-254">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-254">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="f2610-255">![Agregar una guía a una fórmula](media/instruction-guides-Formula.png "Agregar una guía a una fórmula")</span><span class="sxs-lookup"><span data-stu-id="f2610-255">![Adding a Guide to a formula](media/instruction-guides-Formula.png "Adding a Guide to a formula")</span></span>

## <a name="associate-a-guide-to-a-formula-version"></a><a name="formula-versions"></a><span data-ttu-id="f2610-256">Asociar una guía a una versión de una fórmula</span><span class="sxs-lookup"><span data-stu-id="f2610-256">Associate a Guide to a formula version</span></span>

<span data-ttu-id="f2610-257">Puede agregar una guía a cualquier [versión de fórmula](bill-of-material-bom.md#bom-and-formula-versions).</span><span class="sxs-lookup"><span data-stu-id="f2610-257">You can add a guide to any [formula version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-formula-versions"></a><span data-ttu-id="f2610-258">Escenario típico con versiones de fórmulas</span><span class="sxs-lookup"><span data-stu-id="f2610-258">Typical scenario using formula versions</span></span>

<span data-ttu-id="f2610-259">Las guías adjuntas a una versión individual de una fórmula brindan a los trabajadores del taller instrucciones que explican la producción de esa versión de la receta de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="f2610-259">Guides attached to an individual version of a formula provide shop floor workers with instructions that walk through the production of that version of the formula recipe.</span></span>

> [!TIP]
> <span data-ttu-id="f2610-260">Puede asignar una guía relevante para los procesos de producción basada en esta versión de fórmula a una ruta, versión de ruta o relaciones de operación de ruta.</span><span class="sxs-lookup"><span data-stu-id="f2610-260">You can assign guidance relevant for production processes based on this formula version to a route, route version, or route operation relations.</span></span>  

> [!NOTE]
> <span data-ttu-id="f2610-261">Actualmente, las guías no se pueden adjuntar a líneas de fórmula individuales.</span><span class="sxs-lookup"><span data-stu-id="f2610-261">Guides can't currently be attached to individual formula lines.</span></span>

### <a name="add-a-guide-to-a-formula-version"></a><span data-ttu-id="f2610-262">Agregar una guía a una versión de fórmula</span><span class="sxs-lookup"><span data-stu-id="f2610-262">Add a Guide to a formula version</span></span>

<span data-ttu-id="f2610-263">Para agregar una guía a una versión de fórmula:</span><span class="sxs-lookup"><span data-stu-id="f2610-263">To add a Guide to a formula version:</span></span>

1. <span data-ttu-id="f2610-264">Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Fórmulas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-264">Go to **Production information management \> Bills of materials and formulas \> Formulas**.</span></span>
1. <span data-ttu-id="f2610-265">Abra la fórmula que incluye una versión a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-265">Open the formula that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-266">Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.</span><span class="sxs-lookup"><span data-stu-id="f2610-266">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="f2610-267">Sobre la ficha desplegable **Versiones de fórmulas** , seleccione la versión a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-267">On the **Formula versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-268">Sobre la barra de herramientas **Versiones de fórmulas** , seleccione **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-268">On the **Formula versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="f2610-269">![Abra las guías asociadas con una versión de fórmula seleccionada](media/instruction-guides-FormulaVersion.png "Abra las guías asociadas con una versión de fórmula seleccionada")</span><span class="sxs-lookup"><span data-stu-id="f2610-269">![Open the Guides associated with a selected formula version](media/instruction-guides-FormulaVersion.png "Open the Guides associated with a selected formula version")</span></span>
1. <span data-ttu-id="f2610-270">La página **Guías asociadas** se abre para la versión de fórmula.</span><span class="sxs-lookup"><span data-stu-id="f2610-270">The **Associated Guides** page opens for your formula version.</span></span>
1. <span data-ttu-id="f2610-271">En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-271">Select **Add** on the Action Pane to add a new line to the grid.</span></span> 
1. <span data-ttu-id="f2610-272">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-272">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="f2610-273">![Agregar una guía a una versión de fórmula](media/instruction-guides-FormulaVersionAddGuide.png "Agregar una guía a una versión de fórmula")</span><span class="sxs-lookup"><span data-stu-id="f2610-273">![Adding a Guide to a formula version](media/instruction-guides-FormulaVersionAddGuide.png "Adding a Guide to a formula version")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials"></a><a name="bom"></a><span data-ttu-id="f2610-274">Asociar una guía a una lista de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-274">Associate a Guide to a bill of materials</span></span>

<span data-ttu-id="f2610-275">Puede agregar una guía a cualquier [lista de materiales](bill-of-material-bom.md) (LMAT).</span><span class="sxs-lookup"><span data-stu-id="f2610-275">You can add a guide to any [bill of materials](bill-of-material-bom.md) (BOM).</span></span>

### <a name="typical-scenario-using-bills-of-materials"></a><span data-ttu-id="f2610-276">Escenario típico con listas de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-276">Typical scenario using bills of materials</span></span>

<span data-ttu-id="f2610-277">Las guías adjuntas a una lista de materiales proporcionan a los trabajadores del taller instrucciones que explican cómo preparar y manipular el material de una lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="f2610-277">Guides attached to a BOM provide shop floor workers with instructions that explain how to prepare and handle material from a BOM.</span></span> <span data-ttu-id="f2610-278">Las guías también se pueden asignar a versiones de una LMAT.</span><span class="sxs-lookup"><span data-stu-id="f2610-278">Guides can also be assigned to versions of a BOM.</span></span>

> [!NOTE]
> <span data-ttu-id="f2610-279">Actualmente, las guías no se pueden adjuntar a líneas de LMAT individuales.</span><span class="sxs-lookup"><span data-stu-id="f2610-279">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials"></a><span data-ttu-id="f2610-280">Agregar una guía a una lista de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-280">Add a Guide to a bill of materials</span></span>

<span data-ttu-id="f2610-281">Para agregar una guía a una lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="f2610-281">To add a Guide to a bill of material:</span></span>

1. <span data-ttu-id="f2610-282">Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Listas de materiales**.</span><span class="sxs-lookup"><span data-stu-id="f2610-282">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="f2610-283">Abra la lista de materiales al que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-283">Open the bill of materials that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-284">Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.</span><span class="sxs-lookup"><span data-stu-id="f2610-284">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="f2610-285">Amplíe la ficha desplegable **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-285">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="f2610-286">Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-286">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="f2610-287">Se agrega una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-287">A new line is added to the grid.</span></span>
1. <span data-ttu-id="f2610-288">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-288">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="f2610-289">![Agregar una guía a una LMAT](media/instruction-guides-BOM.png "Agregar una guía a una LMAT")</span><span class="sxs-lookup"><span data-stu-id="f2610-289">![Adding a Guide to a BOM](media/instruction-guides-BOM.png "Adding a Guide to a BOM")</span></span>

## <a name="associate-a-guide-to-a-bill-of-materials-version"></a><a name="bom-versions"></a><span data-ttu-id="f2610-290">Asociar una guía a una versión de lista de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-290">Associate a Guide to a bill of materials version</span></span>

<span data-ttu-id="f2610-291">Puede agregar una guía a cualquier [versión de lista de materiales](bill-of-material-bom.md#bom-and-formula-versions).</span><span class="sxs-lookup"><span data-stu-id="f2610-291">You can add a guide to any [bill of materials version](bill-of-material-bom.md#bom-and-formula-versions).</span></span>

### <a name="typical-scenario-using-bill-of-materials-versions"></a><span data-ttu-id="f2610-292">Escenario típico con versiones de listas de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-292">Typical scenario using bill of materials versions</span></span>

<span data-ttu-id="f2610-293">Las guías adjuntas a una versión individual de la lista de materiales brindan a los trabajadores del taller instrucciones que explican cómo preparar y manipular el material para una versión de una lista de materiales que es diferente de la lista de materiales genérica u otras versiones de la misma.</span><span class="sxs-lookup"><span data-stu-id="f2610-293">Guides attached to an individual BOM version provide shop floor workers with instructions that explain how to prepare and handle material for a version of a BOM that is different from the generic BOM or other versions of it.</span></span>

> [!NOTE]
> <span data-ttu-id="f2610-294">Actualmente, las guías no se pueden adjuntar a líneas de LMAT individuales.</span><span class="sxs-lookup"><span data-stu-id="f2610-294">Guides can't currently be attached to individual BOM lines.</span></span>

### <a name="add-a-guide-to-a-bill-of-materials-version"></a><span data-ttu-id="f2610-295">Agregar una guía a una versión de lista de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-295">Add a Guide to a bill of materials version</span></span>

<span data-ttu-id="f2610-296">Para agregar una guía a una versión de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="f2610-296">To add a Guide to a bill of materials version:</span></span>

1. <span data-ttu-id="f2610-297">Vaya a **Gestión de información de producción \> Listas de materiales y fórmulas \> Listas de materiales**.</span><span class="sxs-lookup"><span data-stu-id="f2610-297">Go to **Production information management \> Bills of materials and formulas \> Bills of materials**.</span></span>
1. <span data-ttu-id="f2610-298">Abra la LMAT que incluye una versión a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-298">Open the BOM that includes a version that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-299">Abra la pestaña **Encabezamiento** encima de la pestaña desplegable superior.</span><span class="sxs-lookup"><span data-stu-id="f2610-299">Open the **Header** tab above the top FastTab.</span></span>
1. <span data-ttu-id="f2610-300">Sobre la ficha desplegable **Versiones de LMAT** , seleccione la versión a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-300">On the **BOM versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-301">Sobre la barra de herramientas **Versiones de LMAT** , seleccione **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-301">On the **BOM versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="f2610-302">![Abra las guías asociadas con una versión de LMAT seleccionada](media/instruction-guides-BOMVersion.png "Abra las guías asociadas con una versión de LMAT seleccionada")</span><span class="sxs-lookup"><span data-stu-id="f2610-302">![Open the Guides associated with a selected BOM version](media/instruction-guides-BOMVersion.png "Open the Guides associated with a selected BOM version")</span></span>
1. <span data-ttu-id="f2610-303">La página **Guías asociadas** se abre para la versión de LMAT.</span><span class="sxs-lookup"><span data-stu-id="f2610-303">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="f2610-304">En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-304">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="f2610-305">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-305">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="f2610-306">![Agregar una guía a una versión de LMAT](media/instruction-guides-BOMVersionAddGuide.png "Agregar una guía a una versión de LMAT")</span><span class="sxs-lookup"><span data-stu-id="f2610-306">![Adding a Guide to a BOM version](media/instruction-guides-BOMVersionAddGuide.png "Adding a Guide to a BOM version")</span></span>

## <a name="associate-a-guide-to-a-route"></a><a name="routes"></a><span data-ttu-id="f2610-307">Asociar una guía a una ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-307">Associate a Guide to a route</span></span>

<span data-ttu-id="f2610-308">Puede agregar una guía a cualquier [ruta](routes-operations.md).</span><span class="sxs-lookup"><span data-stu-id="f2610-308">You can add a guide to any [route](routes-operations.md).</span></span>

### <a name="typical-scenario-using-routes"></a><span data-ttu-id="f2610-309">Escenario típico con rutas</span><span class="sxs-lookup"><span data-stu-id="f2610-309">Typical scenario using routes</span></span>

<span data-ttu-id="f2610-310">Las rutas se utilizan normalmente para especificar cómo se producirá un determinado producto publicado en función de una lista de materiales o una versión de lista de materiales y con un conjunto de recursos o grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="f2610-310">Routes are typically used to specify how a certain released product shall be produced based on a BOM or BOM version and with a set of resources or resource groups.</span></span>

<span data-ttu-id="f2610-311">Asigne una guía a una ruta para proporcionar instrucciones paso a paso para el proceso de producción respectivo.</span><span class="sxs-lookup"><span data-stu-id="f2610-311">Assign a Guide to a route to provide step-by-step instructions for the respective production process.</span></span>

### <a name="add-a-guide-to-a-route"></a><span data-ttu-id="f2610-312">Agregar una guía a una ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-312">Add a Guide to a route</span></span>

<span data-ttu-id="f2610-313">Para agregar una guía a una ruta:</span><span class="sxs-lookup"><span data-stu-id="f2610-313">To add a Guide to a route:</span></span>

1. <span data-ttu-id="f2610-314">Vaya a **Control de producción \> Todas las rutas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-314">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="f2610-315">Abra la ruta a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-315">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-316">Amplíe la ficha desplegable **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-316">Expand the **Associated Guides** FastTab.</span></span>
1. <span data-ttu-id="f2610-317">Seleccione **Añadir** desde la barra de herramientas **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-317">Select **Add** from the **Associated Guides** toolbar.</span></span> <span data-ttu-id="f2610-318">Se agrega una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-318">A new line is added to the grid.</span></span>
1. <span data-ttu-id="f2610-319">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-319">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="f2610-320">![Agregar una guía a una ruta](media/instruction-guides-Route.png "Agregar una guía a una ruta")</span><span class="sxs-lookup"><span data-stu-id="f2610-320">![Adding a Guide to a route](media/instruction-guides-Route.png "Adding a Guide to a route")</span></span>

## <a name="associate-a-guide-to-a-route-version"></a><a name="route-versions"></a><span data-ttu-id="f2610-321">Asociar una guía a una versión de una ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-321">Associate a Guide to a route version</span></span>

<span data-ttu-id="f2610-322">Puede agregar una guía a cualquier [versión de ruta](routes-operations.md#route-versions).</span><span class="sxs-lookup"><span data-stu-id="f2610-322">You can add a guide to any [route version](routes-operations.md#route-versions).</span></span>

### <a name="typical-scenario-using-route-versions"></a><span data-ttu-id="f2610-323">Escenario típico con versiones de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-323">Typical scenario using route versions</span></span>

<span data-ttu-id="f2610-324">Las versiones de rutas se utilizan normalmente para especificar variantes de procesos de producción en función de una ruta existente.</span><span class="sxs-lookup"><span data-stu-id="f2610-324">Routes versions are typically used to specify variants of production processes based on an existing route.</span></span> <span data-ttu-id="f2610-325">Puede asignar diferentes Guías a cada versión de ruta.</span><span class="sxs-lookup"><span data-stu-id="f2610-325">You can assign different Guides to each route version.</span></span>

### <a name="add-a-guide-to-a-route-version"></a><span data-ttu-id="f2610-326">Agregar una guía a una versión de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-326">Add a Guide to a route version</span></span>

<span data-ttu-id="f2610-327">Para agregar una guía a una versión de ruta:</span><span class="sxs-lookup"><span data-stu-id="f2610-327">To add a Guide to a route version:</span></span>

1. <span data-ttu-id="f2610-328">Vaya a **Control de producción \> Todas las rutas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-328">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="f2610-329">Abra la ruta a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-329">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-330">Sobre la ficha desplegable **Versiones** , seleccione la versión a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-330">On the **Versions** FastTab, select the version you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-331">Sobre la barra de herramientas **Versiones** , seleccione **Guías asociadas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-331">On the **Versions** toolbar, select **Associated Guides**.</span></span>
    <span data-ttu-id="f2610-332">![Abra las guías asociadas con una versión de ruta seleccionada](media/instruction-guides-RouteVersion.png "Abra las guías asociadas con una versión de ruta seleccionada")</span><span class="sxs-lookup"><span data-stu-id="f2610-332">![Open the Guides associated with a selected route version](media/instruction-guides-RouteVersion.png "Open the Guides associated with a selected route version")</span></span>
1. <span data-ttu-id="f2610-333">La página **Guías asociadas** se abre para la versión de LMAT.</span><span class="sxs-lookup"><span data-stu-id="f2610-333">The **Associated Guides** page opens for your BOM version.</span></span>
1. <span data-ttu-id="f2610-334">En el Panel de acciones, seleccione **Agregar** para agregar una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-334">Select **Add** on the Action Pane to add a new line to the grid.</span></span>
1. <span data-ttu-id="f2610-335">Para la nueva línea, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-335">For the new line, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span>
    <span data-ttu-id="f2610-336">![Agregar una guía a una versión de ruta](media/instruction-guides-RouteVersionAddGuide.png "Agregar una guía a una versión de ruta")</span><span class="sxs-lookup"><span data-stu-id="f2610-336">![Adding a Guide to a route version](media/instruction-guides-RouteVersionAddGuide.png "Adding a Guide to a route version")</span></span>

## <a name="associate-a-guide-to-a-route-operation-relation"></a><a name="route-operation-relations"></a><span data-ttu-id="f2610-337">Asociar una guía a una relación de operación de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-337">Associate a Guide to a route operation relation</span></span>

<span data-ttu-id="f2610-338">Puede agregar una guía a cualquier [relación de operación de ruta](routes-operations.md#operation-relations).</span><span class="sxs-lookup"><span data-stu-id="f2610-338">You can add a guide to any [route operation relation](routes-operations.md#operation-relations).</span></span>

### <a name="typical-scenario-using-route-operation-relations"></a><span data-ttu-id="f2610-339">Escenario típico que usa relaciones de operación de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-339">Typical scenario using route operation relations</span></span>

<span data-ttu-id="f2610-340">Las relaciones de operación son la forma más específica de agregar orientación al proceso de un producto y sus operaciones relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f2610-340">Operation relations are the most specific way to add guidance to a product process and its related operations.</span></span> <span data-ttu-id="f2610-341">Puede especificar una guía para cada operación en una ruta y especificar una guía diferente para cualquier tipo de contexto de relación especificado para una ruta, como para elementos específicos, configuraciones y más.</span><span class="sxs-lookup"><span data-stu-id="f2610-341">You can specify guidance for each operation in a route and specify different guidance for any type of relation context specified for a route, such as for specific items, configurations, and more.</span></span> <span data-ttu-id="f2610-342">También puede especificar a qué etapas de la operación se aplica la guía (como configuración, puesta en cola, proceso o transporte).</span><span class="sxs-lookup"><span data-stu-id="f2610-342">You can also specify to which stages in the operation the guidance applies (such as setup, queueing, process, or transport).</span></span>

> [!NOTE]
> <span data-ttu-id="f2610-343">Si especifica guías para varias relaciones de operación de una ruta, entre esas guías, solo la guía de la relación más específica se mostrará en el piso de producción para el trabajo generado.</span><span class="sxs-lookup"><span data-stu-id="f2610-343">If you specify guides for several operation relations of a route, among those guides, only the guide from the most specific relation will be show on the shop floor for the generated job.</span></span>

### <a name="add-a-guide-to-a-route-operation-relation"></a><span data-ttu-id="f2610-344">Agregar una guía a una relación de operación de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-344">Add a Guide to a route operation relation</span></span>

<span data-ttu-id="f2610-345">Para agregar una guía a una relación de operación de ruta:</span><span class="sxs-lookup"><span data-stu-id="f2610-345">To add a Guide to a route operation relation:</span></span>

1. <span data-ttu-id="f2610-346">Vaya a **Control de producción \> Todas las rutas**.</span><span class="sxs-lookup"><span data-stu-id="f2610-346">Go to **Production control \> All routes**.</span></span>
1. <span data-ttu-id="f2610-347">Abra la ruta a la que desea asignar una guía.</span><span class="sxs-lookup"><span data-stu-id="f2610-347">Open the route that you want to assign a Guide to.</span></span>
1. <span data-ttu-id="f2610-348">En el panel Acción, abra la pestaña **Ruta** y, desde el grupo **Mantener** , seleccione **Detalles de ruta**.</span><span class="sxs-lookup"><span data-stu-id="f2610-348">On the Action Pane, open the **Route** tab and from the **Maintain** group, select **Route details**.</span></span>
1. <span data-ttu-id="f2610-349">Se abre la página **Detalles de ruta** para la ruta seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f2610-349">The **Route details** page opens for your selected rout.</span></span>
1. <span data-ttu-id="f2610-350">En la cuadrícula superior, seleccione la operación para la que desea proporcionar orientación.</span><span class="sxs-lookup"><span data-stu-id="f2610-350">In the top grid, select the operation you want to provide guidance for.</span></span>
1. <span data-ttu-id="f2610-351">En la cuadrícula inferior, seleccione una relación específica (o la relación genérica **Todos** ).</span><span class="sxs-lookup"><span data-stu-id="f2610-351">In the bottom grid, select a specific relation (or the generic **All** relation).</span></span>
    <span data-ttu-id="f2610-352">![Seleccione una operación y luego una relación](media/instruction-guides-RouteOperationRelation.png "Seleccione una operación y luego una relación")</span><span class="sxs-lookup"><span data-stu-id="f2610-352">![Select an operation and then a relation](media/instruction-guides-RouteOperationRelation.png "Select an operation and then a relation")</span></span>
1. <span data-ttu-id="f2610-353">Encima de la cuadrícula inferior, abra la pestaña **Guías asociadas**. ![ La pestaña Guías asociadas](media/instruction-guides-RouteOperationRelation-AddGuide.png "La pestaña Guías asociadas")</span><span class="sxs-lookup"><span data-stu-id="f2610-353">Above the bottom gird, open the **Associated Guides** tab.  ![The Associated Guides tab](media/instruction-guides-RouteOperationRelation-AddGuide.png "The Associated Guides tab")</span></span>
1. <span data-ttu-id="f2610-354">Seleccione **Añadir** en la barra de herramientas en la parte superior de la cuadrícula inferior para agregar una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="f2610-354">Select **Add** from the toolbar at the top of the bottom grid to add a new line to the grid.</span></span>
1. <span data-ttu-id="f2610-355">Para la nueva fila, use la lista desplegable en la columna **Nombre** para elegir la Guía que desea asignar.</span><span class="sxs-lookup"><span data-stu-id="f2610-355">For the new row, use the drop-down list in the **Name** column to choose the Guide you want to assign.</span></span> <span data-ttu-id="f2610-356">En el resto de la fila, seleccione la casilla de verificación para cada contexto donde la Guía seleccionada debería estar disponible.</span><span class="sxs-lookup"><span data-stu-id="f2610-356">In the rest of the row, select the check box for each context where the selected Guide should be available.</span></span>

> [!NOTE]
> <span data-ttu-id="f2610-357">Puede agregar una o más guías para cada etapa de cada operación.</span><span class="sxs-lookup"><span data-stu-id="f2610-357">You can add one or more guides for each stage of each operation.</span></span>

## <a name="select-guides-from-the-shop-floor-execution-interface"></a><span data-ttu-id="f2610-358">Seleccionar guías de la interfaz de ejecución de la planta</span><span class="sxs-lookup"><span data-stu-id="f2610-358">Select guides from the shop floor execution interface</span></span>

<span data-ttu-id="f2610-359">Cuando un trabajador abre una lista de trabajos en la interfaz de ejecución de la planta, Supply Chain Management encuentra las guías relevantes para los trabajos que se muestran.</span><span class="sxs-lookup"><span data-stu-id="f2610-359">When a worker opens a job list on the shop floor execution interface, Supply Chain Management finds the relevant guides for the jobs shown.</span></span> <span data-ttu-id="f2610-360">Utilice el botón **Guías** para ver las guías relevantes.</span><span class="sxs-lookup"><span data-stu-id="f2610-360">Use the **Guides** button to view the relevant guides.</span></span>

<span data-ttu-id="f2610-361">![Botón Guías en la interfaz de ejecución de la planta](media/instruction-guides-Shopfloor1.png "Botón Guías en la interfaz de ejecución de la planta")</span><span class="sxs-lookup"><span data-stu-id="f2610-361">![Guides button in the shop floor execution interface](media/instruction-guides-Shopfloor1.png "Guides button in the shop floor execution interface")</span></span>

<span data-ttu-id="f2610-362">Entonces coloque un HoloLens y acceda a la guía respectiva echando un vistazo al código QR y activando la Guía respectiva.</span><span class="sxs-lookup"><span data-stu-id="f2610-362">Then put on a HoloLens and access the respective guide by glancing at the QR code and activating the respective Guide.</span></span>

<span data-ttu-id="f2610-363">![Código QR para acceder a las guías mediante un HoloLens](media/instruction-guides-Shopfloor2.png "Código QR para acceder a las guías mediante un HoloLens")</span><span class="sxs-lookup"><span data-stu-id="f2610-363">![QR code to access guides using a HoloLens](media/instruction-guides-Shopfloor2.png "QR code to access guides using a HoloLens")</span></span>

## <a name="resolving-the-logic-for-selecting-guides"></a><a name="logic"></a><span data-ttu-id="f2610-364">Resolver la lógica para seleccionar guías</span><span class="sxs-lookup"><span data-stu-id="f2610-364">Resolving the logic for selecting Guides</span></span>

<span data-ttu-id="f2610-365">Puede agregar guías a los siguientes datos de producción:</span><span class="sxs-lookup"><span data-stu-id="f2610-365">You can add Guides to the following production data:</span></span>

- [<span data-ttu-id="f2610-366">Recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-366">Resources</span></span>](#resources)
- [<span data-ttu-id="f2610-367">Grupos de recursos</span><span class="sxs-lookup"><span data-stu-id="f2610-367">Resource groups</span></span>](#resource-groups)
- [<span data-ttu-id="f2610-368">Productos emitidos</span><span class="sxs-lookup"><span data-stu-id="f2610-368">Released products</span></span>](#released-products)
- [<span data-ttu-id="f2610-369">Fórmulas </span><span class="sxs-lookup"><span data-stu-id="f2610-369">Formulas</span></span>](#formulas)
- [<span data-ttu-id="f2610-370">Versiones de fórmula</span><span class="sxs-lookup"><span data-stu-id="f2610-370">Formula versions</span></span>](#formula-versions)
- [<span data-ttu-id="f2610-371">Listas de materiales (LMAT)</span><span class="sxs-lookup"><span data-stu-id="f2610-371">Bills of material (BOMs)</span></span>](#bom)
- [<span data-ttu-id="f2610-372">Versiones de listas de materiales</span><span class="sxs-lookup"><span data-stu-id="f2610-372">BOM versions</span></span>](#bom-versions)
- [<span data-ttu-id="f2610-373">Rutas</span><span class="sxs-lookup"><span data-stu-id="f2610-373">Routes</span></span>](#routes)
- [<span data-ttu-id="f2610-374">Versiones de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-374">Route versions</span></span>](#route-versions)
- [<span data-ttu-id="f2610-375">Relaciones de operación de ruta</span><span class="sxs-lookup"><span data-stu-id="f2610-375">Route operation relations</span></span>](#route-operation-relations)

<span data-ttu-id="f2610-376">Cuando Supply Chain Management genera los trabajos para el piso de producción, recopilará las Guías relevantes de esas fuentes.</span><span class="sxs-lookup"><span data-stu-id="f2610-376">When Supply Chain Management generates the jobs for the production floor, it will collect the relevant Guides from those sources.</span></span> <span data-ttu-id="f2610-377">Tome nota de las siguientes reglas importantes.</span><span class="sxs-lookup"><span data-stu-id="f2610-377">Take note of the following important rules.</span></span>

- <span data-ttu-id="f2610-378">Si adjunta una versión de lista de materiales o una versión de fórmula a una ruta u orden de producción, las guías adjuntas a esta versión, y también las guías adjuntas a la lista de materiales principal o fórmula de esa versión, se mostrarán en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-378">If you attach a BOM version or formula version to a route or production order, then any Guides attached to this version, and also the Guides attached to the parent BOM or formula of that version, will be shown on the job.</span></span>
- <span data-ttu-id="f2610-379">Si adjunta una versión de ruta a una orden de producción, las guías adjuntas a esta versión, y también las guías adjuntas a la ruta principal de esa versión, se mostrarán en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-379">If you attach a route version to a production order, then any Guides attached to this version, and also the Guides attached to the parent route of that version, will be shown on the job.</span></span>
- <span data-ttu-id="f2610-380">Si define varias relaciones de operación de ruta que incluyen la relación *Todos* y asignar Guías a esos, solo se mostrarán las Guías de la relación más específica para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f2610-380">If you define several route operation relations that include the *All* relation and assign Guides to those, only the Guides from the most specific relation will be shown for the job.</span></span>  

<span data-ttu-id="f2610-381">![Diagrama de resolución de las Guías relevantes](media/instruction-guides-Resolve.png "Diagrama de resolución de las Guías relevantes")</span><span class="sxs-lookup"><span data-stu-id="f2610-381">![Diagram on resolving the relevant Guides](media/instruction-guides-Resolve.png "Diagram on resolving the relevant Guides")</span></span>
