---
title: Crear un perfil de funcionalidad en línea
description: Este tema describe cómo crear un perfil de funcionalidad en línea en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: be78b92858979b8bb009a4699eff96379ef7cef3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791111"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="03f36-103">Crear un perfil de funcionalidad en línea</span><span class="sxs-lookup"><span data-stu-id="03f36-103">Create an online functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="03f36-104">Este tema presenta una visión general de la configuración de un perfil de funcionalidad en línea para Microsoft Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="03f36-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="03f36-105">El perfil de funcionalidad en línea proporciona varias configuraciones utilizadas para los canales en línea.</span><span class="sxs-lookup"><span data-stu-id="03f36-105">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="03f36-106">Cada canal en línea debe especificar un perfil de funcionalidad en línea.</span><span class="sxs-lookup"><span data-stu-id="03f36-106">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="03f36-107">Crear un perfil de funcionalidad en línea</span><span class="sxs-lookup"><span data-stu-id="03f36-107">Create an online functionality profile</span></span>

<span data-ttu-id="03f36-108">El siguiente procedimiento explica cómo crear un perfil de funcionalidad en línea desde la aplicación Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="03f36-108">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="03f36-109">En el panel de navegación, vaya a **Módulos \> Configuración de canal \> Configuración de la tienda en línea \> Perfiles de funcionalidad**.</span><span class="sxs-lookup"><span data-stu-id="03f36-109">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="03f36-110">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="03f36-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="03f36-111">En el campo **Perfil**, introduzca un id. para el perfil.</span><span class="sxs-lookup"><span data-stu-id="03f36-111">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="03f36-112">En el campo **Descripción**, introduzca un valor ("Perfil de Adventure Works" en la imagen de ejemplo que se muestra a continuación).</span><span class="sxs-lookup"><span data-stu-id="03f36-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="03f36-113">En la sección **Funciones**, modifique la configuración de **CARRO**, **CLIENTES COMERCIALES** o **FINALIZAR COMPRA**, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="03f36-113">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="03f36-114">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="03f36-114">On the action pane, select **Save**.</span></span>

<span data-ttu-id="03f36-115">La siguiente imagen muestra un perfil de funcionalidad en línea de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="03f36-115">The following image shows an example online functionality profile.</span></span>
  
![Ejemplo de perfil de funcionalidad en línea](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="03f36-117">Funciones</span><span class="sxs-lookup"><span data-stu-id="03f36-117">Functions</span></span>

- <span data-ttu-id="03f36-118">**Productos agregados**: cuando está habilitada, esta función permite que el carro actualice la cantidad cuando se agrega el mismo artículo varias veces.</span><span class="sxs-lookup"><span data-stu-id="03f36-118">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="03f36-119">**Permitir finalizar compra sin pagos**: cuando está habilitada, esta función maneja el escenario cuando los artículos agregados al carro tienen un precio 0,00 $.</span><span class="sxs-lookup"><span data-stu-id="03f36-119">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="03f36-120">**Crear cliente en modo asincrónico**: esta es una configuración heredada aplicable a canales de comercio electrónico de terceros y no es aplicable al sitio de comercio electrónico de Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="03f36-120">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="03f36-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="03f36-121">Additional resources</span></span>

[<span data-ttu-id="03f36-122">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="03f36-122">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="03f36-123">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="03f36-123">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="03f36-124">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="03f36-124">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="03f36-125">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="03f36-125">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="03f36-126">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="03f36-126">Set up a call center channel</span></span>](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
