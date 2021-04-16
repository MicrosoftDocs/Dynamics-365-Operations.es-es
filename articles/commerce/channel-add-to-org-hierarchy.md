---
title: Agregar un canal a una jerarquía organizativa
description: En este tema se describe cómo agregar un canal a una jerarquía organizativa en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c7ff6d8ee7e526e45975cfa500b5e6d6079054dc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800696"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a><span data-ttu-id="a62a9-103">Agregar un canal a una jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="a62a9-103">Add a channel to an organizational hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a62a9-104">En este tema se describe cómo agregar un canal a una jerarquía organizativa en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a62a9-104">This topic describes how to add a channel to an organizational hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a62a9-105">Información general</span><span class="sxs-lookup"><span data-stu-id="a62a9-105">Overview</span></span>

<span data-ttu-id="a62a9-106">Los canales deben estar asociados con una o más jerarquías organizativas.</span><span class="sxs-lookup"><span data-stu-id="a62a9-106">Channels need to be associated with one or more organizational hierarchies.</span></span> <span data-ttu-id="a62a9-107">Antes de crear canales, debe confirmar que se han configurado sus jerarquías organizativas.</span><span class="sxs-lookup"><span data-stu-id="a62a9-107">Before creating channels, you need to confirm that your organizational hierarchies have been set up.</span></span>  

<span data-ttu-id="a62a9-108">Consulte [Jerarquías organizativas](channels-org-hierarchies.md) para ver más detalles sobre cómo crear jerarquías organizativas.</span><span class="sxs-lookup"><span data-stu-id="a62a9-108">See [Organizational hierarchies](channels-org-hierarchies.md) for more details on how to create organizational hierarchies.</span></span>

## <a name="select-a-hierarchy"></a><span data-ttu-id="a62a9-109">Seleccionar una jerarquía</span><span class="sxs-lookup"><span data-stu-id="a62a9-109">Select a hierarchy</span></span>

<span data-ttu-id="a62a9-110">Para seleccionar una jerarquía, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a62a9-110">To select a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="a62a9-111">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Jerarquía organizativa**.</span><span class="sxs-lookup"><span data-stu-id="a62a9-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="a62a9-112">En la lista, seleccione la jerarquía organizativa a la que va a agregar el canal.</span><span class="sxs-lookup"><span data-stu-id="a62a9-112">From the list, select the organization hierarchy that you'll be adding the channel to.</span></span>
1. <span data-ttu-id="a62a9-113">En el panel de acciones, seleccione **Ver** para ver los detalles de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="a62a9-113">On the action pane, select **View** to view hierarchy details.</span></span>

<span data-ttu-id="a62a9-114">La siguiente imagen muestra detalles de la jerarquía organizativa para la jerarquía seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a62a9-114">The following image shows organizational hierarchy details for the selected hierarchy.</span></span>

![Detalles de la jerarquía organizativa para la jerarquía seleccionada.](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a><span data-ttu-id="a62a9-116">Agregar un canal a un nodo de jerarquía</span><span class="sxs-lookup"><span data-stu-id="a62a9-116">Add a channel to a hierachy node</span></span>

<span data-ttu-id="a62a9-117">Para agregar un canal a un nodo de jerarquía, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a62a9-117">To add a channel to a hierachy node, follow these steps.</span></span>

1. <span data-ttu-id="a62a9-118">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a62a9-118">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="a62a9-119">Seleccione el nodo de jerarquía al que desea agregar el canal y, a continuación, desde la lista desplegable **Insertar**, seleccione **Canal comercial**.</span><span class="sxs-lookup"><span data-stu-id="a62a9-119">Select the hierachy node you want the channel added to, then from the **Insert** drop-down list, select **Retail Channel**.</span></span> 
1. <span data-ttu-id="a62a9-120">Seleccione el canal para agregar y, a continuación, seleccione el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a62a9-120">Select the channel to add, then select the **OK** button.</span></span>
1. <span data-ttu-id="a62a9-121">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a62a9-121">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="a62a9-122">En el panel de acciones, seleccione **Publicar** y proporcione una **Fecha de vigencia** del pasado para que esta acción entre en vigor de inmediato.</span><span class="sxs-lookup"><span data-stu-id="a62a9-122">On the action pane, select **Publish** and provide an **Effective date** in the past to have this action go into effect immediately.</span></span>

<span data-ttu-id="a62a9-123">La siguiente imagen muestra cómo seleccionar un canal para agregarlo a un nodo de jerarquía.</span><span class="sxs-lookup"><span data-stu-id="a62a9-123">The following image shows how to select a channel to add to a hierarchy node.</span></span>

![Seleccionar un canal para agregarlo a un nodo de jerarquía](media/channel-add-to-org-hierarchy-2.png)

<span data-ttu-id="a62a9-125">La siguiente imagen muestra una jerarquía con varios canales agregados.</span><span class="sxs-lookup"><span data-stu-id="a62a9-125">The following image shows a hierarchy with various channels added.</span></span>

![Una jerarquía con varios canales agregados](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="a62a9-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a62a9-127">Additional resources</span></span>

[<span data-ttu-id="a62a9-128">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="a62a9-128">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a62a9-129">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="a62a9-129">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a62a9-130">Visión general de las organizaciones y las jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="a62a9-130">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a62a9-131">Planificación de su jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="a62a9-131">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a62a9-132">Jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="a62a9-132">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="a62a9-133">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="a62a9-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="a62a9-134">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="a62a9-134">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]