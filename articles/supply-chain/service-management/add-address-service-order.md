---
title: Agregar una dirección a un pedido de servicio
description: Este tema describe cómo agregar una dirección de cliente a un pedido de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5b1c0e300edc45ae3f4be9eae8afa56e06cccd6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203098"
---
# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="a161a-103">Agregar una dirección a un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="a161a-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a161a-104">Este tema describe cómo agregar una dirección de cliente a un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="a161a-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="a161a-105">Al crear un pedido de servicio, la información de dirección se transfiere del proyecto al que está vinculado el pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="a161a-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="a161a-106">Sin embargo, puede seleccionar una ubicación alternativa a las direcciones que ya haya especificado en Microsoft Dynamics AX para clientes, proveedores, sitios, almacenes, pedidos de servicio y proyectos.</span><span class="sxs-lookup"><span data-stu-id="a161a-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="a161a-107">También puede crear una nueva dirección.</span><span class="sxs-lookup"><span data-stu-id="a161a-107">You can also create a new address.</span></span> <span data-ttu-id="a161a-108">De forma predeterminada, la nueva dirección se transfiere al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a161a-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="a161a-109">Sin embargo, puede especificar que la nueva dirección solo sea pertinente para esta instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="a161a-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="a161a-110">Si lo hace, la nueva dirección no se transfiere al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a161a-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="a161a-111">Crear una dirección de cliente para un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="a161a-111">Create a customer address for a service order</span></span>

<span data-ttu-id="a161a-112">Para agregar una dirección a un pedido de servicio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a161a-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="a161a-113">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a161a-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="a161a-114">Abra el pedido de servicio para el que desea crear una dirección.</span><span class="sxs-lookup"><span data-stu-id="a161a-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="a161a-115">En el **panel de acciones**, haga clic en **Editar** y, a continuación, haga clic en la **Visualización de encabezado**.</span><span class="sxs-lookup"><span data-stu-id="a161a-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="a161a-116">En la ficha desplegable **Dirección**, haga clic en **Agregar dirección**.</span><span class="sxs-lookup"><span data-stu-id="a161a-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="a161a-117">En el formulario **Dirección nueva**, especifique un nombre exclusivo para la dirección y complete los campos restantes.</span><span class="sxs-lookup"><span data-stu-id="a161a-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="a161a-118">Si especifica el mismo nombre que una dirección existente, la información que especifique en los campos restantes sobrescribirá la información de la dirección existente.</span><span class="sxs-lookup"><span data-stu-id="a161a-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="a161a-119">Haga clic en **Aceptar** para copiar la nueva dirección al pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="a161a-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="a161a-120">Especificar una dirección alternativa en un pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="a161a-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="a161a-121">Para agregar una dirección alternativa a un pedido de servicio, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="a161a-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="a161a-122">Haga clic en **Gestión de servicio** \> **Común** \> **Pedidos de servicio** \> **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a161a-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="a161a-123">Abra el pedido de servicio para el que especificar una dirección alternativa.</span><span class="sxs-lookup"><span data-stu-id="a161a-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="a161a-124">En el **panel de acciones**, haga clic en **Editar** y, a continuación, haga clic en la **Visualización de encabezado**.</span><span class="sxs-lookup"><span data-stu-id="a161a-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="a161a-125">En la ficha desplegable **Dirección**, haga clic en **Otra dirección**.</span><span class="sxs-lookup"><span data-stu-id="a161a-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="a161a-126">En el formulario **Selección de dirección**, en el campo **Tipo de registro**, seleccione **Pedidos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="a161a-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="a161a-127">Seleccione una dirección y haga clic en **Aceptar** para copiarla en el pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="a161a-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  


