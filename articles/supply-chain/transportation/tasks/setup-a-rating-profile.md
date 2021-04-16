---
title: Perfiles de clasificación
description: Este tema describe cómo configurar datos para perfiles de clasificación.
author: Henrikan
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TMSRatingProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d359394ee0086edc5c8b9a3a0c48cf5933963ceb
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828451"
---
# <a name="rating-profiles"></a><span data-ttu-id="67296-103">Perfiles de clasificación</span><span class="sxs-lookup"><span data-stu-id="67296-103">Rating profiles</span></span>

<span data-ttu-id="67296-104">Un perfil de calificación se parece a un contrato de logística (pero no a un contrato legal).</span><span class="sxs-lookup"><span data-stu-id="67296-104">A rating profile resembles a logistics contract (but not a legal contract).</span></span> <span data-ttu-id="67296-105">Se utiliza para determinar las tarifas de transporte de cargas.</span><span class="sxs-lookup"><span data-stu-id="67296-105">It's used to determine transportation tariffs for loads.</span></span> 

<span data-ttu-id="67296-106">Cada perfil de clasificación es único para un transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="67296-106">Each rating profile is unique to a shipping carrier.</span></span> <span data-ttu-id="67296-107">En el perfil, se asocia el transportista de envío a una tasa maestra.</span><span class="sxs-lookup"><span data-stu-id="67296-107">In the profile, you associate the shipping carrier with a rate master.</span></span> <span data-ttu-id="67296-108">La tasa maestra define la asignación de base de tasa y la base de tasa.</span><span class="sxs-lookup"><span data-stu-id="67296-108">The rate master defines the rate base assignment and the rate base.</span></span> <span data-ttu-id="67296-109">La base de tasa determina la tasa del transportista.</span><span class="sxs-lookup"><span data-stu-id="67296-109">The rate base determines the rate of the carrier.</span></span>

<span data-ttu-id="67296-110">Puede configurar un perfil de clasificación mediante una página genérica que muestra una visión general de todos los perfiles de clasificación existentes.</span><span class="sxs-lookup"><span data-stu-id="67296-110">You can set up a rating profile by using a generic page that shows an overview of all existing rating profiles.</span></span> <span data-ttu-id="67296-111">Alternativamente, puede configurar un perfil de clasificación directamente a partir del transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="67296-111">Alternatively, you can set up a rating profile directly from the shipping carrier.</span></span> <span data-ttu-id="67296-112">En ambos casos, la información que configura para el perfil de calificación es la misma.</span><span class="sxs-lookup"><span data-stu-id="67296-112">In both cases, the information that you set up for the rating profile is the same.</span></span>

## <a name="create-or-edit-a-rating-profile-on-the-rating-profiles-page"></a><span data-ttu-id="67296-113">Cree o edite un perfil de calificación en la página Perfiles de calificación</span><span class="sxs-lookup"><span data-stu-id="67296-113">Create or edit a rating profile on the Rating profiles page</span></span>

<span data-ttu-id="67296-114">Sobre la página **Perfiles de calificación**, puede revisar todos los perfiles de calificación disponibles.</span><span class="sxs-lookup"><span data-stu-id="67296-114">On the **Rating profiles** page, you can review all available rating profiles.</span></span> <span data-ttu-id="67296-115">También puede editar perfiles existentes y crear perfiles nuevos.</span><span class="sxs-lookup"><span data-stu-id="67296-115">You can also edit existing profiles and create new profiles.</span></span>

1. <span data-ttu-id="67296-116">Vaya a **Administración de transporte \> Configuración \> Clasificación \> Perfil de clasificación**.</span><span class="sxs-lookup"><span data-stu-id="67296-116">Go to **Transportation management \> Setup \> Rating \> Rating profile**.</span></span>
1. <span data-ttu-id="67296-117">En el panel de acciones, seleccione **Nuevo** para agregar un nuevo perfil de calificación a la cuadrícula, o seleccione **Editar** para editar un perfil existente.</span><span class="sxs-lookup"><span data-stu-id="67296-117">On the Action Pane, select **New** to add a new rating profile to the grid, or select **Edit** to edit an existing profile.</span></span>
1. <span data-ttu-id="67296-118">En la fila del perfil de calificación nuevo o existente, configure los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="67296-118">In the row for the new or existing rating profile, set the following fields:</span></span>

    - <span data-ttu-id="67296-119">**Perfil de clasificación** – Especifique un identificador (id.) y una descripción únicos para el perfil de clasificación.</span><span class="sxs-lookup"><span data-stu-id="67296-119">**Rating profile** – Enter a unique identifier (ID) for the rating profile.</span></span>
    - <span data-ttu-id="67296-120">**Nombre** - Especifique un nombre descriptivo para el perfil de clasificación.</span><span class="sxs-lookup"><span data-stu-id="67296-120">**Name** – Enter a descriptive name for the rating profile.</span></span>
    - <span data-ttu-id="67296-121">**Transportista de envío** - Seleccione un transportista.</span><span class="sxs-lookup"><span data-stu-id="67296-121">**Shipping carrier** – Select a shipping carrier.</span></span> <span data-ttu-id="67296-122">El perfil de calificación que está configurando también se mostrará en la página **Transportistas de envío** del operador seleccionado.</span><span class="sxs-lookup"><span data-stu-id="67296-122">The rating profile that you're setting up will also be shown on the **Shipping carriers** page for the selected carrier.</span></span>
    - <span data-ttu-id="67296-123">**Sitio** y **Almacén** - Seleccione un sitio y un almacén.</span><span class="sxs-lookup"><span data-stu-id="67296-123">**Site** and **Warehouse** – Select a site and warehouse.</span></span>
    - <span data-ttu-id="67296-124">**Motor de tarifas** - Seleccione el motor de tarifas para el perfil de calificación.</span><span class="sxs-lookup"><span data-stu-id="67296-124">**Rate engine** – Select the rate engine for the rating profile.</span></span>
    - <span data-ttu-id="67296-125">**Maestro de tarifas** - Seleccione el maesetro de tarifas para el perfil de calificación.</span><span class="sxs-lookup"><span data-stu-id="67296-125">**Rate master** – Select the rate master for the rating profile.</span></span> <span data-ttu-id="67296-126">Puede usar la tasa maestra para definir un tipo de base de tasa y una base de tasa.</span><span class="sxs-lookup"><span data-stu-id="67296-126">You can use the rate master to define a rate base type and a rate base.</span></span> <span data-ttu-id="67296-127">Para obtener más información, vea [Configurar maestros de tarifas](set-up-rate-masters.md).</span><span class="sxs-lookup"><span data-stu-id="67296-127">For more information, see [Set up rate masters](set-up-rate-masters.md).</span></span>
    - <span data-ttu-id="67296-128">**Motor de tiempo de tránsito** - Seleccione el motor de tiempo de tránsito para el perfil de calificación.</span><span class="sxs-lookup"><span data-stu-id="67296-128">**Transit time engine** – Select the transit time engine for the rating profile.</span></span>
    - <span data-ttu-id="67296-129">**Índice de combustible de transportista** – Seleccione el motor de cálculo de tránsito y el índice de combustible del transportista para el perfil de clasificación.</span><span class="sxs-lookup"><span data-stu-id="67296-129">**Carrier fuel index** – Select the carrier fuel index for the rating profile.</span></span>
    - <span data-ttu-id="67296-130">**Fecha y hora de inicio del efecto** y **Fecha y hora de finalización efectiva** - Definir el período en el que debe estar activo el perfil de calificación.</span><span class="sxs-lookup"><span data-stu-id="67296-130">**Effect start date and time** and **Effective end date and time** – Define the period when the rating profile should be active.</span></span>

1. <span data-ttu-id="67296-131">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="67296-131">On the Action Pane, select **Save**.</span></span>

## <a name="create-a-rating-profile-directly-on-the-shipping-carriers-page"></a><span data-ttu-id="67296-132">Cree un perfil de calificación directamente en la página Transportistas de envío</span><span class="sxs-lookup"><span data-stu-id="67296-132">Create a rating profile directly on the Shipping carriers page</span></span>

1. <span data-ttu-id="67296-133">Vaya a **Administración de transporte \> Configuración \> Transportistas \> Transportistas de envío**.</span><span class="sxs-lookup"><span data-stu-id="67296-133">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="67296-134">Seleccione un transportista de envío en la lista.</span><span class="sxs-lookup"><span data-stu-id="67296-134">Select a shipping carrier in the list.</span></span>
1. <span data-ttu-id="67296-135">En la ficha desplegable **Perfiles de clasificación**, haga clic en **Nuevo** para crear un perfil de clasificación.</span><span class="sxs-lookup"><span data-stu-id="67296-135">On the **Rating profiles** FastTab, select **New** to create a rating profile.</span></span>
1. <span data-ttu-id="67296-136">Configure los campos para el nuevo perfil de calificación.</span><span class="sxs-lookup"><span data-stu-id="67296-136">Set the fields for the new rating profile.</span></span> <span data-ttu-id="67296-137">Estos campos corresponden a los campos de la página **Perfiles de calificación**, como se describe en la sección anterior de este tema.</span><span class="sxs-lookup"><span data-stu-id="67296-137">These fields correspond to the fields on the **Rating profiles** page, as described in previous section of this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="67296-138">Perfiles que se crean en la página **Transportistas de envío** también se muestran en la página **Perfiles de calificación**.</span><span class="sxs-lookup"><span data-stu-id="67296-138">Profiles that are created on the **Shipping carriers** page are also shown on the **Rating profiles** page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]