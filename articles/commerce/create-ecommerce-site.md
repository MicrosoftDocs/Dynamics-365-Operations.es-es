---
title: Crear un sitio de comercio electrónico
description: En este tema se describen los pasos y la información necesarios para crear un nuevo sitio de comercio electrónico con el configurador de sitios de Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3d3d8a290f06d9734be21f2d59152acac6857506
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002022"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="42ff5-103">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="42ff5-103">Create an e-Commerce site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="42ff5-104">En este tema se describen los pasos y la información necesarios para crear un nuevo sitio de comercio electrónico con el configurador de sitios de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="42ff5-104">This topic describes the steps and information required to create a new e-Commerce site in Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="42ff5-105">Antes de empezar a desarrollar su sitio de comercio electrónico debe establecer un nuevo sitio en el configurador de sitios.</span><span class="sxs-lookup"><span data-stu-id="42ff5-105">Before you can start developing your e-Commerce site, you must first establish a new site in site builder.</span></span> 


<span data-ttu-id="42ff5-106">Para empezar a desarrollar su sitio de comercio electrónico, primero debe establecer un nuevo sitio en el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="42ff5-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="42ff5-107">Para poder crear un sitio nuevo, se debe crear al menos una tienda en línea en Commerce.</span><span class="sxs-lookup"><span data-stu-id="42ff5-107">Before you can create a new site, at least one online store must be created in Commerce.</span></span> 


## <a name="set-up-your-site"></a><span data-ttu-id="42ff5-108">Configurar su sitio</span><span class="sxs-lookup"><span data-stu-id="42ff5-108">Set up your site</span></span>

<span data-ttu-id="42ff5-109">Para configurar el sitio, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="42ff5-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="42ff5-110">Abra el entorno del configurador de sitios.</span><span class="sxs-lookup"><span data-stu-id="42ff5-110">Open the site builder environment.</span></span> <span data-ttu-id="42ff5-111">Encontrará un vínculo al configurador de sitios en Microsoft Lifecycle Services (LCS), en la página de características del entorno para Commerce.</span><span class="sxs-lookup"><span data-stu-id="42ff5-111">You can find a link to site builder in Microsoft Lifecycle Services (LCS) in the environment features page for Commerce.</span></span>
1. <span data-ttu-id="42ff5-112">En la página principal para el entorno de creación del sitio, seleccione **Nuevo sitio**.</span><span class="sxs-lookup"><span data-stu-id="42ff5-112">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="42ff5-113">En el cuadro de diálogo **Nuevo sitio**, proporcione la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="42ff5-113">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="42ff5-114">Campo</span><span class="sxs-lookup"><span data-stu-id="42ff5-114">Field</span></span>                               | <span data-ttu-id="42ff5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="42ff5-115">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="42ff5-116">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="42ff5-116">Site name</span></span>                           | <span data-ttu-id="42ff5-117">Especifique el nombre para mostrar que se debe usar para el sitio en el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="42ff5-117">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="42ff5-118">Este nombre solo es visible en el entorno de creación y no se mostrará a los clientes.</span><span class="sxs-lookup"><span data-stu-id="42ff5-118">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="42ff5-119">Grupo de seguridad del administrador del sitio</span><span class="sxs-lookup"><span data-stu-id="42ff5-119">Site administrator's security group</span></span> | <span data-ttu-id="42ff5-120">Especifique el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que administra a los usuarios con el rol de administrador de este sitio.</span><span class="sxs-lookup"><span data-stu-id="42ff5-120">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="42ff5-121">Canal predeterminado (número de unidad operativa)</span><span class="sxs-lookup"><span data-stu-id="42ff5-121">Default channel (operating unit number)</span></span> | <span data-ttu-id="42ff5-122">Seleccione la tienda en línea para la que este sitio servirá como el escaparate web.</span><span class="sxs-lookup"><span data-stu-id="42ff5-122">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="42ff5-123">Si desea que su sitio de comercio electrónico admita varias tiendas en línea, debe asociar las tiendas con su sitio en **Valores de configuración de sitio** después de configurar el sitio.</span><span class="sxs-lookup"><span data-stu-id="42ff5-123">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="42ff5-124">Idioma predeterminado</span><span class="sxs-lookup"><span data-stu-id="42ff5-124">Default language</span></span>                            | <span data-ttu-id="42ff5-125">Especifique el idioma predeterminado para esta tienda en línea y mercado.</span><span class="sxs-lookup"><span data-stu-id="42ff5-125">Specify the default language for this online store and market.</span></span> <span data-ttu-id="42ff5-126">Una tienda en línea puede admitir varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="42ff5-126">An online store can support multiple languages.</span></span> <span data-ttu-id="42ff5-127">Si desea admitir varios idiomas para esta tienda en línea u otra tienda en línea, puede configurar dicha compatibilidad en **Valores de configuración de sitio** después de que se configure el sitio.</span><span class="sxs-lookup"><span data-stu-id="42ff5-127">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="42ff5-128">Dominio</span><span class="sxs-lookup"><span data-stu-id="42ff5-128">Domain</span></span>                              | <span data-ttu-id="42ff5-129">Seleccione un nombre de dominio que servirá como el dominio para esta tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="42ff5-129">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="42ff5-130">Si no ha configurado dominios en LCS, puede dejar este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="42ff5-130">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="42ff5-131">Cuando su dominio se haya configurado en LCS, debe agregarlo a la tienda en línea en **Valores de configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="42ff5-131">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="42ff5-132">Ruta</span><span class="sxs-lookup"><span data-stu-id="42ff5-132">Path</span></span>                              | <span data-ttu-id="42ff5-133">Cuando el sitio admite más de un idioma para un nombre de dominio determinado, use el campo de ruta para crear una dirección URL de sitio única para dicha combinación de dominio e idioma.</span><span class="sxs-lookup"><span data-stu-id="42ff5-133">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="42ff5-134">Si el idioma que ha especificado en el campo **Idioma predeterminado** es el único idioma que admitirá para este dominio, o seguirá siendo el idioma predeterminado después de que haya localizado su sitio en otros idiomas, se recomienda dejar este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="42ff5-134">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="42ff5-135">Una vez creado el sitio, puede comprobar que esté asociado a la tienda en línea seleccionando la pestaña **Productos**. Solo debería ver la selección de productos que se ha asignado a la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="42ff5-135">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="42ff5-136">Puede usar el menú desplegable en la parte superior izquierda de la página para obtener acceso a los productos asignados por categoría.</span><span class="sxs-lookup"><span data-stu-id="42ff5-136">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42ff5-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="42ff5-137">Additional resources</span></span>

[<span data-ttu-id="42ff5-138">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="42ff5-138">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="42ff5-139">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="42ff5-139">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="42ff5-140">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="42ff5-140">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="42ff5-141">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="42ff5-141">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="42ff5-142">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="42ff5-142">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="42ff5-143">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="42ff5-143">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="42ff5-144">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="42ff5-144">Enable location-based store detection</span></span>](enable-store-detection.md)
