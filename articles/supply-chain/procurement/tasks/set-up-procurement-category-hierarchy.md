---
title: Configurar una jerarquía de categorías de compras
description: Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra.
author: mkirknel
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c7010fb702d16dc276bfee397066ccf95bf5d25a
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147282"
---
# <a name="set-up-a-procurement-category-hierarchy"></a><span data-ttu-id="ba681-103">Configurar una jerarquía de categorías de compras</span><span class="sxs-lookup"><span data-stu-id="ba681-103">Set up a procurement category hierarchy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba681-104">Este procedimiento muestra cómo crear nuevos nodos en una jerarquía de categorías de compras y cómo configurar una categoría de compras para usarla en un proceso de compra.</span><span class="sxs-lookup"><span data-stu-id="ba681-104">This procedure shows you how to create new nodes in a procurement category hierarchy and how to configure a procurement category to be used in a procurement process.</span></span> <span data-ttu-id="ba681-105">Estas tareas las realizará normalmente el director de compras.</span><span class="sxs-lookup"><span data-stu-id="ba681-105">These tasks would typically be carried out by a Purchasing manager.</span></span> <span data-ttu-id="ba681-106">Para poder comenzar este procedimiento, debe haber una jerarquía de categorías de tipo Adquisición.</span><span class="sxs-lookup"><span data-stu-id="ba681-106">Before you can start this procedure, there must be a category hierarchy of type Procurement.</span></span> <span data-ttu-id="ba681-107">Si usa una empresa de datos de demostración, puede ejecutar este procedimiento en la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="ba681-107">If you're using a demo data company, you can run this procedure in the USMF company.</span></span>


## <a name="add-a-new-procurement-category"></a><span data-ttu-id="ba681-108">Adición de una nueva categoría de compras</span><span class="sxs-lookup"><span data-stu-id="ba681-108">Add a new procurement category</span></span>
1. <span data-ttu-id="ba681-109">Vaya a **Panel de exploración > Módulos > Adquisición y abastecimiento > Entrega > Categorías de adquisición**.</span><span class="sxs-lookup"><span data-stu-id="ba681-109">Go to **Navigation pane > Modules > Procurement and sourcing > Consignment > Procurement categories**.</span></span>
2. <span data-ttu-id="ba681-110">En el Panel de acción, seleccione **Editar jerarquía de categoría**.</span><span class="sxs-lookup"><span data-stu-id="ba681-110">On the action pane, select **Edit category hierarchy**.</span></span> <span data-ttu-id="ba681-111">La jerarquía de la categoría de compras actual se muestra en el lado izquierdo de la página.</span><span class="sxs-lookup"><span data-stu-id="ba681-111">The current procurement category hierarchy is displayed in the left side of the page.</span></span> <span data-ttu-id="ba681-112">Va a modificar la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="ba681-112">You  are about to modify the hierarchy.</span></span>  
3. <span data-ttu-id="ba681-113">En el Panel de acción, seleccione **Nueva categoría de nodo**.</span><span class="sxs-lookup"><span data-stu-id="ba681-113">On the action pane, select **New category node**.</span></span> <span data-ttu-id="ba681-114">El sistema selecciona el nodo superior de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ba681-114">The system selects the top node by default.</span></span> <span data-ttu-id="ba681-115">Si está ejecutando este procedimiento como guía de tarea, puede hacer clic en el botón Desbloquear y seleccionar otro nodo principal donde insertar su nuevo nodo.</span><span class="sxs-lookup"><span data-stu-id="ba681-115">If you are running this procedure as a task guide, you can click the Unlock button and select another parent node to insert your new node into.</span></span> <span data-ttu-id="ba681-116">Una vez hecho, bloquee la guía de tarea de nuevo y haga clic en Nodo de categoría nueva.</span><span class="sxs-lookup"><span data-stu-id="ba681-116">Once that is done, lock the task guide again and then click New category node.</span></span>  
4. <span data-ttu-id="ba681-117">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba681-117">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="ba681-118">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba681-118">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="ba681-119">En el campo **Nombre descriptivo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ba681-119">In the **Friendly name** field, type a value.</span></span> <span data-ttu-id="ba681-120">El nombre descriptivo es opcional.</span><span class="sxs-lookup"><span data-stu-id="ba681-120">The friendly name is optional.</span></span> <span data-ttu-id="ba681-121">Se mostrará en las búsquedas de categorías junto con el nombre de la categoría.</span><span class="sxs-lookup"><span data-stu-id="ba681-121">It will be displayed in category lookups together with the category name.</span></span>  
7. <span data-ttu-id="ba681-122">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ba681-122">Select **Save**.</span></span>

## <a name="add-products-to-your-new-procurement-category"></a><span data-ttu-id="ba681-123">Adición de productos a su nueva categoría de compra</span><span class="sxs-lookup"><span data-stu-id="ba681-123">Add products to your new procurement category</span></span>
1. <span data-ttu-id="ba681-124">Vaya a **Adquisición y abastecimiento > Entrega > Categorías de compras**.</span><span class="sxs-lookup"><span data-stu-id="ba681-124">Go to **Procurement and sourcing > Consignment > Procurement categories**.</span></span> <span data-ttu-id="ba681-125">Seleccione el nodo que acaba de agregar.</span><span class="sxs-lookup"><span data-stu-id="ba681-125">Select the node you just added.</span></span> <span data-ttu-id="ba681-126">Si está ejecutando este procedimiento como guía de tarea, puede que tenga que desbloquear la guía de tarea para seleccionar el nodo.</span><span class="sxs-lookup"><span data-stu-id="ba681-126">If you're running this procedure as a task guide you might need to unlock the task guide to select the node.</span></span>  
2. <span data-ttu-id="ba681-127">Expanda la sección **Productos**.</span><span class="sxs-lookup"><span data-stu-id="ba681-127">Toggle the expansion of the **Products** section.</span></span>
3. <span data-ttu-id="ba681-128">Seleccione **Agregar** para asociar productos con la categoría de adquisición.</span><span class="sxs-lookup"><span data-stu-id="ba681-128">Select **Add** to associate products with the procurement category.</span></span>
4. <span data-ttu-id="ba681-129">Seleccione los productos que desea agregar a la categoría de adquisición.</span><span class="sxs-lookup"><span data-stu-id="ba681-129">Select the products you want to add to the procurement category.</span></span>
5. <span data-ttu-id="ba681-130">Seleccione la flecha para agregar los productos a la tabla **Seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="ba681-130">Select the arrow to add the products to the **Selected** table.</span></span>
6. <span data-ttu-id="ba681-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba681-131">Select **OK**.</span></span>
