---
title: Ubicaciones del inventario
description: "Las ubicaciones de inventario se usan con el almacenamiento básico (WMS I) para determinar dónde se almacenan los artículos y dónde se seleccionan los artículos desde un almacén de WMS I."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 22f4d0c93b0fccdb5439998a68add7b7e0e7750b
ms.contentlocale: es-es
ms.lasthandoff: 09/12/2017

---

# <a name="inventory-locations"></a><span data-ttu-id="d1d69-103">Ubicaciones del inventario</span><span class="sxs-lookup"><span data-stu-id="d1d69-103">Inventory locations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d1d69-104">Las ubicaciones de inventario se usan con el almacenamiento básico (WMS I) para determinar dónde se almacenan los artículos y dónde se seleccionan los artículos desde un almacén de WMS I.</span><span class="sxs-lookup"><span data-stu-id="d1d69-104">Inventory locations are used with basic warehousing (WMS I) to determine where items are stored and where items are picked from in a WMS I warehouse.</span></span>

<span data-ttu-id="d1d69-105">Este tema se aplica a las características en el módulo de Gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="d1d69-105">This topic applies to features in the Inventory management module.</span></span> <span data-ttu-id="d1d69-106">No se aplica a las características en el módulo de Administración de almacenes.</span><span class="sxs-lookup"><span data-stu-id="d1d69-106">It does not apply to features in the Warehouse management module.</span></span>

<span data-ttu-id="d1d69-107">El término ubicación hace referencia al lugar en el que se almacenan los artículos y del que se extraen.</span><span class="sxs-lookup"><span data-stu-id="d1d69-107">The term location refers to the place that items are stored and drawn from.</span></span>

<span data-ttu-id="d1d69-108">Para cada ubicación, también se puede especificar el lugar en el que se inserta el artículo.</span><span class="sxs-lookup"><span data-stu-id="d1d69-108">For each location, the place where the item is inserted can also be specified.</span></span> <span data-ttu-id="d1d69-109">De forma predeterminada, coinciden.</span><span class="sxs-lookup"><span data-stu-id="d1d69-109">By default, they are the same.</span></span> <span data-ttu-id="d1d69-110">Los artículos normalmente se insertan y extraen de la misma parte una ubicación, aunque no siempre.</span><span class="sxs-lookup"><span data-stu-id="d1d69-110">Items are usually inserted and drawn from the same side of a location, but not always.</span></span> <span data-ttu-id="d1d69-111">Por ejemplo, los artículos almacenados en estanterías de almacenamiento se insertan desde un pasillo y se extraen desde otro.</span><span class="sxs-lookup"><span data-stu-id="d1d69-111">For example, items that are stored in live storage racks are inserted from one aisle and drawn from another.</span></span> <span data-ttu-id="d1d69-112">La entrada principal la proporciona el nombre de la ubicación, que normalmente se determina por sus coordenadas: almacén, pasillo, estantería, balda y hueco.</span><span class="sxs-lookup"><span data-stu-id="d1d69-112">The main input is given by a location name, which is usually determined by its coordinates: warehouse, aisle, rack, shelf, and bin.</span></span> <span data-ttu-id="d1d69-113">Este nombre o id. se puede especificar manualmente o generarse desde las coordenadas de la ubicación (por ejemplo, 01-02-03-4 para el pasillo 1, la estantería 2, la balda 3 y el hueco 4 en la página Ubicaciones de inventario).</span><span class="sxs-lookup"><span data-stu-id="d1d69-113">This name or ID can be entered manually or generated from the location coordinates—for example, 01-02-03-4 for aisle 1, rack 2, shelf 3, bin 4 in the Inventory locations page.</span></span>
<span data-ttu-id="d1d69-114">Propiedades de ubicación</span><span class="sxs-lookup"><span data-stu-id="d1d69-114">Location properties</span></span>

<span data-ttu-id="d1d69-115">Una ubicación tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="d1d69-115">A location has the following characteristics:</span></span>
-   <span data-ttu-id="d1d69-116">Tamaño (alto, ancho, profundidad y, por tanto, volumen)</span><span class="sxs-lookup"><span data-stu-id="d1d69-116">Size (height, width, depth, and thereby volume)</span></span>
-   <span data-ttu-id="d1d69-117">Almacén, pasillo, estantería, balda y posición en hueco</span><span class="sxs-lookup"><span data-stu-id="d1d69-117">Warehouse, aisle, rack, shelf, and bin position</span></span>
-   <span data-ttu-id="d1d69-118">Tipo de ubicación (ubicación de almacenaje, ubicación de picking, muelle de llegada, muelle de salida, ubicación de entrada de producción, ubicación de inspección o supermercado kanban)</span><span class="sxs-lookup"><span data-stu-id="d1d69-118">Location type (bulk location, picking location, inbound dock, outbound dock, production input location, inspection location, or kanban supermarket)</span></span>

<span data-ttu-id="d1d69-119">El texto de comprobación puede usarse en sistemas en línea para comprobar si el operador ha seleccionado la ubicación correcta para un artículo concreto.</span><span class="sxs-lookup"><span data-stu-id="d1d69-119">Check text can be used in online systems to verify that the operator has selected the correct location for a specific item.</span></span> <span data-ttu-id="d1d69-120">Este texto de comprobación se puede crear manualmente o de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d1d69-120">This check text can be created manually or by default.</span></span>

## <a name="sort-codes"></a><span data-ttu-id="d1d69-121">Códigos de ordenación</span><span class="sxs-lookup"><span data-stu-id="d1d69-121">Sort codes</span></span>
<span data-ttu-id="d1d69-122">Use códigos de ordenación para optimizar la gestión de líneas de selección, que detallan la información necesaria para los artículos de selección desde el inventario, incluido el pedido de selección.</span><span class="sxs-lookup"><span data-stu-id="d1d69-122">Use sort codes to optimize the handling of picking lines, which describe the information that is required for picking items from inventory, including the picking order.</span></span> <span data-ttu-id="d1d69-123">Los códigos de ordenación se pueden especificar por pasillo y otras coordenadas, o bien puede asignarse manualmente para la ubicación.</span><span class="sxs-lookup"><span data-stu-id="d1d69-123">Sort codes can be specified by the aisle and other coordinates, or assigned manually for the location.</span></span>

## <a name="blocked-locations"></a><span data-ttu-id="d1d69-124">Ubicaciones bloqueadas</span><span class="sxs-lookup"><span data-stu-id="d1d69-124">Blocked locations</span></span>
<span data-ttu-id="d1d69-125">Ocasionalmente, quizás desee indicar que una ubicación está bloqueada durante un período de tiempo, por ejemplo, para permitir las reparaciones.</span><span class="sxs-lookup"><span data-stu-id="d1d69-125">Occasionally, you might want to indicate that a location is blocked for a period of time, for example, to allow for repairs.</span></span> <span data-ttu-id="d1d69-126">En otras ocasiones, es posible desee indicar el bloqueo de solo la entrada o solo la salida.</span><span class="sxs-lookup"><span data-stu-id="d1d69-126">At other times, you may want to indicate blocking of only the input or only output.</span></span>

## <a name="tree-structure"></a><span data-ttu-id="d1d69-127">Estructura en árbol</span><span class="sxs-lookup"><span data-stu-id="d1d69-127">Tree structure</span></span>

<span data-ttu-id="d1d69-128">En la página Ubicaciones de inventario, puede ver la configuración de almacén en una estructura en árbol basada en las coordenadas de ubicaciones de inventario, en un formato de representación definido.</span><span class="sxs-lookup"><span data-stu-id="d1d69-128">In the Inventory locations page, you can view the warehouse layout in a tree structure based on the coordinates of inventory locations, in a defined display format.</span></span>

## <a name="maintain-inventory-locations-via-the-warehouse-form"></a><span data-ttu-id="d1d69-129">Mantener las ubicaciones de inventario mediante el formulario de almacén</span><span class="sxs-lookup"><span data-stu-id="d1d69-129">Maintain inventory locations via the warehouse form</span></span>

<span data-ttu-id="d1d69-130">Es posible copiar las ubicaciones de un almacén a otro y crear ubicaciones a través de un asistente.</span><span class="sxs-lookup"><span data-stu-id="d1d69-130">It is possible to copy locations from one warehouse to another and to create locations via a wizard.</span></span> <span data-ttu-id="d1d69-131">Antes de ejecutar el asistente debe asegurarse de haber definido los nombres de la ubicación predeterminada en la página Almacén.</span><span class="sxs-lookup"><span data-stu-id="d1d69-131">Before you run the wizard you should make sure that you have defined the default location names on the Warehouse page.</span></span>



<a name="see-also"></a><span data-ttu-id="d1d69-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1d69-132">See also</span></span>
--------

[<span data-ttu-id="d1d69-133">Creación de un nuevo diseño de almacén (Guía de tareas)</span><span class="sxs-lookup"><span data-stu-id="d1d69-133">Create a new warehouse layout (Task guide)</span></span>](/dynamics365/unified-operations/supply-chain/inventory/tasks/create-new-warehouse-layout)

