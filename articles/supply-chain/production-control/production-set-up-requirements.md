---
title: "Requisitos de configuración de producción"
description: "Este artículo proporciona información acerca de los requisitos de configuración para poder trabajar con el Control de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParameters, RouteOpr, RouteOprTable, WorkCalendarTable, WorkTimeTable, WrkCtrTable
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 55561
ms.assetid: 1953059f-478d-4706-b461-25b89ace5fc3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 47fe11168ad2ddea2a7033eda8d8bd8220efea32
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="production-setup-requirements"></a><span data-ttu-id="8f2cd-103">Requisitos de configuración de producción</span><span class="sxs-lookup"><span data-stu-id="8f2cd-103">Production setup requirements</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="8f2cd-104">Este artículo proporciona información acerca de los requisitos de configuración para poder trabajar con el Control de producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-104">This article provides information about setup requirements before you can work with Production control.</span></span> 

<span data-ttu-id="8f2cd-105">Control de producción se integra con funciones de otros módulos.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-105">Production control is integrated with features in other modules.</span></span> <span data-ttu-id="8f2cd-106">Esta interconectividad le permite modificar las órdenes de producción y garantizar que se actualizan automáticamente en los demás procesos y cálculos del sistema.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-106">This interconnectivity lets you change production orders and make sure that they are automatically updated in all other related processes and calculations in the system.</span></span> <span data-ttu-id="8f2cd-107">Los siguientes procesos de configuración se enumeran en el orden en que se deben realizar.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-107">The following setup processes are listed in the order that you should complete them in.</span></span>

## <a name="required-baseline-setup-in-other-modules"></a><span data-ttu-id="8f2cd-108">Configuración de línea base requerida en los demás módulos</span><span class="sxs-lookup"><span data-stu-id="8f2cd-108">Required baseline setup in other modules</span></span>
<span data-ttu-id="8f2cd-109">Para poder trabajar con Control de producción, debe configurarse previamente información en los demás módulos.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-109">Information in other modules must be set up before you can work with Production control.</span></span> <span data-ttu-id="8f2cd-110">Esta configuración incluye las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8f2cd-110">This setup includes the following tasks:</span></span>

-   <span data-ttu-id="8f2cd-111">La configuración de la información general de la empresa.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-111">Set up general company information.</span></span>
-   <span data-ttu-id="8f2cd-112">La configuración de la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-112">Set up the general ledger.</span></span>
-   <span data-ttu-id="8f2cd-113">La definición de grupos de artículos.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-113">Define item groups.</span></span>
-   <span data-ttu-id="8f2cd-114">La configuración de cuentas contables para grupos de artículos.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-114">Set up ledger accounts for item groups.</span></span>
-   <span data-ttu-id="8f2cd-115">La configuración de la tabla de artículos de inventario en Gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-115">Set up the inventory item table in Inventory management.</span></span>
-   <span data-ttu-id="8f2cd-116">La creación de listas de materiales (L. MAT.) y versiones de L. MAT. en Gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-116">Create bills of materials (BOMs) and BOM versions in Inventory management.</span></span>

## <a name="required-calendar-and-resource-setup"></a><span data-ttu-id="8f2cd-117">Configuración necesaria del calendario y del recurso</span><span class="sxs-lookup"><span data-stu-id="8f2cd-117">Required calendar and resource setup</span></span>
<span data-ttu-id="8f2cd-118">Antes de utilizar Control de producción, abra Administración de la organización y cree y defina el calendario y los recursos de operaciones en el orden siguiente:</span><span class="sxs-lookup"><span data-stu-id="8f2cd-118">Before you use Production control, open Organization administration, and create and define the calendar and operations resources in the following order:</span></span>

1.  <span data-ttu-id="8f2cd-119">**Plantillas de horarios de trabajo**: configure las plantillas de horarios de trabajo para definir los tiempos que están disponibles para la programación de producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-119">**Working time templates** – Set up working time templates to define the times that are available for production scheduling.</span></span>
2.  <span data-ttu-id="8f2cd-120">**Calendarios**: configure los calendarios de horarios de trabajo para definir los días de año que están disponibles para la programación de producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-120">**Calendars** – Set up working time calendars to define the days of the year that are available for production scheduling.</span></span>
3.  <span data-ttu-id="8f2cd-121">**Grupos de recursos**: configure los grupos de recursos para agrupar los recursos de operaciones y, así, obtener una visión general de las capacidades libres cuando se ejecuta la programación.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-121">**Resource groups** – Set up resource groups to group the operations resources, so that you can get an overview of any free capacity when you run scheduling.</span></span> <span data-ttu-id="8f2cd-122">No tiene que configurar grupos de recursos antes de configurar recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-122">You don't have to set up resource groups before you set up operations resources.</span></span> <span data-ttu-id="8f2cd-123">Sin embargo, recomendamos que entienda cómo se agrupan recursos cuando configura Control de producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-123">However, we recommend that you understand how to group resources when you set up Production control.</span></span>
4.  <span data-ttu-id="8f2cd-124">**Recursos**: configure los recursos de operaciones para definir los recursos utilizados para completar el proceso de producción y planificar la capacidad.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-124">**Resources** – Set up operations resources to define the resources that are used to complete the production process and plan for capacity.</span></span>

## <a name="required-production-parameters-setup"></a><span data-ttu-id="8f2cd-125">Configuración de parámetros de producción</span><span class="sxs-lookup"><span data-stu-id="8f2cd-125">Required production parameters setup</span></span>
<span data-ttu-id="8f2cd-126">**Parámetros de control de producción**: configure los parámetros de producción básicos para definir cómo debe el sistema gestionar y procesar los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-126">**Production control parameters** – Set up basic production parameters to define how the system handles and processes production orders.</span></span> <span data-ttu-id="8f2cd-127">Defina cómo se crean, estiman, programan y consumen los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-127">Define how production orders are created, estimated, scheduled, and consumed.</span></span> <span data-ttu-id="8f2cd-128">También puede escoger qué clase de realimentación desea y cómo se realiza la contabilidad de costes.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-128">You can also select what kind of feedback you want and how cost accounting is done.</span></span>

## <a name="required-journal-name-identification"></a><span data-ttu-id="8f2cd-129">Identificación del nombre del diario</span><span class="sxs-lookup"><span data-stu-id="8f2cd-129">Required journal name identification</span></span>
<span data-ttu-id="8f2cd-130">**Nombres de diario de producción**: especifique los nombres de diario de producción que se usan para registrar y contabilizar transacciones.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-130">**Production journal names** – Specify the production journal names that are used to record and post transactions.</span></span>

## <a name="setup-if-you-use-operations"></a><span data-ttu-id="8f2cd-131">Configuración en caso de utilizar operaciones</span><span class="sxs-lookup"><span data-stu-id="8f2cd-131">Setup if you use operations</span></span>
<span data-ttu-id="8f2cd-132">Las operaciones representan las actividades específicas para obtener el producto final.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-132">Operations represent the specific activities that are completed to produce the finished product.</span></span> <span data-ttu-id="8f2cd-133">**Nota:** debe conocer a los tipos de actividades necesarias para producir el artículo, y el orden y las prioridades de dichas actividades.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-133">**Note:** You must know the types of activities that are required in order to produce your item, and the order and priorities of those activities.</span></span> <span data-ttu-id="8f2cd-134">También debe conocer qué recursos están involucrados y cuántos.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-134">You must also know which resources are involved, and how many.</span></span>

1.  <span data-ttu-id="8f2cd-135">**Operaciones**: configure las operaciones para representar las tareas que se deben realizar para producir el artículo finalizado.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-135">**Operations** – Set up operations to represent the tasks that must be completed to produce the finished item.</span></span>
2.  <span data-ttu-id="8f2cd-136">**Relaciones**: configure las relaciones de operaciones para establecer propiedades detalladas.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-136">**Relations** – Set up operation relations to establish detailed properties.</span></span> <span data-ttu-id="8f2cd-137">Para definir relaciones de operaciones, haga clic en **Relaciones** en la página **Operaciones**.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-137">To define operation relations, click **Relations** on the **Operations** page.</span></span>

## <a name="setup-if-you-use-routes"></a><span data-ttu-id="8f2cd-138">Configuración en caso de utilizar rutas</span><span class="sxs-lookup"><span data-stu-id="8f2cd-138">Setup if you use routes</span></span>
<span data-ttu-id="8f2cd-139">Si trabaja con rutas, deben definirse operaciones para cada ruta de producción configurada.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-139">If you're working with routes, operations must be defined for every production route that you set up.</span></span> <span data-ttu-id="8f2cd-140">La ruta representa la ruta que sigue el artículo de una operación a otra desde el inicio hasta el final del proceso.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-140">The route represents the path that the item takes from operation to operation, from the start of the production process to the end.</span></span>

1.  <span data-ttu-id="8f2cd-141">**Categorías de coste**: configure categorías de costes para definir el coste por hora de los procesos y las horas de configuración especificadas.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-141">**Cost categories** – Set up cost categories to define the cost per hour of specified processes and setup times.</span></span>
2.  <span data-ttu-id="8f2cd-142">**Grupos de coste**: configure grupos de costes para crear y mantener diferentes tipos de versiones de costes.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-142">**Cost groups** – Set up cost groups to create and maintain different types of costing.</span></span>
3.  <span data-ttu-id="8f2cd-143">**Grupos de rutas**: configure grupos de rutas para definir parámetros relacionados con los grupos de rutas.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-143">**Route groups** – Set up route groups to define parameters that are related to groups of routes.</span></span> <span data-ttu-id="8f2cd-144">Debe configurar los grupos de rutas antes de poder crear rutas de producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-144">You must set up route groups before you can create production routes.</span></span>
4.  <span data-ttu-id="8f2cd-145">**Rutas**: configure rutas de producción y defina los parámetros predeterminados para el control de programación, las operaciones de coste y el precio de rutas y controlar los informes de progreso.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-145">**Routes** – Set up production routes, and define default settings to control scheduling, costing, and pricing of route operations, and to control progress reporting.</span></span>
5.  <span data-ttu-id="8f2cd-146">**Rutas**: configure versiones de ruta para habilitar variaciones del artículo en la producción.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-146">**Routes** – Set up route versions to enable item variations in production.</span></span>

## <a name="optional-advanced-settings"></a><span data-ttu-id="8f2cd-147">Parámetros avanzados opcionales</span><span class="sxs-lookup"><span data-stu-id="8f2cd-147">Optional advanced settings</span></span>
1.  <span data-ttu-id="8f2cd-148">**Grupos de producción**: configure grupos de producción para establecer relaciones entre la orden de producción y las cuentas contables.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-148">**Production groups** – Set up production groups to establish relationships between the production order and ledger accounts.</span></span> <span data-ttu-id="8f2cd-149">Las cuentas contables se usan para registrar o agrupar pedidos que están listos para informe.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-149">The ledger accounts are used to post or group orders for reporting.</span></span>
2.  <span data-ttu-id="8f2cd-150">**Conjuntos de producción**: cree grupos de producción para agrupar órdenes de producción para el procesamiento de órdenes de producción urgentes o para la eliminación y el registro de grupos de pedidos.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-150">**Production pools** – Create production pools to group production orders so that you can process urgent production orders, or delete and post groups of orders.</span></span>
3.  <span data-ttu-id="8f2cd-151">**Propiedades**: defina propiedades para crear atributos especiales que puede asignar a sus recursos para controlar el orden de las producciones.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-151">**Properties** – Define properties to create special attributes that you can assign to your resources to control the order of productions.</span></span> <span data-ttu-id="8f2cd-152">Estos atributos x la plantilla de horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f2cd-152">These attributes are connected to the working time template.</span></span>





