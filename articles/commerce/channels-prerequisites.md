---
title: Requisitos previos de configuración de canales
description: Este tema presenta una visión general de los requisitos previos de configuración de canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
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
ms.openlocfilehash: 270f751e860e56a03e20df720c088f275d0298e7
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477933"
---
# <a name="channel-setup-prerequisites"></a><span data-ttu-id="6d10e-103">Requisitos previos de configuración del canal</span><span class="sxs-lookup"><span data-stu-id="6d10e-103">Channel setup prerequisites</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6d10e-104">Este tema presenta una visión general de los requisitos previos de configuración de canales en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6d10e-104">This topic presents an overview of channel setup prerequisites in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6d10e-105">Para poder crear un canal de Dynamics 365 Commerce es necesario completar antes varias tareas de requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="6d10e-105">Before a Dynamics 365 Commerce channel can be created, several prerequisite tasks must be completed.</span></span> <span data-ttu-id="6d10e-106">Las siguientes listas de tareas de requisitos previos están organizadas por tipo de canal.</span><span class="sxs-lookup"><span data-stu-id="6d10e-106">The following lists of prerequisite tasks are organized by channel type.</span></span>

> [!NOTE]
> <span data-ttu-id="6d10e-107">Todavía se está escribiendo parte de la documentación. Los vínculos se actualizarán a medida que se publique nuevo contenido.</span><span class="sxs-lookup"><span data-stu-id="6d10e-107">Some documentation is still being written, and links will be updated as new content is published.</span></span>

## <a name="initialization"></a><span data-ttu-id="6d10e-108">Inicialización</span><span class="sxs-lookup"><span data-stu-id="6d10e-108">Initialization</span></span>

- [<span data-ttu-id="6d10e-109">Inicializar datos semilla</span><span class="sxs-lookup"><span data-stu-id="6d10e-109">Initialize seed data</span></span>](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a><span data-ttu-id="6d10e-110">Requisitos previos globales necesarios para todos los tipos de canales</span><span class="sxs-lookup"><span data-stu-id="6d10e-110">Global prerequisities required for all channel types</span></span>

- [<span data-ttu-id="6d10e-111">Definir y configurar su estructura de entidad jurídica</span><span class="sxs-lookup"><span data-stu-id="6d10e-111">Define and configure your legal entity structure</span></span>](channels-legal-entities.md) 
- [<span data-ttu-id="6d10e-112">Configurar su jerarquía organizativa</span><span class="sxs-lookup"><span data-stu-id="6d10e-112">Configure your organizational hierarchy</span></span>](channels-org-hierarchies.md)
- [<span data-ttu-id="6d10e-113">Configurar un almacén</span><span class="sxs-lookup"><span data-stu-id="6d10e-113">Set up a warehouse</span></span>](channels-setup-warehouse.md)
- [<span data-ttu-id="6d10e-114">Configurar impuestos</span><span class="sxs-lookup"><span data-stu-id="6d10e-114">Configure sales tax</span></span>](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="6d10e-115">Configurar un perfil de notificación por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="6d10e-115">Set up an email notification profile</span></span>](email-notification-profiles.md)
- [<span data-ttu-id="6d10e-116">Configurar secuencias numéricas</span><span class="sxs-lookup"><span data-stu-id="6d10e-116">Set up number sequences</span></span>](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="6d10e-117">Configurar un cliente y una libreta de direcciones predeterminados</span><span class="sxs-lookup"><span data-stu-id="6d10e-117">Set up a default customer and address book</span></span>](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a><span data-ttu-id="6d10e-118">Requisitos previos de canal comercial</span><span class="sxs-lookup"><span data-stu-id="6d10e-118">Retail channel prerequisites</span></span>

- [<span data-ttu-id="6d10e-119">Códigos de información y grupos de códigos de información</span><span class="sxs-lookup"><span data-stu-id="6d10e-119">Info codes and info code groups</span></span>](info-codes-retail.md)
- [<span data-ttu-id="6d10e-120">Configurar un perfil de funcionalidad comercial</span><span class="sxs-lookup"><span data-stu-id="6d10e-120">Set up a retail functionality profile</span></span>](retail-functionality-profile.md)
- [<span data-ttu-id="6d10e-121">Configurar una libreta de direcciones de empleado</span><span class="sxs-lookup"><span data-stu-id="6d10e-121">Set up an employee address book</span></span>](new-address-book.md)
- [<span data-ttu-id="6d10e-122">Configurar un diseño de pantalla</span><span class="sxs-lookup"><span data-stu-id="6d10e-122">Set up a screen layout</span></span>](pos-screen-layouts.md)
- [<span data-ttu-id="6d10e-123">Configurar una estación de hardware</span><span class="sxs-lookup"><span data-stu-id="6d10e-123">Set up a hardware station</span></span>](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a><span data-ttu-id="6d10e-124">Requisitos previos de canales de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="6d10e-124">Call Center channel prerequisites</span></span>

- <span data-ttu-id="6d10e-125">Parámetros del centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6d10e-125">Call center parameters</span></span>
- [<span data-ttu-id="6d10e-126">Métodos de pedido de centro de llamadas y devolución de pagos</span><span class="sxs-lookup"><span data-stu-id="6d10e-126">Call center order and refund payment methods</span></span>](work-with-payments.md)
- [<span data-ttu-id="6d10e-127">Modos de entrega y cobros de los modos de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="6d10e-127">Call center modes of delivery and charges</span></span>](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a><span data-ttu-id="6d10e-128">Requisitos previos del canal en línea</span><span class="sxs-lookup"><span data-stu-id="6d10e-128">Online channel prerequisites</span></span>

- [<span data-ttu-id="6d10e-129">Crear un perfil de funcionalidad en línea</span><span class="sxs-lookup"><span data-stu-id="6d10e-129">Create an online functionality profile</span></span>](online-functionality-profile.md)

## <a name="additional-resources"></a><span data-ttu-id="6d10e-130">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6d10e-130">Additional resources</span></span>

[<span data-ttu-id="6d10e-131">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="6d10e-131">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="6d10e-132">Visión general de las organizaciones y las jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="6d10e-132">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="6d10e-133">Configurar jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="6d10e-133">Set up organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="6d10e-134">Crear entidades jurídicas</span><span class="sxs-lookup"><span data-stu-id="6d10e-134">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="6d10e-135">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="6d10e-135">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="6d10e-136">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="6d10e-136">Set up an online channel</span></span>](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
