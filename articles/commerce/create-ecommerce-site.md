---
title: Crear un sitio de comercio electrónico
description: Este tema describe las tareas asociadas a la creación de un sitio nuevo de comercio electrónico en Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 10/31/2019
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
ms.openlocfilehash: 54259d3f5dfd8c8e1ff2caaadfac497cc0e133e0
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945844"
---
# <a name="create-an-e-commerce-site"></a><span data-ttu-id="d7ad0-103">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="d7ad0-103">Create an e-Commerce site</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="d7ad0-104">Este tema describe las tareas asociadas a la creación de un sitio nuevo de comercio electrónico en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-104">This topic describes the tasks that are associated with the creation of a new e-Commerce site in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d7ad0-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="d7ad0-105">Overview</span></span>

<span data-ttu-id="d7ad0-106">Para empezar a desarrollar su sitio de comercio electrónico, primero debe establecer un nuevo sitio en el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-106">To start to develop your e-Commerce site, you must first establish a new site in the site authoring environment.</span></span> <span data-ttu-id="d7ad0-107">Para poder crear un sitio nuevo, se debe crear al menos una tienda en línea en Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-107">Before you can create a new site, at least one online store must be created in Dynamics 365 Retail.</span></span> 

## <a name="set-up-your-site"></a><span data-ttu-id="d7ad0-108">Configurar su sitio</span><span class="sxs-lookup"><span data-stu-id="d7ad0-108">Set up your site</span></span>

<span data-ttu-id="d7ad0-109">Para configurar el sitio, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-109">To set up your site, do the following.</span></span>

1. <span data-ttu-id="d7ad0-110">En el Microsoft Lifecycle Services (LCS), seleccione el vínculo para el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-110">In Microsoft Lifecycle Services (LCS), select the link for the site authoring environment.</span></span> 
1. <span data-ttu-id="d7ad0-111">En la página principal para el entorno de creación del sitio, seleccione **Nuevo sitio**.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-111">On the home page for the site authoring environment, select **New site**.</span></span>
1. <span data-ttu-id="d7ad0-112">En el cuadro de diálogo **Nuevo sitio**, proporcione la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-112">In the **New site** dialog box, provide the following information.</span></span>

| <span data-ttu-id="d7ad0-113">Campo</span><span class="sxs-lookup"><span data-stu-id="d7ad0-113">Field</span></span>                               | <span data-ttu-id="d7ad0-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="d7ad0-114">Description</span></span> |
|-------------------------------------|-------------|
| <span data-ttu-id="d7ad0-115">Nombre del sitio</span><span class="sxs-lookup"><span data-stu-id="d7ad0-115">Site name</span></span>                           | <span data-ttu-id="d7ad0-116">Especifique el nombre para mostrar que se debe usar para el sitio en el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-116">Enter the display name that should be used for your site in the site authoring environment.</span></span> <span data-ttu-id="d7ad0-117">Este nombre solo es visible en el entorno de creación y no se mostrará a los clientes.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-117">This name is visible only in the authoring environment and will not be shown to customers.</span></span> |
| <span data-ttu-id="d7ad0-118">Grupo de seguridad del administrador del sitio</span><span class="sxs-lookup"><span data-stu-id="d7ad0-118">Site administrator's security group</span></span> | <span data-ttu-id="d7ad0-119">Especifique el grupo de seguridad de Microsoft Azure Active Directory (Azure AD) que administra a los usuarios con el rol de administrador de este sitio.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-119">Specify the Microsoft Azure Active Directory (Azure AD) security group that manages users who have the site administrator role in this site.</span></span> |
| <span data-ttu-id="d7ad0-120">Canal predeterminado (número de unidad operativa)</span><span class="sxs-lookup"><span data-stu-id="d7ad0-120">Default channel (operating unit number)</span></span> | <span data-ttu-id="d7ad0-121">Seleccione la tienda en línea para la que este sitio servirá como el escaparate web.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-121">Select the online store that this site will serve as the web storefront for.</span></span> <span data-ttu-id="d7ad0-122">Si desea que su sitio de comercio electrónico admita varias tiendas en línea, debe asociar las tiendas con su sitio en **Valores de configuración de sitio** después de configurar el sitio.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-122">If you want your e-Commerce site to support multiple online stores, you must associate the stores with your site in **Site settings** after the site is set up.</span></span> |
| <span data-ttu-id="d7ad0-123">Idioma predeterminado</span><span class="sxs-lookup"><span data-stu-id="d7ad0-123">Default language</span></span>                            | <span data-ttu-id="d7ad0-124">Especifique el idioma predeterminado para esta tienda en línea y mercado.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-124">Specify the default language for this online store and market.</span></span> <span data-ttu-id="d7ad0-125">Una tienda en línea puede admitir varios idiomas.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-125">An online store can support multiple languages.</span></span> <span data-ttu-id="d7ad0-126">Si desea admitir varios idiomas para esta tienda en línea u otra tienda en línea, puede configurar dicha compatibilidad en **Valores de configuración de sitio** después de que se configure el sitio.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-126">If you want to support multiple languages for this online store or another online store, you can configure that support in **Site settings** after the site is set up.</span></span>  |
| <span data-ttu-id="d7ad0-127">Dominio</span><span class="sxs-lookup"><span data-stu-id="d7ad0-127">Domain</span></span>                              | <span data-ttu-id="d7ad0-128">Seleccione un nombre de dominio que servirá como el dominio para esta tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-128">Select a domain name that will serve as the domain for this online store.</span></span> <span data-ttu-id="d7ad0-129">Si no ha configurado dominios en LCS, puede dejar este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-129">If you haven't configured any domains in LCS, you can leave this field blank.</span></span> <span data-ttu-id="d7ad0-130">Cuando su dominio se haya configurado en LCS, debe agregarlo a la tienda en línea en **Valores de configuración de sitio**.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-130">After your domain is configured in LCS, you must add it to your online store in **Site settings**.</span></span>  |
| <span data-ttu-id="d7ad0-131">Ruta</span><span class="sxs-lookup"><span data-stu-id="d7ad0-131">Path</span></span>                              | <span data-ttu-id="d7ad0-132">Cuando el sitio admite más de un idioma para un nombre de dominio determinado, use el campo de ruta para crear una dirección URL de sitio única para dicha combinación de dominio e idioma.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-132">When your site supports more than one language for a given domain name, use the path field to create a unique site URL for that domain and language combination.</span></span> <span data-ttu-id="d7ad0-133">Si el idioma que ha especificado en el campo **Idioma predeterminado** es el único idioma que admitirá para este dominio, o seguirá siendo el idioma predeterminado después de que haya localizado su sitio en otros idiomas, se recomienda dejar este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-133">If the language you specified in the **Default language** field is the only language you will support for this domain, or will continue to be the default language after you have localized your site into additional languages, we recommend that you leave this field empty.</span></span> |


<span data-ttu-id="d7ad0-134">Una vez creado el sitio, puede comprobar que esté asociado a la tienda en línea seleccionando la pestaña **Productos**. Solo debería ver la selección de productos que se ha asignado a la tienda en línea.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-134">After your site is created, you can verify that it is associated with your online store by selecting the **Products** tab. You should see the assortment of products that has been allocated to the online store.</span></span> <span data-ttu-id="d7ad0-135">Puede usar el menú desplegable en la parte superior izquierda de la página para obtener acceso a los productos asignados por categoría.</span><span class="sxs-lookup"><span data-stu-id="d7ad0-135">You can also use the drop-down menu in the upper left of the page to access the allocated products by category.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d7ad0-136">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d7ad0-136">Additional resources</span></span>

[<span data-ttu-id="d7ad0-137">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="d7ad0-137">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="d7ad0-138">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="d7ad0-138">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="d7ad0-139">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="d7ad0-139">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="d7ad0-140">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="d7ad0-140">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="d7ad0-141">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="d7ad0-141">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="d7ad0-142">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="d7ad0-142">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="d7ad0-143">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="d7ad0-143">Enable location-based store detection</span></span>](enable-store-detection.md)