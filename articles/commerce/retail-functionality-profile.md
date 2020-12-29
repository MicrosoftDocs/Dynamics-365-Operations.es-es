---
title: Crear un perfil de funcionalidad comercial
description: Este tema describe cómo crear un perfil de funcionalidad en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6bee51eb25b04eb65e588dd4cf54a0cef587aa15
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415405"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="a32d9-103">Crear un perfil de funcionalidad comercial</span><span class="sxs-lookup"><span data-stu-id="a32d9-103">Create a retail functionality profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a32d9-104">Este tema describe cómo crear un perfil de funcionalidad en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a32d9-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a32d9-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="a32d9-105">Overview</span></span>

<span data-ttu-id="a32d9-106">El perfil de funcionalidad comercial proporciona varias configuraciones utilizadas para los canales en línea.</span><span class="sxs-lookup"><span data-stu-id="a32d9-106">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="a32d9-107">Cada canal debe especificar un perfil de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="a32d9-107">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="a32d9-108">Crear un perfil de funcionalidad</span><span class="sxs-lookup"><span data-stu-id="a32d9-108">Create a functionality profile</span></span>

<span data-ttu-id="a32d9-109">Para crear un perfil de funcionalidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a32d9-109">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="a32d9-110">En el panel de navegación, vaya a **Módulos \> Configuración de canal \> Perfiles de PDV \> Perfiles de funcionalidad**.</span><span class="sxs-lookup"><span data-stu-id="a32d9-110">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="a32d9-111">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a32d9-111">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a32d9-112">En el campo **Perfil**, introduzca un id. para el perfil ("FN006" en la imagen de ejemplo que se muestra a continuación).</span><span class="sxs-lookup"><span data-stu-id="a32d9-112">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="a32d9-113">En el campo **Descripción**, introduzca un valor ("Perfil de Adventure Works" en la imagen de ejemplo que se muestra a continuación).</span><span class="sxs-lookup"><span data-stu-id="a32d9-113">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="a32d9-114">En la sección **General**, seleccione un país para la configuración regional **ISO**.</span><span class="sxs-lookup"><span data-stu-id="a32d9-114">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="a32d9-115">En la sección **General**, modifique otros ajustes, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a32d9-115">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="a32d9-116">En la sección **General**, seleccione un **Id. de perfil de recibo** para recibos por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="a32d9-116">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="a32d9-117">En la sección **Funciones**, modifique la configuración, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a32d9-117">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="a32d9-118">En la sección **Importe**, modifique la configuración según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a32d9-118">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="a32d9-119">En la sección **Códigos de información**, modifique la configuración, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a32d9-119">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="a32d9-120">En la sección **Numeración del recibo**, modifique la configuración, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a32d9-120">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="a32d9-121">La siguiente imagen muestra un perfil de funcionalidad de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a32d9-121">The following image shows an example functionality profile.</span></span>
  
![Ejemplo de perfil de funcionalidad](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="a32d9-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a32d9-123">Additional resources</span></span>

[<span data-ttu-id="a32d9-124">Códigos de información y grupos de códigos de información</span><span class="sxs-lookup"><span data-stu-id="a32d9-124">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="a32d9-125">Crear nueva libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="a32d9-125">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="a32d9-126">Visión general del diseño de pantalla</span><span class="sxs-lookup"><span data-stu-id="a32d9-126">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="a32d9-127">Instalar y configurar Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="a32d9-127">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 
