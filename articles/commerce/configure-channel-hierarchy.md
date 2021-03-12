---
title: Configurar un canal para usar una jerarquía de navegación de canales
description: En este tema se describe cómo configurar un canal para usar una jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3dcba743e6557b1bd366ac79ecb49ead831dceb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001034"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="4d266-103">Configurar un canal para usar una jerarquía de navegación de canales</span><span class="sxs-lookup"><span data-stu-id="4d266-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4d266-104">En este tema se describe cómo configurar un canal para usar una jerarquía de navegación de canales en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4d266-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4d266-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="4d266-105">Overview</span></span>

<span data-ttu-id="4d266-106">Las jerarquías de navegación de canales organizan los productos en categorías para que los productos se puedan examinar en un sitio de comercio electrónico o en puntos de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="4d266-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="4d266-107">Los canales comerciales y en línea deben configurarse con jerarquías de navegación de canales.</span><span class="sxs-lookup"><span data-stu-id="4d266-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="4d266-108">Configurar el canal</span><span class="sxs-lookup"><span data-stu-id="4d266-108">Configure the channel</span></span>

<span data-ttu-id="4d266-109">Para configurar un canal de forma que use una jerarquía de navegación de canales, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4d266-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="4d266-110">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Categorías de canal y atributos de producto**.</span><span class="sxs-lookup"><span data-stu-id="4d266-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="4d266-111">Seleccione el canal que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="4d266-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="4d266-112">En el panel de acciones, seleccione **Establecer metadatos de atributos**.</span><span class="sxs-lookup"><span data-stu-id="4d266-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="4d266-113">En la lista desplegable **Jerarquía de categorías**, seleccione la jerarquía de navegación de canales apropiada.</span><span class="sxs-lookup"><span data-stu-id="4d266-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="4d266-114">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="4d266-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="4d266-115">En **Grupo de atributos**, agregue los grupos de atributos que serán atributos globales para todos los nodos.</span><span class="sxs-lookup"><span data-stu-id="4d266-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="4d266-116">La siguiente imagen muestra cómo se configura un canal para usar una jerarquía de navegación de canales.</span><span class="sxs-lookup"><span data-stu-id="4d266-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Ejemplo de configuración de canal](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="4d266-118">Configurar metadatos de atributos</span><span class="sxs-lookup"><span data-stu-id="4d266-118">Set attribute metadata</span></span>

<span data-ttu-id="4d266-119">Establecer los metadatos de atributos permitirá configurar los atributos en cada nodo.</span><span class="sxs-lookup"><span data-stu-id="4d266-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="4d266-120">Para establecer metadatos de atributos, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4d266-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="4d266-121">En el panel de acciones, seleccione **Establecer metadatos de atributos**.</span><span class="sxs-lookup"><span data-stu-id="4d266-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="4d266-122">Para cada nodo, seleccione **Atributos de producto del canal**.</span><span class="sxs-lookup"><span data-stu-id="4d266-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="4d266-123">Establezca **Mostrar atributo en el canal** en **Sí** y **Se puede refinar** en **Sí** para habilitar los refinadores en ese canal.</span><span class="sxs-lookup"><span data-stu-id="4d266-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="4d266-124">Después de configurar cada nodo como desee, en el **Panel de acciones**, seleccione el botón **Guardar** para guardar.</span><span class="sxs-lookup"><span data-stu-id="4d266-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="4d266-125">Selecciona la **X** en la esquina superior derecha para salir de esta pantalla y volver a la página **Categorías de canal y atributos de producto**.</span><span class="sxs-lookup"><span data-stu-id="4d266-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="4d266-126">La siguiente imagen muestra un conjunto de ejemplos de atributos de producto de canal configurados en un nodo de categoría de canal.</span><span class="sxs-lookup"><span data-stu-id="4d266-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Atributos de canal en un nodo de categoría de canal](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="4d266-128">Publicar cambios</span><span class="sxs-lookup"><span data-stu-id="4d266-128">Publish changes</span></span>

<span data-ttu-id="4d266-129">Para que los cambios surtan efecto debe publicarlos.</span><span class="sxs-lookup"><span data-stu-id="4d266-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="4d266-130">Para publicar cambios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="4d266-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="4d266-131">En el panel de acciones, seleccione **Publicar actualizaciones de canal**.</span><span class="sxs-lookup"><span data-stu-id="4d266-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="4d266-132">En el panel **Publicar actualizaciones de canal**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d266-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="4d266-133">La siguiente imagen muestra cómo publicar actualizaciones de canal.</span><span class="sxs-lookup"><span data-stu-id="4d266-133">The following image shows how to publish channel updates.</span></span>

![Publicar actualizaciones de canal](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="4d266-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4d266-135">Additional resources</span></span>

[<span data-ttu-id="4d266-136">Crear una jerarquía de navegación de canales</span><span class="sxs-lookup"><span data-stu-id="4d266-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)


