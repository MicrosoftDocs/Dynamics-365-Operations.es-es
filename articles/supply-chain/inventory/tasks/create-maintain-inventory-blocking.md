---
title: Creación y mantenimiento de un bloqueo del inventario
description: Este tema describe cómo usar un bloqueo de inventario para impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e9aa38ca52da577fff258bb330922ad7f4044330
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956167"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="9e0b2-103">Creación y mantenimiento de un bloqueo del inventario</span><span class="sxs-lookup"><span data-stu-id="9e0b2-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e0b2-104">Este tema describe cómo usar un bloqueo de inventario para impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-104">This topic describes how to use an inventory blocking to prevent physical on-hand inventory from being reserved by other outbound source documents.</span></span> <span data-ttu-id="9e0b2-105">Necesita tener un artículo con inventario disponible físico antes de comenzar los procedimientos de este tema.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-105">Before you start the procedures in this topic, you must have an item that physical on-hand inventory is available for.</span></span>

## <a name="block-inventory"></a><span data-ttu-id="9e0b2-106">Bloquear inventario</span><span class="sxs-lookup"><span data-stu-id="9e0b2-106">Block inventory</span></span>

<span data-ttu-id="9e0b2-107">Para crear un registro de bloqueo de inventario de modo que el inventario esté bloqueado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-107">To create an inventory blocking record so that inventory is blocked, follow these steps.</span></span>

1. <span data-ttu-id="9e0b2-108">Vaya a **Gestión del inventario \> Tareas periódicas \> Bloqueo del inventario**.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-108">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="9e0b2-109">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-109">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="9e0b2-110">En el encabezado del nuevo registro de bloqueo, establezca el campo **Número de artículo** al elemento que desea bloquear e introduzca una descripción.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-110">On the header of the new blocking record, set the **Item number** field to the item that you want to block, and enter a description.</span></span>
1. <span data-ttu-id="9e0b2-111">En la ficha desplegable **General**, en el campo **Cantidad** escriba el número de artículos a bloquear.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-111">On the **General** FastTab, in the **Quantity** field, enter the number of items to block.</span></span>
1. <span data-ttu-id="9e0b2-112">En la ficha desplegable **Dimensiones de inventario**, especifique el sitio y el almacén donde se encuentran actualmente los artículos que desea bloquear.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-112">On the **Inventory dimensions** FastTab, specify the site and warehouse where the items that you want to block are currently located.</span></span>
1. <span data-ttu-id="9e0b2-113">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-113">On the Action Pane, select **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="9e0b2-114">Actualización de las condiciones de bloqueo de inventario</span><span class="sxs-lookup"><span data-stu-id="9e0b2-114">Update the conditions of the inventory blocking</span></span>

<span data-ttu-id="9e0b2-115">Para actualizar un registro de bloqueo de inventario, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-115">To update an inventory blocking record, follow these steps.</span></span>

1. <span data-ttu-id="9e0b2-116">Vaya a **Gestión del inventario \> Tareas periódicas \> Bloqueo del inventario**.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-116">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="9e0b2-117">En el panel de lista, seleccione el registro de bloqueo relevante.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-117">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="9e0b2-118">Edite el registro según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-118">Edit the record as required.</span></span> <span data-ttu-id="9e0b2-119">Por ejemplo, podría cambiar el valor del campo **Fecha esperada** para indicar cuándo se espera que el inventario bloqueado quede disponible para reserva.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-119">For example, you might change the value of the **Expected date** field to indicate when the blocked inventory is expected to become available for reservation.</span></span> <span data-ttu-id="9e0b2-120">Si la opción **Recepciones esperadas** está seleccionada, la fecha aparecerá en la transacción esperada.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-120">If the **Expected receipts** option is selected, the date will appear on the expected transaction.</span></span> <span data-ttu-id="9e0b2-121">(La opción **Recepciones esperadas** está seleccionada de forma predeterminada cuando crea manualmente un registro de bloqueo).</span><span class="sxs-lookup"><span data-stu-id="9e0b2-121">(The **Expected receipts** option is selected by default when you manually create a blocking record.)</span></span>
1. <span data-ttu-id="9e0b2-122">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-122">On the Action Pane, select **Save**.</span></span>

## <a name="unblock-inventory"></a><span data-ttu-id="9e0b2-123">Desbloquear inventario</span><span class="sxs-lookup"><span data-stu-id="9e0b2-123">Unblock inventory</span></span>

<span data-ttu-id="9e0b2-124">Para eliminar un registro de bloqueo de inventario de modo que el inventario esté bloqueado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-124">To remove an inventory blocking record so that inventory is unblocked, follow these steps.</span></span>

1. <span data-ttu-id="9e0b2-125">Vaya a **Gestión del inventario \> Tareas periódicas \> Bloqueo del inventario**.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-125">Go to **Inventory management \> Periodic tasks \> Inventory blocking**.</span></span>
1. <span data-ttu-id="9e0b2-126">En el panel de lista, seleccione el registro de bloqueo relevante.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-126">In the list pane, select the relevant blocking record.</span></span>
1. <span data-ttu-id="9e0b2-127">En el panel de acciones, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-127">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="9e0b2-128">Se le pedirá que confirme la operación.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-128">You're prompted to confirm the operation.</span></span> <span data-ttu-id="9e0b2-129">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-129">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="9e0b2-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="9e0b2-130">Close the page.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
