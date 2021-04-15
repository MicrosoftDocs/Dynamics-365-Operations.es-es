---
title: Crear un perfil de funcionalidad comercial
description: Este tema describe cómo crear un perfil de funcionalidad en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: b8d481597485775796290f61de19ef7682cb9f43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792007"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="d0b1a-103">Crear un perfil de funcionalidad comercial</span><span class="sxs-lookup"><span data-stu-id="d0b1a-103">Create a retail functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d0b1a-104">Este tema describe cómo crear un perfil de funcionalidad en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d0b1a-105">El perfil de funcionalidad comercial proporciona varias configuraciones utilizadas para los canales en línea.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-105">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="d0b1a-106">Cada canal debe especificar un perfil de funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-106">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="d0b1a-107">Crear un perfil de funcionalidad</span><span class="sxs-lookup"><span data-stu-id="d0b1a-107">Create a functionality profile</span></span>

<span data-ttu-id="d0b1a-108">Para crear un perfil de funcionalidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-108">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="d0b1a-109">En el panel de navegación, vaya a **Módulos \> Configuración de canal \> Perfiles de PDV \> Perfiles de funcionalidad**.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-109">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="d0b1a-110">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d0b1a-111">En el campo **Perfil**, introduzca un id. para el perfil ("FN006" en la imagen de ejemplo que se muestra a continuación).</span><span class="sxs-lookup"><span data-stu-id="d0b1a-111">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="d0b1a-112">En el campo **Descripción**, introduzca un valor ("Perfil de Adventure Works" en la imagen de ejemplo que se muestra a continuación).</span><span class="sxs-lookup"><span data-stu-id="d0b1a-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="d0b1a-113">En la sección **General**, seleccione un país para la configuración regional **ISO**.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-113">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="d0b1a-114">En la sección **General**, modifique otros ajustes, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-114">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="d0b1a-115">En la sección **General**, seleccione un **Id. de perfil de recibo** para recibos por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-115">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="d0b1a-116">En la sección **Funciones**, modifique la configuración, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-116">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="d0b1a-117">En la sección **Importe**, modifique la configuración según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-117">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="d0b1a-118">En la sección **Códigos de información**, modifique la configuración, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-118">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="d0b1a-119">En la sección **Numeración del recibo**, modifique la configuración, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-119">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="d0b1a-120">La siguiente imagen muestra un perfil de funcionalidad de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d0b1a-120">The following image shows an example functionality profile.</span></span>
  
![Ejemplo de perfil de funcionalidad](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="d0b1a-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d0b1a-122">Additional resources</span></span>

[<span data-ttu-id="d0b1a-123">Códigos de información y grupos de códigos de información</span><span class="sxs-lookup"><span data-stu-id="d0b1a-123">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="d0b1a-124">Crear nueva libreta de direcciones</span><span class="sxs-lookup"><span data-stu-id="d0b1a-124">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="d0b1a-125">Visión general del diseño de pantalla</span><span class="sxs-lookup"><span data-stu-id="d0b1a-125">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="d0b1a-126">Instalar y configurar Retail Hardware Station</span><span class="sxs-lookup"><span data-stu-id="d0b1a-126">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
