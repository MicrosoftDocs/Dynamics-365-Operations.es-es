---
title: "Gestión de almacenes"
description: "Use la gestión de almacenes para supervisar y automatizar procesos de almacén."
author: BibiSp
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSParameters
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ba426692e2e404ab75e5730b8205115fc59e402f
ms.openlocfilehash: 43167cc36398d3f7f8d639187f67fad1bae8082f
ms.contentlocale: es-es
ms.lasthandoff: 02/08/2018

---
# <a name="warehouse-management"></a><span data-ttu-id="4a48e-103">Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="4a48e-103">Warehouse management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4a48e-104">El módulo de gestión de almacenes de Dynamics 365 for Finance and Operations, Enterprise Edition, le permite gestionar los procesos de almacén en la fabricación, la distribución y en las empresas al por menor.</span><span class="sxs-lookup"><span data-stu-id="4a48e-104">The Warehouse management module for Dynamics 365 for Finance and Operations, Enterprise edition lets you manage warehouse processes in manufacturing, distribution, and retail companies.</span></span> <span data-ttu-id="4a48e-105">Este módulo tiene una gran variedad de características que le permitirán sacarle el máximo rendimiento a su instalación de almacén.</span><span class="sxs-lookup"><span data-stu-id="4a48e-105">This module has a wide range of features to support the warehouse facility at an optimal level, at any time.</span></span> <span data-ttu-id="4a48e-106">La gestión de almacenes está completamente integrada con otros procesos empresariales en Finance and Operations, tales como el transporte, la fabricación, el control de calidad, las compras, las ventas, las transferencias y las devoluciones.</span><span class="sxs-lookup"><span data-stu-id="4a48e-106">Warehouse management is fully integrated with other business processes in Finance and Operations such as transportation, manufacturing, quality control, purchase, transfer, sales, and returns.</span></span>

## <a name="get-started"></a><span data-ttu-id="4a48e-107">Introducción</span><span class="sxs-lookup"><span data-stu-id="4a48e-107">Get started</span></span>
<span data-ttu-id="4a48e-108">Para empezar a trabajar con la gestión de almacenes, debe completar la configuración de los parámetros generales del almacén para los procesos empresariales de la empresa.</span><span class="sxs-lookup"><span data-stu-id="4a48e-108">To start working with Warehouse management, you need to complete the setup of the general warehouse parameters to support the business processes of you company.</span></span>

- <span data-ttu-id="4a48e-109">Vaya a la página **Parámetros de gestión de almacenes** en **Gestión de almacenes** > **Configuración** y configure los parámetros generales del almacén.</span><span class="sxs-lookup"><span data-stu-id="4a48e-109">Go to the **Warehouse management parameters** page under **Warehouse management** > **Setup** to set up general warehouse parameters.</span></span>

<span data-ttu-id="4a48e-110">Debe configurar los componentes de los flujos de trabajo entrantes y salientes del proceso de almacén según sus requisitos empresariales.</span><span class="sxs-lookup"><span data-stu-id="4a48e-110">You must configure components for inbound and outbound warehouse process workflows according to business requirements.</span></span> <span data-ttu-id="4a48e-111">Los componentes más importantes que debe configurar son plantillas de oleada, plantillas de trabajo, grupos de trabajo y directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="4a48e-111">The most important components that you must configure are wave templates, work templates, work pools, and location directives.</span></span>

- [<span data-ttu-id="4a48e-112">Configuración de almacén</span><span class="sxs-lookup"><span data-stu-id="4a48e-112">Warehouse configuration</span></span>](warehouse-configuration.md)
- [<span data-ttu-id="4a48e-113">Controlar el trabajo de almacén usando plantillas de trabajo y directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="4a48e-113">Control warehouse work by using work templates and location directives</span></span>](control-warehouse-location-directives.md)
- [<span data-ttu-id="4a48e-114">Configurar dispositivos móviles para el trabajo de almacén</span><span class="sxs-lookup"><span data-stu-id="4a48e-114">Set up mobile devices for warehouse work</span></span>](configure-mobile-devices-warehouse.md)
- [<span data-ttu-id="4a48e-115">Configurar una directiva de ubicación para ubicación de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="4a48e-115">Set up a location directive for purchase order put-away</span></span>](../transportation/tasks/set-up-location-directive-purchase-order-put-away.md)
- [<span data-ttu-id="4a48e-116">Configurar una plantilla de trabajo para pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="4a48e-116">Set up a work template for purchase orders</span></span>](./tasks/set-up-work-template-purchase-orders.md)

## <a name="warehouse-management-processes"></a><span data-ttu-id="4a48e-117">Procesos de gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="4a48e-117">Warehouse management processes</span></span>
- <span data-ttu-id="4a48e-118">Soporte integrado para los documentos de origen de los pedidos de ventas, devoluciones, pedidos de transferencia, pedidos de producción y kanban</span><span class="sxs-lookup"><span data-stu-id="4a48e-118">Integrated support for source documents for sales orders, returns, transfer orders, production orders, and kanban</span></span>  
- <span data-ttu-id="4a48e-119">Soporte flexible de flujo de trabajo de material entrante y saliente basado en consultas</span><span class="sxs-lookup"><span data-stu-id="4a48e-119">Flexible, inbound and outbound material workflow support based on queries</span></span>
- <span data-ttu-id="4a48e-120">Integración total con las ofertas de fabricación y transporte</span><span class="sxs-lookup"><span data-stu-id="4a48e-120">Full integration with the Manufacturing and Transportation offerings</span></span>
- <span data-ttu-id="4a48e-121">Control total de los límites de existencias y las métricas de volumen de la ubicación</span><span class="sxs-lookup"><span data-stu-id="4a48e-121">Full control of location stocking limits and location volumetrics</span></span>
- <span data-ttu-id="4a48e-122">Propiedades de inventario controladas por el estado de inventario</span><span class="sxs-lookup"><span data-stu-id="4a48e-122">Inventory properties controlled by inventory status</span></span>
- <span data-ttu-id="4a48e-123">Soporte del lote completo y del artículo de serie</span><span class="sxs-lookup"><span data-stu-id="4a48e-123">Full batch and serial item support</span></span>
- <span data-ttu-id="4a48e-124">Capacidad para recibir varios artículos</span><span class="sxs-lookup"><span data-stu-id="4a48e-124">Various item receiving capabilities</span></span>
- <span data-ttu-id="4a48e-125">Varias estrategias de selección</span><span class="sxs-lookup"><span data-stu-id="4a48e-125">Multiple picking strategies</span></span>
- <span data-ttu-id="4a48e-126">Soporte integrado para la siguiente generación de lectores de códigos de barras</span><span class="sxs-lookup"><span data-stu-id="4a48e-126">Out-of-the-box support for the next generation of barcode scanners</span></span>
- <span data-ttu-id="4a48e-127">Tipos de pallet y contenedores para los procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="4a48e-127">Pallet/container types for warehouse processes</span></span>
- <span data-ttu-id="4a48e-128">Capacidades de conteo avanzadas</span><span class="sxs-lookup"><span data-stu-id="4a48e-128">Advanced counting capabilities</span></span>
- <span data-ttu-id="4a48e-129">Impresión y enrutamiento de etiquetas con el soporte de Zebra ZPL</span><span class="sxs-lookup"><span data-stu-id="4a48e-129">Label printing and label routing with Zebra ZPL support</span></span>
- <span data-ttu-id="4a48e-130">Integración de Business Intelligence en Power BI</span><span class="sxs-lookup"><span data-stu-id="4a48e-130">Business intelligence integration into Power BI</span></span>
- <span data-ttu-id="4a48e-131">Movimientos automáticos y manuales del inventario</span><span class="sxs-lookup"><span data-stu-id="4a48e-131">Manual and automatic movement of inventory</span></span>
- <span data-ttu-id="4a48e-132">Control de calidad totalmente integrado (QMS)</span><span class="sxs-lookup"><span data-stu-id="4a48e-132">Fully-integrated quality control (QMS)</span></span>
- <span data-ttu-id="4a48e-133">Rastreabilidad completa de la gestión de material de los trabajadores</span><span class="sxs-lookup"><span data-stu-id="4a48e-133">Full traceability of workers' material handling</span></span>
- <span data-ttu-id="4a48e-134">Procesamiento de oleadas de salida</span><span class="sxs-lookup"><span data-stu-id="4a48e-134">Outbound wave processing</span></span>
- <span data-ttu-id="4a48e-135">Soporte para el embalaje manual y la puesta en contenedores automática</span><span class="sxs-lookup"><span data-stu-id="4a48e-135">Manual packing and automatic containerization support</span></span>
- <span data-ttu-id="4a48e-136">Picking en clúster</span><span class="sxs-lookup"><span data-stu-id="4a48e-136">Cluster picking</span></span>
- <span data-ttu-id="4a48e-137">Tránsito directo simple</span><span class="sxs-lookup"><span data-stu-id="4a48e-137">Simple cross docking</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a48e-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4a48e-138">Additional resources</span></span>
### <a name="whats-new-and-in-development"></a><span data-ttu-id="4a48e-139">Novedades y características en desarrollo</span><span class="sxs-lookup"><span data-stu-id="4a48e-139">What's new and in development</span></span>
<span data-ttu-id="4a48e-140">Consulte [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) (Guía básica de Microsoft Dynamics 365) para ver qué características nuevas hemos lanzado y cuáles están en desarrollo.</span><span class="sxs-lookup"><span data-stu-id="4a48e-140">Go to the [Microsoft Dynamics 365 Roadmap](https://roadmap.dynamics.com/) to see what new features have been released and what new features are in development.</span></span>

### <a name="blogs"></a><span data-ttu-id="4a48e-141">Blogs</span><span class="sxs-lookup"><span data-stu-id="4a48e-141">Blogs</span></span>
<span data-ttu-id="4a48e-142">Puede encontrar opiniones, noticias y otra información sobre la gestión de almacenes y otras soluciones en el [blog de Microsoft Dynamics 365](https://community.dynamics.com/b/msftdynamicsblog).</span><span class="sxs-lookup"><span data-stu-id="4a48e-142">You can find opinions, news, and other information about Warehouse management and other solutions on the [Microsoft Dynamics 365 blog](https://community.dynamics.com/b/msftdynamicsblog).</span></span>


 


