---
title: Propietarios del producto
description: Este tema proporciona información acerca de los propietarios de productos. Un propietario de producto es un grupo de usuarios que son responsables de productos específicos. Solo los miembros del grupo pueden lanzar esos productos. El propietario del producto también se puede utilizar en el flujo de trabajo de aprobación.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 90f5596f9b5fc45e78cc49a3309c45864e07e70b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967342"
---
# <a name="product-owners"></a><span data-ttu-id="4af7a-106">Propietarios del producto</span><span class="sxs-lookup"><span data-stu-id="4af7a-106">Product owners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4af7a-107">El propietario del producto es un grupo de usuarios que son responsables de productos específicos.</span><span class="sxs-lookup"><span data-stu-id="4af7a-107">The product owner is a group of users who are responsible for specific products.</span></span> <span data-ttu-id="4af7a-108">Cuando un grupo de propietarios de productos se asigna a un producto, solo los miembros de ese grupo pueden lanzar el producto.</span><span class="sxs-lookup"><span data-stu-id="4af7a-108">When a product owner group is assigned to a product, only the members of that group can release the product.</span></span> <span data-ttu-id="4af7a-109">El propietario del producto también se puede utilizar en la gestión de cambios de ingteniería.</span><span class="sxs-lookup"><span data-stu-id="4af7a-109">The product owner can also be used in the approval workflow in engineering change management.</span></span>

<span data-ttu-id="4af7a-110">Los propietarios de productos son entornos globales.</span><span class="sxs-lookup"><span data-stu-id="4af7a-110">Product owners are global settings.</span></span> <span data-ttu-id="4af7a-111">Por tanto, están disponibles para todas las personas jurídicas.</span><span class="sxs-lookup"><span data-stu-id="4af7a-111">Therefore, they are available to all legal entities.</span></span>

## <a name="create-a-product-owner-group"></a><span data-ttu-id="4af7a-112">Crear un grupo de propietarios de productos</span><span class="sxs-lookup"><span data-stu-id="4af7a-112">Create a product owner group</span></span>

<span data-ttu-id="4af7a-113">Para crear un grupo de propietarios de productos y agregarle miembros, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4af7a-113">To create a product owner group and add members to it, follow these steps.</span></span>

1. <span data-ttu-id="4af7a-114">Vaya a **Gestión de cambios de ingeniería \> Preparar \> Propietarios del producto**.</span><span class="sxs-lookup"><span data-stu-id="4af7a-114">Go to **Engineering change management \> Setup \> Product owners**.</span></span>
2. <span data-ttu-id="4af7a-115">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="4af7a-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="4af7a-116">En el campo **Propietario del producto**, especifique un nombre descriptivo para el grupo de productos.</span><span class="sxs-lookup"><span data-stu-id="4af7a-116">In the **Product owner** field, enter a name for the group.</span></span>
4. <span data-ttu-id="4af7a-117">En el campo **Nombre**, especifique una descripción del grupo.</span><span class="sxs-lookup"><span data-stu-id="4af7a-117">In the **Name** field, enter a description of the group.</span></span>
5. <span data-ttu-id="4af7a-118">Sobre la ficha desplegable **Miembros**, agregue los trabajadores que deberían ser miembros del grupo.</span><span class="sxs-lookup"><span data-stu-id="4af7a-118">On the **Members** FastTab, add the workers who should be members of the group.</span></span>

## <a name="assign-a-product-owner-to-a-product"></a><span data-ttu-id="4af7a-119">Asignar un propietario de producto a un producto</span><span class="sxs-lookup"><span data-stu-id="4af7a-119">Assign a product owner to a product</span></span>

<span data-ttu-id="4af7a-120">Para asignar un propietario de producto a un producto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="4af7a-120">To assign a product owner to a product, follow these steps.</span></span>

1. <span data-ttu-id="4af7a-121">Abra la página **Detalles de producto** para el producto o producto maestro relevante.</span><span class="sxs-lookup"><span data-stu-id="4af7a-121">Open the **Product details** page for the relevant product or product master.</span></span>
1. <span data-ttu-id="4af7a-122">En la ficha desplegable **General**, establezca el campo **Dueño del producto** en el nombre del grupo de propietarios de producto relevante.</span><span class="sxs-lookup"><span data-stu-id="4af7a-122">On the **General** FastTab, set the **Product owner** field to the name of the relevant product owner group.</span></span>

<span data-ttu-id="4af7a-123">Mientras que un propietario de producto está asignado a un producto, solo los miembros del grupo de propietarios de producto pueden editar la configuración **Dueño del producto**.</span><span class="sxs-lookup"><span data-stu-id="4af7a-123">While a product owner is assigned to a product, only the members of the product owner group can edit the **Product owner** setting.</span></span>

<span data-ttu-id="4af7a-124">El propietario del producto también es visible en la página **Productos lanzados**.</span><span class="sxs-lookup"><span data-stu-id="4af7a-124">The product owner is also visible on the **Released products** page.</span></span>

## <a name="product-owners-and-product-releases"></a><span data-ttu-id="4af7a-125">Propietarios de productos y lanzamientos de productos</span><span class="sxs-lookup"><span data-stu-id="4af7a-125">Product owners and product releases</span></span>

<span data-ttu-id="4af7a-126">Solo los usuarios del grupo de propietarios de productos de un producto pueden lanzar ese producto.</span><span class="sxs-lookup"><span data-stu-id="4af7a-126">Only users from a product's product owner group can release that product.</span></span> <span data-ttu-id="4af7a-127">Sin embargo, hay una excepción cuando el producto es un artículo secundario y su padre es liberado por el propietario del padre.</span><span class="sxs-lookup"><span data-stu-id="4af7a-127">However, there is an exception when the product is a child item, and its parent is released by the parent's owner.</span></span> <span data-ttu-id="4af7a-128">En otras palabras, si el producto es parte de la lista de materiales de otro producto, el sistema no verifica al propietario del producto de cada artículo en la lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="4af7a-128">In other words, if the product is part of the BOM of another product, the system doesn't check the product owner of each item in the BOM.</span></span> <span data-ttu-id="4af7a-129">Solo verifica el propietario del producto del artículo principal.</span><span class="sxs-lookup"><span data-stu-id="4af7a-129">It checks only the product owner of the parent item.</span></span>

<span data-ttu-id="4af7a-130">Por ejemplo, el producto X se asigna al grupo de propietarios de productos *Armarios de diseño*.</span><span class="sxs-lookup"><span data-stu-id="4af7a-130">For example, product X is assigned to the *Design cabinets* product owner group.</span></span> <span data-ttu-id="4af7a-131">El producto X también forma parte de la lista de materiales del producto Y, que se asigna al grupo de propietarios de productos *Ponentes de diseño*.</span><span class="sxs-lookup"><span data-stu-id="4af7a-131">Product X is also part of the BOM of product Y, which is assigned to the *Design Speakers* product owner group.</span></span> <span data-ttu-id="4af7a-132">Si un usuario del grupo propietario del producto *Ponentes de diseño* lanza el producto y su lista de materiales, el producto X se lanzará junto con el producto Y.</span><span class="sxs-lookup"><span data-stu-id="4af7a-132">If a user from the *Design Speakers* product owner group releases product Y and its BOM, product X will be released together with product Y.</span></span>

## <a name="product-owners-and-approvals"></a><span data-ttu-id="4af7a-133">Propietarios y aprobaciones de productos</span><span class="sxs-lookup"><span data-stu-id="4af7a-133">Product owners and approvals</span></span>

<span data-ttu-id="4af7a-134">Dado que los propietarios de productos saben si los cambios de ingeniería específicos beneficiarán a sus productos, a menudo tiene sentido incluirlos como parte del proceso de aprobación en la gestión de cambios de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="4af7a-134">Because product owners know whether specific engineering changes will benefit their products, it often makes sense to include them as part of the approval process in engineering change management.</span></span> <span data-ttu-id="4af7a-135">Puede implementar este enfoque configurando a los propietarios del producto como proveedores participantes en los flujos de trabajo que se utilizan para la gestión de cambios de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="4af7a-135">You can implement this approach by setting up the product owners as participant providers in the workflows that are used for engineering change management.</span></span> <span data-ttu-id="4af7a-136">Luego, el sistema asignará tareas de aprobación en los flujos de trabajo, en función de los productos que se encuentran en las solicitudes de cambio de ingeniería y las órdenes de cambio de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="4af7a-136">The system will then assign approval tasks in the workflows, based on the products that are in engineering change requests and engineering change orders.</span></span> <span data-ttu-id="4af7a-137">Para más información, ver [Gestionar cambios en productos de ingeniería](engineering-change-management.md).</span><span class="sxs-lookup"><span data-stu-id="4af7a-137">For more information, see [Manage changes to engineering products](engineering-change-management.md).</span></span>
