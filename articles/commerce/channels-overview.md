---
title: Visión general de canales
description: Este tema presenta una visión general de los canales en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 7f5d527dd14d24c06aef874de0088bb07c49849b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800552"
---
# <a name="channels-overview"></a><span data-ttu-id="ce7a5-103">Visión general de canales</span><span class="sxs-lookup"><span data-stu-id="ce7a5-103">Channels overview</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="ce7a5-104">Este tema presenta una visión general de los canales en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-104">This topic presents an overview of channels in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="ce7a5-105">Incluye información acerca de las tareas que debe completar tanto antes como después de configurar cada canal.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-105">It includes information about the tasks that you must complete both before and after you set up each channel.</span></span>

## <a name="types-of-channels"></a><span data-ttu-id="ce7a5-106">Tipos de canales</span><span class="sxs-lookup"><span data-stu-id="ce7a5-106">Types of Channels</span></span>

<span data-ttu-id="ce7a5-107">Dynamics 365 Commerce admite tres tipos de canales diferentes: de minorista, de centro de llamadas y en línea.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-107">Dynamics 365 Commerce supports three different channel types: retail, call center, and online channels.</span></span>

### <a name="retail-channels"></a><span data-ttu-id="ce7a5-108">Canales comerciales</span><span class="sxs-lookup"><span data-stu-id="ce7a5-108">Retail channels</span></span>

<span data-ttu-id="ce7a5-109">Los canales minoristas representan tiendas físicas estándar.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-109">Retail channels represent standard brick-and-mortar stores.</span></span> <span data-ttu-id="ce7a5-110">Cada tienda puede tener sus propios registros de punto de venta (PDV), cuentas de ingresos y gastos, y personal.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-110">Each store can have its own point of sale (POS) registers, income and expense accounts, and staff.</span></span> 

### <a name="call-center-channels"></a><span data-ttu-id="ce7a5-111">Canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="ce7a5-111">Call center channels</span></span>

<span data-ttu-id="ce7a5-112">Los canales de centro de llamadas representan pedidos de centro de llamadas y administración de clientes.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-112">Call center channels represent call center order and customer management.</span></span>

### <a name="online-channels"></a><span data-ttu-id="ce7a5-113">Canales en línea</span><span class="sxs-lookup"><span data-stu-id="ce7a5-113">Online channels</span></span>

<span data-ttu-id="ce7a5-114">Los canales en línea representan escaparates de comercio electrónico en línea.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-114">Online channels represent online e-Commerce storefronts.</span></span> <span data-ttu-id="ce7a5-115">Cuando se crea un canal en línea, hay que crear un sitio con la herramienta Configurador de sitios de Microsoft Dynamics 365 Commerce u otra solución de comercio electrónico de terceros.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-115">Once an online channel is created, a site must be created using the Microsoft Dynamics 365 Commerce Site Builder tool or other third-party e-Commerce solution.</span></span>

## <a name="channel-setup-basics"></a><span data-ttu-id="ce7a5-116">Fundamentos de la configuración de canales</span><span class="sxs-lookup"><span data-stu-id="ce7a5-116">Channel setup basics</span></span>

<span data-ttu-id="ce7a5-117">La configuración de canales se realiza en la herramienta Commerce.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-117">Channel set up is performed in the Commerce tool.</span></span> <span data-ttu-id="ce7a5-118">Cada canal puede tener sus propios métodos de pago, grupos de precios, jerarquías de productos, surtidos y conjunto de productos.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-118">Each channel can have its own payment methods, price groups, product hierarchies, assortments, and set of products.</span></span> <span data-ttu-id="ce7a5-119">Una vez creado un canal, puede asignar los productos que desea que tenga y vender.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-119">After you create a channel, you assign the products that you want it to carry and sell.</span></span> <span data-ttu-id="ce7a5-120">Cada tipo de canal tiene un conjunto único de características que puede ser necesario configurar.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-120">Each channel type has a unique set of features that may need to be configured.</span></span> <span data-ttu-id="ce7a5-121">Por ejemplo, un canal minorista necesita empleados, registros y clientes asignados.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-121">For example, a retail channel needs assigned employees, registers, and customers.</span></span> <span data-ttu-id="ce7a5-122">Una vez que se crea un nuevo canal, debe asignarse a una jerarquía organizativa.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-122">Once a new channel is created, it needs to be assigned to an organization hierarchy.</span></span>

## <a name="channel-setup-prerequisites"></a><span data-ttu-id="ce7a5-123">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="ce7a5-123">Channel setup prerequisites</span></span>

<span data-ttu-id="ce7a5-124">Para poder configurar un canal, antes debe completar algunas tareas de requisitos previos, en función del tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-124">Before you can set up a channel, you must complete some prerequisite tasks based on the channel type.</span></span> <span data-ttu-id="ce7a5-125">Para obtener más información, consulte [Requisitos previos de configuración de canales](channels-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="ce7a5-125">For more information, see [Channel setup prerequisites](channels-prerequisites.md).</span></span>

## <a name="set-up-a-channel"></a><span data-ttu-id="ce7a5-126">Configurar un canal</span><span class="sxs-lookup"><span data-stu-id="ce7a5-126">Set up a channel</span></span>

<span data-ttu-id="ce7a5-127">Después de completar las tareas de requisitos previos, use los siguientes vínculos para obtener más instrucciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="ce7a5-127">After you complete the prerequisite tasks, for further setup instructions, use the following links.</span></span>

- [<span data-ttu-id="ce7a5-128">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="ce7a5-128">Set up a retail channel</span></span>](channel-setup-retail.md)
- [<span data-ttu-id="ce7a5-129">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="ce7a5-129">Set up a call center channel</span></span>](channel-setup-callcenter.md)
- [<span data-ttu-id="ce7a5-130">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="ce7a5-130">Set up an online channel</span></span>](channel-setup-online.md)

<!--
## Post-channel configuration

After you create a channel, you may need to complete some of the below tasks:

- [Add channel to an organizational hierarchy](add-channel-org-hierarchy.md)
- Set up fulfillment groups. (LINK TBD)
- Configure the POS registers for the store. (LINK TBD)
- Assign product assortments to the store. (LINK TBD)
- Process assortments to generate the list of products that are included in the assortment and to make the products available in the retail store. (LINK TBD)
- Send data such as number sequences, hardware profiles, and POS screen layouts to the Retail POS registers.(LINK TBD)
- Publish the retail store to send store data to Retail POS. (LINK TBD)
- Run the jobs to send the store data to Retail POS. (LINK TBD)
-->

## <a name="additional-resources"></a><span data-ttu-id="ce7a5-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ce7a5-131">Additional resources</span></span>

[<span data-ttu-id="ce7a5-132">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="ce7a5-132">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="ce7a5-133">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="ce7a5-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="ce7a5-134">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="ce7a5-134">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="ce7a5-135">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="ce7a5-135">Set up a call center channel</span></span>](channel-setup-callcenter.md)

[<span data-ttu-id="ce7a5-136">Configurar jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="ce7a5-136">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]