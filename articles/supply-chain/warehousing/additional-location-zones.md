---
title: Zonas de ubicación adicionales
description: Este tema proporciona una descripción general de las nuevas zonas de ubicación que se han agregado a Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 6cf81939989b8faffcda51bbbd5bc6b27aec7eea
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437219"
---
# <a name="additional-location-zones"></a><span data-ttu-id="74f11-103">Zonas de ubicación adicionales</span><span class="sxs-lookup"><span data-stu-id="74f11-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74f11-104">Tres nuevos campos de zona están disponibles en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="74f11-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="74f11-105">Los gerentes de almacén pueden usarlos para definir organizaciones o diseños de almacén adicionales.</span><span class="sxs-lookup"><span data-stu-id="74f11-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="74f11-106">Los nuevos campos de zona se pueden configurar manualmente o mediante el uso del asistente de **Configuración de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="74f11-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="74f11-107">Se pueden usar en cualquier consulta o filtrado que use la tabla Ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="74f11-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="74f11-108">No se requiere configuración adicional para usar los campos de zona.</span><span class="sxs-lookup"><span data-stu-id="74f11-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="74f11-109">Activar la característica de zona de ubicación adicional</span><span class="sxs-lookup"><span data-stu-id="74f11-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="74f11-110">Antes de poder usar la característica *Zona de ubicación adicional*, esta debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="74f11-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="74f11-111">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="74f11-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="74f11-112">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="74f11-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="74f11-113">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="74f11-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="74f11-114">**Nombre de la característica:** *Zona de ubicación adicional*</span><span class="sxs-lookup"><span data-stu-id="74f11-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="74f11-115">Usar zonas de ubicación</span><span class="sxs-lookup"><span data-stu-id="74f11-115">Use location zones</span></span>

1. <span data-ttu-id="74f11-116">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Asistente de configuración de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="74f11-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="74f11-117">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="74f11-117">Set the following values:</span></span>

    - <span data-ttu-id="74f11-118">En el campo **Almacén**, seleccione _62_.</span><span class="sxs-lookup"><span data-stu-id="74f11-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="74f11-119">En el campo **Id. de zona**, escriba _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="74f11-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="74f11-120">En el campo **Zona adicional 1**, escriba _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="74f11-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="74f11-121">En el campo **Zona adicional 2**, escriba _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="74f11-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="74f11-122">En el campo **Id. de perfil de ubicación**, seleccione _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="74f11-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="74f11-123">Seleccione la línea **Floor**.</span><span class="sxs-lookup"><span data-stu-id="74f11-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="74f11-124">En el campo **Desde número**, escriba _1_.</span><span class="sxs-lookup"><span data-stu-id="74f11-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="74f11-125">En el campo **Hasta número**, escriba _3_.</span><span class="sxs-lookup"><span data-stu-id="74f11-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="74f11-126">Seleccione la línea **Aisle**.</span><span class="sxs-lookup"><span data-stu-id="74f11-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="74f11-127">En el campo **Desde número**, escriba _1_.</span><span class="sxs-lookup"><span data-stu-id="74f11-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="74f11-128">En el campo **Hasta número**, escriba _5_.</span><span class="sxs-lookup"><span data-stu-id="74f11-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="74f11-129">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="74f11-129">Select **Create**.</span></span>
8. <span data-ttu-id="74f11-130">Recibe mensajes que indican que se han agregado nuevas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="74f11-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="74f11-131">Seleccione el botón **Mostrar mensajes** para ver los mensajes.</span><span class="sxs-lookup"><span data-stu-id="74f11-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="74f11-132">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="74f11-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="74f11-133">Las nuevas ubicaciones aparecen en la lista y todos los campos de zona están disponibles (es decir, el campo de zona existente y los nuevos campos de zona adicionales).</span><span class="sxs-lookup"><span data-stu-id="74f11-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
