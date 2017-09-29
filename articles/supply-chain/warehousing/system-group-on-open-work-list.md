---
title: Agrupamiento del sistema en una lista de trabajo abierta
description: "Este tema describe cómo filtrar la lista de trabajos abierta en un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 0c68d544fec985f325e6472203533f23948cc9b4
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="system-grouping-on-an-open-work-list"></a><span data-ttu-id="e5b6a-103">Agrupamiento del sistema en una lista de trabajo abierta</span><span class="sxs-lookup"><span data-stu-id="e5b6a-103">System grouping on an open work list</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e5b6a-104">Usando un campo de agrupamiento del sistema puede filtrar una lista de trabajos abierta sin tener que editar el elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-104">By using a system grouping field, you can filter an open work list without having to edit the mobile device menu item.</span></span>
<span data-ttu-id="e5b6a-105">Donde corresponda, el agrupamiento del sistema funciona para filtrar una lista de trabajos en un solo campo de encabezados de trabajos.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-105">Where it applies, system grouping works for filtering a work list on a single work header field.</span></span> <span data-ttu-id="e5b6a-106">No puede usar el agrupamiento del sistema para filtrar campos en el nivel de línea.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-106">You cannot use system grouping to filter on line level fields.</span></span>

## <a name="set-up-system-grouping-on-an-open-work-list"></a><span data-ttu-id="e5b6a-107">Configuración del agrupamiento del sistema en una lista de trabajos abierta</span><span class="sxs-lookup"><span data-stu-id="e5b6a-107">Set up system grouping on an open work list</span></span>
<span data-ttu-id="e5b6a-108">Siga estos pasos para configurar el agrupamiento del sistema en una lista de trabajos abierta.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-108">Use these steps to set up system grouping on an open work list.</span></span>

-   <span data-ttu-id="e5b6a-109">Desde un elemento de menú del dispositivo móvil, seleccione **Modo: Indirecto** y **Código de actividad: Mostrar lista de trabajo abierta**.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-109">From a mobile device menu item, select **Mode: Indirect** and **Activity Code: Display open work list**.</span></span> <span data-ttu-id="e5b6a-110">Están disponibles las siguientes opciones.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-110">The following options become available.</span></span> <span data-ttu-id="e5b6a-111">Estas opciones son obligatorias para el agrupamiento del sistema en una lista de trabajo abierta.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-111">These options are required for system grouping on an open work list.</span></span> 

| <span data-ttu-id="e5b6a-112">Opción</span><span class="sxs-lookup"><span data-stu-id="e5b6a-112">Option</span></span>        | <span data-ttu-id="e5b6a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="e5b6a-113">Description</span></span>   | 
| ------------- | ------------- |
| <span data-ttu-id="e5b6a-114">Permitir agrupamientos del sistema</span><span class="sxs-lookup"><span data-stu-id="e5b6a-114">Allow system grouping</span></span>   | <span data-ttu-id="e5b6a-115">Habilita los agrupamientos del sistema para un elemento de menú seleccionado de la lista de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-115">Enables system groping for a selected work list menu item.</span></span>| 
| <span data-ttu-id="e5b6a-116">Campo de agrupamiento del sistema</span><span class="sxs-lookup"><span data-stu-id="e5b6a-116">System grouping field</span></span>   | <span data-ttu-id="e5b6a-117">Disponible solo si **Permitir trabajos del sistema** está configurado en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-117">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="e5b6a-118">Seleccione el campo que determina cómo se agrupará el trabajo de selección para los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-118">Select the field that determines how picking work will be grouped for workers.</span></span> <span data-ttu-id="e5b6a-119">Por ejemplo, si selecciona el campo **ShipmentId**, el trabajador explorará la identificación del envío para agrupar el trabajo de picking.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-119">For example, if you select the **ShipmentId** field, the worker will scan the shipment ID to group the picking work.</span></span> <span data-ttu-id="e5b6a-120">Todo el trabajo para el envío se asigna al trabajador.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-120">All work for the shipment is then assigned to the worker.</span></span> <span data-ttu-id="e5b6a-121">Este campo requiere que cree un elemento de menú para usar el trabajo existente que el sistema ha agrupado.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-121">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="e5b6a-122">Use el campo **Etiqueta de agrupamiento del sistema** para informar al trabajador de qué debe escanear.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-122">Use the **System grouping label** field to inform the worker what to scan.</span></span> |
| <span data-ttu-id="e5b6a-123">Etiqueta de agrupamiento del sistema</span><span class="sxs-lookup"><span data-stu-id="e5b6a-123">System grouping label</span></span>   | <span data-ttu-id="e5b6a-124">Disponible solo si **Permitir trabajos del sistema** está configurado en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-124">Available only if **Allow system work** is set to **Yes**.</span></span> <span data-ttu-id="e5b6a-125">Especifique la información para el trabajador sobre qué escanear cuando el trabajo de selección se agrupe.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-125">Enter information for the worker about what to scan when picking work is grouped.</span></span> <span data-ttu-id="e5b6a-126">Por ejemplo, si usa el campo **ShipmentId** para agrupar el trabajo de selección por envíos, puede especificar el Id. del envío en el campo.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-126">For example, if you use the **ShipmentId** field to group picking work by shipment, you might enter Shipment ID in the field.</span></span> <span data-ttu-id="e5b6a-127">Este campo requiere que cree un elemento de menú para usar el trabajo existente que el sistema ha agrupado.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-127">This field requires that you create a menu item to use existing work that is grouped by the system.</span></span> <span data-ttu-id="e5b6a-128">También debe seleccionar el campo por el que desea agrupar en el campo **Agrupamiento del sistema**.</span><span class="sxs-lookup"><span data-stu-id="e5b6a-128">You must also select the field to group by in the **System grouping** field.</span></span>|

