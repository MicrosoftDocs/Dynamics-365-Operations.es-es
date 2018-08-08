---
title: "Envío parcial de una carga de transporte"
description: "Este tema explica cómo puede registrar parcialmente una carga y posponer la planificación de capacidad para la carga."
author: Mirzaab
manager: AnnBe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSTransportLoad
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 8c172f1b66e56f60e89f56ea98910f8d0e4f3e36
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="partial-shipment-of-a-transport-load"></a><span data-ttu-id="103d4-103">Envío parcial de una carga de transporte</span><span class="sxs-lookup"><span data-stu-id="103d4-103">Partial shipment of a transport load</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="103d4-104">Si configura el envío parcial de cargas, podrá gestionar las cargas en las que la capacidad no se pueda determinar hasta que todas las líneas de ventas se hayan agregado a una carga.</span><span class="sxs-lookup"><span data-stu-id="103d4-104">By setting up partial shipment of loads, you can handle loads where the capacity can't be determined until all the sales lines have been added to a load.</span></span> <span data-ttu-id="103d4-105">El proceso puede ser concluido cuando ya se conoce el recuento exacto del pallet.</span><span class="sxs-lookup"><span data-stu-id="103d4-105">The process can then be finalized when the exact pallet count is known.</span></span> <span data-ttu-id="103d4-106">Por lo tanto, no es necesario decidir qué pallets se asignarán a qué transporte hasta el momento en que un transporte se carga físicamente fuera del inventario.</span><span class="sxs-lookup"><span data-stu-id="103d4-106">Therefore, you don't have to decide which pallets will be assigned to which transport until the moment when a transport is being physically loaded out of the staged inventory.</span></span>

<span data-ttu-id="103d4-107">Esta característica permite una alternativa al cumplimiento de una estructura más rígida, donde debe determinar qué pallets se asignarán a qué transporte antes de que se cree el trabajo de picking o el trabajo de carga.</span><span class="sxs-lookup"><span data-stu-id="103d4-107">This feature offers an alternative to the enforcement of a more rigid structure, where you must determine which pallets will be assigned to which transport before picking work or loading work can be created.</span></span> <span data-ttu-id="103d4-108">En su lugar, los usuarios pueden configurar cargas individuales para una confirmación de envío parcial.</span><span class="sxs-lookup"><span data-stu-id="103d4-108">Instead, users can configure individual loads for a partial shipment confirmation.</span></span> <span data-ttu-id="103d4-109">Los procesos de carga del transporte para esas cargas pueden ocurrir continuación.</span><span class="sxs-lookup"><span data-stu-id="103d4-109">The transport loading processes for those loads can then occur.</span></span> <span data-ttu-id="103d4-110">Por lo tanto, el departamento de planificación de transporte puede planificar las cargas sin tener que tener en cuenta la capacidad de transportes individuales.</span><span class="sxs-lookup"><span data-stu-id="103d4-110">Therefore, the transportation planning department can plan loads without having to consider the capacity of individual transports.</span></span>

<span data-ttu-id="103d4-111">En el momento de la carga, los trabajadores pueden definir una nueva carga de transporte que se puede cargar a un pallet.</span><span class="sxs-lookup"><span data-stu-id="103d4-111">At the time of loading, workers can define a new transport load that a pallet can be loaded to.</span></span> <span data-ttu-id="103d4-112">Como alternativa, puede identificar una carga de transporte existente.</span><span class="sxs-lookup"><span data-stu-id="103d4-112">Alternatively, they can identify an existing transport load.</span></span> <span data-ttu-id="103d4-113">Estos datos se pueden registrar mediante un dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="103d4-113">This data can be recorded via a mobile device.</span></span> <span data-ttu-id="103d4-114">Por lo tanto, varios trabajadores de almacén pueden cargar el inventario desde las mismas cargas o distintas de cargas sobre el mismo camión.</span><span class="sxs-lookup"><span data-stu-id="103d4-114">Therefore, several warehouse workers can load inventory from the same loads or different loads onto the same truck.</span></span> <span data-ttu-id="103d4-115">Las cargas a continuación pueden enviarse total o parcialmente.</span><span class="sxs-lookup"><span data-stu-id="103d4-115">The loads can then be fully or partially shipped.</span></span>

> [!NOTE] 
> <span data-ttu-id="103d4-116">Para cargar el inventario de una carga a una carga específica de transporte y registrar parcialmente la carga, el trabajo se debe generar mediante una clase de carga en una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="103d4-116">In order to load inventory from a load to a specific transport load and partially ship the load, work must be generated by using a loading class in a work template.</span></span> <span data-ttu-id="103d4-117">El trabajo habitual de picking del tipo **Picking** no se puede cargar a una carga de transporte como un camión.</span><span class="sxs-lookup"><span data-stu-id="103d4-117">Ordinary picking work of the **Picking** type can't be loaded to a transport load such as a truck.</span></span>

## <a name="set-up-transport-loads-for-partial-shipment"></a><span data-ttu-id="103d4-118">Configurar cargas de transporte para envío parcial</span><span class="sxs-lookup"><span data-stu-id="103d4-118">Set up transport loads for partial shipment</span></span>

<span data-ttu-id="103d4-119">La configuración del envío parcial de cargas consta de los dos procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="103d4-119">The setup for partial shipment of loads consists of the following two procedures.</span></span>

### <a name="set-the-loading-strategy"></a><span data-ttu-id="103d4-120">Establecer la estrategia de carga</span><span class="sxs-lookup"><span data-stu-id="103d4-120">Set the loading strategy</span></span>

<span data-ttu-id="103d4-121">Debe habilitar la carga parcial estableciendo la estrategia de carga.</span><span class="sxs-lookup"><span data-stu-id="103d4-121">You must enable partial loading by setting the loading strategy.</span></span> <span data-ttu-id="103d4-122">Puede establecer la estrategia de carga después de que haya creado una carga.</span><span class="sxs-lookup"><span data-stu-id="103d4-122">You can set the loading strategy after you've created a load.</span></span>

1. <span data-ttu-id="103d4-123">Seleccione **Gestión de almacenes** \> **Cargas** \> **Todos cargas**.</span><span class="sxs-lookup"><span data-stu-id="103d4-123">Select **Warehouse management** \> **Loads** \> **All loads**.</span></span>
2. <span data-ttu-id="103d4-124">Seleccione una carga y, a continuación, haga clic en **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="103d4-124">Select a load, and then click **Header**.</span></span>
3. <span data-ttu-id="103d4-125">En el campo **Estrategia de carga**, seleccione **Envío parcial de carga permitido**.</span><span class="sxs-lookup"><span data-stu-id="103d4-125">In the **Loading strategy** field, select **Partial load shipping allowed**.</span></span>

### <a name="create-a-menu-item-for-loading-of-transport-loads"></a><span data-ttu-id="103d4-126">Crear un artículo de menú para carga de las cargas de transporte</span><span class="sxs-lookup"><span data-stu-id="103d4-126">Create a menu item for loading of transport loads</span></span>

<span data-ttu-id="103d4-127">Debe crear un nuevo artículo de menú que habilite las cargas de transporte que se cargarán.</span><span class="sxs-lookup"><span data-stu-id="103d4-127">You must create a new menu item that enables transport loads to be loaded.</span></span> <span data-ttu-id="103d4-128">Una carga de transporte le permite agrupar líneas del grupo de trabajo a partir de una carga o de múltiples cargas.</span><span class="sxs-lookup"><span data-stu-id="103d4-128">A transport load lets you group work lines from one load or multiple loads.</span></span> <span data-ttu-id="103d4-129">Todo lo que se agrega a la carga de transporte se puede enviar usando un escáner móvil.</span><span class="sxs-lookup"><span data-stu-id="103d4-129">Everything that is added to the transport load can then be shipped by using a mobile scanner.</span></span>

1. <span data-ttu-id="103d4-130">Seleccione **Gestión de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="103d4-130">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="103d4-131">Seleccione **Nuevo** y, en el campo **Modo**, seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="103d4-131">Select **New**, and then, in the **Mode** field, select **Work**.</span></span>
3. <span data-ttu-id="103d4-132">Establezca la opción **Usar trabajo existente** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="103d4-132">Set the **Use existing work** option to **Yes**.</span></span>
4. <span data-ttu-id="103d4-133">En la ficha **General**, en el campo **Dirigido por**, seleccione **Carga de transporte**.</span><span class="sxs-lookup"><span data-stu-id="103d4-133">On the **General** tab, in the **Directed by** field, select **Transport loading**.</span></span>
5. <span data-ttu-id="103d4-134">Para habilitar la confirmación de envío en un escáner móvil, en el campo **Tipo de confirmación de envío permitida**, seleccione **Carga de transporte**.</span><span class="sxs-lookup"><span data-stu-id="103d4-134">To enable shipment confirmation on a mobile scanner, in the **Allowed ship confirmation type** field, select **Transport load**.</span></span>

## <a name="confirm-shipment-of-a-transport-load-from-the-client"></a><span data-ttu-id="103d4-135">Confirmar el envío de una carga de transporte desde el cliente</span><span class="sxs-lookup"><span data-stu-id="103d4-135">Confirm shipment of a transport load from the client</span></span>

<span data-ttu-id="103d4-136">Esta configuración le permite confirmar una carga de transporte que incluya una carga completa o una carga parcial cargada que ser enviada</span><span class="sxs-lookup"><span data-stu-id="103d4-136">This setup lets you confirm a transport load that includes a full load or a partially loaded load to be shipped.</span></span>

1. <span data-ttu-id="103d4-137">Seleccione **Gestión de almacenes** \> **Cargas** \> **Cargas de transporte**.</span><span class="sxs-lookup"><span data-stu-id="103d4-137">Select **Warehouse management** \> **Loads** \> **Transport loads**.</span></span>
2. <span data-ttu-id="103d4-138">En el panel de acciones, en la ficha **Enviar y recibir**, en el grupo **Confirmar**, seleccione **Transporte**.</span><span class="sxs-lookup"><span data-stu-id="103d4-138">On the Action Pane, on the **Ship and receive** tab, in the **Confirm** group, select **Transport**.</span></span>

