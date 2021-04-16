---
title: Configuración de entrega
description: Este tema explica cómo configurar las operaciones de entrada de inventario de envío.
author: perlynne
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5229559647274d4c845325c6b86afbdba43f29e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834178"
---
# <a name="set-up-consignment"></a><span data-ttu-id="d166f-103">Configuración de entrega</span><span class="sxs-lookup"><span data-stu-id="d166f-103">Set up consignment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d166f-104">Este tema explica cómo configurar las operaciones de entrada de inventario de envío.</span><span class="sxs-lookup"><span data-stu-id="d166f-104">This topic explains how to configure inbound consignment inventory operations.</span></span>

<span data-ttu-id="d166f-105">El inventario de envío es el inventario que es propiedad de un proveedor, pero se almacena en su ubicación.</span><span class="sxs-lookup"><span data-stu-id="d166f-105">Consignment inventory is inventory that’s owned by a vendor, but stored at your site.</span></span> <span data-ttu-id="d166f-106">Cuando esté listo para consumir o usar el inventario, asume el control de la propiedad del inventario.</span><span class="sxs-lookup"><span data-stu-id="d166f-106">When you’re ready to consume or use the inventory, you take over the ownership of the inventory.</span></span> <span data-ttu-id="d166f-107">Este tema describe la configuración necesaria para habilitar procesos de envío.</span><span class="sxs-lookup"><span data-stu-id="d166f-107">This topic describes the setup needed to enable consignment processes.</span></span> <span data-ttu-id="d166f-108">Para obtener más información acerca de los procesos de envío, consulte [Configuración de entrega](consignment.md).</span><span class="sxs-lookup"><span data-stu-id="d166f-108">For more information about consignment processes, see [Set up consignment](consignment.md).</span></span>

## <a name="inventory-owners"></a><span data-ttu-id="d166f-109">Propietarios de inventario</span><span class="sxs-lookup"><span data-stu-id="d166f-109">Inventory owners</span></span>
<span data-ttu-id="d166f-110">Para registrar el inventario entrante físico de envío, es necesario definir un propietario de proveedor.</span><span class="sxs-lookup"><span data-stu-id="d166f-110">In order to record physical inbound consignment inventory, you need to define a vendor owner.</span></span> <span data-ttu-id="d166f-111">Esto se hace en la página **Propietario de inventario**.</span><span class="sxs-lookup"><span data-stu-id="d166f-111">This is done on the **Inventory owner** page.</span></span> <span data-ttu-id="d166f-112">Al seleccionar **Cuenta de proveedor** se generan valores predeterminados para los campos **Nombre** y **Propietario**.</span><span class="sxs-lookup"><span data-stu-id="d166f-112">When you select a **Vendor account** this generates default values for the **Name** and **Owner** fields.</span></span> <span data-ttu-id="d166f-113">El valor del campo **Propietario** estará visible para el proveedor, por lo que es posible que desee cambiarlo si los nombres de cuenta de sus proveedores no son fáciles de reconocer por parte de las entidades externas.</span><span class="sxs-lookup"><span data-stu-id="d166f-113">The value in the **Owner** field will be visible to the vendor, so you might want to change it if your vendor account names aren’t easy for external people to recognize.</span></span> <span data-ttu-id="d166f-114">Es posible editar el campo **Propietario**, pero solo hasta el punto al guardar el registro **Propietario de inventario**.</span><span class="sxs-lookup"><span data-stu-id="d166f-114">It’s possible to edit the **Owner** field, but only up to the point when you save the **Inventory owner** record.</span></span> <span data-ttu-id="d166f-115">El campo **Nombre** se rellena con el nombre de la parte a la que se asocia la cuenta del proveedor y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="d166f-115">The **Name** field is populated with the name of the party that the vendor account is associated with, and this cannot be changed.</span></span>

<span data-ttu-id="d166f-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span><span class="sxs-lookup"><span data-stu-id="d166f-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span></span>

## <a name="tracking-dimension-group"></a><span data-ttu-id="d166f-117">Grupo de dimensiones de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d166f-117">Tracking dimension group</span></span>
<span data-ttu-id="d166f-118">Los artículos que se van a usar en procesos de envío se deben asociar al **Grupo de dimensiones de seguimiento** donde la dimensión de **Propietario** está establecida en **Activa**.</span><span class="sxs-lookup"><span data-stu-id="d166f-118">Items that are going to be used in consignment processes must be associated with a **Tracking dimension group** where the **Owner** dimension is set to **Active**.</span></span> <span data-ttu-id="d166f-119">La dimensión de Propietario siempre tiene las opciones **Inventario físico** e **Inventario financiero** seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="d166f-119">The Owner dimension always has the **Physical inventory** and **Financial inventory** options selected.</span></span> <span data-ttu-id="d166f-120">El **Plan de cobertura por dimensión** nunca está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d166f-120">The **Coverage plan by dimension** is never selected.</span></span>

<span data-ttu-id="d166f-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span><span class="sxs-lookup"><span data-stu-id="d166f-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span></span>

## <a name="inventory-ownership-change-journal"></a><span data-ttu-id="d166f-122">Diario de cambio de propiedad de inventario</span><span class="sxs-lookup"><span data-stu-id="d166f-122">Inventory ownership change journal</span></span>
<span data-ttu-id="d166f-123">El diario de **Cambio de propiedad de inventario** se usa para registrar la transferencia de propiedad del inventario de envío del proveedor a la entidad jurídica que lo consume.</span><span class="sxs-lookup"><span data-stu-id="d166f-123">The **Inventory ownership change** journal is used to record the transfer of ownership of consignment inventory from the vendor to the legal entity that’s consuming it.</span></span> <span data-ttu-id="d166f-124">Como cualquier diario de inventario, debe identificarse con un nombre de diario de inventario.</span><span class="sxs-lookup"><span data-stu-id="d166f-124">Like any inventory journal, it must be identified with an Inventory journal name.</span></span> <span data-ttu-id="d166f-125">Dichos nombres se crean en la página **Nombres de diario de inventario**, y el **Tipo de diario** se debe establecer en **Cambio de propiedad**.</span><span class="sxs-lookup"><span data-stu-id="d166f-125">These names are created on the **Inventory journal names** page, and the **Journal type** must be set to **Ownership change**.</span></span>

<span data-ttu-id="d166f-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span><span class="sxs-lookup"><span data-stu-id="d166f-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span></span>

## <a name="vendor-collaboration-in-consignment-processes"></a><span data-ttu-id="d166f-127">Colaboración de proveedor en procesos de envío</span><span class="sxs-lookup"><span data-stu-id="d166f-127">Vendor collaboration in consignment processes</span></span>
<span data-ttu-id="d166f-128">Si los proveedores usan la interfaz de colaboración de proveedor, pueden usarla para controlar el consumo de inventario de su ubicación.</span><span class="sxs-lookup"><span data-stu-id="d166f-128">If your vendors are using the vendor collaboration interface, they can use this to monitor the consumption of inventory at your site.</span></span> <span data-ttu-id="d166f-129">Para obtener más información acerca de la configuración de los proveedores para utilizar la colaboración de proveedor, consulte [Seguridad para los usuarios del portal de proveedores](../procurement/configure-security-vendor-portal-users.md).</span><span class="sxs-lookup"><span data-stu-id="d166f-129">For more information about setting up vendors to use vendor collaboration, see [Vendor portal user security](../procurement/configure-security-vendor-portal-users.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]